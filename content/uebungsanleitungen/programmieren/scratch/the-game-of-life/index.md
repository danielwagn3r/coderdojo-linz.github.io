---
title: "The Game of Life"
description: "Erwecke Zellen zum Leben."
type: "uebungsanleitungen/programmieren/scratch"
img: "img/the-game-of-life.png"
imgposition: "center bottom"
level: 3
version: 3
sprites: 2
scripts: 21
data: 20
aliases:
- /trainingsanleitungen/scratch/scratch-the-game-of-life-v3.html
- /trainingsanleitungen/scratch/scratch-the-game-of-life.html
---

{{< imgblock "img/the-game-of-life.png" "The game of life" >}}
Die Idee zu „The Game Of Life“ geht auf den Mathematiker John Conway zurück. Das Spielfeld besteht aus einem großen Raster von Zellen, die zwei Zustände haben können: „tot“ (weiß) oder „lebendig“ (farbig). Basierend auf dem Zustand des Rasters wird die nächste Generation von Zellen berechnet, und zwar nach folgenden Regeln:

* Eine tote Zelle mit genau drei lebenden Nachbarn wird neu geboren
* Lebende Zellen mit weniger als zwei lebenden Nachbarn sterben an Einsamkeit
* Lebende Zellen mit zwei oder drei lebenden Nachbarn bleiben am Leben
* Lebende Zellen mit mehr als drei lebenden Nachbarn sterben an Überbevölkerung

Durch diese einfachen Regeln können aus bestimmten Anfangsmustern komplexe Strukturen entstehen. Es gibt stabile Muster, oszillierende Objekte wie Pulsare oder sogar Raumschiffe. Wer weiß, vielleicht entsteht auf deinem Raster irgendwann eine neue künstliche Lebensform? Durch Klick in das Grid wird das vorausgewählte Muster angelegt.
{{< /imgblock >}}

