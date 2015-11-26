# Einführung in Python

> Ein Teil dieses Kapitels basiert auf dem Tutorial der Geek Girls Karotten (http://django.carrots.pl/).

Fangen wir an, schreiben wir Code!

## Der Python Prompt

Um Python zu starten, musst du an die *Konsole* deines Computers. Wie das geht weißt du bereits -- denn du hast es im Kapitel [Einführung in die Konsole](../intro_to_command_line/README.md) bereits durchgenommen.

Also öffne die Konsole, dann fangen wir an.

Wir wollen eine Python Konsole aufmachen also tippe in Winows `python` ein oder in Mac OS/Linux `python3` und drücke `enter`.

    $ python3 
    Python 3.4.3 (...) 
    Type "help", "copyright", "credits" or "license" for more information.
     >>>
    

## Dein erster Python-Befehl!

Nach Eingabe von python3 in der Konsole ändert sich das Prompt-Zeichen zu `>>>`. Für uns bedeutet das, dass wir ab nun nur mehr Python-Code eingeben können. Den Python-Prompt `>>>` musst du nicht jedesmal eingeben - dies macht Python für dich.

Wenn du die Python-Konsole wieder verlassen möchtest, gib einfach `exit()` ein oder nutze das Tastatur-Kürzel `Strg + Z` unter Windows bzw. `Strg + D` wenn du einen Mac hast oder Linux verwendest. Dann bist Du wieder in der normalen Konsole und der Python-Prompt `>>>` ist weg.

Aber jetzt wollen wir noch nicht die Python-Konsole beenden. Wir wollen mehr darüber erfahren. Fangen wir mit etwas wirklich Einfachem an. Zum Beispiel, versuche mal etwas mathematisches einzugeben, wie `2 + 3` und drücke auf `enter`.

    >>> 2 + 3 
    5
    

Cool! Schon ist das Ergebnis da. Python kann rechnen! Versuche einfach auch einige andere Befehle, wie z.B.: - `4 * 5` - `5 - 1` - `40 / 2`

Spiele ein wenig rum, dann machen wir weiter :).

Wie du siehst, kann Python richtig toll rechnen. Aber Python kann noch viel mehr ...

## Strings

Strings sind Zeichenketten. Das ist eine Folge von Buchstaben, die von Anführungszeichen umgeben sind. Gebe einfach mal deinen Namen ein (bei mir "Ola"):

    >>> "Ola"
    'Ola'
    

Nun hast du deinen ersten String erzeugt! Dies ist eine Folge von Zeichen (also nicht nur Buchstaben, wie ich oben schrieb, sondern Zeichen aller Art), die von einem Computer verarbeitet werden können. Ein String muss stets mit dem gleichen Zeichen beginnen und enden. Dies kann entweder ein einzelnes Gänsefüßchen sein (`'`) oder doppelte(`"`) (da gibt es keinen Unterschied!) Die Anführungszeichen zeigen Python nur an, dass alles innerhalb ein String ist.

Strings können zusammengesetzt werden. Versuche es einmal:

    >>> "Hi there " + "Ola"
    'Hi there Ola'
    

Du kannst Strings auch vervielfältigen:

    >>> "Ola" * 3
    'OlaOlaOla'
    

Brauchst du ein Apostroph in einem String, so hast Du zwei Möglichkeiten.

Du kannst für den String doppelte Anführungszeichen verwenden:

    >>> "Runnin' down the hill"
    "Runnin' down the hill"
    

oder du kannst den Apostroph mit einem Backslash (``) markieren:

    >>> 'Runnin\' down the hill'
    "Runnin' down the hill"
    

Toll, was? Um deinen Namen in Großbuchstaben anzuzeigen, gib einfach folgendes ein:

    >>> "Ola".upper()
    'OLA'
    

Hier hast du die `upper` **function** für deinen String verwendet! Eine Funktion (wie `upper()`) ist eine Abfolge von Anweisungen die Python ausführt, wenn die Funktion bei einem gegebenen Objekt (hier `"Ola"`) aufgerufen wird.

Nehmen wir an, du möchtest die Zahl der Buchstaben in deinem Namen wissen. Auch dafür gibt es eine Funktion!

    >>> len("Ola")
    3
    

Nun fragst du dich sicher, warum du manchmal eine Funktion mit einem `.` am Ende des Strings (wie bei `"Ola".upper()`) schreibst und manchmal eine Funktion direkt aufrufst und den String dahinter in Klammern setzt? Nun, in einigen Fällen gehören solche Funktionen, wie `upper()`, zu Objekten (hier: ein String) und funktionieren auch nur bei diesen. In solchen Fällen bezeichnen wir eine Funktion als **Methode**. In anderen Fällen sind Funktionen dagegen allgemeiner und können auf unterschiedliche Datentypen angewendet werden, wie beispielsweise `len()`. Daher übergeben wir `"Ola"` als Parameter an die `len` Funktion.

