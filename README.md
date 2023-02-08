# Dynamisk web - data som objekter

Vi har tidligere arbejdet med forskellige datatyper, såsom string, number, boolean og arrays.
Arrays er "smarte" fordi de kan indeholde serier af data.

En datatype vi netop ikke har arbejdet så meget med er objekter. Objekter er gode til at definere lidt mere komplekse datastrukturer

Forestil dig, at vi for eksempel har noget data om en person. Der relaterer sig mange detaljer til personer. Det kan fx være deres for- og efternavn, deres alder, hvor de bor, hvilket husdyr de har, og hvad deres husdyr hedder. 

Et objekt som indeholder de data kunne for eksempel se sådan ud:
```js
let person = {
  firstname: "Ole",
  lastname: "Erling",
  age: 54, 
  hometown: "Roskilde", 
  pet: "Klapperslange", 
  petname: "Holger"
}
```
Ovenfor defineres en variabel "person" som indeholder et objekt. 

Et objekt defineres ved at omkranse de data som objektet indeholder med krølleparenteser. Inde i objektet defineres en række data. Data består af to halvdele, lidt lige som css. En egenskab og en værdi. Hvert sæt af egenskaber og værdier adskilles af et komma. Når man refererer til data i objektet gøres det ved at referere til objekt navnet efterfulgt af et punktum, og herefter den egenskab (property) man gerne vil have udskrevet. Værdien for den pågældnde egenskab returneres. Denne måde kaldes for "dot notation". 

```js
console.log(person.firstname) // Ole
console.log(person.lastname) // Erling
```

### Men  krølleparenteser bruges da til...
Ja, krølleparenteser bruges til forskellige ting, afhængig af hvor du er i din kode. Derfor er det er måske ikke den bedst tænkelige syntaks. Du lærer dog ret hurtigt at skelne imellem de måder krølleparenteserne bruges, og dermed til at spotte, om der er tale om en funktion, et objekt eller noget helt tredje.

## En anden måde
Du kan også referere til egenskaber i objekter med firkantparanteser `[]`. Hvis du vil bruge denne metode, skal du først skrive objekt-navnet og derefter navnet på den egenskab du vil referere til, som en string i firkant-paranteser. Denne måde kaldes for "bracket notation", og kunne for eksempel se sådan ud: 

```js
console.log(person["pet"]) // Klapperslange
console.log(person["petname"]) // Holger
```


## Opgave 1 
Opret et objekt som indeholder mindst fire forskellige egenskaber. Udskriv de fire egenskaber i konsollen en ad gangen. Brug begge syntakser til at udskrive egenskaberne med, så du får prøvet både "dot notation" og "bracket notation".

## Datatyper i objekter
I eksemplet ovenfor bruges der både strings og en enkelt number værdi (age/alder) i objektet. 
Objekter kan indeholde alle typer af værdier, sågar andre objekter. Hvis vi forestiller os objektet ovenfor, med nogle flere data-typer, kunne det fx. se sådan ud: 

```js
let person = {
  firstname: "Ole",
  lastname: "Erling",
  married: true,
  age: 54, 
  hometown: "Roskilde", 
  hobbies: ["Reptiler", "Frimærker", "Programmering"],
  pet: {
    type: "Klapperslange", 
    name: "Holger"
  },
}
```

Ovenfor er person-objektet nu udvidet med både en boolean værdi (married), et array (hobbies) og et objekt (pet).
Når vi taler om objekter indeholdt i andre objekter, kaldes de for *nestede* objekter.
Hvis du vil udskrive værdierne i fx. hobbies arrayet, kan du gøre det med fx. array-metoden `forEach`.

```js
person.hobbies.forEach(function(hobby) {
  console.log(hobby)
}
// Reptiler
// Fimærker
// Programmering
```
- og hvis du vil referere til pet-objektet, skal du `'dotte'` videre, til du når til den egenskab du gerne vil udskrive: 

```js
console.log(person.pet.type) // Klapperslange
console.log(person.pet.name) // Holger
```

## Opgave 2 
- Lav en kopi af dit objekt fra opgave 1, og udvid det, så det indeholder både booleans, arrays og objekter. 
- Lav en løkke som udskriver værdierne af dit array i konsollen.
- udskriv værdierne fra det *nestede* objekt i konsollen.

## Opgave 3
- Formålet med opgaven er at træne dynamisk generering af html på baggrund af data. Brugeren skal nu kunne se de forskellige data i browseren, og ikke kun i konsollen som i de tidligere opgaver.
- Opret et nyt data objekt, som og brug gerne alle de datatyper du kan komme i tanke om. Objektet skal indeholde *nestede objekter og arrays*. 
  Brug de forskellige data fra det nye objekt, til dynamisk at generere forskellige UI(HTML) elementer i index.html.