Du kannst das fertige Spiel unter [https://scratch.mit.edu/projects/303836690/](https://scratch.mit.edu/projects/303836690/) auch gleich ausprobieren.

Das Spiel besteht aus 2 Figuren und 21 Skripten.

## Die Figuren und Skripte

{{< imgblock "img/figuren.png" "Figuren" >}}
Wir benötigen nur zwei Figuren namens „Selection“ und „Grid“. Selection dient der Anzeige eines einfachen Befehlsmenüs im unteren Bereich. Grid ist unser Spielfeld, das sich fortlaufend selbst neu zeichnet.
{{< /imgblock >}}

## Die Figur Selection

{{< imgblock "img/kostueme-selection.png" "Kostüme Selection" >}}
Für die Figur Selection benötigen wir sechs Kostüme für die sechs Kommandos, die man via Mausklick ausführen kann. Verwende dazu das Textwerkzeug, und schreibe die Namen der Kommandos wie oben angegeben in das Zeichenfeld. Setze den Drehpunkt der Kostüme jeweils in das linke untere Eck des Textbereichs. Wähle den Textbereich nicht zu groß, damit die Befehle nebeneinander Platz haben. Eine Höhe von etwa 20 Pixeln geht sich gut aus. Alternativ kannst du die Figur ohne Skripte auch hier herunterladen und in dein Projekt importieren:

[Selection.sprite2](Selection.sprite2)
{{< /imgblock >}}

{{< imgblock "img/skripte-selection.png" "Skripte Selection" 8 >}}
Die Skripte von Selection sind relativ einfach. Sie dienen dazu die Menükommandos zu zeichnen, und bei Mausklick entsprechende Nachrichten an das Grid zu senden:
{{< /imgblock >}}

## Die Figur Grid

{{< imgblock "img/daten-grid.png" "Daten Grid" 4 >}}
Hier ist das eigentliche Spiel implementiert. Das Grid zeichnet sich mit dem Malstift selbst, daher hat es nur ein leeres Kostüm:
Nun können wir die Variablen anlegen. Bitte erstelle alle Variablen für „Nur für diese Figur“, also für die Figur Grid:
{{< /imgblock >}}

Jetzt müssen wir das Grid noch programmieren. Wir beginnen mit Funktionsblöcken, die wir später im Hauptprogramm benötigen werden.

{{< imgblock "img/neue-funktion.png" "Neue Funktion anelgen" >}}
InsertPattern dient dem Einfügen von Mustern in das Grid. Wichtig: Selektiere bei allen Blöcken „Ohne Bildschirmaktualisierung laufen lassen“, sonst ist das Programm zu langsam.
{{< /imgblock >}}

{{< imgblock "img/funktion-insert-pattern.png" "Funktion InsertPattern" >}}{{< /imgblock >}}

In CalcNextGeneration wird die nächste Generation von Zellen berechnet:
{{< imgblock "img/funktion-calculate-next-generation.png" "Funktion CalcNextGeneration" >}}{{< /imgblock >}}

Paint dient dem Zeichnen des Grids mit dem Malstift. In InitGrid wird das Grid leer befüllt:
{{< imgblock "img/funktion-paint-and-init-grid.png" "Funktionen Paint und InitGrid" >}}{{< /imgblock >}}

Nun folgt das Hauptprogramm, das zuerst alle Variablen initialisiert, und dann in einer Hauptschleife die Neuberechnung und das Zeichnen des Grids aufruft. Außerdem wird abgefragt, ob neue Muster einzufügen sind.

{{< imgblock "img/skripte-grid-1.png" "Skripte Grid" >}}{{< /imgblock >}}

Zuguterletzt benötigen wir noch einige Funktionen zur Nachrichtenbehandlung:

{{< imgblock "img/skripte-grid-2.png" "Skripte Grid" >}}{{< /imgblock >}}

Wie du siehst definieren wir hier die beiden großen Muster GliderGun und Pulsar. Wie das Grid selbst bestehen sie aus einer langen Zeichenkette von 0en und 1en – so lange, dass man sie gar nicht in einer Zeile drucken kann. Daher hier nochmal zum Abtippen oder Kopieren aus dem Internet:

GliderGun:

```shell
000000000000000000000000100000000000
000000000000000000000010100000000000
000000000000110000001100000000000000
000000000001000100001100000000000011
110000000010000010001100000000000011
110000000010001011000010100000000000
000000000010000010000000100000000000
000000000001000100000000000000000000
000000000000110000000000000000000000
```

Pulsar:
```shell
0011100011100
0000000000000
1000010100001
1000010100001
1000010100001
0011100011100
0000000000000
0011100011100
1000010100001
1000010100001
1000010100001
0000000000000
0011100011100
```

## Ausprobieren

Du kannst das fertige Projekt unter [https://scratch.mit.edu/projects/303836690/](https://scratch.mit.edu/projects/303836690/) ausprobieren.

Eine andere Variante unter [https://scratch.mit.edu/projects/96326891](https://scratch.mit.edu/projects/96326891) wurde weiter verbessert, und berechnet bzw. zeichnet ein Grid mit hundertfacher Zellenanzahl in zehnfacher Geschwindigkeit (Gesamt-Speedup = 1000). Das wird erreicht, indem das Programm sich merkt welche Zellen zuletzt verändert wurden, und welche Nachbarzellen neu berechnet werden müssen. Weiters werden 65536 Zellengruppen-Veränderungen zu Beginn einmal vorberechnet, und müssen dann nicht jedesmal neu kalkuliert werden. Und das Grid wird nicht als Zeichenkette gespeichert, sondern als Liste von Zahlen, wobei eine Zahl gleich mehrere Zellen beinhaltet.

Die Skripte werden dadurch allerdings auch etwas komplizierter. Solche Geschwindigkeitsverbesserungen sind eine wichtige Aufgabe in der Software-Entwicklung. 
