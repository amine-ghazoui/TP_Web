## Introduction

This TP focuses on **JavaScript programming** and the implementation of **interactive web functionalities**. It covers the following fundamental concepts:

- Handling **events** (e.g., button clicks).
- Reading and dynamically updating **HTML input fields**.
- Performing **mathematical operations** in real-time.
- Applying **logic and conditions** to categorize results.

---

## 📌 Exercises

### 📝 Exercise 1: Text Swap  
This script allows swapping the content of two text fields when a button is clicked.

#### 🔹 JavaScript Function:
```js
function swapText(){
    var text1 = document.getElementById("firstText").value;
    var text2 = document.getElementById("secondText").value;

    document.getElementById("firstText").value = text2;
    document.getElementById("secondText").value = text1;
}
```


---



### 🧮 Exercise 2: Simple Calculator
This script performs **basic mathematical operations**:  
✔ Addition  
✔ Subtraction  
✔ Multiplication  
✔ Division  

#### 🔹 JavaScript Functions:
```js
function addition(){
    var number1 = Number(document.getElementById("nbr1").value);
    var number2 = Number(document.getElementById("nbr2").value);
    document.getElementById("rslt").value = number1 + number2;
}

function subtraction(){
    var number1 = Number(document.getElementById("nbr1").value);
    var number2 = Number(document.getElementById("nbr2").value);
    document.getElementById("rslt").value = number1 - number2;
}

function multiplication(){
    var number1 = Number(document.getElementById("nbr1").value);
    var number2 = Number(document.getElementById("nbr2").value);
    document.getElementById("rslt").value = number1 * number2;
}

function division(){
    var number1 = Number(document.getElementById("nbr1").value);
    var number2 = Number(document.getElementById("nbr2").value);
    if (number2 !== 0) {
        document.getElementById("rslt").value = number1 / number2;
    } else {
        document.getElementById("rslt").value = "Error: Division by zero";
    }
}

```

---


## ⚖️ Exercise 3: BMI Calculation
This script allows you to **calculate the Body Mass Index (BMI)** based on the user's weight and height.

#### 🔹 JavaScript Function:
```js
function calculateBMI(){
    var weight = parseFloat(document.getElementById("weight").value);
    var height = parseFloat(document.getElementById("height").value);

    if (isNaN(weight) || isNaN(height) || height <= 0) {
        document.getElementById('result').textContent = "Please enter valid values.";
        return;
    }

    var bmi = weight / (height * height);
    bmi = bmi.toFixed(2);

    var category = "";
    if (bmi < 18.5) {
        category = "Underweight";
    } 
    else if (bmi < 25) {
        category = "Normal weight";
    } 
    else if (bmi < 30) {
        category = "Overweight";
    } 
    else if (bmi < 35) {
        category = "Moderate obesity (Class 1)";
    } 
    else if (bmi < 40) {
        category = "Severe obesity (Class 2)";
    } 
    else {
        category = "Morbid or massive obesity (Class 3)";
    }

    document.getElementById('result').textContent =
        "Your BMI is " + bmi + ". You are in the category: " + category + ".";
}
