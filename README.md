# Zwischentest-1
Notenrechner
Programmieren Sie einen Rechner, der eine Bewertung aufgrund von gesammelten Punkten durchführt!

Aufgabe
Ihr Rechner liest abwechselnd Abgabetyp und Punkte ein und gibt als Zwischenergebnis die gesammelten Punkte pro Abgabetyp sowie die erreichbare Gesamtpunktzahl aus. Nach Abschluss der Eingabe gibt der Rechner die erreichten Punkte als konkrete Summe und als Prozentwert der erreichbaren Punkte und auch die berechnete Note aus.

Zu Beginn gibt das Programm die Punktezahl pro Abgabetyp aus (alles auf 0):


ZT Punkte: 0.00
AT Punkte: 0.00
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 0.00
Danach liest das Programm in einer Schleife wiederholt Abgabetyp und zugehörige erreichte Punkte ein. Der Abgabetyp wird als einzelnes Zeichen eingelesen. Es gibt drei unterschiedliche Abgabetypen und einen Spezialtyp zum Beenden der Eingabe:

Eingabe 'z': Zwischentest
Eingabe 'a': Abschlusstest
Eingabe 'u': Übungsbeispiel
Eingabe '=': Beendet die Eingabe
Danach liest das Programm die Punktzahl für den Abgabetyp als Fließkommawert ein (double). Pro Abgabetyp gibt es dabei folgende Regeln:

Zwischentest
Die Punktzahl für einen Zwischentest hat minimal 0 Punkte und maximal 10 Punkte. Wird ein Wert eingelesen, der außerhalb dieses Bereichs liegt, gibt das Programm "ungueltiger Bereich: min 0.00, max 10.00" aus und ignoriert die Eingabe.
Sofern eine gültige Punktzahl eingelesen wurde, zählt das Programm den eingelesenen Wert zu den gesammelten Punkte für den Zwischentest hinzu.
Nach jeder gültigen Eingabe zählt das Programm 10 Punkte zur maximal erreichbaren Gesamtpunktzahl hinzu.
Beispiel für gültige Eingaben:


ZT Punkte: 0.00
AT Punkte: 0.00
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 0.00
Typ: z

Punkte: 9.85

ZT Punkte: 9.85
AT Punkte: 0.00
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 10.00
Typ: z

Punkte: 0

ZT Punkte: 9.85
AT Punkte: 0.00
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 20.00
Typ: z

Punkte: 3

ZT Punkte: 12.85
AT Punkte: 0.00
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 30.00
Abschlusstest
Die Punktzahl für einen Abschlusstest hat minimal 0 Punkte und maximal 70 Punkte. Wird ein Wert eingelesen, der außerhalb dieses Bereichs liegt, gibt das Programm "ungueltiger Bereich: min 0.00, max 70.00" aus und ignoriert die Eingabe.
Außerdem darf es nur einen Abschlusstest geben. Wenn in einer vorherigen Eingabe bereits ein Abschlusstest eingegeben wurde, liest das Programm keine Punktzahl ein und gibt stattdessen "nur ein Abschlusstest erlaubt" aus. Andernfalls speichert das Programm die Abschlusstestpunkte.
Nach der ersten gültigen Eingabe zählt das Programm 70 Punkte zur maximal erreichbaren Gesamtpunktzahl hinzu. Dies geschieht nur einmal.
Beispiel:


ZT Punkte: 12.85
AT Punkte: 0.00
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 30.00
Typ: a

Punkte: 67.25

ZT Punkte: 12.85
AT Punkte: 67.25
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 100.00
Typ: a

Nur ein Abschlusstest erlaubt
ZT Punkte: 12.85
AT Punkte: 67.25
UE Punkte: 0.00
Erreichbare Gesamtpunkte: 100.00
Übungsbeispiel
Die Punktzahl für ein Übungsbeispiel hat minimal 0 Punkte und maximal 0.5 Punkte. Wird ein Wert eingelesen, der außerhalb dieses Bereichs liegt, gibt das Programm "ungueltiger Bereich: min 0.00, max 0.50" aus und ignoriert die Eingabe.
Sobald eine gültige Punktzahl eingelesen wurde, zählt das Programm den eingelesenen Wert zu den gesammelten Punkten für die Übungsbeispiele hinzu.
Die gesammelten Punkte für die Übungsbeispiele dürfen nicht mehr als insgesamt 10 Punkte sein. Wenn die Übungsbeispielpunkte durch eine Eingabe über 10 wachsen würden, limitiert das Programm die Punktzahl auf 10 Punkte.
Punkte aus den Übungsbeispielen bei der maximal erreichbaren Gesamtpunktzahl nicht berücksichtigt.
Beispiel:


