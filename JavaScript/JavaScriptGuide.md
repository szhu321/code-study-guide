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

## Booleans and If-Statements

### Booleans
A boolean is a value that can be `true` or `false`.

```JavaScript
console.log(2 > 5); // false
console.log(2 < 5); // true
```

### Comparison Operators
```JavaScript
> // Greater than
< // Less than
>= // Greater than or equal to
<= // Less than or equal to
=== // Strictly equal to
== // Equal to
!== // Strictly not equal to
!= // Not equal to
```

- It is almost always better to use Strictly equal `===` over `==` and strictly not equal `!==` over `!=` because they make sure both values have the same type.
```JavaScript
console.log(2 == "2") // true, JavaScript converts both to the same type then compares.
console.log(2 === "2") // false, number type is not equal string type.
```

### If-Statements
- Used to run code only if a condition is true.
```JavaScript
if(condition) {
    // Runs if condition is true.
}
```
- The condition of the if-statement should evaluate to a boolean.
```JavaScript
// Condition is true. This will always run.
if(true) {
    // ...
}

// 1 > 2 evaluates to false so the code inside never runs.
if(1 > 2) {
    // ...
}

// If the variable num is greater than 0 the code inside runs.
if(num > 0) {
    // ...
}
```

### If-else
- Used to run code only if a condition is true. If the condition is false code inside the else block runs.
```JavaScript
if(condition) {
    // Runs if condition is true.
} else {
    // Else run code here.
}
```
- You can omit the brackets `{}` if there is a single statement inside the if or else.
```JavaScript
if(condition)
    console.log("Hello"); // Single Statement
else
    console.log("Bye"); // Single Statement
```
- You can chain if-else statements.
```JavaScript
if(condition1) {
    // Runs if condition1 is true...
} else if(condition2) {
    // Runs if condition1 is false and condition2 is true...
} else if(condition3) {
    // Runs if both condition1 and condition2 are false and condition3 is true...
} else {
    // Runs if condition1, condition2, and condition3 are false...
}
```

### Logical Operators 
- The and (`&&`) operator.
- `condition1 && condition2` evaluates to true if both `condition1` and `condition2` evaluates to true. Otherwise it is false.
```JavaScript
console.log(true && true) // true
console.log(false && true) // false
console.log(false && false) // false
console.log(true && false) // false

//E.g.
console.log(1 > 0 && 1 > 2) // false, becuase 1 > 2 is false.
```
- The or (`||`) operator.
- `condition1 || condition2` evaluates to true if at least one condition is true. Otherwise it is false.
```JavaScript
console.log(true || true) // true
console.log(false || true) // true
console.log(true || false) // true
console.log(false || false) // false

//E.g.
console.log(1 > 0 || 1 > 2) // true, because the left side(1 > 0) is true.
```
- The not(`!`) operator.
- `!condition` evaluates to true if condition is false. Otherwise it is false.
```JavaScript
console.log(!true) // false
console.log(!false) // true

//E.g.
console.log(!(1 > 0)) // false, because (1 > 0) is true and we flip it to get false.
```

### Scope
- If statements creates a scope (with the `{}`). A scope is an imaginary box that limits variable created to only exist inside of it.
```JavaScript
if(true) {
    const num = 0;
    console.log(num); // 0.
}
console.log(num); // Error. num only exist inside the curly brackets({}) of the if-statement.
```
- Variables with the same name can be created in different scopes.
```JavaScript
const num = 0;
if(true) {
    // It is possible to create another num because it is in a different scope.
    const num = 3; 
    console.log(num); // 3
}
console.log(num); // 0. Uses the num created in this scope.
```
- If a variable is not found in the current scope the outer scope is searched.
```JavaScript
const num = 0;
if(true) {
    console.log(num); // 0. Uses the num created in the outer scope.
}
```
- If you want to use a variable created inside of an if-statement you have to move it outside.
```JavaScript
// Bad
if(true) {
    const num = 0;
    console.log(num); // 0
}
console.log(num); // Error
```
```JavaScript
// Good
const num = 0;
if(true) {
    console.log(num); // 0
}
console.log(num); // 0
```
- Note: variable created by `var` scope to the immediate function body and `let` scope to the enclosing block created by `{}`.
- `var` should be avoided as it can cause some weird errors with scoping.
```JavaScript
const num = 0;
if(true) {
    var num = 0; // Error. 
}
```

