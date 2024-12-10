# Session 01: Datentypen und konsolenbasierte Interaktion

## Konsolenbasierte Interaktion
Das Erstellen einer Anwendung mit konsolenbasierter Nutzerinteraktion hat in der Programmierung mittlerweile den Status der mit Abstand beliebtesten Aufgabe für Einsteiger.  Sie ist vergleichsweise einfach zu verstehen und schnell umgesetzt.<br><br>
Interaktionen mit dem Benutzer lassen sich in Input (Eingabe) und Output (Ausgabe) unterteilen. Beide Begriffe sind recht selbsterklärend, deswegen starten wir direkt mit einem Beispiel.<br>
Ähnlich wie die meisten anderen Programmiersprachen auch, liefert Python eingebaute Methoden um sowohl konsolenbasierten Input, als auch konsolenbasierten Output im Handumdrehen in eine Applikation zu integrieren.<br>Introducing: `input()` und `print()`<br>
**Beispiel:**
```python
# Benutzer soll Wert in die Konsole eingeben
# Zu beachten gilt hier, dass die Variable in welcher der Eingabewert gespeichert wird, standardmäßig den Typ "String" hat.
value = input("Bitte Wert eingeben: ")

# Hier könnten wir jetzt etwas mit der Variable "value" machen
...

# Ausgabe der Variable
print(value)
```
Anhand der eingebauten Funktionen `input()` und `print()` können wir also über die Konsole mit unserem Benutzer interagieren und Daten austauschen.

## Fundamentale Datentypen in Python
Wie in den meisten Programmiersprachen, kann eine Variable auch in Python einen von vielen unterschiedlichen Datentypen haben. Die folgende Tabelle erklärt die 6 wichtigsten Datentypen in Python, deren Wertebereiche und wofür sie eingesetzt werden können.

| Datentyp       | Beschreibung                                                                                                                                                                         | Wertebereich                                                            | Referenz                                                                |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Boolean / bool | Bool'scher Wert / Wahrheitswert                                                                                                                                                      | True oder False                                                         | https://python-reference.readthedocs.io/en/latest/docs/bool/index.html  |
| String / str   | Zeichenkette/Text, welcher von Python auch nur als solcher interpretiert werden kann. Mathematische Berechnungen anhand von Strings sind in Python nicht ohne Konvertierung möglich. | UNICODE-Zeichensatz: https://symbl.cc/en/unicode-table/                 | https://python-reference.readthedocs.io/en/latest/docs/str/index.html   |
| Integer / int  | Ganzzahl ohne Komma                                                                                                                                                                  | -2147483648 bis 2147483647                                              | https://python-reference.readthedocs.io/en/latest/docs/ints/            |
| Float / float  | Kommazahl                                                                                                                                                                            | Abhängig von der Plattform, heutzutage meist 1.7e-308 bis 1.7e+308      | https://python-reference.readthedocs.io/en/latest/docs/float/index.html |
| Long / long    | Lange Ganzzahl                                                                                                                                                                       | Unbegrenzt, nur abhängig von der Größe des verfügbaren Arbeitsspeichers | https://python-reference.readthedocs.io/en/latest/docs/ints/indexl.html |
| List / list    | Indizierte Liste von Objekten                                                                                                                                                        | Unbegrenzt, nur abhängig von der Größe des verfügbaren Arbeitsspeichers | https://python-reference.readthedocs.io/en/latest/docs/list/index.html  |


### Zuordnung von Datentypen
Bei der einfachen Initialisierung einer Variable wählt Python automatisch den passenden Datentyp für diese. Wir als Entwickler müssen entsprechend nichts tun um sicherzustellen dass eine Variable den richtigen Datentyp besitzt.<br>
**Beispiel:**<br>
```python
python_is_cool = True      # Variable hat den Typ "bool"
my_name = "Lucas"          # Variable hat den Typ "str" (für String)
my_age = 21                # Variable hat den Typ "int" (für Integer)
my_height = 1.88           # Variable hat den Typ "float"
```
Dieser Mechanismus vereinfacht das Handling von Variablen in Python natürlich sehr, jedoch ist es manchmal nötig, eine Variable manuell in einen anderen Datentypen zu konvertieren.


### Konvertierung zwischen Datentypen
Python liefert diverse eingebaute Methoden, welche in der Lage sind, Variablen zwischen bestimmten Datentypen (bspw. String zu Integer) zu konvertieren. Die Dokumentationen in der Spalte "Referenzen" der oben dargestellten Tabelle listen alle Methoden entsprechend auf.<br><br>Für diese Erklärung beschränken wir uns ausnahmsweise nur auf ein konkretes Beispiel. Unser Python-Script soll den Benutzer nach zwei Zahlen fragen, welcher dieser über die Konsole eingeben soll. Anschließend soll das Script beide Zahlen addieren und das Ergebnis auf der Konsole ausgeben. Wie oben bereits beschrieben, liefert die `input()`-Methode einen Wert von Typ `String` zurück, sodass für die Addition eine Konvertierung von `String` zu `Integer` nötig ist. Das folgende Beispiel zeigt eine ausführliche Version dieses Anwendungsfalls, welche sich natürlich noch erheblich verkürzen ließe.

```python
# Abfragen der Werte vom Benutzer über die Konsole
firstNumber = input("Bitte geben Sie die erste Zahl ein: ")
secondNumber = input("Bitte geben Sie die zweite Zahl ein: ")

# Konvertieren der Benutzereingaben in nutzbare Zahlenwerte
# Hier kann man Konvertierung und Rechnung auch direkt kombinieren
firstNumber = int(firstNumber)
secondNumber = int(secondNumber)

# Berechnung des Ergebnisses
result = firstNumber + secondNumber

# Ausgabe des Ergebnisses
# Hier gilt es zu beachten, dass die "print()"-Methode zwar eine Kombination aus Werten unterstützt, diese jedoch immer dem gleichen Datentyp angehören müssen. Deswegen die Konvertierung des Ergebnisses in einen String.
print("Ergebnis: " + str(result))
```

Nur damit du es schon mal gesehen hast, eine verkürzte Variante wie man sie in einem professionellen Umfeld verwenden würde, könnte zum Beispiel so aussehen:

```python
firstNumber = input("Bitte geben Sie die erste Zahl ein: ")
secondNumber = input("Bitte geben Sie die zweite Zahl ein: ")
result = int(firstNumber) + int(secondNumber)

print("Ergebnis: " + str(result))
```