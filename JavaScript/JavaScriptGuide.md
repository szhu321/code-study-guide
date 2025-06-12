# JavaScript Study Guide
This is a study guide for JavaScript. This guide can be used as a refresher for important JavaScript concepts.

## Introduction

JavaScript is a programming language, but you should already know that.

## DOM Manipulation
```JavaScript
// Updates the page with your custom text.
document.body.innerHTML = "It's a sunny day!";
// Alerts the user with a popup.
alert("WARNING: page broken. Unrecoverable");
```

## Math
### Basic Operations
```JavaScript
// Addition
1 + 1 // = 2

// Subtraction
1 - 1 // = 0

// Division
1 / 1 // = 1

// Multiplication
1 * 1 // = 1

// Order of operations
2 * (2 + 5) // = 14
```

### Caculation inaccuracy
When doing math with floats (e.g. decimals like 1.1) there are sometimes rounding errors.
```JavaScript
1.1 + 1.8 // = 2.9000000000000004
```
Calculate using whole number to avoid this
```JavaScript
(11 + 18) / 10 // = 2.9
```


### Rounding numbers

```JavaScript
Math.round(2.9) // = 3
```

## Strings
Strings are texts. 
```JavaScript
"I am a string" // Double quote
'I am a string as well' // Single quote
`I am a string too` // Template string
```

### String concatenation
We can add strings together.
```JavaScript
"Hello " + "?" // = "Hello ?"
```
We can also add strings and numbers. The number is converted to a string when adding.
```JavaScript
"Money" + 6 // = "Money6"
6 + "Money" // = "6Money"
```
Strings also follow order of operations.
```JavaScript
2 + 4 + "Money" // = "6Money"
2 + (4 + "Money") // = "24Money" (Interesting!)
```

### Escape character
You can use escape character for single quote (\\') to convert it to pure text with no special meaning.
```JavaScript
// How to use single quote without error?
'I'm fat'
```
``` JavaScript
'I\'m fat' // Can use escape character single quote.
"I'm fat" // Or we could have just surround with double quotes.
```

The escape character (\\n) creates a new line.
```JavaScript
"New\nLine"
/* = "New
Line" */
```

### Template string
- **Interpolation** - Allow you to insert a value inside a string.
```JavaScript
`I have ${1 + 1} dollars.` // "I have 2 dollars."
```

- Multiline strings.
```JavaScript
`New
Line` // 2 lines
```

## Variables 
Variables are used to store values that can then be used later.  

### Creating Variables
- The following code creates a new variable called number, and then logs it to the console.
```JavaScript
let number = 3;
console.log(number);
```
- Use `const` if you don't want to change the variable later.
- It is a good practice to use `const` by default and change it to `let` if you need to change the variable.
```JavaScript
const number = 3;
number = 4; // Error.
```
- Use `var`. Old way with issues, just use `let` instead.
```JavaScript
var number = 3;
```



### Variable Name Restrictions
- Cannot use keywords like `let` as a variable name.
```JavaScript
let let = 1; // Nope
let let1 = 1; // Ok
let let2 = 2; // Ok
```
- Cannot start with a number.
```JavaScript
let 2hot = 2; // Nope
```
- Cannot use special characters except `$` and `_`
```JavaScript
let num!@#%^&* = 2; // No Special Characters
let num 2 = 2; // No Spaces
let num_2 = 2; // Ok
let num$ = 2; // Ok
```

### Note on the use of semicolons `;`
- A semicolon marks the end of an statement. Use it to seperate statements.
```JavaScript
let num = 1; // Creating a variable is an statement.
```
- Statements on the same line should be seperated by semicolons.
```JavaScript
let num = 1 let num2 = 2 // This will cause an error.
let num = 1; let num2 = 2; // Ok
```
- JavaScript have automatic semicolon insertion rules.
```JavaScript
let num = 1
let num = 2 // These are ok.
```
You can read more about automatic semicolon insertion [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#automatic_semicolon_insertion).


### Reassigning Variables
- Once you created a variable you can change its value.
```JavaScript
let num = 2;
num = 3;
console.log(num); // Logs 3 
num = num + 1;
console.log(num); // Logs 4
```
- Variable re-assignment shortcuts.
```JavaScript
num++ // num = num + 1;
num-- // num = num - 1;
num += 2 // num = num + 2;
num -= 2 // num = num - 2;
num *= 2 // num = num * 2;
num /= 2 // num = num / 2;
```


### Naming Conventions and Best Practices
- camel case: `cartQuantity`
    - Used for variable names
- pascal case: `CartQuantity`
    - Used for class names
- kebab case: `cart-quantity`
    - Cant be used as variable name in JavaScript
    - Used for file names.
    - Used in HTML and CSS.
- snake case: `cart_quantity`
    - Used in other languages (not JavaScript).
- Variable names should be short and concise. It should be easily understood at a glance. 
    - E.g. Number of items in a shopping cart.
        - `numberOfItemsInTheCart` is ok but a bit long.
        - `cartQuantity` good.
        - `num` num of what? too vague.
    - E.g. The age of a person.
        - `ageOfThePerson` is ok but a bit long.
        - `age` good.
        - `a` what? just the letter a? too vague.

### Keyword `typeof`
- This keyword let us know the type of value inside a variable.
```JavaScript
let num = 1;
let str = "Hello";
console.log(typeof num); // number
console.log(typeof str); // string
```

## More coming soon

## Credits
This study guide is based on the material from ["JavaScript Tutorial Full Course - Beginner to Pro"](https://youtu.be/EerdGm-ehJQ?si=DwCl2GqrbDYP0rce) by SuperSimpleDev.

