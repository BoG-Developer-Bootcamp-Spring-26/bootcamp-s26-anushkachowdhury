# Bits Of Good

Why should you learn Git? : a “commit” is like a save point for a relatively small change in your codebase. It is like ctrl + z for large changes in your code.

- Todo list commit examples:
1. Initialize code base
2. Design todo component
3. Add component functionality
4. Fix state management bug

Commits are like snapshots of your code: can revert back to previous snapshots at any time

- Like version history in google docs (but with commit messages)

They create two different “brach” one for each. After both are done with their individual features, they integrate their code using Git’s merging feature that makes the process hassle and bug free. 

- branch: main
- branch: bob-custom-blocks
- branch: alice-schedule-share

1. Initialize a Git repository (only do this once per project) git init
2. Make changes (unstaged changes)
3. Stage (add) these changes git add .
4. Commit these changes git commit -m “message”
5. Push these changes (typically to GitHub) git push origin main

![image.png](attachment:bef184f7-7571-4110-bf23-d772d9e4bdfb:image.png)

Branches (like a tree):

- Every repository has a main branch (this is the one that’s deployed)
- New branches are created for new features
- Each branch may have its own different files/changes
- Create new branch: git branch <name>
- Switch branches: git checkout <name>

Unix Commands:

- Commands used in terminals of Unix-based operating systems
    - macOS and Linux are Unix-based OS
    - Windows is not
- Used to create/edit folders & files, navigate directories connect to servers, etc
- Faster than using your computer’s GUI
- Use these commands in Terminal, Git Bash

Is: list the contents of the current directory

- Is -al list all contents during hidden files & folders
- Is directoryName → list contents in specific directory

Cd: change directories

- cd → go to the root directory
- cd .. → go up a directory
- cd - → go to back to the previous directory

pwd: print working directory

touch: create files:

- touch.file.txt: create a new file in the working directory

mkdir: make directories:

- mkdir folderName: make a new directory
- mkdir location/folderName → make a new directory in a specific location

rm: remove files & folders:

- rm file.txt: remove a file
- rm -R folderName: remove a directory
- rm -rf folderName: remove a directory and all of its contents

mv: move files & folders

- mv initial.txt new.txt → transfers the content of initial.txt to the new.txt. and deletes initial.txt. Used to rename a file or folder
- mv initialDestination newDestination → transfers the content from the initial file to the new file

## Lecture 2

HTML: the skeleton of web pages 

- Defines what is on the page
- <div>, <h1>, <p>, <a>, etc
- Those <> are called tags or elements
- Tags can have attributes in a format of attribute=”value”
- HTML5 is most recent, and most used standard

<!DOCTYPE html> 

<html>
    <head>
        //page metadata goes here
    </head>
    <body>
        //page content goes here
    </body>
</html>

Important Content Tags:
- div: a container for other html elements
- p, h1, h2, h3 - text tags
- img image
- button button
- ol, ul, ordered and unordered list
- a hyperlink

CSS: The style of web pages
- Use selectors to identify tags to add styles
    - tag (tag itself), class (.), id (#)
    - ids must be unique
    - classes and ids are properties that can exist on every single HTML element, flagging them for CSS styling. 
- Properties: each attribute of css rule
- Rule: collection of properties bound by curly braces

.flex-col {
    display: flex;
    flex-direction: column;
}

p {
    background-color: lightblue;
}

.center {
    background-color: red;
    text-align: center;
    color: red;
}

#main-content {
    background-color: purple;
    padding: 20px;
}

Specificity: what wins for competing styles?
- If two rules sets with overlapping rules are applied to the same element, what happens?
    - In this case, the specificity of the selector is what determines the style that is applied
    - Typically, id>clas>tag when dealing with specificity

More on CSS Selectors (styling...)
- descendants/multiple selectors
    - .class1.class2 selects all elements marked with both class 1 and class 2
    - .class1 .class2 selects class2-marked elements that are descendants of class1
    - element.class(p.class1) selects all <p> that are also of class class1
    - pseudo (:) used to style "states" of elements like :hover, :visited, :focused, etc

    .btn:hover {
        [insert styles here]
    }

