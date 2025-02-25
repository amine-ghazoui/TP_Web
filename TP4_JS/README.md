# JavaScript Lab - Introduction to JavaScript

This repository contains solutions to JavaScript exercises as part of an introductory lab. The exercises cover basic concepts such as variables, loops, functions, and control structures.

---

## Exercise 1: Temperature Conversion

**Objective**: Convert a temperature from Fahrenheit to Celsius using the formula `tempC = (5/9) * (tempF - 32)`.

**Function**:
- Takes a temperature in Fahrenheit as input.
- Calculates the temperature in Celsius.
- Displays the result rounded to one decimal place.

```javascript
function degreC(tempF){
            let tempC = (5 / 9) * (tempF-32)
            console.log(`Une température en Fahrenheit : ${tempF}`);
            console.log(`cette température équivaut à ${tempC.toFixed(1)} degrés Celsius`);
}
```
---

## Exercise 2: Time Conversion

**Objective**: Convert a number of seconds into days, hours, minutes, and seconds.

**Function**:
- Takes a number of seconds as input.
- Calculates the equivalent days, hours, minutes, and seconds.
- Displays the converted time..

```javascript
function hjms(nbrSeconds){
            let jours = Math.floor(nbrSeconds / (24 * 3600));
            nbrSeconds %= 24 * 3600;
            let heures = Math.floor(nbrSeconds / 3600);
            nbrSeconds %= 3600;
            let minutes = Math.floor(nbrSeconds / 60);
            let secondes = nbrSeconds % 60;
            
            console.log(`Une durée en secondes : ${secondes}`);
            console.log(`Cette durée équivaut à ${jours} jours, ${heures} heures, ${minutes} minutes, et ${secondes} secondes`);

}
```
---

## Exercise 2-bis: Improved Time Conversion

**Objective**: Enhance the previous function to skip zero values and handle singular/plural units.

**Function**:
- Adds logic to ignore zero values.
- Displays units in singular if the value is 1.
- Formats the output for better readability.

```javascript
function hjms_2bis(nbrSeconds){
            let jours = Math.floor(nbrSeconds / (24 * 3600));
            let reste = nbrSeconds % (24 * 3600);
            let heures = Math.floor(reste / 3600);
            reste %= 3600;
            let minutes = Math.floor(reste / 60);
            let secondes = reste % 60;

            let parties = [];

            if(jours > 0){
                parties.push(`${jours} jour${jours > 1 ? 's' : ''}`);
            }

            if(heures > 0){
                parties.push(`${heures} heure${heures > 1 ? 's' : ''}`);
            }

            if(minutes > 0){
                parties.push(`${minutes} minute${minutes > 1 ? 's' : ''}`);
            }

            if(minutes > 0){
                parties.push(`${secondes} seconde${secondes > 1 ? 's' : ''}`);
            }

            let duree = parties.join(' ');

            console.log(`Une durée en secondes : ${secondes}`);
            console.log(`Cette durée équivaut à ${duree}`);

}
```
---

## Exercise 3: Sorting Three Numbers

**Objective**: Sort three numbers in ascending order.

**Function**:
- Takes three numbers as input.
- Sorts them using the `sort` method.
- Displays the sorted numbers.

```javascript
function troisNombres(a, b, c){
            let tableau = [a, b, c];

            tableau.sort(function(x, y) {
                return x-y;
            })
            console.log("Les nombres dans l'ordre croissant sont : " + tableau.join(" "));
}
```
---

## Exercise 4: Pattern Display - Stairs

**Objective**: Display a triangular pattern using `while` and `for` loops.

**Function**:
- Takes a size as input.
- Uses loops to generate the pattern.
- Displays the pattern line by line.

```javascript
function triangle1(taille){
            let ligne = 1; 
            while (ligne <= taille){
                let etoiles = "";
                let compteur = 1;
                while (compteur <= ligne){
                    etoiles += "*";
                    compteur++;
                }

                console.log(etoiles);
                ligne++;
            }
}
```
---

## Exercise 4-bis: Pattern Display - Pyramid

**Objective**: Display a pyramid pattern.

**Function**:
- Takes a size as input.
- Uses loops to generate spaces and stars.
- Displays the pyramid line by line.

```javascript
function pyramide(taille){
            for (let i = 1; i <= taille; i++){
                let espaces = "";

                for (let e = 1; e <= (taille - i); e++){
                    espaces += " ";
                }

                let etoiles = "";
                for (let s = 1; s <= (2 * i - 1); s++){
                    etoiles += "*";
                }

                console.log(espaces + etoiles);
            }
}
```
---

## Exercise 5: Prime Number Check

**Objective**: Check if a number is prime.

**Function**:
- Takes a number as input.
- Checks if it is divisible by any number other than 1 and itself.
- Displays whether the number is prime or not.

```javascript
function Premier(n) {

            if (n < 2){
                console.log(`${n} n'est pas un entier positif > 1`);
                return false;
            }

            for (let i = 2; i <= Math.sqrt(n); i++){
                if (n % i === 0) {
                    console.log(`${n} n'est pas premier, il est divisible par ${i}`);
                    return false;
                }
            }

            console.log(`${n} est premier`);
            return true;
}
```
---

## Exercise 6: Fibonacci Sequence

**Objective**: Calculate the n-th term of the Fibonacci sequence.

**Function**:
- Takes an integer `n` as input.
- Calculates the corresponding term using a loop.
- Returns the result.

```javascript
function Fiboi(n) {

            if (n === 0) return 0;
            if (n === 1) return 1;

            let f0 = 0;
            let f1 = 1;

            for (let i = 2; i <= n; i++) {
                let temp = f0 + f1;
                f0 = f1;
                f1 = temp;
            }
            return f1;
}
```
---

## Exercise 7: Approximate Square Root

**Objective**: Calculate an approximate value of the square root of a number.

**Function**:
- Takes a positive number as input.
- Uses an iterative method to approximate the square root.
- Returns the approximate value.

```javascript
function racine(A, iteration = 10){
            if (A <= 0) {
                console.log("A doit étre > 0");
                return;
            }

            let un = 1; // u0
            for (let i = 0; i < iteration; i++) {
                un = 0.5 * (un + A / un);
            }
            return un;
}

        //let A = 2;
        //let approx = racine(A, 10); // 10 itérations
        //console.log(`valeur approché de la racine de ${A} : ${approx}`);
```
---
