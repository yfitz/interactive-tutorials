Tutorial
--------

Zeichenketten(Strings) sind Text. Diese werden definiert durch Anführungszeichen:

    astring = "Hello world!"
    astring2 = 'Hello world!'

Wie man sehen kann, die erst Sache die wir lernen ist die Ausgabe einfacher Sätze. Der Satz wird als Zeichenkette gespeichert. 
Bevor wir den Satz ausgeben, probieren wir aus was sonst noch möglich. 
Einfache Anführung sind auch möglich, aber haben Probleme mit einfachen Anführungszeichen innerhalb der Zeichenkette. 
Zum Beispiel die folgende Zeichenkette muss in doppelte Anführungszeichen: "single quotes are ' ' "

    astring = "Hello world!"
    print("single quotes are ' '")

    print(len(astring))

Dies gibt 12 aus, weil das die Anzahl der Zeichen der Zeichenkette "Hello world!" ist.

    astring = "Hello world!"
    print(astring.index("o"))

Dies gibt 4 aus, weil weil das erste 'o' das 4.Zeichen in der Zeichenkette ist. (Man beachte es wird mit 0.Zeichen (H) begonnen.)
Nur das erste Vorkommen wird gefunden. 

Warum nicht 5, Wie andere Programmiersprachen beginnt der Index bei 0 nicht 1 d.h. das erste Zeichen ist 0.Zeichen usw. 

    astring = "Hello world!"
    print(astring.count("l"))

Es werden hier die Anzahl der 'l' in der Zeichenkette gezählt, so dass sich 3 ergibt. 

    astring = "Hello world!"
    print(astring[3:7])

Es wird eine Teilzeichenkette ausgegeben, beginnende beim 3.Zeichen bis zum 6.Zeichen (Man beachte es wird mit 0.Zeichen (H) begonnen.) 
Nicht das 7.Zeichen - dies macht Mathe innerhalb der [] einfacher.

Mit nur einer Zahl in der Klammern [], wird nur das Zeichen mit diesem Index geliefert.
Mit einer Zahl und Doppelpunkt in Klammern [], wird die Teilzeichenkette, die beim angegebenen Index beginnt bis zum Ende der Zeichenkette.  

Auch negative Zahlen sind in den Klammern [] möglich. Dabei beginnt die Zählung von hinten in der Zeichenkette, so dass -3 das 3.letzte Zeichen angibt. 

    astring = "Hello world!"
    print(astring[3:7:2])

Die Ausgabe beginnt beim Index 3 bis 7 - wobei in 2er Schritten. Dies erweitert die slice (Teilzeichenketten) Syntax. Generelle Form ist [start:stop:step].

    astring = "Hello world!"
    print(astring[3:7])
    print(astring[3:7:1])

Beachte: Beide produzieren gleichen Output. 

Es gibt keine Funktion, die eine Zeichenkette umdreht, aber die oben gezeigte Funktion leistet diese auch wie folgt: 

    astring = "Hello world!"
    print(astring[::-1])

Folgendes

    astring = "Hello world!"
    print(astring.upper())
    print(astring.lower())

erzeugt Zeichenkette aus Klein- bzw. Großbuchstaben.  

    astring = "Hello world!"
    print(astring.startswith("Hello"))
    print(astring.endswith("asdfasdfasdf"))

Folgendes prüft ob eine Zeichenkette ein bestimmtes Anfangs- oder Endzeichen besitzt. Das erste Beispiel gibt True aus, wenn die
Zeichenkette mit "Hello" beginnt. Das zweite Beispiel gibt False aus, weil die Zeichenkette nicht mit "asdfasdfasdf" endet.

    astring = "Hello world!"
    afewwords = astring.split(" ")

Dies zertrennt die Zeichenkette in mehrere Zeichenkette, die in eine Liste gespeichert werden. Im Beispiel wird bei jedem Leerzeichen 
getrennt, dass heisst diese werden erfernt und die Ergebnisliste enthält "Hello" und "world!".

Übung
-----

Versuche den Code zu reparieren um die korrekte Information auszugeben. 

Tutorial Code
-------------

s = "Hey there! what should this string be?"
# Länge soll 20 sein
print("Length of s = %d" % len(s))

# Erste Vorkommen von "a" soll bei Index 8 sein. 
print("The first occurrence of the letter a = %d" % s.index("a"))

# Anzahl der  a's soll 2 sein
print("a occurs %d times" % s.count("a"))

# Zertrennen der Zeichenkette in Teilzeichenketten 
print("The first five characters are '%s'" % s[:5]) # Beginne bei 5
print("The next five characters are '%s'" % s[5:10]) # Von 5 bis 10
print("The thirteenth character is '%s'" % s[12]) # Nur Zahl 12
print("The characters with odd index are '%s'" %s[1::2]) # Index beginnt bei 0 
print("The last five characters are '%s'" % s[-5:]) # Die 5 letzten Zeichen

# Konvertiere in Großbuchstaben
print("String in uppercase: %s" % s.upper())

# Konvertiere in Kleinbuchstaben
print("String in lowercase: %s" % s.lower())

# Prüfe wie eine Zeichenkette beginnt
if s.startswith("Str"):
    print("String starts with 'Str'. Good!")

# Prüfe wie eine Zeichenkette endet
if s.endswith("ome!"):
    print("String ends with 'ome!'. Good!")

# Zertrenne die Zeichenkette in drei Teilzeichenketten, jede nur aus einem Wort bestehend. 
print("Split the words of the string: %s" % s.split(" "))

Expected Output
---------------

test_object("s", incorrect_msg="Make sure you change the string assigned to `s` to match the exercise instructions.")
success_msg("Great work!")

Solution
--------

s = "Strings are awesome!"
# Länge soll 20 sein
print("Length of s = %d" % len(s))

# Erste Vorkommen von "a" soll bei Index 8 sein. 
print("The first occurrence of the letter a = %d" % s.index("a"))

# Anzahl der  a's soll 2 sein
print("a occurs %d times" % s.count("a"))

# Zertrennen der Zeichenkette in Teilzeichenketten 
print("The first five characters are '%s'" % s[:5]) # Start to 5
print("The next five characters are '%s'" % s[5:10]) # 5 to 10
print("The thirteenth character is '%s'" % s[12]) # Just number 12
print("The characters with odd index are '%s'" %s[1::2]) #(0-based indexing)
print("The last five characters are '%s'" % s[-5:]) # 5th-from-last to end

# Konvertiere in Großbuchstaben
print("String in uppercase: %s" % s.upper())

# Konvertiere in Kleinbuchstaben
print("String in lowercase: %s" % s.lower())

# Prüfe wie eine Zeichenkette beginnt
if s.startswith("Str"):
    print("String starts with 'Str'. Good!")

# Prüfe wie eine Zeichenkette endet
if s.endswith("ome!"):
    print("String ends with 'ome!'. Good!")

# Zertrenne die Zeichenkette in drei Teilzeichenketten, jede nur aus einem Wort bestehend. 
print("Split the words of the string: %s" % s.split(" "))
