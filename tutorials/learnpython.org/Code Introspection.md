Tutorial
--------

Code Introspection ist eine Möglichkeit Klassen, Funktionen und Schlüsselwörter zu untersuchen, um herauszufinden was vorliegt, was diese machen und was wir wissen. 

Python liefert verschiedene Funktionen und Tools für Code Introspection.

    help()
    dir() 
    hasattr() 
    id() 
    type() 
    repr() 
    callable() 
    issubclass() 
    isinstance() 
    __doc__ 
    __name__ 
    

Oft ist die wichtigste die help Funktion, um zu ermitteln was eine andere Funktion macht. 

Exercise
--------

Produziere eine Liste als Ausgabe, die aus den Attributen des gegebenen Vehicle Objekt besteht.

Tutorial Code
-------------

# Verwenden die help Funktion um dessen Funktionalität anzuzeigen.
# Lösche dies wenn fertig
help(dir)
help(hasattr)
help(id)

# Definiere die Vehicle Klasse
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

# Liste als Ausgabe, die aus den Attributen des gegebenen Vehicle Objekt besteht
# Hier Code einfügen


Expected Output
---------------

test_output_contains("['__doc__', '__module__', 'color', 'description', 'kind', 'name', 'value']")
test_student_typed("print")
success_msg("Very nice!")

Solution
--------

# Definiere die Vehicle Klasse
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

# Liste als Ausgabe, die aus den Attributen des gegebenen Vehicle Objekt besteht
print(dir(Vehicle))