Tips:
- Border is self-explanatory (use it make borders)
- Margin and padding are for spacing
    - Margin adds spacing outside
    - Padding adds spacing inside
- Use inspect element and hover over HTML tags to see each element's bounds
    - Or enable select mode*
Margin -> Border -> Padding -> Content

Border:
- Border is self-explanatory (use it to make borders)
- border-color
- border-style
- border-width
- pt (point 1pt = 1/72 of 1 in)
- em (relative to the font size of element (2em means 2 times the size of the current font))
- rem (relative to font-size of the root element)
- % (relative to the parent element)

The 'display' property: how children are ordered
- Determines how an element looks
- Impacts page element layout
- divs are blocks by default, so they will take up 100% of their parent's width
inline: does not start on new line, cannot control width/height
block: does start on new line, can control width/height
inline-block: does not start on new line, can control width/height

A flexible display type:
- display: flex
- Simpler (kinda)
- Wrap the elements you want to align with a div
- The space that your children elements fill is dependent on the parent div

Flexbox: flex-direction
- The direction you want your elements to align
- Formally, sets your "main axis"

Flexblock: justify-content
- Works in the direction of your flex-direction

Flexbox: align-items
- Works along the "cross axis", the direction perpindicular to your flex-direction
Grid:
- More specific flex application
    - Similar ideas to flexbox, but for having a more rigid grid like structures with rows and columns
    - display:grid
    - grid-template-columns property allows for setting up
        - grid-template-columns: 1 fr 50px 1 fr sets up three columns with those respective width
        - fr: fractional unit that evenly splits the remaining space across other fractional columns
Positioning: not just in-order
- static, relative, absolute, fixed, sticky
Static: default, follows regular flow of the page
Relative: positioned relative to its normal (static) would-be position
Absolute: positioned relative to parent container, regardless of where the element wouldbe in its static position
Sticky: toggles between relative and fixed positioning based on scroll distance, acts relative until a certain offset, then remains fixed

Responsive Design: same code for multiple screen sizes
- A responsive website dynamically adjusts the website's layout and its corresponding element's sizes depending on the screen size
- Enhanced user experience: consistent, seamless, multi-device user experience
- Increased mobile reach: access wider audience on various devices
- Easier maintenance: simplifies updates, reduces costs as you have to only maintain one codebase

Media Query:
- Media queries are a feature of CSS that allow you to apply styles conditionally based on the characteristics ofthe device, primarily focusing on the width and height
- The attributes padding and text-align remain the same in the example
- This is used to change the website's layout based on the screen size
//this is screen formatting for smaller screens (less then 600 px)
media screen and (max-width: 600px) {
    .box {
        width: 100x;
        background-color: lightcoral; //change background color
    }
}

flexible grid layouts: use relative units like percentages instead of fixed units like px 
.column {
    float: left;
    width: 50%;
}

responsive typography: adjusting the text size and spacing based on screen size: 
@media (min-width: 600 px) {
    body {
        font-size: 1.2em;
    }
}

viewport meta tag: controls how a webpage is displayed on mobile devices. without this tag, mobile devices typically scale down.
<meta name = "viewport" content= "width=device-wdth, initial-scale=1">

Tailwind CSS: faster and conveniet css
What is Tailwind? A CSS framework that uses ready-made classes to hellp you style your site directly in the HTML
- No more changing between HTML and CSS file every second!
- Conveniet for responsiveness with prefixed classes.

## Lecture 3
Javascript: 
How Websites Work: need a program to read these files

It goes from client -> browser -> server

Static websites: each page is it's own HTML file: pages are the same for all users; there is no data
- Think of it as frontend code only
Dynamic websites: content changes with every request to the web server
Frontend -> the UI (HTML, CSS, React)
Backend -> the API, database, authentication

Client (frontend) -> send a request -> API (server) -> query to the database -> send back to the API server -> send a response in JSON to the client

This process repeats each time to user reloads or requests another html page.

JavaScript: makes static websites dynamic, browsers have JS engines that execute JS scripts

