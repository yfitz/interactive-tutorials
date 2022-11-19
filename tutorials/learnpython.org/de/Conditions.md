Tutorial
--------

Python verwendet Boolesche Werte in Bedingungen. Die Booleschen Werte True und False werden zurückgegeben wenn ein Ausdruck verglichen oder ausgewertet wird. 
Zum Beispiel:

    x = 2
    print(x == 2) # prints out True
    print(x == 3) # prints out False
    print(x < 3) # prints out True

Beachte Variable Zuweisung unter Verwendung des Operators "=", hingegen werden Vergleiche zweier Variablen unter Verwendung des Operators "==". Der "not equals" Operator 
wird durch folgenden Operator "!=" dargestellt.

### Boolesche Operatoren

Die "and" und "or" Operatoren erlaben es komplexe Ausdrücke zu erzeugen, zum Beispiel:

    name = "John"
    age = 23
    if name == "John" and age == 23:
        print("Your name is John, and you are also 23 years old.")

    if name == "John" or name == "Rick":
        print("Your name is either John or Rick.")

### Der "in" Operator

Der "in" Operator kann verwendet werden um zu prüfen ob das angegebene Objekt in dem iterierbaren Objekt, wie zum Beispiel einer Liste enthalten ist:

    name = "John"
    if name in ["John", "Rick"]:
        print("Your name is either John or Rick.")

Python verwendet Einrücken um Blöcke zu definieren, statt Klammern. Standardmäßig wird 4 Leerzeichen eingerückt (obwohl Tab und andere Anzahl von Leerzeichen auch funktionieren, wenn konsistent).  
Beachte keine speziellen Zeichen am Ende des Blockes notwendig.

Hier ein Beispiel in Python mit "if" Anweisung und dessen Code Block:

    statement = False
    another_statement = True
    if statement is True:
        # do something
        pass
    elif another_statement is True: # else if
        # do something else
        pass
    else:
        # do another thing
        pass

Beispiel:
    x = 2
    if x == 2:
        print("x equals two!")
    else:
        print("x does not equal to two.")

Eine Anweisung wird zu true ausgewertet wenn eins folgender Kriterien korrekt sind:
1. Die Variable The "True" ist gegeben, oder ist Ergebnis der Auswertung der Anweisung
2. Ein Objekt welches nicht 'empty' ist wird ausgewertet

Hier Beispiele für Objekte die als 'empty' angesehen werden:
1. Eine leere Zeichenkette: ""
2. Eine leere Liste: []
3. Die Zahl 0: 0
4. Der false Boolesche Wert: False

### Der 'is' Operator

Ungleich dem doppelten gleich Operator "==", der "is" Operator vergleicht nicht die Werte der Variablen, sondern der Instanz selber. Zum Beispiel:

    x = [1,2,3]
    y = [1,2,3]
    print(x == y) # Ausgabe True
    print(x is y) # Ausgabe False

### Der "not" Operator

Verwendung des "not" Opertors vor einem Ausdruck invertiert das Ergebnis:

    print(not False) # Ausgabe True
    print((not False) == (False)) # Ausgabe False

Exercise
--------

Verändere die Variablen im ersten Teil, sodass jede Auswertung der Ausdrücke m zweiten Teil True liefert. 

Tutorial Code
-------------

# Verändere diesen Code
number = 10
second_number = 10
first_array = []
second_array = [1,2,3]

if number > 15:
    print("1")

if first_array:
    print("2")

if len(second_array) == 2:
    print("3")

if len(first_array) + len(second_array) == 5:
    print("4")

if first_array and first_array[0] == 1:
    print("5")

if not second_number:
    print("6")

Expected Output
---------------

test_output_contains("1", no_output_msg= "Did you print out 1 if `number` is greater than 15?")
test_output_contains("2", no_output_msg= "Did you print out 2 if there exists a list `first_array`?")
test_output_contains("3", no_output_msg= "Did you print out 3 if the length of `second_array` is 2?")
test_output_contains("4", no_output_msg= "Did you print out 4 if len(first_array) + len(second_array) == 5?")
test_output_contains("5", no_output_msg= "Did you print out 5 if first_array and first_array[0] == 1?")
test_output_contains("6", no_output_msg= "Did you print out 6 if not second_number?")
success_msg("Great Work!")

Solution
--------

# Verändere diesen Code
number = 16
second_number = 0
first_array = [1,2,3]
second_array = [1,2]

if number > 15:
    print("1")

if first_array:
    print("2")

if len(second_array) == 2:
    print("3")

if len(first_array) + len(second_array) == 5:
    print("4")

if first_array and first_array[0] == 1:
    print("5")

if not second_number:
    print("6")
