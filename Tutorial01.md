## Ein erstes Dreieck

Das "Hello, world!"-Pendant zu GL-Programmen ist ein einfaches Dreieck. Warum?
Weil Computergrafik-Modelle aus mehreren Dreiecken bestehen und so bereits
eine solide Basis zum Fortführen steht.

Im Falle von WebGL wird dazu eine WebGL-Instanz in einem HTML-Canvas
geladen. Zusätzlich werden sowohl ein Vertex- als auch ein Fragment-Shader
benötigt. Dabei gilt zu beachten, dass man den Code der Shader zwingend in
der HTML-Datei oder im JavaScript als String einbetten muss, solange man die
HTML-Datei lokal öffnet. Um Shader in separate Dateien auszulagern, wird eine
serverseitige Einrichtung benötigt, welche den Rahmen dieses Tutorials sprengen
würde.

Dazu benutzen Sie als Vorlage die Dateien, die sich im Ordner ``example``
befinden.

Wie läuft das Programm denn jetzt genau? Folgende Schritte werden
durchgeführt:

1. Initialisiere WebGL im gegebenen Canvas
2. Setze eine Löschfarbe (lies: Hintergrundfarbe)
3. Erstelle ein Shader-Programm und binde die Shader-Uniforms an
   JavaScript-Variablen.
4. Binde das Attribut für die Vertizen an eine JavaScript-Variable
5. Erstelle ein Puffer für die Vertizen
6. Erstelle ein Array mit gegebenen Vertizen
7. Binde den Puffer an WebGL und übergebe das Array an den Puffer

Im der Render-Funktion werden die folgenden Punkte ständig wiederholt
aufgerufen:

1. Lege Größe des Canvas fest
2. Fülle den zu zeichnenden Frame mit der vorher gesetzten Löschfarbe
3. Aktiviere das vorher erstellte Shader-Programm
4. Binde das Attribut für die Vertizen an WebGL
5. Binde den Puffer an WebGL
6. Übergebe wichtige Eigenschaften des Attributs an WebGL
7. Fülle Uniforms mit Daten
8. Zeichne Vertizen

TODO Erläuterung einzelner Punkte