Node.js: we can also run JS on Node.js
- A JS runtime - where your code is executed
- Builds on top of Chrome's V8 engine

JavaScript VS. Node.js
JS: a programming languages, runs in the browser (client-side)
Node.js: a javascript runtime environment, allows JS to run on the server (server-side), other languages commonly used in servers: Python, Go, C#

node hello.js -> executing JS programs
JS Syntax:
- {} curly braces form blocks
- // for online comments, /**/ for multi-line comments
- semicolons after statements are optional (but recommended, use a linter like Prettify)
- identifiers are case-sensitive
- very similar to java

Variables:
- let, const, var
- "let" has a block scope, can't be redeclared, can be reassigned
- "const" has a block scope, can't be redeclared, can't be reassigned
- "var" has a function scope, can be reassigned
    - do not use var it is outdated and functions weirdly

let x = 10
const y = "Hi"
var z = true

Javascript is a weakly typed language
- Variables can be reassigned to different types whenever
- Don't need to declare variable type like in java

null, undefined, boolean, number, bigInt, string, symbol

Arrays: collection of values
- resizeable, can contain mixed data types
- access elements by arr[index]
let arr = []
arr.push(1, 2, 3)
arr.length 
arr[1]
- this has similar functionality as an arraylist in java

objects: collection of key-value pairs
- property: value
- property names can be identifiers, strings, or numbers
- values can be any other data type including objects, functions, & arrays
- access object values with dot notation or bracket notation
Values can be primitive, arrays, objects and even funtions

const dog = {
    name: "casey",
    breed: "pomeranian",
    "age": 10,
    friendly: true
}

const breed = dog.breed // dot notation
const name = dog["name"] //bracket notation
const age = dog."age" //not allowed

Const Array and Objects (Reference vs Value):
- Elements of const array and objects are mutable
- Only the reference to the array or object is constant, not the values in them
const arr = [bits, of, good];
arr[0] = bytes //good
arr = [bytes, of, good] //BAD

Spread Operators:
- How would you copy an array?
    - Object and array arguments are passed by reference, not value
    function copyAnArray(array) {
        return array;
    }
    function copyAnArray(array) {
        const copy = []
        for (let i = 0; i < array.length; i++) {
            copy.push(array[i]);
        }
        return copy;
    }


Dumping elements made easy:
- Use spread operator (...)
    - [...array] will create a new array with all of array's element dumped over
    - shallow copy if you have nested elements (an array of objects)
        - you can use structuredClone() for deep copies
        function copyAnArray(array) {
            return [...array]
        }

        const [one, two, ...rest] = numbers;
        console.log(one); //output: 1
        console.log(two); //output: 2

Copy arrays into other arrays
Copy objects into other objects

//we have an objects
const user = {
    username = "afazio1",
    password = "1234",
    age: 18
};

//spread into new object
const userBio = {
    ...user,
    bios: "GT 26",
    followers: 0
};

Callable Objects: functions!
- contain parameters & a return value
- pass by value, however arrays and objects passed in are changeable
function square(num) {
    return num * num
}

function reverseArr(myArr) {
    myArr.reverse()
}

arr = [1,2,3]
reverseArr(arr) //call function
console.log(arr) 

Another way to declare functions:
- assign function to variables
- allows us to pass functions in as parameters
- notice that a function name is optional
const square = function (num) {
    return num*num
}

Array Functions: const someFunction = () => {...} (like java lambda expression)

- No different from normal function declaration, just convenient
- function someFunction() {...}
Shorter syntax:
- removes the "function" reserved word
- allows for the implicit return
const square = (num) => num * num
const square = (num) => {
    return num * num
}
const square = (num) => (
    num * num
)

A note on equality == VS ===
- == compares "truthyness" (disregards data type)
- === compares value and data type

truthy values
- 'false' (quoted false)
- '0' (quoted zero)
() (empty functions)
[] (empty arrays)
{} (empty objects)
all other values

Array Functions:
- Functions you can apply to arrays:
    - forEach
    - map
    - filter
    - reduce

forEach: executed a function of elemnets in arrays, maps, or sets
    - will not modify that value in the array!
    - if you want to modify each element, use a map

