Tutorial
--------

Eine **Closure** ist ein Objekt von Typ Funktion, dass Werte speichert in einem Gültigkeitsbereich, auch wenn die nicht im Speicher gehalten werden. Erstmal Schritt für Schritt.

Zuerst, eine  **Nested Function** ist eine Funktion, die in einer anderen Funktion definiert wurde. Es ist wichtig zu beachten, dass die Nested Funktion (eingeschlossene Funktion) auf die Variablen des inneren Gültigkeitsbereich zugreifen kann. Jedoch, sind diese in Python, wenigstens nur readonly. Durch das Schlüsselwort "nonlocal" explizit mit diesen Variablen, können diese verändert werden.  

Zum Beispiel:

    def transmit_to_space(message):
        "This is the enclosing function"
        def data_transmitter():
            "The nested function"
            print(message)
    
        data_transmitter()
    
    print(transmit_to_space("Test message"))

Dies funktioniert gut, weil die Funkton 'data_transmitter' Zugriff auf die Variable 'message' hat. Um dies zu demonstrieren, verwende das Schlüsselwort "nonlocal" , und beachte

    def print_msg(number):
        def printer():
            "Here we are using the nonlocal keyword"
            nonlocal number
            number=3
            print(number)
        printer()
        print(number)
    
    print_msg(9)

Ohne das nonlocal Schlüsselwort, hätten wir folgende Ausgabe "3 9", aber, mit diesem, ist die Ausgabe "3 3", dass ist der Wert von der "number" Variable welcher verändert wurde.

Nun wolllen wir das Objekt Funktion zurückleben stat diese aufzurufen.  ( Da in Python Funktionen auch Objekte sind.)

    def transmit_to_space(message):
        "This is the enclosing function"
        def data_transmitter():
            "The nested function"
            print(message)
        return data_transmitter

Und wir rufen die Funktion wie folgt auf:


      def transmit_to_space(message):
        "This is the enclosing function"
        def data_transmitter():
            "The nested function"
            print(message)
        return data_transmitter
        
  	  fun2 = transmit_to_space("Burn the Sun!")
  	  fun2()

Obwohl die Ausführung von "transmit_to_space()" beendet ist, die Nachicht in message bleibt erhalten. Diese Technik nach der die Daten aushalb des enschließenden Codes noch noch erhalten bleibt nennt man in Python Closure. 

VORTEIL : Closures lassen uns globale Variablen vermeiden und liefern trotzdem ein Form des Informations Verbergens (Data Hiding) an. Zum Beispiel wenn es ein paar Methoden in einer Klasse gibt, verwenden wir Closures stattdessen.

Also, die Decorators in Python verwenden Closures sehr viel.

Exercise
--------

Erzeuge eine nested loop und eine Python Closure um Funktionen mit verschiedenen Multiplikationen auszustatten unter Verwendung von Closures. 
Closures können hier verwendet werden um Funktionen wie multiply_with_5() oder multiply_with_4() zu erzeugen. 

Tutorial Code
-------------

# Hier Code einfügen

multiplywith5 = multiplier_of(5)
multiplywith5(9)

Expected Output
---------------

test_output_contains("45")
success_msg("Great work!")

Solution
--------

def multiplier_of(n):
    def multiplier(number):
        return number*n
    return multiplier

multiplywith5 = multiplier_of(5)
print(multiplywith5(9))
