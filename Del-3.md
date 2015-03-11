Med JavaScript kan du också lyssna på händelser och modifiera innehållet och utseendet i en webbsida. Det ska vi prova nu.

I din *index.html*-fil skapar du ett antal HTML-objekt efter *<body>*-taggen:

```javascript
<div id="messageDiv"></div>
<button type="button" id="pushButton">Tryck på mig!</button>
<input type="text" placeholder="Skriv ditt namn" id="nameText">
```

Det vi har skapat är en *div* (division) som är en tagg som brukar användas för att gruppera andra HTML-objekt.
*Button* är en knapp med texten *Tryck på mig!* och slutligen har vi ett inmatningsfält där man kan mata in en text.

Innan vi börjar javascripta kan vi lägga till lite css i *main.css*-filen för att styra utseende på vår sida.

```HTML
(main.css)
#messageDiv {
 border: 1px solid grey;
 padding: 20px;
 font-size: 20px;
 color: red;
 font-weight: bold;
 }
```
*#messageDiv* anger att det är ett objekt med ID:t *messageDiv* som vi stajlar till.

Nu så. Tillbaka till *main.js*-filen

För att skapa en referens till ett specifikt HTML-objekt kan det vara fiffigt att använda objektets id. 
I JavaScript ser det ut så här:

```javascript
// main.js:
var messageDiv = document.getElementById('messageDiv');
```

Här deklarerade vi en variabel *msg* som får en referens till din *div* som har ID:t *messageDiv*.
Med det på plats kan vi fylla diven med lite text, t.ex. så här:

```javascript
// js/main.js:
var messageDiv = document.getElementById('messageDiv');
messageDiv.innerHTML = 'Hej baberiba!';

// Inputfältet kan vi referera till på samma sätt:
var nameText = document.getElementById('nameText');
```

Med det gjort kan vi hämta in ett värde eller skriva ett värde:

```javascript
// main.js:
var nameText = document.getElementById('nameText');
var name = name.value; // Här hämtar vi värdet från inputfältet
nameText.value = 'Elvis Presley' // Här sätter vi värdet i inputfältet
```

Vi kanske vill lyssna på när någon trycker på knappen. Då börjar vi med att skapa en referens till knappen:

```javascript
// main.js:
var pushButton = document.getElementById(‘pushButton’);
```

Sedan lägger vi till en snutt kod som lyssnar på händelsen *click*. När klicket sker körs den koden. Ungefär så här:

```javascript
// main.js:
var pushButton = document.getElementById('pushButton');
pushButton.onclick = function () {
   alert('Klick!');
}
```

Då kan vi kombinera de tre. När knappen trycks ned ska vi visa det som står i input-fältet i messageDiv:en. Ok?

Vi börjar med att skapa en referens var till de tre HTML-objekten:

```javascript
// main.js:
var pushButton = document.getElementById(‘pushButton’);
var messageDiv = document.getElementById(‘messageDiv’);
var nameText = document.getElementById(‘nameText’);
```
 Med det på plats så ska vi lyssna på knapptrycket och hämta värdet från *nameText*-fältet som vi stoppar in i diven:

```
// main.js:
pushButton.onclick = function () {
  name = nameText.value;
  messageDiv.innerHTML = name;
}
```

Voilà!

Men om man inte skriver in något, borde vi inte kolla det?
Jovisst. JavaScript används ofta för att validera inmatningsfält.
Det kan man göra på flera sätt, men det enklaste är att kolla om längden på namnet är större än 0 
och om det inte är det så skickar vi en *alert* till användaren.

Kommer du ihåg hur vi fick ut längden på en sträng från första avsnittet? Vi kollar det i en *if-else*-sats:

```javascript
// main.js:
pushButton.onclick = function () {
  name = nameText.value;
  if (name.length > 0) {
    messageDiv.innerHTML = name;
  } else {
    alert('Glöm inte att skriva ditt namn, kompis!');
  }
}
```

Sidär. Nu har du förhoppningsvis blivit introducerad till de grundläggande begreppen i JavaScript.

I exemplet Sten, sax, påse får du lära dig mer.
Du kan också använda dina kunskaper i JavaScript för att modda Minecraft med ScriptCraft.

*Materialet är baserat på http://vaxjo.coderdojo.se/experiment/javascript-del-fyra/*