### Truthy and Falsy values
- If-statements can work with any type of value, not just booleans. 
- Falsy Values
    - `false`
    - `0`
    - `''` or `""`
    - `NaN` - Invalid math. E.g. `"3" / 2` = `NaN`.
    - `undefined` - No value assigned. E.g. 
        ```JavaScript
        let num;
        console.log(num); // undefined
        // const needs a value so we can directly assign it undefined.
        const num2 = undefined;
        console.log(num2) // undefined
        ```
    - `null`
- All other values are Truthy.
```JavaScript
if(0) {
    // 0 is Falsy. Code wont run.
}
if(3) {
    // 3 is Truthy. Code will run.
}
if("") {
    // "" is Falsy. Code wont run.
}
if("Hot Day") {
    // "Hot Day" is not "", it's Truthy. Code will run.
}
```
- Truthy and Falsy values also work with logical operators.
```JavaScript
if(3 && !"") {
    // Code will run. 
    // 3 is truthy. 
    // "" is falsy, but !"" flips it to true. 
    // Both sides of the && is true so code will run.
}
```

### Ternary Operator `?`
- `condition ? 'truthy' : 'falsy'` Short hand for if-else statement below.
```JavaScript
if(condition) {
    'truthy'
} else {
    'falsy'
}
```
- You can store the result of the ternary operator into a variable.
```JavaScript
const num = true ? 1 : 0;
console.log(num); // 1
```

### Guard Operator `&&`
- Guard operator is a special effect of the and `&&` operator.
- Suppose we have the statement `condition1 && condition2`. If `condition1` is false we know that the whole thing evaluates to false so we dont run `condition2`. This is known as **Short-Circuit Evaluation**.
```JavaScript
false && console.log("Noob"); // [Prints nothing]
```
- We can store the result of the guard operator into a variable.

```JavaScript
const value1 = true && false;
console.log(value1); // false

const value2 = false && "Watermellon";
console.log(value2); // false, because the code doesn't move on to the second condition.
```
- Note: the guard operator can evaluate to not only boolean values but other values as well.
```JavaScript
const value3 = true && "Watermellon";
console.log(value3); // Watermellon, 

const value4 = 3 && "Watermellon";
console.log(value4); // Watermellon, because 3 is truthy so we continue to run the next condition.

const value5 = "" && "Watermellon";
console.log(value5); // "", because "" is falsy. We don't move to the next condition and "" is stored.
```
- If-statement equivalents to the code above.
```JavaScript
let value3 = true;
if(value3) {
    value3 = "Watermellon";
}
console.log(value3); // Watermellon, 

let value4 = 3;
if(value4) {
    value4 = "Watermellon";
}
console.log(value4); // Watermellon

let value5 = "";
if(value5) {
    value5 = "Watermellon";
}
console.log(value5); // ""
```

### Default Operator `||`
- Default operator is a special effect of the and `||` operator.
- Suppose we have the statement `condition1 || condition2`. If `condition1` is true we know that the whole thing evaluates to true, so we can skip evaluating `condition2`.
```JavaScript
// User chooses EUR as currency.
let userCurrency = "EUR";
const currency = userCurrency || "USD";
console.log(currency); // EUR

// If user don't choose a currency. We use USD as default.
userCurrency = undefined;
const currency2 = userCurrency || "USD";
console.log(currency2); // USD
```
- If-statement equivalents to the code above.
```JavaScript
// User chooses EUR as currency.
let userCurrency = "EUR";
let currency = userCurrency;
if(!currency) {
    currency = "USD";
}
console.log(currency); // EUR

// If user don't choose a currency. We use USD as default.
userCurrency = undefined;
let currency2 = userCurrency;
if(!currency2) {
    currency2 = "USD";
}
console.log(currency2); // USD
```