ZT Punkte: 12.85
AT Punkte: 67.25
UE Punkte: 9.25
Erreichbare Gesamtpunkte: 100.00
Typ: u

Punkte: 0.45

ZT Punkte: 12.85
AT Punkte: 67.25
UE Punkte: 9.70
Erreichbare Gesamtpunkte: 100.00
Typ: u

Punkte: 0.5

ZT Punkte: 12.85
AT Punkte: 67.25
UE Punkte: 10.00
Erreichbare Gesamtpunkte: 100.00
Sobald '=' als Abgabetyp eingegeben wird, endet die Eingabe und das Programm berechnet die Endnote. Dies geschieht nach folgendem System:

Zuerst bildet es die Summe aus erreichten Zwischentestpunkten und Abschlusstestpunkten.
Wenn diese Summe kleiner als 55 % der erreichbaren Gesamtpunkte ist, so ist die Gesamtnote gleich 5.
Wenn diese Summe größer oder gleich 55 % der erreichbaren Gesamtpunkte ist, zählt das Programm die Punkte aus den Übungsbeispielen hinzu und berechnet die Gesamtnote nach folgendem Schema:
< 67 % der erreichbaren Gesamtpunkte -> Note 4
>= 67 % und < 78 % -> Note 3
>= 78 % und < 89 % -> Note 2
>= 89 % -> Note 1
Danach gibt das Programm die gezählten Punkte, den erreichten Prozentwert und die Note aus.

Beispiel positive Bewertung (4 Zwischentests, 1 Abschlusstest):


ZT Punkte: 34.85
AT Punkte: 42.25
UE Punkte: 9.25
Erreichbare Gesamtpunkte: 110.00
Typ: =

Gesamtpunkte absolut: 86.35
Gesamtpunkte %: 78.50 %
Note: 2
Beispiel negative Bewertung (3 Zwischentests, 1 Abschlusstest):


ZT Punkte: 3.75
AT Punkte: 43.25
UE Punkte: 9.25
Erreichbare Gesamtpunkte: 100.00
Typ: =

Gesamtpunkte absolut: 47.00
Gesamtpunkte %: 47.00 %
Note: 5
Wichtige Hinweise
Vermeiden Sie bei der Berechnung des Prozentwertes mögliche Divisionen durch 0! Wenn Die erreichbaren Gesamtpunkte gleich 0 sind, so sollen für "Gesamtpunkte %" und "Note" 0 ausgegeben werden.
Sie können davon ausgehen, dass alle Eingaben den richtigen Typ haben - Zeichen, wenn Abgabetypen erwartet werden, Zahlen, wenn Punkte erwartet werden. Die eingebenen Zeichen sind immer nur 'z', 'a', 'u', oder '='. Prüfen Sie jedoch die Wertebereiche der Punkteeingaben!
Durch Einsatz von wiederverwendbaren Funktionen können Sie sich viel duplizierten Code ersparen (z.B. Einlesen einer Zahl in einem Wertebereich, Ausgabe des Punktezwischenstands).
Verwenden Sie dieselbe Ein- und Ausgabestruktur wie im obenstehenden Beispiel, damit Sie die automatisierten Tests erfolgreich bestehen können. Der rote Text dient nur zur Hervorhebung des User Inputs im Beispiel, Sie müssen diese Färbung nicht im Programm abbilden!
Geben Sie Zeilenumbrüche immer vor einer neuen Zeile aus und nicht am Ende. Wenn Sie sich daran halten, sollte die Formatierung leichter zur Übereinstimmung mit der erwarteten Ausgabe gebracht werden können. Das Programm startet daher auch mit einem Zeilenumbruch.
In CodeRunner wird jede einzelne Eingabe von einem Zeilenumbruch bestätigt, der in der Ausgabe aber nicht sichtbar ist. Wenn Sie außerhalb von CodeRunner das Programm starten, selber Werte eingeben (siehe Beispielausgabe) und dabei Zeilenumbrüche produzieren, wirkt sich das auf die Ausgabe aus (mehr Zeilenumbrüche als beim automatischen Testen in CodeRunner).