### Zusammenfassung

Ok, genug über Strings. Bisher haben wir folgendes kennengelernt:

*   **Den Prompt** - Wenn wir beim Python-Prompt Anweisungen (oder Programm-Code) in Python eingeben, dann erhalten wir auch Ergebnisse von Python
*   **Zahlen und Strings** - In Python nutzen wir Zahlen für Berechnungen und Strings für Text-Objekte
*   **Operatoren** - wie + und *, verarbeiten mehrere Werte und erzeugen als Ergebnis einen neuen Wert
*   **Funktionen** - wie upper() und len() tun was mit Objekten (in unserem Beispiel ändern sie diese, wie bei upper(), oder geben eine Eigenschaft zurück, wie bei len()).

Das sind die Grundlagen jeder Programmiersprache, die du lernen wirst. Bist du bereit für die nächste Schwierigkeitsstufe? Bestimmt!

## Fehler

Machen wir etwas Neues: Errors. Können wir die Länge einer Zahl auf die gleiche Weise ermitteln, wie die Länge eines Namens? Gib dazu `len(304023)` ein und drücke auf Enter:

    >>> len(304023)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: object of type 'int' has no len()
    

Ha, unser erster Fehler! Dieser sagt, dass Objekte von Typ "int" (Integers, das sind ganze Zahlen) keine Länge haben. Was also nun? Vielleicht sollten wir unsere Zahl als String schreiben? Denn bei Strings funktioniert es ja, wie wir wissen.

    >>> len(str(304023))
    6
    

Ja, das funktioniert! Hier haben wir die `str` Funktion innerhalb der `len` Funktion aufgerufen. `str()` konvertiert alles zu einem String.

*   Die `str` Funktion wandelt den übergebenen Wert in einen **String** um
*   Die `int` Funktion wandelt den übergebenen Wert in einen **Integer** um

> Wichtig: zwar können wir Zahlen in Text umwandeln, aber nicht immer auch Text in Zahlen - was beispielsweise sollte `int('hello')` ergeben?

## Variable

Ein wichtiger Bestandteil beim Programmieren sind Variablen. Eine Variable ist einfach ein Name für etwas, das wir später unter genau diesem Namen wieder verwenden können. Programmiererinnen nutzen Variablen um Daten zu speichern, den Code lesbar zu halten und um sich nicht immer alles merken zu müssen.

Legen wir eine Variable mit der Bezeichnung `name` an:

    >>> name = "Ola"
    

Das war es schon! Einfach name gleich Ola.

Du hast sicher schon bemerkt, dass Python diesmal kein Ergebnis zurückgegeben hat. Woher sollen wir nun wissen, dass es die Variable jetzt auch tatsächlich gibt? Zum Test geben wir `name` ein und drücken wieder auf Enter:

    >>> name
    'Ola'
    

Hurra! Deine erste Variable :)! Nun kannst du auch jederzeit ändern, was sie enthalten soll:

    >>> name = "Sonja"
    >>> name
    'Sonja'
    

Du kannst sie auch in Funktionen verwenden:

    >>> len(name)
    5
    

Das ist toll, oder? Variable können alles sein, also auch Zahlen. Versuche Folgendes:

    >>> a = 4
    >>> b = 6
    >>> a * b
    24
    

Was aber, wenn wir für eine Variable den falschen Namen verwenden? Oder uns einfach vertippen? Hast du schon eine leise Ahnung, was dann passiert? Probieren wir es aus!

    >>> city = "Tokyo"
    >>> ctiy
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'ctiy' is not defined
    

Ein Fehler! Wie du siehst, kennt Python verschiedene Arten von Fehlern. In unserem Fall hier ist es ein **NameError**. Python liefert diesen Fehler immer dann, wenn du versuchst eine Variable zu verwenden, die du nicht definiert hast, die es also noch gar nicht gibt. Wenn du einen solchen Fehler erhältst, prüfe einfach in deinem Code, ob du dich irgendwo vertippt hast.

Spiel einfach ein wenig rum und schaue, was alles so passiert.

## Die print-Funktion

Gib einmal Folgendes ein:

    >>> name = 'Maria'
    >>> name
    'Maria'
    >>> print(name)
    Maria
    

