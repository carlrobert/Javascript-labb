#Strängar

En text kallas i JavaScript för en sträng (string). Man anger alltid strängar inom apostrofer, `'` även kända som enkelfnuttar. Dubbelapostrof, `"`, funkar också, men vi håller oss till enkla apostrofer.

Prova att skriva ut ditt namn i konsolen. Mitt ser ut så här:

`console.log('Jesper')`

JavaScript är bra på att räkna antalet bokstäver i en sträng. Prova genom att skriva följande:

`console.log('Jesper'.length)`

Stämmer det?

Det finns ett antal bra funktioner man kan köra på en sträng. Prova dessa.Vad händer?

```javascript
console.log('Jesper'.toUpperCase())
console.log('Jesper'.toLowerCase())
```

Fler strängfunktioner hittar du [här](http://www.w3schools.com/jsref/jsref_obj_string.asp)

#Variabler

En variabel är som en hink med ett namn där ett värde kan lagras. Värdet kan vara en sträng, ett tal, ett logiskt värde värde (true/false), en lista (array) eller ett objekt (som vi kommer till lite längre fram). Fördelen med att använda en variabel istället för att skriva ut värdet i klartext överallt är t.ex. att du bara behöver ändra värdet på ett ställe. I exemplet ovan kan vi använda en variabel istället:

```javascript
var name = 'Jesper';
console.log(name.toUpperCase());
console.log(name.toLowerCase());
```
Vi använder nyckelordet `var` för att deklarera variabeln.

Man kan limma ihop strängar med plustecken:

```javascript
var firstname = 'Jesper';
var lastname = 'Svensson';
console.log(firstname + lastname);
```

Kan du klura ut hur du ska få ett mellanslag mellan förnamnet och efternamnet?

#Slingor

Jag vill att din kod ska skriva ut 1 till 5 genom att göra fem `console.log`-anrop. Då kan man skriva så här:

```javascript
console.log(1);
console.log(2);
console.log(3);
console.log(4);
console.log(5);
```

Hur roligt var det där då? Inte alls, eller hur? Repetitiva uppgifter är typiska grejor som vi ska låta datorn sköta. Ok? Då är det läge att använda en slinga.

*Baserat på http://vaxjo.coderdojo.se/experiment/javascript-del-tva/*
