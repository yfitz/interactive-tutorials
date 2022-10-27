Tutorial
--------

Dieser Abschnitt beschreibt wie die Basisoperatoren in Python verwendet werden.

### Arithmetic Operators       

Wie in jeder anderen Programmiersprache, gibt es Addition, Subtraktion, Multiplikation und Division von Zahlen. <br>

    number = 1 + 2 * 3 / 4.0
    print(number)

Versuche die Frage zu beantworten. Hält Python die Rangordnung der Operationen aus der Mathematik ein? 

Ein weiterer Operator ist Modulo (%), welches den ganzzahligen Rest aus der Division liefert: dividend % divisor = rest.

    remainder = 11 % 3
    print(rest)

Mit zwei * Symbolen wird potenziert.

    squared = 7 ** 2
    cubed = 2 ** 3
    print(squared)
    print(cubed)

### Verwendung von Operatoren mit Zeichenketten

Python unterstützt die Verknüpfung von Zeichenketten durch den Additions Operator:

    helloworld = "hello" + " " + "world"
    print(helloworld)

Python unterstützt auch die Multiplikation von Zeichenketten zur vielfachen Aneinanderreihung der gleichen Zeichenkette:

    lotsofhellos = "hello" * 10
    print(lotsofhellos)

### Verwendung von Operatoren mit Listen

Listen können auch mit dem Additions Operator verknüpft werden:

    even_numbers = [2,4,6,8]
    odd_numbers = [1,3,5,7]
    all_numbers = odd_numbers + even_numbers
    print(all_numbers)

Wie schon bei Zeichenketten, unterstützt Python auch die Erzeugung von neuen Listen durch vielfache Aneinanderreihung durch den Multiplikations Operator:

    print([1,2,3] * 3)

Übung
-----

Ziel der Übung ist es zwei Listen `x_list` und `y_list` zu erzeugen, 
die jeweils 10 Instanzen der Variablen `x` und `y` erhalten. 
Ausserdem soll eine Liste `big_list` erzeugt werden, die wiederum 10-mal 
die zuvor erzeugten Listen enthält.

Tutorial Code
-------------

x = object()
y = object()

# TODO: Passe diesen Code an
x_list = [x]
y_list = [y]
big_list = []

print("x_list contains %d objects" % len(x_list))
print("y_list contains %d objects" % len(y_list))
print("big_list contains %d objects" % len(big_list))

# testing code
if x_list.count(x) == 10 and y_list.count(y) == 10:
    print("Almost there...")
if big_list.count(x) == 10 and big_list.count(y) == 10:
    print("Great!")

Expected Output
---------------

Ex().check_object('x_list').has_equal_value(expr_code = 'len(x_list)')
Ex().check_object('y_list').has_equal_value(expr_code = 'len(y_list)')
Ex().check_object('big_list').has_equal_value(expr_code = 'len(big_list)')
success_msg('Good work!')

Solution
--------

x = object()
y = object()

# TODO: Passe diesen Code an
x_list = [x] * 10
y_list = [y] * 10
big_list = x_list + y_list

print("x_list contains %d objects" % len(x_list))
print("y_list contains %d objects" % len(y_list))
print("big_list contains %d objects" % len(big_list))

# testing code
if x_list.count(x) == 10 and y_list.count(y) == 10:
    print("Almost there...")
if big_list.count(x) == 10 and big_list.count(y) == 10:
    print("Great!")
