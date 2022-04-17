# Informatikprojekt-2.Halbjahr: Jump 'n' Run - Spiel
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

* [Arbeitstagebuch](https://github.com/EnisAdzessi/Arbeitstagebuch-2)

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
Zu Beginn des Spiel erscheint der Spieler, ein lila Quadrat, im ersten Level. Wir nutzen als Spieler ein Quadrat, damit die der Bereich in dem der Spieler getroffen werden kann nicht extra programmieren müssen. Bei einem Menschen z.B würden die Arme abstehen und alles wäre nicht nicht in einer geraden Linie. Der Untergrund ist grün und er kann sich auf diesem nach links und rechts in  + und - X-Richtung  bewegen. Außerdem kann er durch Sprünge auch in Y- Richtung bewegt werden. Nach kurzer Zeit landet er, wie im echten Leben auch wieder auf dem Untergrund. 

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

![Level 3](https://user-images.githubusercontent.com/88385824/163714596-39d88e22-1145-4ea8-9733-e989c8e0c8ac.PNG)

#### Waffe
Der Spieler kann eine Waffe aufsammeln, mit der er den Gegnerspawner und die Gegner zerstören kann. Die Waffe erscheint nur im Level 3 und verschwindet, wenn sie vom Spieler aufgesammelt wird. Die Schussprojektile können dann mit der Taste 1 alle 0.8 Sekunden in die Richtung des Mauszeigers geschossen werden. Bei den Schussprojektilen handelt es sich um Klone, die alle 0.8 Sekeunden erstellt werden. 

![Bild Waffe](https://user-images.githubusercontent.com/88385824/163725774-41f341ef-3674-4fa2-a3f6-3169c4740df9.PNG)

![Waffe erscheinen](https://user-images.githubusercontent.com/88385824/163724855-6c8bd603-4cfe-4bc5-9cb4-dc85297eba68.PNG)

![aufgesammelt werden](https://user-images.githubusercontent.com/88385824/163724857-3f7a71e8-02dc-4cb9-bca1-8f0d14cb911e.PNG)

![Schussprojektil Klon Script](https://user-images.githubusercontent.com/88385824/163724862-2f37ed1d-85a7-4e55-af67-e3b05eb5479c.PNG)

![Klone kreien schussprojektil](https://user-images.githubusercontent.com/88385824/163724865-3886b950-35f4-4e60-9b11-d046f75a80b5.PNG)



#### Lebensbalken
Der Lebensbalken zeigt ann wie viel Leben der Gegnerspawner noch hat. Das Leben wird über die Variable "Leben" gesteuert und der Balken sowie auch der Spawner verschwinden wenn diese 0 erreicht. 

![Lebensbalke Bild](https://user-images.githubusercontent.com/88385824/163725775-4590638b-6380-403a-9b89-40adeb14e8b0.PNG)

![Leben verlieren](https://user-images.githubusercontent.com/88385824/163725581-e31882db-7589-4cad-9c76-5c9fdc49ce61.PNG)

![Lebenskostüme](https://user-images.githubusercontent.com/88385824/163725584-c18f1fec-3bc1-4948-8c1e-c0e6322f651c.PNG)

![Lebensbalken script](https://user-images.githubusercontent.com/88385824/163725585-68766422-04e4-49b3-b57a-6bc133bd5436.PNG)

#### Spawner
Der Spawner erschafft die Gegner und tut dies solange bis er zerstört wird. Das Leben des Spawners wird durch den Lebensbalken reguliert. Und der Spawner verschwindet sobald seine Leben 0 sind. Der Spieler kann den Spawner nur mit der Waffe zerstören, indem die Schussprojektile den Spawner treffen. 

![Spawner Bild](https://user-images.githubusercontent.com/88385824/163728609-2e9deb50-dcab-476b-a914-583b8be2aaf7.PNG)

![Spawner Script 1](https://user-images.githubusercontent.com/88385824/163728611-47cd526a-4f5b-41e3-9c90-96a35fc1281f.PNG)

![Spawner Script 2](https://user-images.githubusercontent.com/88385824/163728613-67844b0d-9102-481b-aa33-f34586a6ef1b.PNG)

![Spawner Script 3](https://user-images.githubusercontent.com/88385824/163728615-8a739b0a-2cb5-4f51-815d-1498274a623c.PNG)

Diese Nachricht wird vom Lebensbalken gesendet, wenn das Leben = 0 ist.

#### Gegner
Die Gegner in diesem Level sehen identisch aus zum Gegner im ersten Level. Allerdings bewegen sich diese Spieler nicht in positive und negative X-Richtung, wie der im ersten Level. Sie verschwinden sobald sie den Spieler oder die grüne Wand berühren. Außerdem handelt es sich um Klone, die kreiert werden, sofern der Spawner noch da ist. 


![Gegner erschaffen Message](https://user-images.githubusercontent.com/88385824/163730747-89a6220d-06d1-4852-9f26-2e42fce17142.PNG)

![Wenn sie als Klon starten](https://user-images.githubusercontent.com/88385824/163730749-471ca783-66ee-4ba8-8dce-d5f15de6f9c6.PNG)

![Klon löschen](https://user-images.githubusercontent.com/88385824/163730750-c803276c-08a9-40d6-8200-16d88fc195b6.PNG)

![Variable Klon 1](https://user-images.githubusercontent.com/88385824/163730751-c9be1081-3aaa-4ccf-ad7b-f04015212190.PNG)
![Variable Klon 2](https://user-images.githubusercontent.com/88385824/163730755-cf2ae833-5040-4b85-8d16-1816581b948a.PNG)


### level 4

![Level 4](https://user-images.githubusercontent.com/88385824/163731469-86f1c3c6-07e5-4101-b7de-84cabd0f3417.PNG)

#### Tür 

Wenn der Spieler die Tür berührt und den Schlüssel aus Level 5 noch nicht eingesammelt hat, kriegt er eine Nachricht, die ihm mitteilt ,dass der Schlüssel fehlt. Sollte der Spieler den Schlüssel eingesammelt haben, wird das Spiel beendet und man kommt zum Siegesmenü in dem man das Spiel neu starten kann. Bei der Tür handelt es sich um einen grünen Block, der durch den Ghosteffect allerdings nicht zu sehen ist. Dieser Block fungiert als Tür und senden die Nachrichten "Ende des Spiels" oder Schlüssel fehlt. 

![Tür](https://user-images.githubusercontent.com/88385824/163731687-a7ac3e1d-6ee8-4946-a946-4c2fb5fc4113.PNG)

![Fake Tür](https://user-images.githubusercontent.com/88385824/163731688-be5617a2-02fe-42ae-9010-feb29fc494c6.PNG)

Wie zu erkennen ist, ist dies die eigentliche Tür. Die braune Tür ist kein eigener Sprite und wird vom Spieler auch nicht erkannt. 

![Tür ghost effekt](https://user-images.githubusercontent.com/88385824/163731689-56caa960-34f3-41bb-9864-b01d5b58acbb.PNG)

![Tür schlüssel code](https://user-images.githubusercontent.com/88385824/163731690-0cc2576c-4fcc-44dd-b42f-bd89d7a15e7b.PNG)

#### Wechsel zum Level 5
Sobald der Spieler den äußersten Rand im postiver Y-Richtung erreicht wird seine Position in die niedrigste Y-Koordinate den nächsten Levels geändert, da sich das fünfte Level über dem vierten befindet. Wenn der Spieler die Y-Koordinate 185 erreicht wird die Hintergrund Variable auf 14 gesetzt, wodurch das fünfte Level ausgewählt ist. Wir wählten die Nummer 14, da wir zunächst mehrere Level machen wählten, die sich über anderen befinden, für diese Level wollten wir 10 Potenzen benutzen, also 14, 15 etc. , wir schafften allerdings nicht mehr bis zur Fertigstellung.

![Level 5 Hintergrund](https://user-images.githubusercontent.com/88385824/163733401-4ba5558f-4053-4056-a54a-37c7aebd7797.PNG)

![wechsel auf level 45](https://user-images.githubusercontent.com/88385824/163733438-7a5ccf47-ab8b-466a-bd3f-b604cc19fc88.PNG)

#### Gegner
Der Gegner funktioniert wie in Level 1.

### Level 5

![Level 5](https://user-images.githubusercontent.com/88385824/163733895-3bd0289e-0ff0-4754-90df-37fe47d44692.PNG)

#### Wechsel zum Level 4
Der Wechsel funktioniert ähnlich wie der vom Level 4 zu Level 5. 

![Wechsel 5 4](https://user-images.githubusercontent.com/88385824/163734097-32ffc8ef-3cb0-4c32-aadf-62a0dc74c876.PNG)

#### Laser
Die Laser machen dem Spieler Schaden und erscheinen für eine kurze Zeit. Der Spieler muss im richtigen Moment springen, um nicht getroffen zu werden, da die Laser sehr dem Spieler sehr Leben abziehen. Beim Betreten des level 5 sind sie nicht zu sehen und sieht erst kurz danach zu sehen, was für einen Überraschungsmoment sorgen soll. 

![Laser](https://user-images.githubusercontent.com/88385824/163734385-bf27ffd2-a348-4992-8b2f-c4de7d28e848.PNG)

![Laser Skript](https://user-images.githubusercontent.com/88385824/163734387-bfb48d8a-20bb-4f11-a3fe-2f9c60a7ac32.PNG)

![Laser Schaden an Spieler](https://user-images.githubusercontent.com/88385824/163734388-43070503-00b8-4fc8-9ad8-8d616985c6e3.PNG)

#### Lava
Die Lava ist das Finale Hindernis vor erreichen des Schlüssels. Wenn der Spieler in die Lava fällt, verliert er seine gesamten Herzen und das Spiel beginnt von vorne. Die Lava steigt und sinkt abwechselnd. Das richtige Skript für die Animation haben wir aus diesem Video https://www.youtube.com/watch?v=IbsV0SJBxm4.


![Lava](https://user-images.githubusercontent.com/88385824/163734689-cd53dd2e-270e-4f60-85bf-e5e9f2e743b8.PNG)

![Lava Animation](https://user-images.githubusercontent.com/88385824/163734690-f380bc63-dd24-428a-8b67-0225251b95a0.PNG)

#### Schlüssel
Der Schlüssel ist notwendig um durch die Tür zu kommen und das Spiel zu beenden. Sobald der Spieler den Schlüssel berührt wird dieser eingesammelt und die Schlüssel Variable wird von 0 auf 1 gesetzt. Der Spieler kann nun durch die Tür gehen und das Spiel beenden. Wenn er vom Level 4 ins Level 5 wechselt, nachdem er den Schlüsel eingesammelt hat, ist dieser nicht mehr zu sehen. 

![Schlüssel](https://user-images.githubusercontent.com/88385824/163734984-56676c83-ff2c-4507-9e45-3ae89184ac9c.PNG)

![Schlüssel Code](https://user-images.githubusercontent.com/88385824/163734985-20765c21-54e8-42d3-861f-e9954aef5bc1.PNG)

#### Siegesmenü
Wenn der Spieler den Schlüssel eingesammelt hat und durch die Tür geht hat er das Spiel geschafft. Im Siegesmenü wird ihm gratuliert und er kann das Spiel von vorne starten, indem er auf den "Spiele nochmal" klickt. Wenn der mauszeiger auf diesem befindet ändern sich dessen Farbe.

![gb3twbwz (1)](https://user-images.githubusercontent.com/88385824/163735047-a0490b74-b40c-4b12-bd9b-da3cfe7c7640.gif)

![Siegesscreen Code](https://user-images.githubusercontent.com/88385824/163735161-2977207e-f772-4867-bb4a-150ac19c8020.PNG)
