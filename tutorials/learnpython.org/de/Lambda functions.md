Tutorial
--------
Normalerweise definieren wir Funktion mit dem Schlüsselwort def irgendwo im Code und rufen diese auf gebraucht wird.


    def sum(a,b):
        return a + b

    a = 1
    b = 2
    c = sum(a,b)
    print(c)

Nun statt die Funktion irgendwo zu definieren und aufzurufen, verwenden wir lambda Funktionen, welches inline Funktionen sind Funktionen, 
die da definiert werden wo sie aufgerufen werden. Wir müssen die Funktionen nicht definieren und verwenden diesesn Code nur einmalig. 

Diese brauchen keine Namen, und werden somit anonyme Funktionen genannt. Wir definieren lambda Funktionen mit dem Schlüsselwort lambda.

    your_function_name = lambda inputs : output

Das sum Beispiel von oben sieht als lambda Funktion wie folgt aus,

    a = 1
    b = 2
    sum = lambda x,y : x + y
    c = sum(a,b)
    print(c)

Hier haben wir die lambda Funktion der Variable  **sum** zugewiesen, und wenn die Argumente z.B. a und b übergeben werden, funktioniert es wie eine normale Funktion. 



Exercise
--------
Schreibe ein Programm mit lambda Funktion um zu prüfen ob eine Zahl in einer gegebenen Liste ungerade ist. 
Ausgabe"True" wenn die Zahl ungerade ist oder "False" wenn nicht jedes Element ungerade.

Tutorial Code
-------------
l = [2,4,7,3,14,19]
for i in l:
    # Code hier einfügen

Expected Output
---------------
test_output_contains("False")
test_output_contains("False")
test_output_contains("True")
test_output_contains("True")
test_output_contains("False")
test_output_contains("True")
success_msg("Nice work!")

Solution
--------
l = [2,4,7,3,14,19]
for i in l:
    # Code hier einfügen
    my_lambda = lambda x : (x % 2) == 1
    print(my_lambda(i))
