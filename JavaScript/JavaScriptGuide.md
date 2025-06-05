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

## More coming soon

## Credits
This guide uses material from ["JavaScript Tutorial Full Course - Beginner to Pro"](https://youtu.be/EerdGm-ehJQ?si=DwCl2GqrbDYP0rce) by SuperSimpleDev.

