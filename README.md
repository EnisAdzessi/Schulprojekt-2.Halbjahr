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

Der Spieler bewegt sich in Y-Richtung durch die Variable Geschwindigkeit y und in X-Richtung durch die Variable Geschwindigkeit x. Der Spieler fällt zu Beginn des Spiels auf den Boden, da die Geschwindigkeit y durch durch die Schwerkraft verändert wird. Die Schwerkraft ist auf -1 gesetzt. Das hat zur Folge , dass bei einem Sprung als einer Erhörung der Geschwindigkeit y, die Varible konstant um -1 veringert wird. Wodruch man bei einem längeren Fall beschleunigt und zum Ende schneller fällt. Um den Spieler beim Beühren des grünen Untergrunds zu      n verwendet wird einen eigenen BLock der sich "Bewegung in Schritten", der Vorteil bei eigenen Blöcken in Scratch ist, dass man die Funktion "Run without screen refresh" nutzen kann, wodurch der Code in einem Frame abläuft und man die einzelnen Schritte nicht sieht. 

![run without screen refresh](https://user-images.githubusercontent.com/88385824/163691571-4d85f686-a2a3-49db-bdf0-0ad96c3da182.PNG)

![Repeat Schritte](https://user-images.githubusercontent.com/88385824/163691650-a56c8437-7f19-4e36-9d10-958d2f2cd01c.PNG)

Die Kontrolle wie oft der Untergrund berührt wird, passiert durch die Variable "Schritte" die so definiert ist:

![Schritte definiert 2](https://user-images.githubusercontent.com/88385824/163691745-ea5a53aa-bc12-48ca-8235-62ac47d32b84.PNG)

Durch diesen Code wird dafür gesorgt, dass der Spieler auf dem Untergrund stehen kann und nicht einsickt:

![Auf Untergrund stehen](https://user-images.githubusercontent.com/88385824/163691669-ef1f2233-aa67-49e4-8b64-3bbb83fd47e1.PNG)

Diese Blockabfolge ist essentiell für das Spiel und läuft konstant, sobald der Spieler springt und auf der Untergrund landet. 

### Springen 

Das Springen erfolgt durch das Drücken der Leertaste, Geschwindigkeit Y wird dann auf 13 gesetzt und der Spieler bewegt sich 13 Y Koordinaten nach unten. Wenn er den höchsten Punkt erreicht hat, wird er die Geschwindigkeit y um die Schwerkraft, die -1 beträgt gesenkt und der Spieler fällt, bis er den grünen Untergrund berührt. 



