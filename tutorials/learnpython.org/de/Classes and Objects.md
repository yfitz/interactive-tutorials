Tutorial
-----------------

Objekte sind eingeschlossener Code von Variablen und Funktionen in einer einzigen Entität. Objekte bekommen ihre Variablen und Funktionen von Klassen. 
Klassen sind initial Templates um Objekte zu erzeugen. 

Eine erste Klasse würde wie folgt aussehen: 

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

Die Erklärung von "self" als Parameter folgt später. Zuerst, um die Klasse auf ein Objekt anzuwenden wird folgendes gemacht: 

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()

Nun ist die Variable "myobjectx" ein Objekt vom Typ Klasse "MyClass" , welches die Variablen und Funktionen der Klasse "MyClass" enthält.

### Zugriff auf die Objekt Variablen

Um Zugang zu den Variablen innerhalb des neuerzeugten Objekts "myobjectx" zu erhalten, mache folgendes:

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()

    myobjectx.variable

So wird zum Beispiel das folgende die Zeichenkette "blah" ausgeben:

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()

    print(myobjectx.variable)

Wie folgt lassen sich mehrere Objekte der gleichen Klasse erzeugen (mit den selben Variablen und Funktionen). Aber, jedes Objekt enthält ein unabhängige Kopie der Variablen in der Klasse. 
Zum Beispiel, wenn wir noch ein Objekt der Klasse "MyClass" definieren und die Zeichenketten verändern:  

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()
    myobjecty = MyClass()

    myobjecty.variable = "yackity"

    # Ausgabe beider Werte
    print(myobjectx.variable)
    print(myobjecty.variable)


### Zugang zu den Objekt Funktionen

Um die Funktion in einem Objekt zuzugreifen verwendet man folgende Notation:

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()

    myobjectx.function()

Das würde folgende Ausgabe erzeugen "This is a message inside the class."

### __init__()

Die `__init__()` Funktion, ist eine Spezialfunktion, die aufgerufen wird wenn eine Klasse initiert wird. 
Es wird verwendet um Werte in Klassen erste Werte zuzuweisen. (Initialisierung)
    class NumberHolder:
       
       def __init__(self, number):
           self.number = number
           
       def returnNumber(self):
           return self.number

    var = NumberHolder(7)
    print(var.returnNumber()) #Prints '7'
    
Exercise
--------

Wir haben eine Klasse für Fahrzeuge die Vehicle heißt. Erzeuge zwei Fahrzeuge car1 und car2.
Setze car1 auf red convertible worth $60,000.00 mit dem Namen Fer,
und car2 soll ein blue van mit dem Namen Jump worth $10,000.00.

Tutorial Code
-------------

# definiere die Vehicle Klasse
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str
        
# Hier soll ihr Code eingefügt werden

# test code
print(car1.description())
print(car2.description())

Expected Output
---------------

#test_output_contains('Fer is a red convertible worth $60000.00.')
#test_output_contains('Jump is a blue van worth $10000.00.')
success_msg("Great job!")

Solution
--------

# definiere die Vehicle Klasse
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

# Hier soll ihr Code eingefügt werden
car1 = Vehicle()
car1.name = "Fer"
car1.color = "red"
car1.kind = "convertible"
car1.value = 60000.00

car2 = Vehicle()
car2.name = "Jump"
car2.color = "blue"
car2.kind = "van"
car2.value = 10000.00

# test code
print(car1.description())
print(car2.description())
