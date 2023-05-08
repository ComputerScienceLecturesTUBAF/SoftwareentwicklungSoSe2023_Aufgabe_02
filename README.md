# Softwareentwicklung SoSe2023 - Aufgabe 02

Dieses Aufgabeblatt adressiert nochmals die Grundelemente der Programmiersprache C# und wechselt dann zu objektorientierten Konzepten.

## Bearbeitungszeit

SWE: 15. Mai - 19. Mai 2023 (Mm, BWM, ROB, BAI, BGIP, BBWL, BBL, MGIN)

Einführung in SWE: 29. Mai - 9. Juni 2023 (KGB, BENG, VTC, MB)


## 1. Statische Methoden, for-each-Schleifen, Console, Sleep

Schreiben Sie ein Programm, das Zeichenketten von der Konsole einliest, sie in Morsezeichen überführt und anschließend auch visualisiert (blinkendes Konsolenfenster).

Im Repository finden Sie die Datei [MorseTable.cs](https://github.com/ComputerScienceLecturesTUBAF/SoftwareentwicklungSoSe2022_Aufgabe_02/blob/main/MorseTable.cs). Sie enthält die statische Klasse  **MorseTable**, die wiederum über die statische Methode *GetMorseCode(...)* verfügt. Damit lassen sich einzelne Zeichen (Typ char) in Zeichenketten umwandeln. Sie setzen sich aus Punkten (kurz), Strichen (lang) und Leerzeichen zusammen.

Bitte nutzen Sie, soweit möglich, foreach-Schleifen zur Iteration und legen Sie sich statische Hilfsmethoden an - z. B. *static void Flash(int delay)*, um das Terminal für eine gewisse Zeit (in Millisekunden) umzufärben. Folgende Klassen, Methoden und Eigenschaften könnten außerdem nützlich sein:

+ Methode *static void Sleep(int millisecondsTimeout)* in der Klasse **System.Threading.Thread**

+ Property *static ConsoleColor BackgroundColor* in der Klasse **System.Console**

+ Methode *static void Clear()* in der Klasse **System.Console**

## 2. Klassen, Felder, Eigenschaften, Methoden, Konstruktor

a. Analog der Aufgabe des Aufgabenblatts 00 sollen die Daten verschiedener Energiewesen:  

+ Bezeichnung,
+ Registriernummer und
+ Kategorie (THERMO, ELEKTRO oder NONE) und
+ Leistung

in einem C#-Programm verarbeitet werden.

+ Erstellen Sie dazu die Klasse Energiewesen in einer separaten Datei und definieren Sie in der Klasse zum Speichern der Daten private Datenfelder passenden Datentyps. Für die Kategorie verwenden Sie bitte eine Enumeration.

+ Um den Zugriff auf Daten von außerhalb der Klasse zu ermöglichen sind für die Datenfelder Getter- und Setter-Methoden zu erstellen (z. B. *public string GetBezeichnung()* und *public void SetBezeichnung(string bezeichnung)*).

+ Definieren Sie weiterhin zwei Konstruktoren: ein mit 4 Parametern zum Initialisieren der Datenfelder und ein ohne Parametern. Überlegen Sie auf welche Standard-Werte können die Datenfelder sinnvollerweise initialisiert werden im Konstruktor ohne Parameter.

+ Die zur Klasse gehörige *Print*-Methode soll die Daten eines Energiewesens ausgeben.

+ Eine weitere zu erstellende Klasse soll nur die Main-Methode beinhalten. Legen Sie in der Main-Methode Instanzen der Klasse Energiewesen und testen Sie die erstellten Methoden.

b. Stellen Sie die Klasse Energiewesen so um, dass statt Datenfelder und Getter- und Setter-Methoden die automatischen Properties verwendet werden.

## 3. Struct, Eigenschaften, Konstruktor, Exception

Erstellen Sie die Struktur (struct) **Size**, die zwei private Datenfelder *width* und *height* beinhaltet.

Erstellen Sie einen Konstruktor mit zwei Parametern zum Initialisieren der Datenfelder und die get- und set-Properties für beide Datenfelder.
In den set- Properties und im Konstruktor soll überpruft werden, ob die übergegenen Werte negativ sind. In disem Fall soll statt einer Initialisierung der Auswurf der **System.ArgumentException** erfolgen.

Testen Sie die Struktur in der Main-Funktion. Denken Sie daran die beim Anlegen von Instanzen bzw. Verwenden von set-Properties evtl. entstehenden Exception zu behandeln.

## 4. Nullable Types

Schreiben Sie ein Programm, das den Sperrmechanismus eines Smartphones modelliert.

+ Erstellen Sie bitte zunächst eine Klasse **Smartphone**.

+ Fügen Sie ihr ein privates Feld namens *Pin* hinzu. Es soll Integer-Zahlen speichern können, aber auch den Wert *null* zulassen, der den "Nicht-gesetzt"-Zustand repräsentiert.

+ Nach Instanziierung des Smartphones soll zunächst keine PIN gesetzt sein.

+ Fügen Sie der Smartphone-Klasse bitte eine private Methode zur Authentifizierung hinzu. Sie fragt den Benutzer nach einer PIN (wenn gesetzt), die auf der Konsole eingegeben werden soll. Wenn die PIN stimmt, gibt die Methode *true* zurück. Nach einer Fehleingabe hat der Nutzer weitere Versuche, jedoch insgesamt maximal drei. Anschließend wird das Smartphone permanent gesperrt und lässt keine Authentifizierung mehr zu. In diesem Fall gibt die Methode *false* zurück. Die richtige Eingabe der PIN (z. B. nach zwei Fehlversuchen) soll die Anzahl der Fehlversuche auf 0 zurücksetzen.

+ Verwenden Sie zum Zählen der Fehlversuche ein int-Datenfeld und zum Festhalten des Smartphonezustandes (ob gesperrt und nicht gesperrt) ein bool-Datenfeld.

+ Fügen Sie der Smartphone-Klasse eine öffentliche Methode zum Ändern der PIN hinzu. Dafür wird der Nutzer zunächst authentifiziert und darf anschließend einen neuen Wert auf der Konsole eingeben. Im Falle einer leeren Eingabe wird die PIN als "nicht gesetzt" markiert.

+ Testen Sie das Verhalten der Smartphone-Klasse in der Main-Methode. Sie können auch weitere Methoden hinzufügen, die die Authentifizierung des Benutzers erfordern.