## Functions
Functions lets you reuse code.
```JavaScript
function hello() {
    console.log("Hello there");
}

hello(); // Hello there
hello(); // Hello there
hello(); // Hello there
// ...
// You can reuse the function as many times as you want.
```
- Functions are created with the `function` keyword.
- The name of the function is next and follow the same rules as variable names.
    - No keywords: E.g. let, function, etc.
    - Can't start with a number.
    - Can't use special characters except `$` `_`.
    - Best practice: Use camelCase. E.g. `sayHello`
- Finally, the code goes inside the `{}` of the funcion.
- Note: Creating the function doesn't run the code. You have to call it by typing the function name with `()`. E.g. `hello()`.
```JavaScript
// Creating the function. Doesn't run the code yet.
function sayHello() {
    console.log("I said hello!");
}

// Calling the function
sayHello(); // I said hello!
```
### Function Scope
- Function creates a scope. All variables created inside the function only exist inside the function.
```JavaScript
function checkWeather() {
    const weather = "sunny";
    console.log(weather);
}

checkWeather(); // sunny
console.log(weather); // Error, weather only exist inside the function.
```

### Return statement
- The `return` keyword allows you to get back a value from a function.
```JavaScript
function getSecretNumber() {
    return 2;
}

// Stores the secret number in a variable.
const secretNumber = getSecretNumber(); 
console.log(secretNumber); // 2

// Directly prints the secret number to the console.
console.log(getSecretNumber()); // 2
```
- Other things we can return.
```JavaScript
// Calculation
return 5 + 10;
// Variables
return secretNumber;
// Anything else that results in a value.
return getSecretNumber();
```
- If no return value is provided, undefined will be returned.
```JavaScript
function getCreditCardNumber() {
    return;
}
console.log(getCreditCardNumber()) // undefined
```
- A return statement ends the function immediately.
```JavaScript
function tellJoke() {
    console.log("Knock Knock.");
    console.log("Who's there?");
    // early return. The rest of the function is not called.
    return;
    console.log("Joe");
}
tellJoke(); // Knock Knock. 
            // Who's there?
```

### Parameter
- A **Parameter** is a special variable that store the value passed into functions.
- An **Argument** is the actual value that is passed into a function when it is called.
- We can create parameters by putting them into the `()` of a function.
- Parameter naming rules follow the same rules as variable and functions.
- The values that we pass into a function are called **arguments**.
```JavaScript
// function with a single parameter name.
function printFavoriteColor(name) {
    if(name === "Bob") {
        console.log("Green");
    } else if(name === "Steve") {
        console.log("Yellow");
    } else {
        console.log("Unknown");
    }
}

// "Bob", "Steve", and "Bill" are arguments.
printFavoriteColor("Bob") // Green
printFavoriteColor("Steve") // Yellow
printFavoriteColor("Bill") // Unknown
```
- We seperate multiple parameters with a `,`.
```JavaScript
// Returns num1 if it is bigger. Otherwise return num2.
function getMax(num1, num2) {
    if(num1 > num2) {
        return num1;
    }
    return num2;
}
console.log(getMax(2, 3)); // 3
console.log(getMax(5, 5)); // 5
```
### Default Values
- If you dont provide a value to a function the parameter's value will be `undefined`.
```JavaScript
function print(value) {
    console.log(value);
}
print("Hello"); // Hello
print(); // undefined
```
- You can provide a default value to the parameter.
```JavaScript
function print(value = "Empty") {
    console.log(value);
}
print("Hello"); // Hello
print(); // Empty
```


## Objects

Objects are values that act as a container to group other values.

```JavaScript
const person = {
    firstName: "John",
    lastName: "Smith",
    age: 38
}
```
- In the example above, `firstName`, `lastName`, and `age` are all **properties** of the object.
- The **values** of these properties appear after the colon `:`.
- Each of the **property-value pairs** is separated by a comma `,`.
- Using `typeof` keyword on an object will return `'object'`.