dog.forEach(dog => console.log(dog));
// -> dog 1, dog 2, dog 3
java equivalent: for (char c : charArray);

Map: creates a new array based off of the results in a provided function iterating over every item in an array. basically calls a function on every element and creates a new array with the outputs
- will create an entirely new array!
const newDogs = dogs.map((dog, index) => dog.name);
// -> ["Poodle", "Pomeranian", "Lab"]

Filter an array by certain criteria, returns a new array with the elements that satisfy the criteria
    - if the new array should not include that item, return false
    - otherwise, return true
let result = arr.filter((currentValue, currentIndex, currentArr) => {
    //filter logic here, return true or false
})

dogs.filter(dog => dog.breed.includes("Shiba))
// -> array with only Shiba dogs

reduce an array to a single value, this value is the result of a reducer function that you apply to each element in the array
array.reduce(function(accumlator, currentValue, currentIndex, array) {
    //reudcer logic here
    return accumulators
}, initialValue);

const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulators, currentValue) => {
    return accumulators + currentValue;
}, 0)

Why Map Filter Reduce?
- Declarative Nature, map, filter, and reduce describe what to do with the data, making the code easier to read and understand, as opposed to for loops which require describing how to perform each step
- Performative Optimizations: Modern JS engines optimize map, filter, and reduce well, making them competitive in performance with traditional loops for many use cases
- Reduced boilerplate: they eliminate boilerplate code like setting up loop counters and exit conditions allowing for more succinct code
- Immutability: these methods do not alter the original array but instead return a new array or value, promoting the principle of immutability which helps prevent side effects

## Lecture 4:  JS Continued

//install JSON formatter as a chrome extension
DOM: document object model
- a tree of HTML elements
- specifies how to interact with a web document as an object

Why the DOM?
- allows us to select elements defined by HTML to be dynamically modified
- enables developers to define specific outcomes to different events
    - adding/updating/deleting elements based on browser or user events

Import JS in your HTML
<script> </script>
- put a script tag at the end of body
- JS file is loaded in order of your HTML elements
    - head is loaded first, so if you put your script tag in there you may not have loaded any selectors by that point
    <script type = "text/javscript" src = "index.js"></script>
Using the DOM API
Coding using the DOM
document.getElementById('ID') //id
document.getElementsByTagName('tag') //html tag
document.getElementsByClassName('className') //class
document.querySelectorAll('cssStyleSelector') //CSS selector 


## Lecture 5
TYpescript:
- We want websites that work
- JS is dynamically typed!
- Any errors in the code aren't discovered until runtime
- TS lets us add structure to our data through types and will check it before compiling
- It's industry standard to use TS

Why not vanilla JS?
Problem 1: too many requests when routing
Problem 2: tedious to grab data from DOM

Solution 1: Single Page Application (SPA)
- Instead of fetching a completely new page every time we navigate to a new route, what if we just change the current page's content dynamically?
Solution 2: No need for DOM because everything is JS
- what if we made HTML as part of your js?

React: a javascript library for buildings UIs
- HTML-in-your-javascript approach to building web apps
- single-page application
- a better developer experience when building web apps
    - web apps: centered around user interaction to modify/display data dynamically
    - websites: primarily static content
- uses jsx
    - not HTML, not js, but kinda both
    - centered around the idea of having each distinct logical section be separated into its own component
    - this is so that each componenet is responsible for how it consumes/modifies data


JSX: its differences:
- className attribute instead of class
- javascript that can interact with HTML directly instead of keeping them in separate files
- CSS can be applied through imports or inlines
- HTML-in-your-JS

Components: the building blocks of react apps
- javascript funcitons that return JSX
- classes vs functional components
- independently in control of its contents and data logic
- can contain other components and pass in props




import React from "react";

export default function ProfileCar() {
    return {
        <div className = {styles.container}>
            <p>My name is Anushka Chowdhury, i'm a first year CS Major at Georgia Institute of Technology
            </p>
        </div>
    }
}
Props Arguments?
- props are one way you can pass data from one component to another
- allows you to manually define certain data that you want to pass