Wenn du in der zweiten Zeile `name` eintippst, dann gibt der Python-Interpreter die String-*Darstellung* (engl. 'representation') der Variable 'name' aus. In unserem Beispiel die Buchstaben M-a-r-i-a, umschlossen von einfachen Anführungszeichen ('). Wenn du hingegen `print(name)` schreibst, dann gibt Python den Inhalt der Variablen ohne die Anführungszeichen zurück, was etwas schöner aussieht.

Wie wir später sehen werden, ist `print()` auch recht nützlich, wenn wir etwas aus Funktionen heraus ausgeben möchten oder auch eine Ausgabe über mehrere Zeilen darstellen wollen.

## Listen

Außer Strings (Zeichenketten) und Integern (ganze Zahlen) hat Python noch einige andere Arten von Daten-Objekten. Von denen wollen wir uns nun **Listen** anschauen. Listen sind genau das, was du wahrscheinlich schon vermutest: Objekte, welche Listen von anderen Objekten enthalten :)

Legen wir los und erzeugen eine Liste:

    >>> []
    []
    

Ja, dies ist eine leere Liste. Für uns noch nicht sehr nützlich. Legen wir nun eine Liste von Lottozahlen an. Da wir uns nicht dauernd wiederholen wollen, ordnen wir diese Liste auch direkt einer Variablen zu:

    >>> lottery = [3, 42, 12, 19, 30, 59]
    

So, nun haben wir eine Liste mit Lottozahlen! Was aber können wir damit tun? Zuerst einmal wollen wir feststellen, wieviele Zahlen in ihr enthalten sind. Hast du schon eine Idee, wie dies geht? Klar, das weißt du ja bereits!

    >>> len(lottery)
    6
    

Genau! `len()` liefert die Anzahl von Objekten in einer Liste zurück. Praktisch, nicht wahr? Nun wollen wir die Liste sortieren:

    >>> lottery.sort()
    

Diese Anweisung gibt nichts zurück. Was passiert, ist, dass die Reihenfolge der Objekte in der Liste geändert werden. Nun wollen wir die Liste ausgeben um nachzusehen was geschehen ist:

    >>> print(lottery)
    [3, 12, 19, 30, 42, 59]
    

Wie du siehst, sind die Zahlen in der Liste nun aufsteigend sortiert. Super!

Aber vielleicht wollten wir es genau andersherum haben? Nichts leichter als das!

    >>> lottery.reverse()
    >>> print(lottery)
    [59, 42, 30, 19, 12, 3]
    

Einfach, oder? Du kannst auch etwas zu deiner Liste hinzufügen:

    >>> lottery.append(199)
    >>> print(lottery)
    [59, 42, 30, 19, 12, 3, 199]
    

Falls du nicht immer die gesamte Liste, sondern beispielsweise nur den ersten Eintrag sehen möchtest, kannst du dafür **Indices** benützen. Ein Indice (fortan verwenden wir dann die englische Bezeichnung Index) gibt die Stelle innerhalb einer Liste an, die uns interessiert. Programmierer bevorzugen es bei 0 mit dem Zählen anzufangen. Also hat das erste Objekt in deiner Liste den Index 0, das nächste die 1 und so weiter. Gib einmal Folgendes ein:

    >>> print(lottery[0])
    59
    >>> print(lottery[1])
    42
    

Wie du siehst, kannst du auf die einzelnen Objekt in deiner Liste zugreifen, indem du den Namen der Liste verwendest und anschließend den Index in eckigen Klammern anführst.

Um etwas aus deiner Liste zu löschen, musst du **Indizes** und die **del** Anweisung benutzen, wie wir es weiter oben gelernt haben (del ist eine Abkürzung für delete). Lass uns ein Beispiel versuchen und das verstärken, was wir zuvor gelernt haben; wir werden die erste Nummer aus unserer Liste löschen.

    >>> print(lottery) 
    [59, 42, 30, 19, 12, 3, 199] 
    >>> print(lottery[0]) 
    59 
    >>> del lottery[0] 
    >>> print(lottery) 
    [42, 30, 19, 12, 3, 199]
    

Das hat doch super geklappt!

Probiere einmal andere Indexe aus: 6, 7, 1000, -1, -6 oder -1000 und versuche dir das Ergebnis vorzustellen, bevor du den jeweiligen Index verwendest. Sind die Ergebnisse sinnvoll?

Eine Liste aller Methoden, die du auf Listen anwenden kannst, findest du in der Python-Dokumentation: https://docs.python.org/3/tutorial/datastructures.html

## Wörterbücher

Ein Wörterbuch (von nun an mit dem englischen Begriff 'Dictionary' bezeichnet) verhält sich ähnlich wie eine Liste, jedoch greifen wir auf die enthaltenen Objekte nicht mit einem Index, sondern mit einem Schlüssel zu (auf englisch 'key', und auch hier verwenden wir im weiteren den englischen Begriff). Ein 'key' kann ein String oder eine Zahl sein. Ein leeres Dictionary legen wir wie folgt an:

    >>> {}
    {}
    

