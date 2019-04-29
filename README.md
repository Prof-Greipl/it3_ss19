# IT3 im SS 2019
Hier finden sie Dateien aus der IT3 Vorlesung. 

## Javascript
Dateien zum Teil Javascript finden sie im Verzeichnis  JS

#### Entwickleroptionen im Browser einschalten

`F12` in Chrome und auch in Firefox. Unerlδsslich fόr Fehlersuche und Verstδndnis!

#### Variablen-Deklaration

Variablen sind Container fόr Werte.  Variablen mόssen deklariert werden, d.h. der Name der Variable muss mit Javascript vereinbart werden. Schlόsselwort ``let``

```js
 let timerWert;
```

#### Wertzuweisung

Einer Variable, also einem Container, wird ein Wert zugewiesen. Die Variable muss einer vorhergehenden Zeile deklariert sein.

```js
 timerWert = 10;
```

#### Funktions-Deklaration

Funktionen sind ein Grundbaustein in JavaScript. Eine Funktion ist eine Prozedur - eine Reihe von Anweisungen, um eine Aufgabe auszufόhren oder eine Wert auszurechnen. Um eine Funktion zu verwenden, musse Sie vorher ebenfalls deklariert werden. Dies erfolgt mit dem Schlόsselwort `function`

```js
  function aendereNameP1() {
        let name;
        name = prompt("Neuer Name: ");
        player1.textContent = "Player 1: " + name;
    }
```
#### Funktionsaufruf

Das Definieren einer Funktion fόhrt diese noch nicht aus. Die Definition gibt der Funktion lediglich einen Namen und beschreibt was geschehen soll, wenn die Funktion aufgerufen wird. Erst der **Aufruf** ermφglicht es, die Aktionen auszufόhren.  Funktionen kφnnen in anderen Funktionen aufgerufen werden.

Beispiel fόr Funktionsaufruf:

```js
aendereName()
```

EIn spezieller Funktionsaufruf ist 

```js
console.log("Test");
```

Die Funktion darf nicht deklariert werden. Sie gibt den Text in den Klammern in der Konsole aus.



#### Zugriff auf einer Element des Dokumentenbaums (Elementreferenz)

Achtung; Die Variable muss vorher deklariert werden.

```js
  kopf = document.getElementById("header");
```

Im Html-Text muss sich ein Element mit dieser Id finden, zum Beispiel:

```hmtl
...
<div id="header"> Spielerauswahl </div></br>
<p id="p1">Player 1: Chris</p><br>
...
```
#### Eventlistener hinzufόgen

```js
player1 = document.getElementById("p1");
player1.addEventListener('click', aendereNameP1);
```

Events: 

```
click, mouseenter, mouseleave
```

#### Setzen des Textinhaltes eines Elementes

```js
player1.textContent = "Player 1: Huber";
```

#### Definieren einer Klasse fόr ein Element

```js
 player1.className = "rot";
```

Achtung: Die Klasse muss CSS Teil angegeben sein. Beispiel:

```css
.rot {
      background-color: red;
}
```


#### HTML Element erzeugen

Ein neues HTML Element wird immer als *Child* eines bereits existierenden Elementes erzeugt. Folgende Programmzeilen hängen eine neues *Child*  - in diesem Fall einene neuen li-Eintrag - an die Liste `meineListe`  an. Der Eintrag ist zuerst leer, deshalb fügen wir mit `absatz.textContent` einen Text hinzu.

```javascript
  let meineListe = document.getElementById("myList");
  let absatz = document.createElement('li');
  absatz.textContent = "Reingefahren :" + Date();
  meineListe.appendChild(absatz);
```



#### HTML Element löschen

Ein existierendes HTML Element wird immer als *Child* eines existierenden Elementes gelöscht. In nachfolgendem Beispiel ist  `myBodi` das exisitierende Element, das ein Child `meineListe` besitzt Die letzte Zeile löscht dann dieses Child. 

```javascript
let meineListe = document.getElementById("myList");
let myBodi = document.getElementById("bodi");
myBodi.removeChild(meineListe);
```



#### Attribut setzen

Mit `setAttribute` lässt sich zu einem Element ein Attribut setzten.

```javascript
let neueListe = document.createElement('ol');
neueListe.setAttribute('id', 'myList');
```


## Aufgabe zu HTML, CSS und Styles

##### 1. Erzeugen Sie eine HTML Datei, die im Browser etwa wie folgt angezeigt wird (achten sie auf Abstδnde und Textgrφίe):

![2019-04-23_17-42-47](assets/2019-04-23_17-42-47.jpg)

##### 2. Erweitern Sie die Datei um einen Javascript Anteil, so dass durch "Hineinfahren" in einen der vier Bereiche die Hintergrundfarbe dieses Bereiches auf Schwarz wechselt und der Text weiί dargestellt wird.

![2019-04-23_17-57-35](assets/2019-04-23_17-57-35.jpg)

(Situation, nachdem in die Zelle 1 "gefahren" wurde).

##### 2. Erweitern Sie die Datei so, dass eine Sekunde, nachdem eine Zelle schwarz wurde, der Originalzustand (nach Schritt 1) wieder hergestellt wird.

