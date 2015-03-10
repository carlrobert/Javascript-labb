#Strängar

En text kallas i JavaScript för en sträng (string). Man anger alltid strängar inom apostrofer, `'` även kända som enkelfnuttar. Dubbelapostrof, `"`, funkar också, men vi håller oss till enkla apostrofer.

Prova att skriva ut ditt namn i konsollen. Mitt ser ut så här:

`console.log('Jesper')`

När man jobbar direkt i konsollen kan man hoppa över `console.log()`. Så det blir faktiskt samma resultat om vi skriver `'Jesper'` direkt. 

JavaScript är bra på att räkna antalet bokstäver i en sträng. Prova genom att skriva följande:

`'Jesper'.length`

Stämmer det?

Det finns ett antal bra funktioner man kan köra på en sträng. Prova dessa.Vad händer?

```javascript
'Jesper'.toUpperCase()
'Jesper'.toLowerCase()
```

Fler strängfunktioner hittar du [här](http://www.w3schools.com/jsref/jsref_obj_string.asp)

#Variabler

En variabel är som en hink med ett namn där ett värde kan lagras. Värdet kan vara en sträng, ett tal, ett logiskt värde värde (true/false), en lista (array) eller ett objekt (som vi kommer till lite längre fram). Fördelen med att använda en variabel istället för att skriva ut värdet i klartext överallt är t.ex. att du bara behöver ändra värdet på ett ställe. I exemplet ovan kan vi använda en variabel istället:

```javascript
var name = 'Jesper';
name.toUpperCase()
name.toLowerCase()
```
Vi använder nyckelordet `var` för att deklarera variabeln.

Man kan limma ihop strängar med plustecken:

```javascript
var firstname = 'Jesper'
var lastname = 'Svensson'
firstname + lastname
```

Kan du klura ut hur du ska få ett mellanslag mellan förnamnet och efternamnet?

#Slingor

Jag vill att din kod ska skriva ut 1 till 5 genom att göra fem `console.log`-anrop. Då kan man skriva så här:

```javascript
console.log(1)
console.log(2)
console.log(3)
console.log(4)
console.log(5)
```

Hur roligt var det där då? Inte alls, eller hur? Repetitiva uppgifter är typiska grejor som vi ska låta datorn sköta. Ok? Då är det läge att använda en slinga.

Eftersom en slinga ofta behöver mer än en kodrad så är det dags att lägga koden i en fil. Häng med!

##En fil att ha koden i
Gör en mapp för dina projektfiler.

Installera [NotePad++](http://notepad-plus-plus.org/) (Windows) eller [Sublime Text](http://www.sublimetext.com/) (MacOS)

Skapa en ny fil som heter *main.js* i din mapp. Där kommer vi att ha programkoden.

Så här kan det se ut i Windows. Jag har valt att kalla mappen *Min-mapp*.

![min-mapp](https://cloud.githubusercontent.com/assets/4598641/6570440/eb70982c-c6fa-11e4-88d8-ff1e7ac2bfed.png)

```html
<!DOCTYPE html>
<html>
    <head>
	    <title>V&auml;lkommen</title>
	</head>
	<body>
	    <p>Hejhejhej!</p>
		
		<script type="text/javascript" src="main.js"></script>
	</body>
</html>
```

JavaScript-filen länkar vi in genom en *script*-tag. Jag brukar stoppa in script-taggarna precis innan den avslutande body-taggen; på det sättet kan html-innehållet visas även om inte all javascript har laddat klart. Vår script-tag ser ut så här:
```<script type="text/javascript" src="main.js"></script>```

*type* berättar att filen är av typen *text/javascript*

*src* berättar vad filen heter och var vi hittar den. I vårt fall *main.js*

##Vi kodar en slinga
En slinga funkar så här: du anger ett startvärde, ett slutvärde och hur mycket det ska räkna upp varje gång slingan körs.

I klartext: värdet börjar på 1, gör så länge värdet är mindre eller lika med 5, räkna upp värdet med ett varje gång loopen körs.  JavaScript skriver man det så här:

```javascript
// main.js
var i;
for ( i = 1; i <= 5; i += 1 ) {
   console.log('hej');
}
```

Vi ger variabeln `i` värdet 1, anger att slingan ska köras så länge `i` är mindre eller lika med 5 och till slut skriver vi `i += 1` så att för varje runda som slingan körs ska värdet av `i` ökas med ett. Det som körs för varje gång slingan körs är det som finns mellan måsvingarna, `{` och `}`.

Prova att köra koden. Dyker det upp fem stycken `hej` i konsollen?

För att skriva ut siffrorna 1 till 5 så ändrar vi `hej`:et till variabeln `i`:

```javascript
// js/main.js:
var i;
for ( i = 1; i <= 5; i += 1 ) {
   console.log(i);
}
```

Fiffigt, va?

#Om si gör så &ndash; annars ...

Ofta när man programmerar vill man göra på ett visst sätt om ett villkor uppfylls. Till exempel: om namnet är Jesper, skriv ut "Hej Jesper". I kod blir det:

```javascript
// js/main.js:
var name = 'Elvis';
if (name === 'Elvis') {
  console.log ('Hej Elvis!');
}
```

Tre likhetstecken? Varför då?
*Ett* likhetstecken använder när man ger en variabel ett värde, t.ex.
`var name = 'Jesper';` *Tre* likhetstecken ger en strikt jämförelse, och utan att gå in på mer detaljer kring det just nu &ndash; bara använd det.

Man kan också skriva ut något om jämförelsen inte lyckas, dvs:

```javascript
// js/main.js:
var name = 'Elvis';
if (name === 'Elvis') {
  console.log ('Hej Elvis');
} else {
  console.log ('Du är ju inte Elvis');
}
```

Det går också att kolla tvärtom &ndash; om något *inte* är lika med &ndash; och då använder man utropstecknet tillsammans med två likhetstecken, `!==`. Till exempel:

```javascript
// js/main.js:
var name = 'Elvisp';
if (name !== 'Elvis') {
  console.log ('Du är ju inte Elvis');
}
```

#Räkna
JavaScript &ndash; och din dator &ndash; är grymt snabba på att räkna. Prova själv!

```javascript
// js/main.js:
var varde1 = 20;
var varde2 = 7;
console.log(varde1 + varde2);
```

Prova att byta ut plustecknet mot `-`, `*`, `/` eller `%`. Just `%` ger resten vid heltalsdivision.

Man kan också slumpa fram ett numeriskt värde genom att använda `Math.random()`-funktionen. I första exemplet får vi ett slumpat värde mellan 0 och 1 och i det andra exemplet ett värde mellan 1 och 100.

```javascript
// js/main.js:
console.log(Math.random());
console.log(Math.floor((Math.random() * 100) + 1));
```

`Math.floor()` avrundar nedåt till närmaste heltal.
`Math.ceil()` avrundar uppåt till närmaste heltal.

I nästa del är det dags för funktioner!

*Baserat på http://vaxjo.coderdojo.se/experiment/javascript-del-tva/*