Und schon hast du ein leeres Dictionary erstellt. Super!

Nun gib einmal Folgendes ein (verwende statt 'Ola' usw. deine eigenen Informationen):

    >>> participant = {'name': 'Ola', 'country': 'Poland', 'favorite_numbers': [7, 42, 92]}
    

Du hast nun soeben die Variable mit dem Namen `participant` angelegt, die ein Dictionary mit drei key-value Paaren enthält (values, also Werte - aber auch hier bleiben wir beim englischen Begriff - sind die Objekte in einem Dictionary):

*   Der key `name` verweist auf den value `'Ola'` (ein `String`-Objekt),
*   `country` verweist auf `'Poland'` (ebenfalls ein `String`-Objekt),
*   und `favorite_numbers` schließlich verweist auf `[7, 42, 92]` (eine `Liste` mit drei Zahlen drin).

Auf die einzelnen Objekte in einem Dictionary kannst du wie folgt zugreifen:

    >>> print(participant['name'])
    Ola
    

Also ganz ähnlich wie bei einer Liste. Aber statt dir einen Index merken zu müssen, benutzt du bei einem Dictionary einfach einen Namen (hier: den String 'name').

Was aber geschieht, wenn wir Python nach dem Wert eines keys fragen, den es gar nicht gibt? Errätst du es schon? Probieren wir es einfach aus und schauen was passiert!

    >>> participant['age']
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'age'
    

Ah, wieder ein Fehler! Diesmal ein **KeyError**. Python hilft uns auch hier und sagt uns, dass es den key `'age'` in diesem Dictionary nicht gibt.

Wenn Du zwischen Dictionaries und Listen wählen kannst, wann sollte welche Datenstruktur verwendet werden? Das ist eine gute Frage, über die es sich nachzudenken lohnt; und vielleicht möchtest Du dies kurz tun, bevor Du weiterliest.

*   Du brauchst nur eine geordnete Folge von Elementen? Dann wähle eine Liste.
*   Du brauchst eine Sammlung von Elemente, auf die du später einzeln, gezielt und effizient mit Hilfe eines Namens (d.h. keys) zugreifen kannst? Dann wähle ein Dictionary.

Dictionaries sind, so wie auch Listen, *mutable*, d. h. nachträglich veränderbar. So kannst du bei Dictionaries später noch weitere key-value Paare hinzufügen:

    >>> participant['favorite_language'] = 'Python'
    

Wie bei Listen können wir auch bei Dictionaries die `len()` Funktion verwenden, um die Zahl der enthaltenen Einträge (das sind die key-value Paare) zu ermitteln: Versuche es gleich aus und tippe dieses Kommando ein:

    >>> len(participant)
    4
    

Ich hoffe, dass das Alles für dich bisher Sinn ergibt. :) Bist du bereit für mehr Spaß mit Dictionaries? Machen wir weiter.

Zum Löschen von Elementen kannst du den `del`-Befehl (oder im englischen: statement) verwenden. Nehmen wir an, du möchtest den Eintrag mit dem key `'favorite_numbers'` entfernen:

    >>> del participant['favorite_numbers']
    >>> participant
    {'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}
    

Wie du an der Ausgabe erkennst, ist nun das key-value Paar von 'favorite_numbers' gelöscht.

Weiters kannst du auch den Wert eines bestehenden Eintrages ändern:

    >>> participant['country'] = 'Germany'
    >>> participant
    {'country': 'Germany', 'favorite_language': 'Python', 'name': 'Ola'}
    

Wie du siehst, hast du nun im key-value Paar mit dem key `'country'` den value von `'Poland'` nach `'Germany'` geändert. :) Hurra! Schon wieder was gelernt.

### Zusammenfassung

Großartig! Inzwischen hast du schon einiges über Programmierung gelernt und die folgenden Dinge sind dir vertraut:

*   **Errors** - du weißt wie sie zu lesen sind und dass Python sie dann ausgibt, wenn es eine Anweisung von dir nicht ausführen kann
*   **Variable** - sind Namen für Objekte die dir dabei helfen, deinen Code leichter zu schreiben und ihn dabei auch gut lesbar zu halten
*   **Listen** - können Objekte in einer geordnete Reihenfolge speichern
*   **Dictionaries** - speichern Objekte als key-value Paare

Schon gespannt auf den nächsten Teil? :)

## Vergleiche

