# Schulprojekt-2.Halbjahr
*von Julian und Enis, 12bc* 
## Inhaltsverzeichnis

* [Programm](#Programm)

* [Aufbau des Spiels](#AufbaudesSpiels)
  * [Spielidee](#Spielidee)
  * [Grundkonzept und Steuerung](#Steuerung)
  
 
* [verschiedene Level](#verschiedeneLevel)
  * [Level 1](#Level1)
  * [Level 2](#Level2)
  * [Level 3](#Level3)
  * [Level 4](#Level4)
  * [Level 5](#Level5)
  * [Ende des Spiels](#EndedesSpiels)

* [Arbeitstagebuch]

* [Spiel] 

## Programm
![Scratchlogo svg](https://user-images.githubusercontent.com/88385822/143713115-9840c9ea-9b26-4cbf-aaf7-b0768424819b.png)
Als Programm für unser Spiel verwendeten wir, wie auch im ersten Halbjahr "Scratch", eine besonders anfänderfreundliche Programiersprache, die keine Vorkenntnisse in einer Programmiersprache vorraussetzte. Ihr Ziel ist es Neueinsteiger, besonders Kinder und Jugendliche mit den Grundkonzepten des Programmieren vertraut zu machen. Hierbei wird der Quellcode in Blöcke vereinfacht, die nach Belieben zusammengeheftet werden können. Die verschiedenen Blockarten unterscheiden sich hier in der Farbe und macht Scratch zu einer sehr visuellen und optisch ansprechenden Programmiersprache. 

## Aufbau des Spiels

### Spielidee
Bei unserem Spiel handelt es sich um ein Jump 'n' Run. Als Jump'n' Run bzeichet man Spiele, bei denen sich die Spielfigur laufen und springend fortbewegt. Ein zentrales Element des Spielprinzips stellt da das präzise Springen dar, da man so mögliches Hindernisse ausweichen kann oder bestimmte Positionen erreichen kann. Es gibt unterschiedliche Level, die sich in den Hindernisse und dem Aussehen unterscheiden. Sollte der Spieler einige Hindernisse nicht überstehen können, wird sein spielbarer Charakter besiegt und er muss das Spiel von vorne beginnen. Das Ziel ist es alle Level zu überstehen ohne besiegt zu werden.

![Level 1](https://user-images.githubusercontent.com/88385824/163688503-fa192bcc-223e-4885-a048-920bee7ddf93.PNG)

*Beispiel für ein Level*

![Hinderniss](https://user-images.githubusercontent.com/88385824/163688691-db811f89-3ade-4630-8f6f-1c627cd8ea17.PNG)

*Beispiel für ein Hindernis*

### Grundkonzept und Steuerung 
Zu Beginn des Spiel erscheint der Spieler, ein lila Quadrat, im ersten Level. Der Untergrund ist grün und er kann sich auf diesem nach links und rechts in  + und - X-Richtung  bewegen. Außerdem kann er durch Sprünge auch in Y- Richtung bewegt werden. Nach kurzer Zeit landet er, wie im echten Leben auch wieder auf dem Untergrund. 

Der Spieler bewegt sich in Y-Richtung durch die Variable Geschwindigkeit y und in X-Richtung durch die Variable Geschwindigkeit x. Der Spieler fällt zu Beginn des Spiels auf den Boden, da die Geschwindigkeit y durch durch die Schwerkraft verändert wird. Die Schwerkraft ist auf -1 gesetzt. Das hat zur Folge , dass bei einem Sprung als einer Erhörung der Geschwindigkeit y, die Varible konstant um -1 veringert wird. Wodruch man bei einem längeren Fall beschleunigt und zum Ende schneller fällt. Um den Spieler beim Berühren des grünen Untergrunds zu stoppen, verwenden wir einen eigenen Block, der sich "Bewegung in Schritten" nennt, der Vorteil bei eigenen Blöcken in Scratch ist, dass man die Funktion "Run without screen refresh" nutzen kann, wodurch der Code in einem Frame abläuft und man die einzelnen Schritte nicht sieht. 

![run without screen refresh](https://user-images.githubusercontent.com/88385824/163691571-4d85f686-a2a3-49db-bdf0-0ad96c3da182.PNG)

![Repeat Schritte](https://user-images.githubusercontent.com/88385824/163691650-a56c8437-7f19-4e36-9d10-958d2f2cd01c.PNG)

Die Kontrolle wie oft der Untergrund berührt wird, passiert durch die Variable "Schritte" die so definiert ist:

![Schritte definiert 2](https://user-images.githubusercontent.com/88385824/163691745-ea5a53aa-bc12-48ca-8235-62ac47d32b84.PNG)

Durch diesen Code wird dafür gesorgt, dass der Spieler auf dem Untergrund stehen kann und nicht einsickt:

![Auf Untergrund stehen](https://user-images.githubusercontent.com/88385824/163691669-ef1f2233-aa67-49e4-8b64-3bbb83fd47e1.PNG)

Diese Blockabfolge ist essentiell für das Spiel und läuft konstant, sobald der Spieler springt und auf der Untergrund landet. 

### Springen 

Das Springen erfolgt durch das Drücken der Leertaste, Geschwindigkeit Y wird dann auf 13 gesetzt und der Spieler bewegt sich 13 Y Koordinaten nach unten. Wenn er den höchsten Punkt erreicht hat, wird er die Geschwindigkeit y um die Schwerkraft, die -1 beträgt gesenkt und der Spieler fällt, bis er den grünen Untergrund berührt. Damit der Spieler nicht unendlich hoch springen kann, benutzen wir eine Variable, die sich Fallen nennt. Je weiter sich der Spieler vom Untergrund entfernt, desto höher wird die Variable, wenn er diesen berührt ist Fallen = 0. Wenn die Fallen Variable = 3 ist ein Sprung möglich, da der Spieler sich dann sehr nah am Boden befindet. Um das Spiel ein wenig schwieriger zu machen muss man die Leertaste jedes mal neu drücken, um zu springen. Dies passiert aufgrund der Variable Sprung Leertaste, die gleich 1 gesetzt wird wenn die Leertaste gedrückt wird. Ein Sprung ist nur dann möglich wenn diese Variable = 0 ist.


![Springen](https://user-images.githubusercontent.com/88385824/163694378-9e706e29-9153-49e8-9be5-9a77a0493b6a.PNG)

### Bewegen nach rechts und links

Der Spieler bewegt sich nach der Variable Geschwindigkeit x nach rechts und links. Um nach rechts zu gehen muss a gedrückt werden und um nach rechts zu kommen wird d gedrückt. Wenn diese gedrückt werden verändert sich die Variable um 2 oder -2, wodurch die x Koordinaten um 2 oder -2 verändert werden. 

![in pace x bewegen](https://user-images.githubusercontent.com/88385824/163694647-7501bb66-43c9-41dd-a3b1-7e4dc52fce56.PNG)

![Schritte definiert 3](https://user-images.githubusercontent.com/88385824/163694786-d834a3c2-8028-491b-a297-3a60b477100d.PNG)

Wie auch bei der Geschwindigkeit y ergibt sich die X-Koordinate, wenn nach die gesamten Distanz, die man sich bewegt durch die Anzahl der Schritte teilt.

### Herzen 
Der Spieler beginnt das Spiel mit 3 Herzen wenn er von einem beispielsweise von einem Stacheln berührt wird, verliert er ein halbes Herz. Wenn er keine Herzen mehr hat, verschwindet der Spieler per "Ghosteffect" und das Spiel wird neu gestartet. Der Spieler landet wieder im ersten Level und fällt auf den Boden. 

![volles Leben](https://user-images.githubusercontent.com/88385824/163709275-7b2d031c-6713-46d9-ae67-75d7e39b3a06.PNG)

![halbes Herz](https://user-images.githubusercontent.com/88385824/163709288-e80905b5-0a67-491b-99b1-6f1efbe2ec8d.PNG)

Die Leben des Spielers werden über die Variable Verliert leben definiert. Wenn sich dieser Variable durch das Berühren eines Hindenisses erhöht, wird das jeweilige Kostüm mit der entsprechendes Herzen ausgewählt. 

![herzen code](https://user-images.githubusercontent.com/88385824/163709369-936181cb-66e0-4afd-816b-69059124806e.PNG)

![keine leben mehr block](https://user-images.githubusercontent.com/88385824/163709376-b6da28a9-4dc7-46b4-92b1-ff9491b5c33a.PNG)

Sobald der Spieler keine Leben mehr hat, wird die "Message" "beende Spiel" "gebroadcastet", was das Spiel neu startet.

![beende Spiel](https://user-images.githubusercontent.com/88385824/163709483-f7b73587-1a97-413b-baad-ce8780aac796.PNG)

"Beginne Spiel" ist die "Message die auch ausgeführt wird, wenn man die grüne Flagge drückt. 


## verschiedene Level

### Level 1
Das Spiel beginnt im ersten Level und diesen erscheint direkt nach Drücken der grünen Flagge. Der Spieler muss auf einen grüner Block springen, hierbei muss er aufpassen, dass er den grünen Klumpen nicht berührt, da dieser ein Gegner ist und ihm Schaden macht. Außerdem sollte er nicht in die Stacheln treten, da diesem ihm auch Schaden zufügen. 

![Level 1 im Game](https://user-images.githubusercontent.com/88385824/163694980-3163cbb8-19e0-4adb-8de3-570b9ff8a9c2.PNG)

#### Grüner Block 
Der Spieler muss zu Beginn des Spiel auf diesen BLock springen, um weiter zu kommen. Der Block zeigt sich sobald "beginne Spiel" gebroadcastet wird. Wenn der Spieler zum nächsten Level übergeht verschwindet dieser wieder. 

![grüner block](https://user-images.githubusercontent.com/88385824/163710145-b5386e52-ee89-4e82-8380-01ae12af2b7d.PNG)

![beginne spiel grüner block](https://user-images.githubusercontent.com/88385824/163710149-24eb2ce6-1183-4c5d-88c2-a05db524005b.PNG)

![hide grüner block](https://user-images.githubusercontent.com/88385824/163710162-bd97fe82-6948-4e32-9699-0ad9f98b9cd7.PNG)

![grüner block code](https://user-images.githubusercontent.com/88385824/163710158-e40d8fa6-4119-4294-87b9-67770aa9ddac.PNG)

Der Code funktioniert ähnlich, wie der des grünen Bodens, wo der Spieler nach Kontakt mit dem Block zu seiner letzen X-Koordinate vor dem Kontakt gebracht wird. Auch dies passiert mit der Funktion "Run without screen refresh", wodurch man diese Schritte nicht einzeln sieht.

#### Gegner
Der Gegnern bewegt sich zwischen zwei grünen Wänden und macht dem Spieler Schaden, wenn er diesen berührt. Er setzt also die Verliert leben Variable um einen Wert. Wie auch der grüne BLock verschwindet dieser, sobald das nächste Level erreicht wird. 

![Gegner](https://user-images.githubusercontent.com/88385824/163710507-df5e40e8-e971-4db4-af00-2511d97c6d24.PNG)

![Gegner 1 show](https://user-images.githubusercontent.com/88385824/163710508-4aeb6754-2958-4e42-8329-fb762f11dae8.PNG)

![rechts links bewegen Gegner](https://user-images.githubusercontent.com/88385824/163710510-5f5de3a7-0064-4fbd-ab17-76400bbadffb.PNG)

Der Gegner berührt den Boden nicht wirklich, wodurch es dort zu keinen Problem kommt. 

![Schaden an Spieler](https://user-images.githubusercontent.com/88385824/163710511-5c5ea373-6501-4b23-a19d-d48589489b18.PNG)

![Forever loop Gegnerr](https://user-images.githubusercontent.com/88385824/163710550-06c46984-b059-4f9c-8d8c-47accfcde34e.PNG)

#### Stacheln
Bei den Stacheln handelt es sich um eine Hindernis, die dem Spieler Schaden hinzufügen, sobald er diese berührt.

![Stacheln](https://user-images.githubusercontent.com/88385824/163710925-5dfcdb56-9075-47b0-9df1-142896106db6.PNG)

![stacheln dmg an ply](https://user-images.githubusercontent.com/88385824/163710926-1ed6c55a-528a-40a4-bd72-32640e00ad8c.PNG)

![stacheln dmg block](https://user-images.githubusercontent.com/88385824/163710927-f0652ab0-a64a-4a43-b96c-6c66898a28c5.PNG)

![Aus Stacheln kommen#](https://user-images.githubusercontent.com/88385824/163710928-5cb12829-1aab-4322-a82d-b1cfb88b2162.PNG)

Damit der Spieler nicht in den Boden einsinkt, wird er bei einem Kontakt mit den Stacheln hochbewegt. Aus dieser Block funktioniert wieder mit der Funktion "Run without screen refresh".

#### Wechsel zum nächsten Level

Wenn der Spieler sich zum äußeren Rand im positiver X-Richtung befindet, dann wird wird der Hintergrund getauscht und er kann direkt weiterlaufen. Die Level sind auch so gebaut, dass er auf der gleichen Ebene bleibt und nicht plözlich in eine Wand läuft. 

![gb3twbwz](https://user-images.githubusercontent.com/88385824/163711110-a6a6ac05-7d26-470f-968c-c3e4ba2a46ee.gif)

Hierfür wird die ganze Zeit die Message "Letzte Position im Hintergrund" gebroadcastet. Diese prüft, ob die X Position des Spieler größer ist als 235, weil dies der äußerste Rand ist. Sobald dies der Fall ist wird die X Koordinate auf -235 gesetzt, damit sich der Spieler am äußersten Rand in -X-Richtung ist. Außerdem wird die Variable Hintergrund # um einen erhöhrt. Dies sorgt dafür, dass das zweite Level gezeigt wird und das erste verschwindet. 

![Letze Position im Hintergrund](https://user-images.githubusercontent.com/88385824/163711431-28f5885c-989c-44f9-aea7-9ed3cfe6e331.PNG)

![Hintergründe](https://user-images.githubusercontent.com/88385824/163711434-091af7b3-9984-4523-b0b8-b95247850d5e.PNG)

![Hintergründe Kostüme](https://user-images.githubusercontent.com/88385824/163711436-0d54c6ff-8171-4c27-b19b-1a8ed252558d.PNG)

### Level 2

![Level 2](https://user-images.githubusercontent.com/88385824/163712152-df25abe5-8ac7-4472-bb07-f4a27d574828.PNG)

#### bewegender Block 
Der Block erscheint sobald er Hiintergrund 2 erhält. er geht dann zu den Koordinaten -129/66. Er gleitet dann in 3 Sekunden zu den Koordinaten -128/21. Im Anschluss wartet er 0.7 Sekunden und gleitet dann wieder zu den Ursprungskoordinaten. 

![Block Animation](https://user-images.githubusercontent.com/88385824/163712708-c69a8ecc-91db-4c37-9db9-2046a4a321e1.PNG)

![block hintergurnd 2](https://user-images.githubusercontent.com/88385824/163712709-e1c804bd-2d2c-4c39-b519-b551a2431d50.PNG)

![bewegender block spieler+](https://user-images.githubusercontent.com/88385824/163712711-63435781-8c7b-40c4-be9c-6b52261543a7.PNG)

Es ist das gleiche Prinzip, wie bei grünen Boden und auch beim grünen Block. Das Problem ist hier allerdings das der Spieler auch auf dem Block steht, selbst wenn er der Sprung nicht richtig getimt war. 

#### Stacheln
Die Stacheln funktionieren, wie die Stacheln im ersten Level.

#### Sprungfeld
Das Sprungfeld erscheint beim Betretren des Levels und verschwindet, wenn man diesen genutzt hat. Es setzt die Geschwindigkeit y des Spielers auf 18, wodurch dieser höher springen kann, ehe er von der Schwerkraft wieder auf den Boden geholt wird. 

![Sprungfeld show](https://user-images.githubusercontent.com/88385824/163712939-208595cc-01e7-441a-8175-112f47ed6c4f.PNG)

![sprungboost message](https://user-images.githubusercontent.com/88385824/163712941-965d3959-a82f-404a-bea9-77a0857aaa2e.PNG)

![sprungboost hide](https://user-images.githubusercontent.com/88385824/163712940-3603a410-0362-465b-8e70-468cb987d9d8.PNG)

#### Aus der Karte fallen
In diesem Level kann man aus der Karte fallen fallen. Dies geschieht, wenn man nach Benutzen des Sprundfeldes nicht auf dem grünen Untergrund landet. Der Spieler dann aus der Karte und das Spiel beginnt von vorne. 


![aus der map fallen](https://user-images.githubusercontent.com/88385824/163713450-659ff703-82d7-4dc4-ac90-57d67ca750ea.PNG)

Wenn die X-Koordinate des Spielers unter -150 ist und der das zweite Level ausgewählt ist, dann verschwindet der Spieler per "Ghosteffect" und das Spiel wird neu gestartet.

### Level 3

#### Waffe

#### Lebensbalken

#### Spawner

#### Gegner

### level 4

#### Tür 

#### Wechsel zum Level 5

#### Ende des Spiels

### Level 5

#### Wechsel zum Level 4

#### Laser

#### Lava

#### Schlüssel

### Ende des Spiels

#### Siegesmenü
