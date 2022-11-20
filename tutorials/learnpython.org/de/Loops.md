Tutorial
--------

Es gibt in Python zwei Arten von Schleifen, for und while.

### Die "for" Schleife

For Schleifen iterieren durch ine gegebene Sequenz. Hier ein Beispiel:

    primes = [2, 3, 5, 7]
    for prime in primes:
        print(prime)

For Schleifen können über ein Sequenz aus Nummern iterieren unter Verwendung von "range" und "xrange" Funktionen. Der Unterschied zwischen range und xrange ist, das die range Funktion 
eine neue Liste aus Zahlen, die den angegebenen Wertbereich wiederspiegeln liefert, hingegen xrange einen Iterator, welcher effizienter ist. 
(In Python 3 reagiert die range Funktion, ungefähr wie xrange). Beachte die range Funktion ist Nullbasiert.

    # Ausgabe der Zahlen 0,1,2,3,4
    for x in range(5):
        print(x)

    # Ausgabe der Zahlen 3,4,5
    for x in range(3, 6):
        print(x)

    # Ausgabe der Zahlen 3,5,7
    for x in range(3, 8, 2):
        print(x)

### "while" Schleife

While Schleife wiederholt sich solange die Bedingung gilt. Zum Beispiel:

    # Ausgabe der Zahlen 0,1,2,3,4

    count = 0
    while count < 5:
        print(count)
        count += 1  # This is the same as count = count + 1

### "break" und "continue" Anweisung

**break** wird verwendet um eine for Schleife oder while Schleife zu verlassen, wohingegen **continue** verwendet wird um Blöcke auszulassen (überspringen)
und zu der for oder while Anweisung zurückzukehren. Ein paar Beispiele:

    # Ausgabe der Zahlen 0,1,2,3,4

    count = 0
    while True:
        print(count)
        count += 1
        if count >= 5:
            break

    # Ausgabe der ungeraden Zahlen - 1,3,5,7,9
    for x in range(10):
        # Check if x is even
        if x % 2 == 0:
            continue
        print(x)

### Können wir else in einer for Schleife verwenden?

Anders als Sprachen wie C,CPP.. können wir **else** in for Schleifen verwenden. Wenn die Bedingung der for oder while Schleife nicht erfüllt ist, wird der Code 
unter else ausgeführt. Wird eine **break** anweisung in der for Schleife ausgeführt, wird der "else" Teil ausgelassen. 
Beachte das "else" wird auch ausgeführt, wenn eine **continue** Anweisung vorhanden.

Hier ein paar Beispiele:

    # Ausgabe der Zahlen 0,1,2,3,4 und dann Ausgabe von "count value reached 5"

    count=0
    while(count<5):
        print(count)
        count +=1
    else:
        print("count value reached %d" %(count))

    # Prints out 1,2,3,4
    for i in range(1, 10):
        if(i%5==0):
            break
        print(i)
    else:
        print("this is not printed because for loop is terminated because of break but not due to fail in condition")


Exercise
--------

Durchlaufe und gebe alle geraden Zahlen aus der numbers Liste in der gleichen Ordnung aus. Zahlen nach der Zahl 237 werden nicht ausgegeben.

Tutorial Code
-------------
numbers = [
    951, 402, 984, 651, 360, 69, 408, 319, 601, 485, 980, 507, 725, 547, 544,
    615, 83, 165, 141, 501, 263, 617, 865, 575, 219, 390, 984, 592, 236, 105, 942, 941,
    386, 462, 47, 418, 907, 344, 236, 375, 823, 566, 597, 978, 328, 615, 953, 345,
    399, 162, 758, 219, 918, 237, 412, 566, 826, 248, 866, 950, 626, 949, 687, 217,
    815, 67, 104, 58, 512, 24, 892, 894, 767, 553, 81, 379, 843, 831, 445, 742, 717,
    958, 609, 842, 451, 688, 753, 854, 685, 93, 857, 440, 380, 126, 721, 328, 753, 470,
    743, 527
]

# Code hier einfügen
for number in numbers:

Expected Output
---------------

test_object("number", undefined_msg="Define a object `number` using the code from the tutorial to print just the desired numbers from the exercise description.",incorrect_msg="Your `number` object is not correct, You should use an `if` statement and a `break` statement to accomplish your goal.")
success_msg("Great work!")

Solution
--------

numbers = [
    951, 402, 984, 651, 360, 69, 408, 319, 601, 485, 980, 507, 725, 547, 544,
    615, 83, 165, 141, 501, 263, 617, 865, 575, 219, 390, 984, 592, 236, 105, 942, 941,
    386, 462, 47, 418, 907, 344, 236, 375, 823, 566, 597, 978, 328, 615, 953, 345,
    399, 162, 758, 219, 918, 237, 412, 566, 826, 248, 866, 950, 626, 949, 687, 217,
    815, 67, 104, 58, 512, 24, 892, 894, 767, 553, 81, 379, 843, 831, 445, 742, 717,
    958, 609, 842, 451, 688, 753, 854, 685, 93, 857, 440, 380, 126, 721, 328, 753, 470,
    743, 527
]

# Code hier einfügen
for number in numbers:
    if number == 237:
        break

    if number % 2 == 1:
        continue

    print(number)