Ein wichtiger Teil beim Programmieren besteht darin, Dinge zu vergleichen. Was lässt sich leicht vergleichen? Zahlen sicherlich. Schauen wir uns mal an, wie das funktioniert:

    >>> 5 > 2
    True
    >>> 3 < 1
    False
    >>> 5 > 2 * 2
    True
    >>> 1 == 1
    True
    >>> 5 != 2
    True
    

Hier haben wir Python einige Zahlen zum Vergleichen gegeben. Wie du siehst, kann Python nicht nur die Zahlen vergleichen, sondern auch die Ergebnisse von Berechnungen. Cool, nicht wahr?

Womöglich wunderst du dich aber über die beiden `==` Gleichheitszeichen zum Vergleich, ob zwei Zahlen den selben Wert haben? Ein einfaches Gleichheitszeichen `=` verwenden wir bereits, um Werte Variablen zuzuweisen. Da beim Progammieren alle Anweisungen eindeutig sein müssen, benötigst du in Python daher **stets** zwei `==` Zeichen, um Dinge auf Gleichheit zu testen. Wir können auch festsetellen, ob Werte unterschiedlich sind. Dafür verwenden wir das Symbol `!=`, wie in obigen Beispiel.

Nun noch zwei weitere Vergleiche:

    >>> 6 >= 12 / 2
    True
    >>> 3 <= 2
    False
    

`>` und `<` sind klar, was aber sollen `>=` und `<=` bedeuten? Vergleiche liest du folgendermaßen:

*   x `>` y bedeutet: x ist größer als y
*   x `<` y bedeutet: x ist kleiner als y
*   x `<=` y bedeutet: x ist kleiner oder gleich y
*   x `>=` y bedeutet: x ist größer oder gleich y

Sensationell! Lust auf mehr? Dann probier das:

    >>> 6 > 2 and 2 < 3
    True
    >>> 3 > 2 and 2 < 1
    False
    >>> 3 > 2 or 2 < 1
    True
    

Du kannst Python beliebig viele Vergleiche vornehmen lassen und wirst ein Ergebnis erhalten. Das ist wirklich cool, oder?

*   **and** - wenn du den `and`-Operator verwendest, müssen beide Vergleiche True (d.h. wahr) ergeben, damit das Gesamtergebnis auch True ist
*   **or** - wenn du den `or`-Operator verwendest, genügt es, wenn einer der beiden Vergleiche True ergibt, damit das Gesamtergebnis True ergibt

Die Redewendung "Äpfel mit Birnen zu vergleichen" hast du bestimmt schon einmal gehört. Machen wir dies doch einmal in Python:

    >>> 1 > 'django'
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: unorderable types: int() > str()
    

Unterschiedliche Dinge, hier die Datentypen Zahlen (`int`) und Strings (`str`), lassen sich auch in Python nicht miteinander vergleichen. In solch einem Fall liefert uns Python einen **TypeError** und sagt uns, dass diese Zwei Datentypen nicht miteinander vergleicht werden können.

## Boolean

Zusammen mit den Vergleichen hast du auch einen weiteren Datentyp in Python kennengelernt. Ein **Boolean** -- dies ist ein Wahrheitswert (und wir bleiben auch hier bei der englischen Bezeichnung 'boolean') und es ist zudem auch der einfachste Datentyp überhaupt.

Es gibt nur zwei boolsche Werte: - True - False (also wahr und falsch)

Damit Python diese beiden Werte versteht, musst du sie auch genau so schreiben (den ersten Buchstaben groß, alle weiteren klein). **true, TRUE, tRUE funktionieren nicht -- nur True ist korrekt.** (Dasselbe gilt natürlich auch für False.)

Boolsche Werte können auch Variable sein:

    >>> a = True
    >>> a
    True
    

Auch Folgendes geht:

    >>> a = 2 > 5
    >>> a
    False
    

Übe ein wenig, indem du mit Booleans rumspielst, zum Beispiel mit diesen Anweisungen:

*   `True and True`
*   `False and True`
*   `True or 1 == 1`
*   `1 != 2`

Glückwunsch! Booleans sind echt eine der coolsten Features beim Programmieren und du hast gerade gelernt damit umzugehen!

# Sichern!

Bisher haben wir den Python Code nur im Interpreter eingegeben, wodurch wir immer nur eine Zeile Code auf einmal ausführen konnten. Richtige Programme dagegen werden in Dateien gespeichert und, je nach Programmiersprache, durch einen **Interpreter** ausgeführt oder durch einen **Compiler** übersetzt. Unseren bisherigen Code haben wir dagegen im Python-**Interpreter** Zeile für Zeile eingegeben und einzeln ausgeführt. Für die nächsten Beispiele brauchen wir mehr als eine Zeile, daher werden wir nun:

