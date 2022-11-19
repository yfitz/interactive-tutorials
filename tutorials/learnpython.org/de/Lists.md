Tutorial
--------

Listen sind ähnlich wie Arrays. Sie können verschiedene Typen von Variablen und soviele wie man will enthalten. Über Listen kann ganz einfach iteriert werden. Hier ein Beispiel:

    mylist = []
    mylist.append(1)
    mylist.append(2)
    mylist.append(3)
    print(mylist[0]) # Ausgabe 1
    print(mylist[1]) # Ausgabe 2
    print(mylist[2]) # Ausgabe 3

    # Ausgabe 1,2,3
    for x in mylist:
        print(x)

Zugriff auf einen nicht existierenden Index erzeugt eine Exception (ein Fehler).

    mylist = [1,2,3]
    print(mylist[10])

Exercise
--------

In dieser Übung werden Zahlen und Zeichenketten an eine Liste gehängt unter Verwendung der "append" Methode. Es sollen die Zahlen 1,2, und 3 an die Liste "numbers" angehängt werden, und die Wörter 'hello' und 'world' an die strings Variable.

Ausserdem soll die Variable second_name mit dem zweiten Namen aus der "names" Liste gesetzt, unter Verwendung der  `[]` Syntax. Beachte das der Index bei 0 beginnt, so dass das zweite Element den Index 1 hat.

Tutorial Code
-------------
numbers = []
strings = []
names = ["John", "Eric", "Jessica"]

# Schreibe deinen Code hier 
second_name = None


# dieser Code gibt die erzeugten Arrays und den zweiten Namen der "names" Liste (Eric) aus. 
print(numbers)
print(strings)
print("The second name on the names list is %s" % second_name)

Expected Output
---------------

test_output_contains("[1,2,3]", no_output_msg= "Make sure that you have printed the `numbers` list.")
test_output_contains("['hello', 'world']", no_output_msg= "Make sure that you have printed the `strings` list.")
test_output_contains("The second name on the names list is Eric", no_output_msg= "Did you fill in the variable `second_name` with the second name in the names list?")
success_msg("Great Job!")

Solution
--------

numbers = []
strings = []
names = ["John", "Eric", "Jessica"]

# Schreibe deinen Code hier 
numbers.append(1)
numbers.append(2)
numbers.append(3)

strings.append("hello")
strings.append("world")

second_name = names[1]

# dieser Code gibt die erzeugten Arrays und den zweiten Namen der "names" Liste (Eric) aus. 
print(numbers)
print(strings)
print("The second name on the names list is %s" % second_name)
