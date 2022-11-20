Tutorial
--------
Bei der Programmierung passieren Fehler. Vielleicht durch falsche Benutzer Eingabe. 
Vielleicht war eine Netzwerk Resource nicht verfügbar. Vielleicht verwendet ein Programm 
zuviel Speicherplatz. Oder der Programmierer hat einen Fehler gemacht.

Python's Lösung von Fehlern sind Exceptions.Vielleicht hast Du schon eine Exception gesehen.

    print(a)
    
    #Fehler
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'a' is not defined

Oops! Vergessen einen Wert der Variable 'a' zuzuweisen. 

Aber machmal soll die Exception nicht das komplette Programm stoppen. 
Vielleicht soll etwas besonderes passieren, wenn die Exception auftritt (raised).
Das passiert im *try/except* Block.

Hier ein triviales Beispiel: Angenommen wir iterieren über eine Liste. 
We müssen über 20 Zahlen itertieren, aber die Liste wird aus Benutzer Eingaben zusammengestellt 
und könnte auch 20 Zahlen enthalten. Nachdem das Listenende erreicht ist, sollen die 
anderen Zahlen als 0 interpretiert werden. 
So könnte man es machen:
    def do_stuff_with_number(n):
        print(n)
    
    def catch_this():
        the_list = (1, 2, 3, 4, 5)
    
        for i in range(20):
            try:
                do_stuff_with_number(the_list[i])
            except IndexError: # Raised when accessing a non-existing index of a list
                do_stuff_with_number(0)
    
    catch_this()

So, nicht schlecht! Es kann mittels Exception gemacht werden. Um mehr Information über Exceptions zu bekommen,
ist folgende Referenz einzusehen: 
[Python Docs](http://docs.python.org/tutorial/errors.html#handling-exceptions)

Exercise
--------

Alle Exceptions behandeln! Im vorherigen Thema wurde der letzte Name des Akteurs (actor) zurück geliefert. 

Tutorial Code
-------------

# Setup
actor = {"name": "John Cleese", "rank": "awesome"}

# Funktion zum modifizieren!
def get_last_name(): 
    return actor["last_name"]

# Test code
get_last_name()
print("All exceptions caught! Good job!")
print("The actor's last name is %s" % get_last_name())

Expected Output
---------------

test_output_contains("Cleese")
test_output_contains("All exceptions caught! Good job!")
test_output_contains("The actor's last name is Cleese")
success_msg("Great work!")

Solution
--------
actor = {"name": "John Cleese", "rank": "awesome"}

def get_last_name():
    return actor["name"].split()[1]

get_last_name()
print("All exceptions caught! Good job!")
print("The actor's last name is %s" % get_last_name())