*   Den Python Interpreter zu beenden
*   Einen Code-Editor unserer Wahl öffnen
*   Code eingeben und diesen in einer Python-Datei sichern
*   Und diesen dann laufen lassen!

Um den Python Interpreter zu beenden, nutze einfach die ~~~ exit()~~~ Funktion:

    >>> exit()
    

Nun siehst du wieder den normalen Kommandozeilen-Prompt.

Ein paar Kapitel zuvor hatten wir uns bereits einen [Code-Editor](../code_editor/README.md) ausgesucht. Diesen öffnest du nun und gibst Folgendes ein:

    python
    print('Hello, Django girls!')
    

> **Hinweis** Achte auf eines der tollsten Features von Code-Editoren: Farben! In der Python-Konsole hatte alles die gleiche Farbe. Der Code-Editor dagegen sollte dir nun die `print`-Funktion in einer anderen Farbe anzeigen als der von ihr auszugebende Text. Dies wird "Syntax Hervorhebung" genannt und ist ein wirklich sehr nützliches Werkzeug beim Coden. Die Farbe von Dingen gibt dir Hinweise wie nicht geschlossene Zeichenfolgen oder Tippfehler in einem Schlüsselwort (wie das `def` in einer Funktion, was wir weiter unten sehen werden). Dies ist einer der Gründe, warum wir Code-Editoren verwenden :)

Da du nun schon einiges an Python-Erfahrung hast, schreibe ein wenig Code mit dem, was du bislang gelernt hast.

Als nächstes wollen wir diesen Code in einer Datei mit einem aussagekräftige Namen speichern. Lass uns die Datei **python_intro.py** nennen und auf dem Desktop speichern. Wir können der Datei jeden Namen geben den wir wollen aber es ist wichtig sicherzustellen, dass die Datei auf **.py** endet. Die **.py** Erweiterung gibt unserem Betriebssystem an, dass dies eine **python executable file** ist und Python diese ausführen kann.

Nun da die Datei gesichert ist, wollen wir sie ausführen! Mit dem, was Du bisher über die Kommandozeile (das mit dem Prompt) gelernt hast, öffne nun die Konsole und **gehe in das Desktop-Verzeichnis**.

Auf einem Mac sieht das etwa so aus:

    $ cd /Users/<your_name>/Desktop
    

Unter Linux ist es ähnlich ("Desktop" könnte bei Dir allerdings "Schreibtisch" heißen):

    $ cd /home/<your_name>/Desktop
    

Nutzt Du dagegen Windows, schaut es wie folgt aus:

    > cd C:\Users\<your_name>\Desktop
    

Kommst Du hier nicht weiter, frag jemanden um Hilfe.

Benutze jetzt Python um den Code in der Datei auszuführen, ungefähr so:

    $ python3 python_intro.py 
    Hello, Django girls!
    

Prima! Du hast soeben Dein erstes Python-Programm aus einer Datei heraus ausgeführt?

Nun wollen wir uns einem wichtigen Teil der Programmierung zuwenden:

## If...elif...else

Oft sollen manche Programmteile nur ausgeführt werden, wenn bestimmt Vorbedingungen erfüllt sind. Dafür gibt es in Python sogenannte **if Anweisungen**.

Nun ändere den Code in Deiner **python_intro.py** Datei:

    python 
    if 3 > 2:
    

Wenn wir dieses nun sichern und anschließend ausführen, erhalten wir einen Fehler:

    $ python3 python_intro.py 
    File "python_intro.py", line 2   
             ^ 
    SyntaxError: unexpected EOF while parsing
    

Python erwartet hier noch weiteren Programmcode, der ausgeführt werden soll, wenn die Bedingung `3 > 2` wahr ist (also `True` ergibt). Lassen wir Python “It works!” ausgeben. Dafür ändere erneut den Code in **python_intro.py**:

    python 
    if 3 > 2:   
       print('It works!')
    

Du fragst Dich nun, warum wir die angefügte Zeile mit 4 Leerzeichen eingerückt haben? Damit teilen wir Python mit, dass dieser Code ausgeführt werden soll, wenn die vorhergehende Bedingung True ergeben hat. Du könntest auch eine andere Anzahl von Leerzeichen werden, aber Python-Programmier nutzen einheitlich 4 Leerzeichen, das sieht dann auch gut aus. Ein einzelnes `Tab` wird ebenso als 4 Leerzeichen gewertet.

Nun sichere die Datei und führe sie noch einmal aus:

    $ python3 python_intro.py 
    It works!
    

### Was passiert, wenn eine Bedingung nicht True ist?