### Accessing the values
```JavaScript
const person = {
    firstName: "John",
    lastName: "Smith",
    age: 38
}

console.log(person.firstName); // John
console.log(person.age); // 38
console.log(person); // {firstName: 'John', lastName: 'Smith', age: 38}
```
- The value of a property that doesn't exist is undefined
```JavaScript
// ... 
console.log(person.dontExist); // undefined
```
### Changing the value
```JavaScript
const person = {
    firstName: "John",
    lastName: "Smith",
    age: 38
}
person.firstName = "Bob";
console.log(person.firstName); // Bob
```
### Adding a value
```JavaScript
const person = {
    firstName: "John",
    lastName: "Smith",
    age: 38
}
person.eyeColor = "Blue"
console.log(person.eyeColor); // Blue
```
### Removing a value
```JavaScript
const person = {
    firstName: "John",
    lastName: "Smith",
    age: 38
}
delete person.age;
console.log(person.age); // undefined
```

### Bracket notation
- Before we used **dot notation** to read, update, and delete values. We can also use **bracket notation**.
    - We can also use **bracket notation** to access values.
    ```JavaScript
    // ... 
    // dot notation
    console.log(person.firstName); // John
    // bracket notation equivalent
    console.log(person["firstName"]); // John
    ```
    - To create/update values.
    ```JavaScript
    // ... 
    // dot notation
    person.eyeColor = "Blue"
    // bracket notation equivalent
    person["eyeColor"] = "Blue"
    ```
    - To delete values
    ```JavaScript
    // ... 
    // dot notation
    delete person.age;
    // bracket notation equivalent
    delete person["age"];
    ```

- You don't need to put strings inside the brackets. Any values or an expression that evaluates to a value will work.
    ```JavaScript
    // ...
    const property = "height";
    // property is a variable with a value of "height".
    person[property] = 60;
    console.log(person[property]); // 60
    ```

- When creating objects the following syntax is also allowed
    ```JavaScript
    const person = {
        firstName: "John",
        ["lastName"]: "Smith", // bracket notation
        "age": 38 // using a string
    }
    ```

### When to use bracket notation
In general, stick with **dot notation**, and only use **bracket notation** for properties that don't work with **dot notation**.
- E.g. `person.first-name` will cause error. Use `person["first-name"]`.


### Nested objects
Objects can have properties with another object as the value.
```JavaScript
const person = {
    name: {
        firstName: "John",
        lastName: "Smith",
        middleName: ""
    }
    age: 38,
}
```
To change the value of the first name we will use **dot notation** twice.
```JavaScript
// ...
// person.name gives us the name object. Then we add .firstName.
person.name.firstName = "Sam";
console.log(person.name.firstName); // Sam
```

### Function as a value
Another type of value is a function. Functions can then also be stored in variables and objects.
- Functions inside of objects are also called **methods**.
```JavaScript
const person = {
    name: "John Smith",
    sayHello: function() {
        console.log("Hello");
    }
}
console.log(person.sayHello()); // Hello
```

### JSON
- JSON is a file format used to store data.
- It uses very similar syntax to JavaScript objects.
```JSON
{
    "firstName": "Sam",
    "lastName": "Smith",
    "age": 35
}
```
- The JSON format can be understood by many different programming languages.

We can use `JSON.stringify()` to convert JavaScript Objects into JSON format.
```JavaScript
const person = {
    firstName: "John",
    lastName: "Smith",
    age: 38
}
const personJSON = JSON.stringify(person);
console.log(typeof personJSON); // string
console.log(personJSON); // {"firstName":"John","lastName":"Smith","age":38}
```
Converting the JSON string back to a JavaScript Object using `JSON.parse()`.
```JavaScript
const personObject = JSON.parse(personJSON);
console.log(typeof personObject); // object
console.log(personObject); // {firstName: 'John', lastName: 'Smith', age: 38}
```

### localStorage
Local Storage can be used to save data onto the browser. The data can be loaded the next time the application runs.

