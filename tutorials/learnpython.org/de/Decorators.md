Tutorial
--------

Decorators erlauben es einfach Veränderungen an aufrufbaren Objekten wie  [functions](http://www.learnpython.org/en/Functions ""), [methods, or classes](http://www.learnpython.org/en/Classes%20and%20Objects "") durch zuführen. 
Wir sollten mit Funktionen hier anfangen. Die Syntax

    @decorator
    def functions(arg):
        return "value"

Ist equivalent zu:

    def function(arg):
        return "value"
    function = decorator(function) # dies übergibt die Funktion dem decorator, und weist es wieder der Funktion zu

Wie bereits gesehen, ist ein decorator nur eine weitere Funktion welche eine Funktion bekommt und eine liefert. 
Zum Beispiel könnte man folgendes machen: 

    def repeater(old_function):
        def new_function(*args, **kwds): # See learnpython.org/en/Multiple%20Function%20Arguments for how *args and **kwds works
            old_function(*args, **kwds) # we run the old function
            old_function(*args, **kwds) # we do it twice
        return new_function # we have to return the new_function, or it wouldn't reassign it to the value

Folgendes würde eine Funktion zweimal ausführen.

    >>> @repeater
    def multiply(num1, num2):
        print(num1 * num2)

    >>> multiply(2, 3)
    6
    6

Man könnte die Ausgabe verändern

    def double_out(old_function):
        def new_function(*args, **kwds):
            return 2 * old_function(*args, **kwds) # modify the return value
        return new_function

oder die Eingabe

    def double_Ii(old_function):
        def new_function(arg): # only works if the old function has one argument
            return old_function(arg * 2) # modify the argument passed
        return new_function

und do checking.

    def check(old_function):
        def new_function(arg):
            if arg < 0: raise (ValueError, "Negative Argument") # This causes an error, which is better than it doing the wrong thing
            old_function(arg)
        return new_function

Wollen wir die Ausgabe mulpilizieren mit einer Variable. Dazu kann der decorator definiert werden und wie folgt verwendet: 

    def multiply(multiplier):
        def multiply_generator(old_function):
            def new_function(*args, **kwds):
                return multiplier * old_function(*args, **kwds)
            return new_function
        return multiply_generator # it returns the new generator
    
    # Usage
    @multiply(3) # multiply is not a generator, but multiply(3) is
    def return_num(num):
        return num
        
    # Nun return_num wird decorated und zurück zugewiesen zu sich selbst
    return_num(5) # sollte 15 liefern

Du kannst mit der alten Funktion alles machen was du willst, sogar es komplett ignorieren. Andere decorators können auch den doc string manipulieren und die Argumenten Anzahl.
Coole decorators unter: <http://wiki.python.org/moin/PythonDecoratorLibrary>.

Exercise
--------
Erzeuge einen decorator factory welches einen decorator liefert, der eine Funktion mit einem Argument ausstattet. Die factory sollte ein Argument bekommen, ein Typ und
liefert einen decorator der ein Funktion erzeugt, wenn der Typ korrekt ist. Wenn diese aber falsch ist, wird ("Bad Type") ausgegeben. (In Wirklichkeit, sollte ein Fehler erscheinen - nicht Thema im Moment). 
Schaue auf den Tutorial Code und die erwartete Ausgabe um zu sehen was es macht. Die Verwendung von isinstance(object, type_of_object) oder type(object) kann helfen.

Tutorial Code
-------------
def type_check(correct_type):
    #put code here

@type_check(int)
def times2(num):
    return num*2

print(times2(2))
times2('Not A Number')

@type_check(str)
def first_letter(word):
    return word[0]

print(first_letter('Hello World'))
first_letter(['Not', 'A', 'String'])


Expected Output
---------------

test_output_contains("4")
test_output_contains("Bad Type")
test_output_contains("H")
test_output_contains("Bad Type")
success_msg("Good job!")

Solution
--------

def type_check(correct_type):
    def check(old_function):
        def new_function(arg):
            if (isinstance(arg, correct_type)):
                return old_function(arg)
            else:
                print("Bad Type")
        return new_function
    return check

@type_check(int)
def times2(num):
    return num*2

print(times2(2))
times2('Not A Number')

@type_check(str)
def first_letter(word):
    return word[0]

print(first_letter('Hello World'))
first_letter(['Not', 'A', 'String'])