In den vorigen Beispielen wurde Code ausgeführt, wenn eine vorhergehende Bedingung True ergab. Aber Python kennt auch `elif` und `else` Anweisungen:

    python 
    if 5 > 2:  
        print('5 is indeed greater than 2') 
    else:  
       print('5 is not greater than 2')
    

Wenn dies ausgeführt wird, wird es anzeigen:

    $ python3 python_intro.py 
    5 is indeed greater than 2
    

Wenn 2 größer als 5 wäre, würde die zweite Anweisung (die nach dem else) ausgeführt. Einfach, nicht wahr? Schauen wir uns nun an, wie `elif` funktioniert:

    python 
    name = 'Sonja' 
    if name == 'Ola': 
        print('Hey Ola!')
    elif name == 'Sonja': 
        print('Hey Sonja!') 
    else: 
        print('Hey anonymous!')
    

und ausgeführt erhalten wir:

    $ python3 python_intro.py 
    Hey Sonja!
    

Hast du bemerkt was passiert ist? `elif` lässt dich zusätzliche Bedingungen hinzufügen, die ablaufen falls die vorherige fehlschlägt.

Du kannst so viele `elif` Bedingungen nach der anfänglichen `if` Anweisung hinzufügen wie du magst. Zum Beispiel:

    python 
    volume = 57 
    if volume < 20:
         print("It's kinda quiet.") 
    elif 20 <= volume < 40:
         print("It's nice for background music") 
    elif 40 <= volume < 60:
         print("Perfect, I can hear all the details") 
    elif 60 <= volume < 80:
         print("Nice for parties") 
    elif 80 <= volume < 100:
         print("A bit loud!") 
    else:
         print("My ears are hurting! :(")
    

Python läuft durch jeden Test in Reihe und gibt aus:

    $ python3 python_intro.py 
    Perfect, I can hear all the details
    

### Zusammenfassung

In den letzten drei Übungen hast Du gelernt:

*   **Vergleiche vorzunehmen** - in Python kannst Du Vergleiche mit den folgenden Operatoren `>`, `>=`, `==`, `<=`, `<` sowie `and` und `or` vornehmen
*   **Boolsche Datentypen** zu verwenden - Dies sind Objekte, die nur zwei Werte annehmen können: `True` bzw. `False`
*   **Dateien zu speichern** - also Programmcode in Dateien abzulegen, so dass Du auch umfangreichere Programme schreiben kannst.
*   **if...elif...else** - Anweisungen zu verwenden, so dass nur bestimmt Programmteile ausgeführt werden.

Und nun zum letzten Kapitel!

## Deine eigenen Funktionen!

Erinnerst Du Dich an Funktionen wie `len()`, die Du in Python aufrufen kannst? Genau sowas kannst Du auch selbst schreiben, und das schauen wir uns nun an!

Eine Funktion ist eine Folge von Anweisungen, die Python ausführen soll. Jede Funktion beginnt mit dem Keyword (auf deutsch 'Schlüsselwort', aber diese Übersetzung ist nicht gebräuchlich) `def`, gefolgt von einem Funktionsnamen und Parametern. Aber nicht alle Funktionen brauchen Parameter. Beginnen wir mit einem einfachen Beispiel ohne Parameter. Ändere den Code in der Datei **python_intro.py** wie folgt:

    python 
    def hi():
         print('Hi there!')
         print('How are you?')
    
    hi()
    

Und schon hast Du Deine erste Funktion erstellt!

Nun magst Du Dich fragen, warum wir am Ende der Datei den Namen der Funktion ein weiteres mal geschrieben haben. Python liest die Datei und führt sie von oben nach unten aus. Um die Funktion also auch zu benutzen, müssen wir sie noch einmal unten hinschreiben.

Schauen wir, was passiert wenn wir die Datei ausführen:

    $ python3 python_intro.py 
    Hi there! How are you?
    

Das war einfach! Als nächsten bauen wir Funktionen mit sogenannten Parametern. Wir werden das gerade gebaute Beispiel benutzen - eine Funktion die die ausführende Person begrüßt - aber diesmal mit Namen:

    python 
    def hi(name):
    

Wie du siehst geben wir der Funktion jetzt einen Parameter, den wir `name` nennen:

    python 
    def hi(name):
          if name == 'Ola':
                print('Hi Ola!')     
          elif name == 'Sonja':
                print('Hi Sonja!')     
          else:
                print('Hi anonymous!') hi()
    

Denk daran: Die `print` Funktion ist 4 Leerzeichen innerhalb der `if` Anweisung eingerückt. Dies liegt daran, dass die Funktion ausgeführt wird wenn die Bedingung eintrifft. Mal sehen, wie das jetzt funktioniert:

    $ python3 python_intro.py 
    Traceback (most recent call last): 
    File "python_intro.py", line 10, in <module>
       hi() 
    TypeError: hi() missing 1 required positional argument: 'name'
    

