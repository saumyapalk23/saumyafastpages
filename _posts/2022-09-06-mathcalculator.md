---
layout: default
title: Calculator Starters
description: A common way to become familiar with a language is to build a calculator.  This calculator shows off button with actions.
permalink: /frontend12/calculator
image: /images/calculator.png
categories: [pbl]
tags: [javascript, css. dom, getElementID]
---

{% include nav_frontend.html %}
<!-- Hack 1: Test conditions on small and big numbers, report on findings -->
<!-- Hack 2: Add a common math operation that is missing from calculator -->
<!-- Hack 3: Implement 1 number operation (ie SQRT) -->

<!-- Style (CSS) implementation of the calculator. -->
<style>
/* class to create the calculator's container; uses CSS grid dsiplay to partition off buttons */
.calculator-container { 
    width: 90vw; /* this width and height is specified for mobile devices by default */
    height: 80vh;
    margin: 0 auto;

    display: grid;
    grid-template-columns: repeat(4, 1fr); /* fr is a special unit; learn more here: https://css-tricks.com/introduction-fr-css-unit/  */
    grid-template-rows: 0.5fr repeat(4, 1fr);
    gap: 10px 10px;
}

/* 
    CSS allows programmers to use media queries to change the size of classes based on the size of the device.
    This allows us to make it so that our website looks good on both mobile and desktop. If the width of the
    device is big enough, then the calculator will take up more of the screen.
*/
@media (min-width: 600px) { 
    .calculator-container {
        width: 40vw;
        height: 80vh;
    }
}

/* styling for the calculator buttons themselves */
.calculator-button {
    width: auto;
    height: auto;
    border-radius: 10px;
    background-color: #665B45;
    border: 3px solid black;
    font-size: 1.5em;

    display: flex;
    justify-content: center;
    align-items: center;

    /* grid display allows programmer to specify how much of the grid an element should take up; these buttons will take up 1 row and 1 column */
    grid-column: span 1;
    grid-row: span 1;

    /* allows for smooth transition of properties and the "animation" effect to appear on hover */
    transition: all 0.5s; 
}

/* darkens the background color on hover to create a selecting effect */
.calculator-button:hover {
    background-color: #373737;
}

/* styling for the top bar which shows the results of the calculator */
.calculator-output {
    /* note how the output instead takes up 4 columns and 1 row; essentially takes up the entirety of the first row */
    grid-column: span 4;
    grid-row: span 1;

    border-radius: 10px;
    padding: 1em;
    font-size: auto;
    border: 5px solid black;

    display: flex;
    align-items: center;
}
</style>


<!-- HTML implementation of the calculator. 
    CSS sets 4 buttons (calculator-button) to a row
    All buttons have onclick JavaScript action
    All actions result in calculator-output.innerHTML change
-->
<div class="calculator-container">
    <!--result-->
    <div class="calculator-output" id="output">0</div>
    <!--row 1-->
    <div class="calculator-button" onclick="number('1')">1</div>
    <div class="calculator-button" onclick="number('2')">2</div>
    <div class="calculator-button" onclick="number('3')">3</div>
    <div class="calculator-button" onclick="operation('+')">+</div>
    <!--row 2-->
    <div class="calculator-button" onclick="number('4')">4</div>
    <div class="calculator-button" onclick="number('5')">5</div>
    <div class="calculator-button" onclick="number('6')">6</div>
    <div class="calculator-button" onclick="operation('-')">-</div>
    <!--row 3-->
    <div class="calculator-button" onclick="number('7')">7</div>
    <div class="calculator-button" onclick="number('8')">8</div>
    <div class="calculator-button" onclick="number('9')">9</div>
    <div class="calculator-button" onclick="operation('*')">*</div>
    <!--row 4-->
    <div class="calculator-button" onclick="clearCalc()">A/C</div>
    <div class="calculator-button" onclick="number('0')">0</div>
    <div class="calculator-button" onclick="number('.')">.</div>
        <!--row 5-->
    <div class="calculator-button" onclick="clearCalc()">A/C</div>
    <div class="calculator-button" onclick="number('0')">0</div>
    <div class="calculator-button" onclick="number('.')">.</div>
        <!--row 6-->
    <div class="calculator-button" onclick="operation('√')">√</div>
    <div class="calculator-button" onclick="operation('sin')">sin</div>
    <div class="calculator-button" onclick="operation('cos')">cos</div>
    <div class="calculator-button" onclick="operation('tan')">tan</div>
    <!--row 6-->
    <div class="calculator-button" onclick="operation('^')">^</div>


          

