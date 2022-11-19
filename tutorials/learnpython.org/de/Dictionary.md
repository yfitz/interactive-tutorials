Tutorial
--------

Ein Dictionary ist ein ähnlicher Datentyp wie Array, nur mit Schlüssel- und Wert-Paare und statt Index wird der Schlüssel verwendet. Auf jeden Wert im Dictionary kann man durch einen Schlüssel zugreifen, der jeden beliebigen Datentyp annehmen kann (string, number, list, etc.).

Zum Beispiel, eine Datenbank aus Telefonnummern können in einem Ditionary wie folgt gespeichert werden: 

    phonebook = {}
    phonebook["John"] = 938477566
    phonebook["Jack"] = 938377264
    phonebook["Jill"] = 947662781
    print(phonebook)

Alternativ, kann das Dictionary wie folgt initialisiert werden: 

    phonebook = {
        "John" : 938477566,
        "Jack" : 938377264,
        "Jill" : 947662781
    }
    print(phonebook)

### Iteration über das Dictionary 

Dictionaries können durchlaufen werden, wie bei Listen. Anders ls bei der Liste, gibt es in Dictionaries keine Anordnung (keine fixe Reihenfolge) der darin gespeicherten Werte.
Um diese Werte zu durchlaufen kann folgende Syntax verwendet werden: 
    
    phonebook = {"John" : 938477566,"Jack" : 938377264,"Jill" : 947662781}
    for name, number in phonebook.items():
        print("Phone number of %s is %d" % (name, number))

### Entfernen eines Wertes 

Um einen Wert zu entfernen, können folgende Notationen verwendet werden:
    
    phonebook = {
       "John" : 938477566,
       "Jack" : 938377264,
       "Jill" : 947662781
    }
    del phonebook["John"]
    print(phonebook)

oder:
    
    phonebook = {
       "John" : 938477566,
       "Jack" : 938377264,
       "Jill" : 947662781
    }
    phonebook.pop("John")
    print(phonebook)


Exercise
--------

Füge "Jake" in das Dictionary phonebook mit der Telefonnummer 938273443 ein, und entferne Jill aus dem phonebook.

Tutorial Code
-------------

phonebook = {  
    "John" : 938477566,
    "Jack" : 938377264,
    "Jill" : 947662781
}  
# Hier Code einfügen

# testing code
if "Jake" in phonebook:  
    print("Jake is listed in the phonebook.")
    
if "Jill" not in phonebook:      
    print("Jill is not listed in the phonebook.")  


Expected Output
---------------

test_output_contains("Jake is listed in the phonebook.")
test_output_contains("Jill is not listed in the phonebook.")
success_msg("Nice work!")

Solution
--------

phonebook = {  
    "John" : 938477566,
    "Jack" : 938377264,
    "Jill" : 947662781
}  

# Hier Code einfügen
phonebook["Jake"] = 938273443  
del phonebook["Jill"]  

# testing code
if "Jake" in phonebook:  
    print("Jake is listed in the phonebook.")
    
if "Jill" not in phonebook:      
    print("Jill is not listed in the phonebook.")  