Hoppla, ein Fehler. Zum Glück gibt uns Python eine recht nützliche Fehlermeldung. Diese besagt, dass die Funktion `hi()` (welche wir definiert haben) ein erforderliches Argument hat ( genannt `name`) und dass wir vergessen haben, dieses zu übermitteln als wir die Funktion aufriefen. Lass uns das am unteren Ende der Datei schnell beheben:

    python 
    hi("Ola")
    

Und führen Sie es erneut aus:

    $ python3 python_intro.py 
    Hi Ola!
    

Und wenn wir den Namen ändern?

    python 
    hi("Sonja")
    

Und führe es aus:

    $ python3 python_intro.py 
    Hi Sonja!
    

Nun, was denkst du wird passieren wenn du einen anderen Namen dort hinein schreibst? (Nicht Ola oder Sonja) Probiere es aus und schau ob du richtig liegst. Es sollte das Folgende ausgeben:

    Hi Anonymer!
    

Das ist genial, richtig? Auf diese Weise musst du dich nicht jedesmal wiederholen wenn du den Namen der Person änderst, die die Funktion grüßen soll. Und dies ist genau warum wir Funktionen brauchen - du willst ja niemals deinen Code wiederholen!

Lass uns etwas klügeres machen -- Es gibt mehr Namen als nur 2 und für jeden eine Bedingung zu schreiben wäre recht schwierig, richtig?

    python 
    def hi(name):
         print('Hi ' + name + '!') 
    
    hi("Rachel")
    

Lass uns den Code aufrufen:

    $ python3 python_intro.py 
    Hi Rachel!
    

Herzlichen Glückwunsch! Du hast gerade gelernt, wie du Funktionen schreibst! :)

## Schleifen

Dies ist bereits der letzte Teil. Das ging doch schnell, richtig? :)

Programmierer wiederholen sich nicht gerne. Beim Programmieren geht es darum Dinge zu automatisieren, so dass wir nicht jede Person mit ihrem Namen manuell grüßen müssen, richtig? Dies ist der Punkt an dem Schleifen nützlich werden.

Eriinerst du dich noch an Listen? Lass uns eine Liste mit Mädchen machen:

    python 
    girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
    

Wir wollen alle mit ihrem Namen grüßen. Wir besitzen bereits die `hi` Funktion um dies zu tun, also las sie uns in einer Schleife verwenden:

    python 
    for name in girls:
    

Die ~ ~ ~ for ~ ~ ~ Anweisung verhält sich ähnlich der ~ ~ ~ if~ ~ ~ Anweisung; Code unter beiden muss 4 Leerzeichen eingerückt werden.

Hier ist der vollständige Code, der in der Datei sein wird:

    python 
    def hi(name):
         print('Hi ' + name + '!') 
    
    girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You'] 
    for name in girls:
         hi(name)
         print('Next girl')
    

Und wenn wir es ausführen:

    $ python3 python_intro.py
    Hi Rachel!
    Next girl
    Hi Monica!
    Next girl
    Hi Phoebe!
    Next girl
    Hi Ola!
    Next girl
    Hi You!
    Next girl
    

Wie du sehen kannst, wird Alles, dass du innerhalb einer `for` Anweisung eingerückt einsetzt, für jedes Element der Liste `girls` wiederholt.

Du kannst auch `for` auf Nummern beziehen wenn du die `range` Funktion benutzt:

    for i in range(1, 6):
         print(i)
    

Das würde ausgeben:

    1 
    2 
    3 
    4 
    5
    

`range` ist eine Funktion, die eine Liste von Nummer (eine nach der anderen) erschafft (die Nummern werden von dir als Parameter bereitgestellt).

Merke, dass die zweite dieser zwei Nummern nicht in der Liste enthalten ist, die von Python ausgegeben wird (bedeutet, dass `range(1, 6)` von 1 bis 5 zählt aber nicht die Nummer 6 enthält). Die liegt daran, weil "range" halb offen ist was widerum bedeutet, dass es den ersten Wert enthält aber nicht den letzten.

## Zusammenfassung

Das ist alles. **You totally rock!** Das war ein heikles Kapitel darum solltest du jetzt stolz auf dich sein. Wir sind definitiv stolz auf dich, dass du es so weit geschafft hast!

Du möchtest jetzt vielleicht kurz etwas anderes tun - stretchen, etwas herumlaufen, deine Augen ausruhen - bevor es wetier zum nächsten Kapitel geht. :)

![Cupcake](images/cupcake.png)