</div>


<!-- JavaScript (JS) implementation of the calculator. -->
<script>
// initialize important variables
let output = document.getElementById("output");
let operator = null;
let firstNumber = null;
let nextReady = true;

// Number action
function number (value) { // function to input numbers into the calculator
    if (value != ".") {
        if (nextReady == true) { // nextReady is used to tell the computer when the user is going to input a completely new number
            output.innerHTML = value;
            if (value != "0") { // if statement to ensure that there are no multiple leading zeroes
                nextReady = false;
            }
        } else {
            output.innerHTML = output.innerHTML + value; // concatenation is used to add the numbers to the end of the input
        }
    } else { // special case for adding a decimal; can't have two decimals
        if (output.innerHTML.indexOf(".") == -1) {
            output.innerHTML = output.innerHTML + value;
            nextReady = false;
        }
    }
}

// Operator action
function operation (choice) { // function to input operations into the calculator
    if (firstNumber == null) { // once the operation is chosen, the displayed number is stored into the variable firstNumber
        firstNumber = parseInt(output.innerHTML);
        nextReady = true;
        operator = choice;
        return; // exits function
    }
    // occurs if there is already a number stored in the calculator
    firstNumber = calculate(firstNumber, parseFloat(output.innerHTML)); 
    operator = choice;
    output.innerHTML = firstNumber.toString();
    nextReady = true;
}

// Calculator
public class Calculator {

public static void main(String[] args) {
Scanner sc = new Scanner(System.in);

System.out.print("Please enter your first number: ");
double a = sc.nextInt();

System.out.print("Please enter your second number: ");
double b = sc.nextInt();

// random error fix
sc.nextLine();

// initialize the result variable "c"
double c = 0;

System.out.print("Please enter your function: ");
String func = sc.nextLine();

switch (func) {
// text function is add, subtract ...

default:
System.out.println("The function you have entered has been misspelled or has not yet been implemented!");

case "help":
System.out.println("Functions avaliable: +, -, *, /, ^, sin, cos, tan, mod(%),(WIP)");
break;
case "add":
c = a + b;
break;

case "subtract":
c = a - b;
break;

case "multiply":
c = a * b;
break;

case "divide":
c = a / b;
break;

// same as above except with symbols
case "+":
c = a + b;
break;

case "-":
c = a - b;
break;

case "*":
c = a * b;
break;

case "/":
c = a / b;
break;

case "sin":
System.out.print("Which number? (a)" + a + " or (b)" + b + ": ");
String sinChoice = sc.next();

if (sinChoice.equals("a")) {
    a = Math.toRadians(a);
    c = Math.sin(a);
}

if (sinChoice.equals("b")) {
    b = Math.toRadians(b);
    c = Math.sin(b);
}

break;

case "cos":
System.out.print("Which number? (a)" + a + " or (b)" + b + ": ");
String cosChoice = sc.next();

if (cosChoice.equals("a")) {
    a = Math.toRadians(a);
    c = Math.cos(a);
}

if (cosChoice.equals("b")) {
    b = Math.toRadians(b);
    c = Math.cos(b);
}

break;

case "tan":
System.out.print("Which number? (a)" + a + " or (b)" + b + ": ");
String tanChoice = sc.next();

if (tanChoice.equals("a")) {
    a = Math.toRadians(a);
    c = Math.tan(a);
}

if (tanChoice.equals("b")) {
    b = Math.toRadians(b);
    c = Math.tan(b);
}

break;

case "sqrt":
System.out.print("Which number? (a)" + a + " or (b)" + b + ": ");
String sqrtChoice = sc.next();

if (sqrtChoice.equals("a")){
    c = Math.sqrt(a);
}
if (sqrtChoice.equals("b")){
    c = Math.sqrt(b);
}
break;

case "^":
System.out.print("(a) "+ a + "^" + b + ", or (b) " + b + "^" + a + "? ");
String powerChoice = sc.next();
if (powerChoice.equals("a")){
    c = Math.pow(a, b);
}
if (powerChoice.equals("b")){
    c = Math.pow(b, a);
    

}
break;
 case "tan": result = Math.tan((first - second + second)); break; default: break; } return result; }

}
// Equal action
function equals () { // function used when the equals button is clicked; calculates equation and displays it
    firstNumber = calculate(firstNumber, parseFloat(output.innerHTML));
    output.innerHTML = firstNumber.toString();
    nextReady = true;
}

// A/C action
function clearCalc () { // clears calculator
    firstNumber = null;
    output.innerHTML = "0";
    nextReady = true;
}
</script>





































