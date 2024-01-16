## 1 - Scambia il contenuto di due variabili a e b, in modo che la prima contenga il valore contenuto nella seconda e viceversa:

```js
let a = "montagna";
let b = "mare";
```

- Code:

```js
let a = "montagna";
let b = "mare";
const x = a;

console.log("A: " + a);
console.log("B: " + b);

a = b;
b = x;

console.log("A: " + a);
console.log("B: " + b);
```

<hr>

## 2 - Stampa questo bellissimo alberello in console:

```
*
**
***
****
*****
******
||
```

bonus - Stampa l'albero completo:

```
     *
    ***
   *****
  *******
 *********
     |
```

- Code:

```js
const height = 6;

let lenght = height - 1;
const truncHeight = parseInt(height / 10);
let star = "*";

for (let i = 0; i < height; i++) {
  let space = "";
  for (let i = 0; i < lenght; i++) {
    space += " ";
  }
  console.log(space + star);
  star += "**";
  lenght--;
}

lenght = height - 1;
let space = "";
let trunc = "|";

for (let i = 0; i < truncHeight; i++) {
  trunc += "||";
  lenght--;
}

for (let i = 0; i < lenght; i++) {
  space += " ";
}

console.log(space + trunc);
```

<hr>

## 3 - Dato questo array di numeri crea due array, uno con tutti i numeri pari e l'altro con tutti quelli dispari

```js
const numeri = [4, 5, 3, 1, 11, 21, 23, 0, 2, 44, 19, 99, 100, 2, 3, 1];
```

- Code:

```js
const numbers = [4, 5, 3, 1, 11, 21, 23, 0, 2, 44, 19, 99, 100, 2, 3, 1];

for (let i = 0; i < numbers.length; i++) {
  let biggerIndex = i;
  let bigger = numbers[i];

  for (let n = i; n < numbers.length; n++) {
    let number = numbers[n];

    if (number > bigger) {
      bigger = number;
      biggerIndex = n;
    }
  }

  numbers.splice(biggerIndex, 1);
  numbers.unshift(bigger);
}

let evens = [];
let odds = [];

for (let i = 0; i < numbers.length; i++) {
  number = numbers[i];

  if (number % 2 == 0) {
    evens.push(number);
  } else {
    odds.push(number);
  }
}

console.table(evens);
console.table(odds);
```

<hr>

## 4 - Dato questo array di nomi ordinato in ordine alfabetico, trova la prima persona fuori posto.

```js
const nomi = ["Amelia", "Ciro", "Edoardo", "Giovanni", "Guido", "Lucia", "Marco", "Bastiano", "Ottavia", "Zeno"];
```

- Code:

```js
const nomi = ["Amelia", "Ciro", "Edoardo", "Giovanni", "Guido", "Lucia", "Marco", "Bastiano", "Ottavia", "Zeno"];

let nome;
let notFound = true;
let i = 1;

while (notFound && i < nomi.length) {
  nome = nomi[i];
  const nomePrec = nomi[i - 1];
  if (nome < nomePrec) {
    notFound = false;
  }

  i++;
}
if (notFound) {
  console.log("nessun nome fuori posto");
} else {
  console.log(nome + ", che ci fai li?");
}
```

<hr>

## 5 - Scrivi un ciclo for che stampa in console il countdown da 10 a 0, poi trasforma il ciclo for in un ciclo while.

- Code:

```js
for (let i = 10; i >= 0; i--) {
  console.log(i);
}

console.log("fine ciclo");

let n = 10;

while (n >= 0) {
  console.log(n);
  n--;
}
```

<hr>

## SuperBonus - Data una stringa contenente una frase stampane la cornicetta

```js
let frase = "il mattino ha l'oro in bocca";
```

deve stampare:

```
***********
* il      *
* mattino *
* ha      *
* l'oro   *
* in      *
* bocca   *
***********
```

- Code:

```js
let frase = "il mattino ha l'oro in bocca";

if (frase.length == 0) frase = "null";

const words = frase.split(" ");
let string = "";

let lenghts = [];

for (let i = 0; i < words.length; i++) {
  lenghts.push(words[i].length);
}

const maxWord = Math.max.apply(null, lenghts);
const maxLenght = maxWord + 4;

for (let i = 0; i < maxLenght; i++) {
  string += "*";
}

console.log(string);

for (let i = 0; i < words.length; i++) {
  let spaces = "";
  string = "* " + words[i];

  for (let i = 0; i < maxLenght - string.length - 1; i++) {
    spaces += " ";
  }

  string += spaces + "*";
  console.log(string);
}

string = "";

for (let i = 0; i < maxLenght; i++) {
  string += "*";
}
console.log(string);
```
