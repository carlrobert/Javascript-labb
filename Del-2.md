Då har vi utvecklingsmiljön på plats och har gått igenom strängar, variabler, slingor, if-satser och lite matte.

Nu ska vi kika på funktioner.

En funktion är ett kodblock som körs när den anropas.
I våra exempel så här långt har vi t.ex. använt JavaScripts inbygda funktioner 
*log ()*, *toUpperCase()*, *toLowerCase()*, *random()* och *floor()*.

Låt oss göra en funktion som skickar upp en *alert* &ndash; som också är en inbyggd JavaScriptfunktion &ndash;
med ett glatt meddelande i.

```javascript
// main.js
function happyMessage() {
  alert('Ett glatt meddelande');
}
```

Om vi bara gör detta händer ingenting. Varför? Funktionen måste anropas också. Så då lägger vi till anropet som ser ut så här,
sist i *main.js*.

```javascript
// main.js
happyMessage();
```

Man kan skicka in argument till funktioner.
Ett argument är ett värde som funktionen behöver för att utföra sitt arbete. 
Vi kan i vår *happyMessage*-funktion skicka in meddelandet som vi vill visa.
Och i anropet lägger vi då till vårt meddelande istället.

```javascript
// main.js:
function happyMessage(message) {
  alert(message);
}

happyMessage('Ett glatt meddelande');
```

På så sätt kan vi använda samma funktion för att skicka fler meddelanden:

```javascript
happyMessage('Ett glatt meddelande');
happyMessage('Ett gladare meddelande');
happyMessage('Glattast meddelande');
```

En funktion kan också returnera ett värde. Det kan till exempel vara bra om man vill göra en beräkning i en funktion:

```javascript
// main.js:
function multiply (value1, value2) {
  return value1 * value2;
}
 
var result = multiply (10, 3);
console.log(result);
``` 

#Lista

En lista (array) i JavaScript kan se ut på många olika sätt. En enkel lista kan t.ex. innehålla veckodagar:

```javascript
var weekDays = ['måndag', 'tisdag', 'onsdag', 'torsdag', 'fredag', 'lördag', 'söndag'];
```

Nu innehåller variabeln *weekDays* alla veckodagar. 
För att skriva ut en veckodag anger vi vilket nummer vi vill ha. 
Vi börjar räkna på 0. 
Så *måndag* återfinns på plats 0, *torsdag* på plats 3 och *söndag* på plats 6.
För att skriva ut dem i konsollen gör vi så här:

```javascript
// main.js:
var weekDays = ['måndag', 'tisdag', 'onsdag', 'torsdag', 'fredag', 'lördag', 'söndag'];
console.log(weekDays[0]);
console.log(weekDays[3]);
console.log(weekDays[6]);
```

Vill vi skriva ut allihop kan vi med fördel använda en slinga:

```javascript
// main.js:
for (var i = 0; i <= 6; i += 1) {
  console.log (weekDays[i]);
}
```

För att slippa ändra sexan ovan om vi skulle få fler eller färre veckodagar :)
kan vi referera till längden på listan direkt istället genom

```javascript
// main.js:
for (var i = 0; i < weekDays.length; i += 1) {
  console.log(weekDays[i]);
}
```

Det var lite funktioner och lite listor. I [del 3](https://github.com/carlrobert/Javascript-labb/blob/master/Del-3.md) ska JavaScript börja snacka med HTML-dokumentet.

*Materialet är baserat på http://vaxjo.coderdojo.se/experiment/javascript-del-tre/*
