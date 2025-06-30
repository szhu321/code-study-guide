## JavaScript Sample Exam 2

1. **Which operator strictly checks both value and type equality in JavaScript?**  
   A) `==`  
   B) `===`  
   C) `!=`  
   D) `!==`  
    

2. **What is the result of `5 == "5"` in JavaScript?**  
   A) `true`  
   B) `false`  
   C) `5`  
   D) `"5"`  
 

3. **Which of the following is a falsy value in JavaScript?**  
   A) `1`  
   B) `"Hello"`  
   C) `0`  
   D) `"false"`  


4. **What does the guard operator (`&&`) return if the first operand is falsy?**  
   A) `true`  
   B) `false`  
   C) The second operand  
   D) The first operand  


5. **What is the result of `!0` in JavaScript?**  
   A) `true`  
   B) `false`  
   C) `0`  
   D) `undefined`  


6. **Which of the following is NOT a valid use of the ternary operator?**  
   A) `const result = condition ? "yes" : "no";`  
   B) `let result = condition ? let a = 5 : "no";`  
   C) `let a = 5 ? "truthy" : "falsy";`  
   D) `console.log(condition ? 1 : 0);`  


7. **What is the result of `true && "Hello"`?**  
   A) `true`  
   B) `"Hello"`  
   C) `false`  
   D) `undefined`  


8. **What is the purpose of the default operator (`||`)?**  
   A) To return the first falsy value in a sequence.  
   B) To return the second operand if the first is falsy.  
   C) To perform logical AND operations.  
   D) To return the first operand if the first is falsy.  


9. **Which of the following prints `"Hello"`?**  
   A) `console.log("Hello" && 5);`  
   B) `console.log("Hello" || 5);`  
   C) `console.log(5 && "Hello");`  
   D) Both B and C  


10. **What does the following code print out?**
    ```JavaScript
    if(true) {
        const num = 0;
    }
    console.log(num);
    ```  
    A) `0`  
    B) `undefined`  
    C) Cause an error  
    D) `"num"`  


11. **What keyword is used to create a function in JavaScript?**  
   A) `let`  
   B) `function`  
   C) `var`  
   D) `return`  


12. **Which of these is a valid function name according to naming rules?**  
   A) `1stFunction`  
   B) `my-function`  
   C) `myFunction`  
   D) `my function`  


13. **What is the result of `mystery(2)` if `mystery` is defined as:**  
    ```javascript  
    function mystery(num1, num2 = 5) {  
        return num1 + num2;  
    }  
    ```  
    A) `2`  
    B) `7`  
    C) `5`  
    D) `undefined`  


14. **Which of the following is true about function scope?**  
   A) Variables created inside a function cannot be accessed outside.  
   B) Variables created inside a function are accessible globally.  
   C) Functions cannot have nested scopes.  
   D) Variables created inside a function cannot have the same name as a global variable.  


15. **What does the `return` statement do in a function?**  
   A) Logs the result to the console.  
   B) Exits the function and optionally returns a value.  
   C) Declares a variable.  
   D) Calls another function.  


16. **What is the difference between a parameter and an argument?**  
   A) Parameters are values passed, arguments are names in the function.  
   B) Parameters are optional, arguments are required.  
   C) Parameters are always numbers, arguments are always strings.  
   D) Parameters are names in the function, arguments are values passed.  


17. **What is the default value of a parameter if no argument is provided?**  
   A) `null`  
   B) `undefined`  
   C) `0`  
   D) `"Empty"`


18. **Which of the following is an example of an early return?**  
   A) `return;` inside a function.  
   B) `console.log();` without a value.  
   C) `let x = 5;` inside a function.  
   D) `function()` without a body.  


19. **Which of these correctly demonstrates a function with a default parameter value?**  
   A) `function greet(name = "Guest") { ... }`  
   B) `function greet(name) { name = "Guest"; ... }`  
   C) `function greet(name, age) { ... }`  
   D) All of the above  


20. **What is the result of `mystery(3, 5)` if `mystery` is defined as:**  
    ```javascript  
    function mystery(num1, num2) {  
        return num1 > num2 ? num1 : num2;  
    }  
    ```  
    A) `3`  
    B) `5`  
    C) `undefined`  
    D) `null`  
