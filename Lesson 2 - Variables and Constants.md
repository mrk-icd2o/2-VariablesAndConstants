# Lesson 2 - Variables and Constants

So far we've been using shapes and colours to generate images, which isn't quite programming. In this lesson we'll learn about the most basic programming concept - the use of variables.

## What are Variables and Constants?

In Math class you have used variables before to represent something ("let x represent…"), and then used those variables within expressions/equations.

In programming a variable or constant is a "container" in the memory that stores a data value. We can use those data values whenever we want. Variables can also change value throughout the program, a constant cannot.

## Data Types

The following are the three main data types we will see in Javascript:

- Number (both integers and decimals)
- String (text)
- Boolean (true or false)

## Creating Variables and Constants

In p5.js we will mostly create variables globally, which means that the whole program can access the variable. To do this we declare the variables just below our header, before the `setup()` function.

`const` is used to declare a constant - you will not be able to change this value later. `let` is used to declare a variable, which can be modified.

```javascript
/*
   Description: Basics of P5.js
   Author: Mr. Kowalczewski
   Date of last edit: February 16, 2026
*/

const myHeight = 183; // Number constant
let myAge = 41; // Number variable

const myName = "Mr Kowalczewski"; // String constant
let mySubject = "Computer Science"; // String variable

const likesCoffee = true; // Boolean constant
let likesStudents = false; // Boolean variable

function setup() {
  createCanvas(windowWidth, windowHeight);
  background(255);
}

function draw() {

}
```

NOTE: if you create a variable or constant within `{ }`, they will only exist inside there. Try to avoid this for now.

## Naming Convention

In programming we use descriptive names for our variables (not `x`, `a`, etc). This way you can immediately identify what a variable is used for, helpful when you start coding large projects.

The convention used in Javascript is camelCase. The first "word" in your variable is lowercase, but the following words are capitalized to increase readability.

## Variables and Constants in p5.js

Variables and constants can be used in place wherever those values are expected. For example:

```javascript
let xValue = 100;
const rectSize = 50;

// drawing a rectangle with my variable and constant
rect(xValue, 200, rectSize, rectSize);
```

The above is the same as `rect(100, 200, 50, 50)`! We can also re-use these values, and potentially change the value of `xValue`.

## Producing Movement

We can now use variables to produce some movement in our programs. We will use the fact that the `draw()` function loops around to do this.

In `script.js`we have a simple line being drawn, and we will modify it to get the expanding across the screen.  In order to do this we will:

- declare a variable to represent the x value of the righthand point
- use that value within the `line()`
- modify the value of our variable


## Modifying Number Type Variables

You can perform many math operations to Number types such as:

- addition `+`
- subtraction `-`
- multiplication `*`
- division `/`

It's important however to always store the result back into the variable:

```javascript
let xValue = 100;

xValue + 50; // this adds 100 + 50 on the spot, but nothing happens to it!

// proper way(s)
xValue = xValue + 50; // this adds 100 + 50 and stores the result back into xValue (right side evaluated first)
xValue += 50; // same result but shorter
```

## When to Use Constants

Imagine that you are coding a program that will involve many similar sized rectangles, such as a chessboard. Perhaps the rectangle has a length and width of 50 and you need to create many (64) of these.

Eventually you decide to change the size - but now you have to modify 64 lengths and widths! If you had just declared a constant at first, and then used that name for all rectangles… you would only need to make one change.

```javascript
// I can modify this one value, and it would change the size of ALL rectangles
const rectSize = 75;

// many rectangles
rect(0, 50, rectSize, rectSize);
rect(200, 200, rectSize, rectSize);
etc
```

## Working with Strings



String type variables contain text. When you create the variable, you enclose the text in quotation marks.

```javascript
// String variables
let teacherName = "Mr K";
let subject = "Computer Science";

// not a String (Number)
let teacherAge = 41;
```

We can display text in our programs by using the `text()` function. You can also combine (or concatenate) strings with other strings or even numbers, by adding them - as many times as you like. You can change the size using `textSize()` and colour using `fill()`. Similar to changing other properties, this must be done before writing the text.

```javascript
textSize(10);
text(string, x, y); // draws the string data (either a variable/constant or direct value) at coordinates (x, y)

// Examples
textSize(20);
text("Hello There", 100, 10);
text(teacherName, 100, 50);
text(teacherName + " is " + teacherAge + " years old.", 100, 90); // concatenating strings and number

// alternate way of combining strings and variables:
text(`${teacherName} is ${teacherAge} years old.`, 100, 90);
```

We can also use `console.log()` to display data in the console. This is not part of your visual, but can be useful for debugging purposes - so you can "see" how your variables are changing.

## Back to the Example

We'll add some `text()` to the screen, as well as show how `console.log()` works for debugging.


## background()

When we first added the value of our variable to the text, it didn't come out right. That's because the `draw()` function loops continuously, meaning that new values of `text()` are drawing on top of each other.

To solve this problem, we can move `background()` to the `draw()` function. This will result in the previous shapes/text being wiped out each time the loop restarts.

## When to use text() and console.log()

`text()` is good when you have information that the user (the person running your program) needs to see.

`console.log()` is good for debugging, or for the programmer to figure out what's going on behind the scenes. In the above example, we used this to figure out the value of our variable - this will be important for future lessons!
