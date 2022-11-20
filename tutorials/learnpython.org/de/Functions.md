Tutorial
--------

### Was sind Funktionen?
 
Der Einsatz von Funktionen ist eine konventielle Methode um Code in Blöcke zu unterteilen, welche das Programm strukturieren, die Lesbarkeit erhöhen, die Wiederverwendbarkeit ermöglichen und Zeit sparen. Ausserdem lassen sich Funktionen als Interfaces definieren um Code für andere Programmierer auszutauschen. 

### Wie erzeugt man Funktionen in Python?

Wie schon gesehen, verwendet Python Blocke.

Ein Block ist ein Bereich aus Code in folgendem Format: 

    block_head:
        1st block line
        2nd block line
        ...

In den einzelnen Zeilen im Block steht Python Code (auch weitere Blöcke) und der Blockkopf ist im folgendem Format:   
block_keyword block_name(argument1,argument2, ...)

Die bekannten Block keywords sind "if", "for", und "while".

Funktionen in Python werden definiert durch das Schlüsselwort "def", gefolgt vom Funktion Namen als Block Name.
Beispiel:
    def my_function():
        print("Hello From My Function!")


Funktionen können auch Argumente (Variaben die vom aufrufenden Code an die Funktion übergeben werden) enthalten.
Beispiel:

    def my_function_with_args(username, greeting):
        print("Hello, %s , From My Function!, I wish you %s"%(username, greeting))


Funktionen können auch Rückgabewert an den aufrufenden Code liefern, unter Verwendung des Schlüsselworts 'return' .
Beispiel:

    def sum_two_numbers(a, b):
        return a + b

### Wie wird die Funktion in Python aufgerufen?

Einfach durch Funktionsname gefolgt durch (), mit den Parametern in den Klammern.
Zum Beispiel, der Aufruf der oben angegebenen Funktion: 

    # Definition dreier Funktionen
    def my_function():
        print("Hello From My Function!")

    def my_function_with_args(username, greeting):
        print("Hello, %s, From My Function!, I wish you %s"%(username, greeting))

    def sum_two_numbers(a, b):
        return a + b

    # print(a simple greeting)
    my_function()

    # prints - "Hello, John Doe, From My Function!, I wish you a great year!"
    my_function_with_args("John Doe", "a great year!")

    # nach dieser Zeile wird x gleich 3 sein! 
    x = sum_two_numbers(1,2)  


Exercise
--------

In dieser Übung werden wir die existierenden Funktionen verwenden, und ausserdem noch unsere eigenen Funktionen definieren, um die volle Funktionalität zu erzeugen. 

1. Ergänze eine Funktion mit dem Namen `list_benefits()`, die folgende Liste von Zeichenketten liefert: "More organized code", "More readable code", "Easier code reuse", "Allowing programmers to share and connect code together"

2. Ergänze eine Funktion mit dem Namen `build_sentence(info)`, die als Argument eine Zeichenkette erhält und eine Zeichenkette als Satz der mit der angegebenen Zeichenkette beginnt oder endet " is a benefit of functions!"

3. Laufen lassen und testen!

Tutorial Code
-------------

# Modifiziere diese Funktion um die Liste der Zeichenketten zu liefern, wie oben definiert. 
def list_benefits():
    return []

# Modifiziere diese Funktion um das übergebene Wort vorne und hinten anzuhängen an folgenden Satz: " is a benefit of functions!"
def build_sentence(benefit):
    return ""

def name_the_benefits_of_functions():
    list_of_benefits = list_benefits()
    for benefit in list_of_benefits:
        print(build_sentence(benefit))

name_the_benefits_of_functions()


Expected Output
---------------

test_output_contains("More organized code is a benefit of functions!")
test_output_contains("More readable code is a benefit of functions!")
test_output_contains("Easier code reuse is a benefit of functions!")
test_output_contains("Allowing programmers to share and connect code together is a benefit of functions!")
success_msg("Nice work!")

Solution
--------

# Modifiziere diese Funktion um die Liste der Zeichenketten zu liefern, wie oben definiert. 
def list_benefits():
    return "More organized code", "More readable code", "Easier code reuse", "Allowing programmers to share and connect code together"

# Modifiziere diese Funktion um das übergebene Wort vorne und hinten anzuhängen an folgenden Satz: " is a benefit of functions!"
def build_sentence(benefit):
    return "%s is a benefit of functions!" % benefit


def name_the_benefits_of_functions():
    list_of_benefits = list_benefits()
    for benefit in list_of_benefits:
        print(build_sentence(benefit))

name_the_benefits_of_functions()
