# *for* ciklas

## Kam reikalingas ciklas?

- atlikti pasikartojančius darbus/logiką/procedūras
- sutaupyti kodo eilučių skaičių, nedarant `copy-paste` tos pačios logikos ar procedūrų

## Standartinis *for* ciklo formatas

Kai ciklo iteracijų kiekis nurodomas iš anksto:

```javascript
for ( let i=0; i<5; i++ ) {
    // following logic...
    console.log(i);
}
```

Kai ciklo iteracijų kiekis paaiškėja iš susijusio sąrašo ilgio:

```javascript
const array = [1, 2, 3, 5, 7, 11, 13, 17, 19, 23];

for ( let i=0; i<array.length; i++ ) {
    const item = array[i];
    // following logic...
    console.log(item);
}
```

Sudedamosios dalys ir logikos vykdimo eiga:
- ciklo iteratoriaus iniciavimas (`loop counter`)
- sąlygos patikrinimas prieš pradedant kiekvieną naują ciklo iteraciją
- logikos vykdimas
- iteratoriaus atnaujinimas

## Nestandartiniai *for* ciklo pateikimo būdai

Iškeliant iteratoriaus iniciavimo iš *for* ciklo bloko

```javascript
const array = [1, 2, 3, 5, 7, 11, 13, 17, 19, 23];

let i=0;
for ( ; i<array.length; i++ ) {
    const item = array[i];
    // following logic...
    console.log(item);
}
```

Iteratoriaus atnaujinimo įkėlimas į *for* ciklo logikos bloką

```javascript
const array = [1, 2, 3, 5, 7, 11, 13, 17, 19, 23];

for ( let i=0; i<array.length; ) {
    const item = array[i];
    // following logic...
    console.log(item);
    i++;
}
```

Sąlygos tikrinimo logikos iškėlimas iš *for* ciklo bloko

```javascript
const array = [1, 2, 3, 5, 7, 11, 13, 17, 19, 23];

function forLogic() {
    return Math.floor(Math.random() * array.length);
}

for ( let i=0; i<forLogic(); i++ ) {
    const item = array[i];
    // following logic...
    console.log(item);
}
```

## Ciklo nutraukimas

Jei ciklas neprivalo pereiti per kiekvieną sąrašo narį ar kaip kitaip išpildyti pradinę sąlygą, kuri valdo kiek kartų ciklas turėtų prasisukti ir tada norime nutraukti ciklo darbą - naudojame `break` sąlygą.

```javascript
const array = [1, 2, 3, 5, 7, 11, 13, 17, 19, 23];

for ( let i=0; i<array.length; i++ ) {
    const item = array[i];
    // following logic...
    console.log(item);

    if ( item >= 10 ) {
        console.log('Ciklas stabdomas, nes pasiekti nebe vienaženkliai pirminiai skaičiai.');
        break;
    }
}
```

## Perėjimas į sekančią ciklo iteraciją

Jei ciklo iteracijos logikos vykdimo metu paaiškėja, jog yra nebetenkinamos kažkokios norimos sąlygos, galima pereiti vykdyti sekančią iteraciją, o esamą nutraukti (peršokame į sekančią iteraciją) - naudojame `continue` sąlygą.

## Atbulinis ciklas

`i--`