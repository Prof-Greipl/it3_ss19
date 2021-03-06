﻿# IT3 Teil Javascript im SS 2020
Hier finden sie Dateien aus der IT3 Vorlesung. 

## Javascript
Dateien zum Teil Javascript finden sie im Verzeichnis  JS

#### Entwickleroptionen im Browser einschalten

`F12` in Chrome und auch in Firefox. Unerlässlich für Fehlersuche und Verständnis!



#### 1. Variablen-Deklaration

Variablen sind Container für Werte.  Variablen müssen deklariert werden, d.h. der Name der Variable muss mit Javascript *vereinbart* werden. 

>  Hinweis: Ohne Deklaration wird zwar kein Fehler gemeldet, aber das Verhalten ist für einen Anfänger schwer nachvollziehbar. Deshalb: immer deklarieren!

```js
 let timerWert;
```



#### 2. Wertzuweisung

Einer Variable, also einem Container, wird ein Wert zugewiesen. Die Variable muss einer vorhergehenden Zeile deklariert sein.

```js
 timerWert = 10;
```



#### 3. Funktions-Deklaration

Funktionen sind ein Grundbaustein in JavaScript. Eine Funktion ist eine Prozedur - eine Reihe von Anweisungen, um eine Aufgabe auszuführen oder eine Wert auszurechnen. Um eine Funktion zu verwenden, musse Sie vorher ebenfalls deklariert werden. Dies erfolgt mit dem Schlüsselwort `function`

```js
  function aendereNameP1() {
        let name;
        name = prompt("Neuer Name: ");
        player1.textContent = "Player 1: " + name;
    }
```


#### 4. Funktionsaufruf

Das Definieren einer Funktion führt diese noch nicht aus. Die Definition gibt der Funktion lediglich einen Namen und beschreibt was geschehen soll, wenn die Funktion aufgerufen wird. Erst der **Aufruf** ermöglicht es, die Aktionen auszuführen.  Funktionen können in anderen Funktionen aufgerufen werden.

Beispiel für Funktionsaufruf:

```js
aendereName()
```

EIn spezieller Funktionsaufruf ist 

```js
console.log("Test");
```

Diese  Funktion ist Teil von Javascript und darf/muss nicht deklariert werden. Sie gibt den Text in den Klammern  aus.



#### 5. Zugriff auf einer Element des Dokumentenbaums (Elementreferenz)

```js
  kopf = document.getElementById("header");
```

Im Html-Text muss sich ein Element mit dieser Id finden, zum Beispiel:

```html
...
<div id="header"> Spielerauswahl </div></br>
<p id="p1">Player 1: Chris</p><br>
...
```


#### 6. Eventlistener hinzufügen

```js
player1 = document.getElementById("p1");
player1.addEventListener('click', aendereNameP1);
```

Events: 

```
click, mouseenter, mouseleave
```



#### 7. Setzen des Textinhaltes eines Elementes

```js
player1.textContent = "Player 1: Huber";
```



#### 8. Definieren einer Klasse für ein Element

```js
 player1.className = "rot";
```

Achtung: Die Klasse muss CSS Teil angegeben sein. Beispiel:

```css
.rot {
      background-color: red;
}
```


#### 9. HTML Element erzeugen

Ein neues HTML Element wird immer als *Child* eines bereits existierenden Elementes erzeugt. Folgende Programmzeilen hängen eine neues *Child*  - in diesem Fall einene neuen li-Eintrag - an die Liste `meineListe`  an. Der Eintrag ist zuerst leer, deshalb fügen wir mit `absatz.textContent` einen Text hinzu.

```javascript
  let meineListe = document.getElementById("myList");
  let absatz = document.createElement('li');
  absatz.textContent = "Reingefahren :" + Date();
  meineListe.appendChild(absatz);
```



#### 10. HTML Element löschen

Ein existierendes HTML Element wird immer als *Child* eines existierenden Elementes gelöscht. In nachfolgendem Beispiel ist  `myBodi` das exisitierende Element, das ein Child `meineListe` besitzt. Die letzte Zeile löscht dieses Child. 

```javascript
let meineListe = document.getElementById("myList");
let myBodi = document.getElementById("bodi");
myBodi.removeChild(meineListe);
```



#### 11. Attribut setzen

Mit `setAttribute` lässt sich zu einem Element ein Attribut setzten.

```javascript
let neueListe = document.createElement('ol');
neueListe.setAttribute('id', 'myList');
```



#### 12. Bedingte Ausführung (if-then-else)

Einzelne Programmzeilen können in Abhängigkeit von einem logischen Ausdruck ausgeführt werden. Wenn die Bedingung `sekunden > 0` erfüllt ist (also der Wert der Variable `sekunde` ist größer 0 ist), werden die Befehle im ersten geschweiften Klammernpaar ausgeführt, andernfalls die Befehle in den geschweiften Klammern nach  `else`.

```javascript
if (sekunden > 0) 
{
  sekunden = sekunden - 1;
  element.textContent = sekunden;
  setTimeout( nachEinerSekunde, 1000);
}
else 
{
   clearInterval();
}
```

#### 13. Timer
Beispiel:
```
setTimeout( zurueck2, 1000);
```


#### 14. Wert eines Eingabefeldes lesen und setzen

Wenn im HTML-Text ein Eingabefeld mit einer `id` notiert ist, kann der aktuelle Wert des Eingabefeldes in Javascript abgerufen werden. Beispiel:

HTML:

```html
<input type="text" id="z1">
```

Javascript:

```javascript
 let feld1 = document.getElementById('z1');
 let wert  = feld1.value
```

Auchtung: Es wird immer eine Zeichkette eingelesen. Zu Umwandlung einer Zeichenkette in eine ganze Zahl wird die Funktion `parseInt()` verwendet.

Der Wert kann auch gesetzt werden:

```javascript
feld1.value = "20";
```




<br>

## Aufgabe 1 zu HTML, CSS und Styles

##### 1. Erzeugen Sie eine HTML Datei, die im Browser etwa wie folgt angezeigt wird (achten sie auf Abstδnde und Textgröße):

![2019-04-23_17-42-47](assets/2019-04-23_17-42-47.jpg)

##### 2. Erweitern Sie die Datei um einen Javascript Anteil, so dass durch "Hineinfahren" in einen der vier Bereiche die Hintergrundfarbe dieses Bereiches auf Schwarz wechselt und der Text weiß dargestellt wird.

![2019-04-23_17-57-35](assets/2019-04-23_17-57-35.jpg)

(Situation, nachdem in die Zelle 1 "gefahren" wurde).

##### 2. Erweitern Sie die Datei so, dass eine Sekunde, nachdem eine Zelle schwarz wurde, der Originalzustand der Zelle wieder hergestellt wird.

