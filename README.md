# Ex.08 Design of a Standard Calculator
## Date:

## AIM:
To design a web application for a standard calculator with minimum five operations.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for creating attractive colors.

### Step 4:
Write JavaScript program for implementing five different operations.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

calc.html
<html lang="en">
  <head>
    <title>Calculator in HTML CSS & JavaScript</title>
    <link rel="stylesheet" href="cal.css" />
  </head>
  <body>
    <div class="container">
      <h1 align="center">SIMPLE CALCULATOR</h1> 
      <input type="text" class="display" />

      <div class="buttons">
        <button class="operator" data-value="AC">AC</button>
        <button class="operator" data-value="DEL">DEL</button>
        <button class="operator" data-value="%">%</button>
        <button class="operator" data-value="/">/</button>

        <button data-value="7">7</button>
        <button data-value="8">8</button>
        <button data-value="9">9</button>
        <button class="operator" data-value="*">*</button>

        <button data-value="4">4</button>
        <button data-value="5">5</button>
        <button data-value="6">6</button>
        <button class="operator" data-value="-">-</button>

        <button data-value="1">1</button>
        <button data-value="2">2</button>
        <button data-value="3">3</button>
        <button class="operator" data-value="+">+</button>

        <button data-value="0">0</button>
        <button data-value="00">00</button>
        <button data-value=".">.</button>
        <button class="operator" data-value="=">=</button>
      </div>
    </div>

    <script src="cal.js"></script>
  </body>
</html>

cal.css

/* Import Google font - Poppins */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}
body {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgb(230, 229, 232);
}

.container {
  position: relative;
  max-width: 500px;
  width: 100%;
  border-radius: 12px;
  padding: 10px 20px 20px;
  background: #0c0202aa;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.716);
}
.display {
  height: 80px;
  width: 100%;
  outline: none;
  border: none;
  text-align: right;
  margin-bottom: 10px;
  font-size: 25px;
  color: #080101;
  pointer-events: none;
}
.buttons {
  display: grid;
  grid-gap: 10px;
  grid-template-columns: repeat(4, 1fr);
  
}
.buttons button {
  padding: 10px;
  border-radius: 6px;
  border: none;
  font-size: 20px;
  cursor: pointer;
  background-color: #fcfafa6c;
}
.buttons button:active {
  transform: scale(0.99);
}
.operator {
  color: hsl(118, 96%, 50%);
}

cal.js

const display = document.querySelector(".display");
const buttons = document.querySelectorAll("button");
const specialChars = ["%", "*", "/", "-", "+", "="];
let output = "";

const calculate = (btnValue) => {
  display.focus();
  if (btnValue === "=" && output !== "") {
    output = eval(output.replace("%", "/100"));
  } else if (btnValue === "AC") {
    output = "";
  } else if (btnValue === "DEL") {
    output = output.toString().slice(0, -1);
  } else {
    if (output === "" && specialChars.includes(btnValue)) return;
    output += btnValue;
  }
  display.value = output;
};

buttons.forEach((button) => {
  button.addEventListener("click", (e) => calculate(e.target.dataset.value));
});
## OUTPUT:
![output](output.png)
## RESULT:
The program for designing a standard calculator using HTML and CSS is executed successfully.