Save data:
```JavaScript
// setItem(key, value). key and value are both strings.
localStorage.setItem("message", "hello there!");
```
Get data:
```JavaScript
// getItem(key).
const message = localStorage.getItem("message");
console.log(message); // hello there!
// getItem returns null if the item is not found.
const money = localStorage.getItem("money");
console.log(money); // null
```
Remove data:
```JavaScript
localStorage.removeItem("message");
```
Remove all data:
```JavaScript
localStorage.clear();
```

### null vs undefined
`null` is a value used when we intentionally want something to have no value.

Unlike `undefined` we can use `null` to avoid using the default value of a parameter.
```JavaScript
function speak(message = "hello") {
    console.log(message);
}

speak(); // "hello"
speak(undefined); // "hello"

speak(null); // null
```
In most cases, `null` and `undefined` works the same way.

### Auto-boxing
When a method or property is accessed on a value (e.g. a string, number, boolean). A temporary **wrapper object** is created.

These built-in objects include `String` for strings, `Number` for numbers, and `Boolean` for booleans. (there are more)

This allows us to run methods directly on strings, numbers, etc.

```JavaScript
const message = "hello".toUpperCase();
console.log(message); // "HELLO"
```

### Objects are references
When we store a new object in a variable. A reference to the object's location in memory is stored.  
This means that if we assign the variable to a new variable, the new variable will be an alias for the same object.

```JavaScript
const object1 = {
    message: "hello",
}
// copy by reference.
const object2 = object1;
object1.message = "good night",

console.log(object1.message); // "good night"
console.log(object2.message); // "good night"
``` 
- Notice how in the code above `object1`'s and `object2`'s messages are both `"good night"`, even though we only set `object1`'s message to `"good night"`? This is because both `object1` and `object2` reference the same object in memory. 
- Also notice how we can change the message of `object1`(with `object1.message`) even though we are using `const`. This is because `object1` stores a reference to the object. Since the reference is not changed, `const` rules are not broken.

Since object references are stored, if we create two objects with the same properties and values they will not be equal.

For them to be equal both need to reference the same object in memory.
```JavaScript
const object1 = {
    message: "hello",
}
const object2 = {
    message: "hello",
}
const object3 = object2;
console.log(object1 === object2); // false
console.log(object2 === object3); // true

// Comparing values works as usual.
console.log(object1.message === object2.message); // true
```

### Shortcuts for objects
#### **Destructuring**  
A shortcut that allows us to store object values into a variable.

Let's say we want to store the object's property to a variable. If the property's name is the same as the variable's name we can use a shortcut called destructuring.
```JavaScript
// Not using destructuring
const person = {
    name: "Andy",
    age: 30,
}
const name = person.name;
const age = person.age;
```
```JavaScript
// Using destructuring 
const person = {
    name: "Andy",
    age: 30,
}
const { name, age } = person;
console.log(name); // "Andy"
console.log(age); // 30
```
- Notice how the variable names have to match the object's property names.
- The order of `{ name, age }` doesn't matter. If we do `{ age, name }`, `age` will still be `30` and `name` will still be `"Andy"`.

#### **Shorthand property**  
There is also a shortcut to creating objects. For example, let's say we are creating an object called `person`.
```JavaScript
// Not using the shorthand property
const name = "Andy";
const age = 30;

const person = {
    name: name,
    age: age,
}
```
We can shorthand this since the property name matches the variable name.
```JavaScript
// Using the shorthand property.
const name = "Andy";
const age = 30;

const person = {
    name,
    age,
}
```

#### **Shorthand method**  
We can create functions in objects without specifying the `function` keyword and the function's name.
```JavaScript
// Normally
const person = {
    name: "Andy",
    age: 30,
    speak: function sayHello() {
        console.log("hello");
    }
}
console.log(person.speak()); // "hello"
```
```JavaScript
// With shorthand method.
const person = {
    name: "Andy",
    age: 30,
    speak() {
        console.log("hello");
    }
}
console.log(person.speak()); // "hello"
```

## More coming soon



## Credits
This study guide is based on the material from ["JavaScript Tutorial Full Course - Beginner to Pro"](https://youtu.be/EerdGm-ehJQ?si=DwCl2GqrbDYP0rce) by SuperSimpleDev.

