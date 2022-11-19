Tutorial
--------

### Was ist CSV?
CSV steht für 'Comma Separated Values'. CSV Format ist das meist verwendete import und export Format für Datenbanken und Excelsheets. 
Eine CSV Datei ist eine einfache Textdatei welches eine Liste von Daten enthält. Meistens werden Kommas als Trennzeichen verwendet, 
aber auch andere Zeichen dürfen verwendet werden z.B Semicolon oder Tabs.

Beispiel CSV Data:

...
column 1 name,column 2 name, column 3 name
first row data 1,first row data 2,first row data 3
second row data 1,second row data 2,second row data 3
...

### CSV Modul in Python
Wenn Python auch eine eingebaute open() Funktion besitzt um mit Dateien zu arbeiten, gibt es auch ein speziell auch CSV Dateien ausgelegtes Modul, welches Klassen die lesen oder schreiben im CSV Format liefert und somit den Umgang mit CSV Dateien erleichert.

### CSV Modul wichtige Funktionen

    csv.field_size_limit – return maximum field size
    csv.get_dialect – get the dialect which is associated with the name
    csv.list_dialects – show all registered dialects
    csv.reader – read data from a csv file
    csv.register_dialect - associate dialect with name
    csv.writer – write data to a csv file
    csv.unregister_dialect - delete the dialect associated with the name the dialect registry
    csv.QUOTE_ALL - Quote everything, regardless of type.
    csv.QUOTE_MINIMAL - Quote fields with special characters
    csv.QUOTE_NONNUMERIC - Quote all fields that aren't numbers value
    csv.QUOTE_NONE – Don't quote anything in output

### Wie verwendet man das csv Modul?
Zuerst importiert man das CSV Modul in das Python Programm.

    import csv

writer und reader Funktionen erlauben ein editieren, modifizieren und übertragen von Daten in eine CSV Datei.

Wie liest man aus einer CSV Datei :-

Um die Daten aus einer CSV Datei zu lesen verwendet man die reader Funktion welche ein reader Objekt erzeugt.

Zum Beispiel:

    with open(filename, 'r') as csvfile:
        csvreader = csv.reader(csvfile)

Zuerst öffnen wir die CSV Datei im READ Modus und geben dem Datei Objekt csvfile. Wir verwenden einen context manager um die Datei zu öffnen, sodass wir uns nicht um das schließen kümmern müssen.
csv.reader Funktion verwendet das Datei Objekt als Eingabe und liefert ein iterate (iterierbares) Objekt. Dieses Objekt wird in csvreader gespeichert.

Wie gesagt, csvreader ist ein iterable Objekt und somit können wir in einer Schleife dieses durchlaufen:

Beispiel 1:

    with open(filename, 'r') as csvfile:
        csvreader = csv.reader(csvfile)
        for row in csvreader:
            print(row)

Der Code oben wird alle Zeilen der CSV Datei ausgeben. Öffne die Datei im 'r' Modus wenn diese bereits existiert. 

Was kommt jetzt?

cvreader ist ein iterable Objekt. Also können wird die Methode .next() verwenden um die nächste Zeile zu holen und auf die nächste Zeile vorzurücken. 

Beispiel 2:

    with open(filename, 'r') as csvfile:
        csvreader = csv.reader(csvfile)
        fields = csvreader.next()
        for row in csvreader:
            print(row)

In Beispiel 1, kann man alle Zeilen in der Konsole ausgegeben sehen einschließlich Überschrift. 
In Beispiel 2, liest die .next() Method die Überschriften der Felder des Objekts und rückt zur nächsten Zeile weiter, so dass alle Zeilen ohne Überschrift ausgegeben werden.


Wie schreibt man eine CSV Datei

Um in eine CSV Datei zu schreiben, liefert das CSV Modul die Funktion csv.writer. Um Daten zu schreiben wird zuerst die Datei im WRITE Modus mode('w') geöffnet
Das Datei Objekt wird csvfile genannt. Wir speichern das csv.writer Objekt als csvwriter.

Beispiel:
#declare header
    fields = ['column1','column2', 'column3']

    #declare rows
    rows = [["foo", "bar", "spam"],
           ["oof", "rab", "maps"],
           ["writerow", "isn't", "writerows"]]

    filename = "university_records.csv"
    
    with open(filename, 'w') as csvfile:
        csvwriter = csv.writer(csvfile)
        csvwriter.writerow(fields)
        csvwriter.writerows(rows)

In dem Beispiel oben, writerow() Funktion schreibt eine Zeile, welches ein Fields Objekt ist. Stattdessen schreibt die Methode writerows() eine komplette Liste von Zeilen in die CSV Datei.

Jetzt gehen wir einen Schritt weiter. Lesen aus einer CSV Datei und schreiben in eine andere CSV Datei .

Beispiel:

    with open('newfilename.csv', 'w') as f2:
        with open('mycsvfile.csv', mode='r') as f1:
            reader = csv.reader(f1)
            csvwriter = csv.writer(f2)
            header = next(reader)  # store the headers and advance reader pointer
            csvwriter.writerow(header) #writes the header into new file
            for row in reader:
                csvwriter.writerow(row)

Hier öffnen wir 'newfilename.csv' im 'W' mode als f2 und öffnen 'mycsvfile.csv' im 'r' mode als f1. Wir verwenden .next(), .reader(),.writer(), .writerow() Funktionen
des CSV Moduls. Die Verwendung von .next(), schiebt den reader Zeiger vorwärts und die Verwendung von csvwriter.writerow() schreibt die eingehende Zeile eine nach der anderen.


### DictReader und DictWriter Klassen in Python

Unten stehen zwei wichtige Klassen um in Python CSV Dateien zu lesen und zu schreiben.

csv.Dictwriter class
csv.DictReader class

Die DictReader und DictWriter sind Klassen zum lesen und schreiben von CSV Dateien. Obwohl diese ähnlich sind wie die reader und writer Funktionen, verenden diese Klassen
dictionary Objekte um zu lesen oder schreiben in CSV Dateien.

DictReader:

Es erzeugt ein Objekt welche die Information liest und abbildet in ein Dictionary, dessen Schlüssel die Feldnamen Parameter sind. Diese Parameter sind optional, aber wnn diese 
nicht in der Datei spezifiziert sind, wird die erste Zeile der Daten zu den Schlüssel des Dictionary. 

Beispiel csv(info.csv)

.....
firstname, lastname
foo, bar
foo1, bar1
.....

Beispiel:

        import csv
        with open('info.csv') as csvfile:
        reader = csv.DictReader(csvfile)
        for row in reader:
            print(row['firstname'], row['lastname'])

DictWriter:

Die csv.DictWriter Klasse opereriert wie ein regulärer writer und übertragt das Python Dictionary in CSV Zeilen. Die Feldnamen Parameter ist eine Sequenz von Schlüsseln welche die Reihenfolge der Werte im Dictionry angibt wie es von der
writerow() Methode in die CSV Datei geschrieben. 
Die Klasse ist definiert als csv.DictWriter(csvfile, fieldnames, restval='', extrasaction='raise', dialect='excel', *args, **kwds)

Beispiel:

        import csv
        f = open('info.csv', 'w')
        with f:
            
            fnames = ['firstname', 'lastname']
            writer = csv.DictWriter(f, fieldnames=fnames)    

            writer.writeheader()
            writer.writerow({'firstname' : 'Rob', 'last_name': 'Scott'})
            writer.writerow({'firstname' : 'Tom', 'last_name': 'Brown'})
            writer.writerow({'firstname' : 'Henry', 'last_name': 'Smith'})



