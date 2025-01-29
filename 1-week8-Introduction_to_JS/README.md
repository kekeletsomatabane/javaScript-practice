## 📄JavaScript questions 

> **Note:**
>These questions test concepts covered in Week 8 (Introduction to JS)

---

1. #### What happens when a variable is initialised without prior declaration in JavaScript and used in the program? 

   <details><summary><b>Answer</b></summary>
    <p>

    #### Answer:

    This creates an implicit **global variable** if the code is run in non-strict mode. 
    The variable becomes a property of the global object 'window' in a browser environment and 'global' in Node.js. 


    However, if the code is run in strict mode (`'use strict'`) attempting to assign a value to an undeclared variable will result in a  `ReferenceError`. 
    So, to avoid unintended consequences and improve code clarity, always declare variables before using them. This helps prevent scope issues and makes the code easier to understand and maintain. 
   </p>
 </details>

---

2. #### The JS programming language is:

   a. Interpreted

   b. Compiled

   c. Just-in-time compiled

   <details><summary><b>Answer</b></summary>
   <p>

   #### Answer: C
 
   In its early days, JavaScript was interpreted. Modern JavaScript engines (like V8 in Chrome and Node.js, SpiderMonkey in Firefox, etc.) use a JIT compiler. They first parse and optimize the code into an intermediate representation (bytecode) and then compile parts of the code into machine code as it's executed, to improve performance. 

   **Just-in-time compilation** is a hybrid approach. Combines the speed benefits of compilation with the flexibility of interpretation.
 </p>
</details>

---

3. #### True or false? 
  
   You can store any data type in a JS variable and the interpreter determines the type at runtime.

   <details><summary><b>Answer</b></summary>
     <p>

    #### Answer: True

    This is because JavaScript is a **dynamically typed** language, meaning variables do not have a fixed type. You can store any data type (numbers, strings, arrays, functions, etc.) in a JavaScript variable, and the JavaScript engine determines the type of the value at runtime.

    This is different from statically typed languages like Java or C++, where you must declare the variable's type.
    </p>
 </details>

---

4. #### True or false? 

   There is an error with this code: 
   ```javascript
   let name = 'John Doe', age = 22, hasCar = true;
   ```

   <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: False

    The code shown is perfectly valid JavaScript syntax where multiple variables are declared in a single statement using the `let` keyword, with each variable initialization separated by commas.

    This syntax is equivalent to writing: 
     ```javascript
     let name = 'John Doe';
     let age = 22;
     let hasCar = true;
     ```
    </p>
  </details>

---
5. #### True or false? 

    Variables declared with 'const' must be initialised immediately. 

   <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: True

    Variables declared with `const` must be initialized at the time of declaration. If you try to declare a `const` variable without initializing it, you will get a syntax error. For example:
    ```javascript
    // this throws a syntax error
    const price; 

    // must declare and initialise immediately
    const price = 106;
    ```

    This is different from `let`, where variables can be declared without initialization. 
    ```javascript
    // you can delcare a variable here...
    let x;

    // and initialise later
    x = 89;
    ```
    </p>
 </details>
 
---
6. #### True or false?

    Variable 'a' is a Boolean type.
   ```javascript
   const a = 'true';
   ```

   <details><summary><b>Answer</b></summary>
    <p>

   #### Answer: False

   Variable `a` is not a Boolean type, it's a string type. The quotation marks '...' indicate that 'true' is a string literal. To compare:

    ```javascript
    const a = 'true';
    console.log(typeof a); // outputs: string

    const b = true;
    console.log(typeof b); // outputs: boolean
    ```

   These would behave differently in comparisons and operations. 

</p>
</details>

---

7. #### The result of this operation is 131

   ```javascript
   let solution = 125 + '6';
   ``` 

   <details><summary><b>Answer</b></summary>
   <p>

   #### Answer: The result of this operation is '1256'

    JavaScript performs string concatenation rather than numerical addition because one operand is a string.  The number `125` is converted to a string and then concatenated with `'6'`, resulting in `'1256'`.

    ```javascript
   //  number + number = number
   console.log(12 + 8); // outputs: 20

   //  number + string = string
   console.log(15 + '6'); // outputs: '156'

   //  string + string = string
   console.log('80' + '6'); // outputs: '806'
   ```

   This is due to JavaScript's type coercion rules - when the `+` operator is used with a string, it favors string concatenation over numerical addition. The answer 131 would only be correct if both operands were numbers.

</p>
</details>

---

8. #### What is logged to the console and why?

   ```javascript 
   let result2 = 10 / '2 apples';
   console.log(result2);

   let result3 = 10 / '5';
   console.log(result3);
   ```

   <details><summary><b>Answer</b></summary>
   <p>

   #### Answer: NaN and 2

   There 2 types of strings: **numeric** and **non-numeric** strings. A numeric string in JavaScript is a string that represents numeric values. Its characters can be interpreted as valid numbers. 

   These are **numeric strings**: '123', '2.66', '-96'

   These are **non-numeric** strings: 'ten', '12 eggs', '58g'

   **Numeric strings** are `implicitly coerced` to numbers in arithmetic expressions (except for in `+` operations) and **non-numeric strings** are `implicitly coerced` to `NaN` in arithmetic expressions (except for in `+` operations).

   So:
   ```javascript
   // Non-numeric string coerced to NaN in an arithmetic operation
   let result2 = 10 / '2 apples';
   console.log(result2); // outputs: NaN

   // Numeric string coerced to number in arithmetic operation
   let result3 = 10 / '5';
   console.log(result3); // outputs: 2
   ```

   The result of dividing any number by `NaN` is `NaN`.
</p>
</details>

--- 

9. #### True or false?
 
   The toFixed( ) method always returns a string.

   <details><summary><b>Answer</b></summary>
   <p>

   #### Answer: True

    The `toFixed()` method in JavaScript always returns a string representation of a number, formatted to a specified number of decimal places. So:

    ```javascript
    let cost = 158.6663578;
    let costTo2 = cost.toFixed(2);
    console.log(typeof costTo2); // outputs: string
    ```
   **NB:** If you are going to perform any further arithmetic operations with the results of a `toFixed()` operation, you need to convert it to a `number` type (you can use `parseFloat()` to do that). 
</p>
</details>

---

### Bonus question:

10. #### These two expressions evaluate to the same value

    ```javascript
    let x = 5 ** 2;
    let y = Math.pow(5, 2);
    ```
    
    <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: Yes, they evaluate to the same value

    `let x = 5 ** 2;` uses the exponentiation operator (introduced in ES6) to raise the first operand to the power of the second. So, `x` is 25. `let y = Math.pow(5, 2);` uses the Math object method `Math.pow()` to compute 5 to the power of 2, which is 25.
</p>
</details>