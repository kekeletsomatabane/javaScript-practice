## 📄JavaScript questions 

> **Note:**
>These questions test concepts covered in week 9 and assume knowledge of concepts from week 8. 

---

1. ### True or false? 

   **A**. An array is a data structure used to store multiple values in a single variable. 
  
   **B**. JS arrays cannot contain mixed data types. 

   **C**. Arrays can be created using the array literal or the array constructor function method. 

   **D**. Creating an empty array in JS will cause an error.

   **E**. You can access the last element of an array named **fruits** using `fruits[fruits.length]`.

   **F**. The array method `.includes()` is case insensitive. 

   **G**. Arrays are mutable and ordered.

   <details><summary><b>Answer</b></summary>
    <p>

    **A**. True

    In JavaScript, an array is a data structure used to store multiple values in a single variable. Arrays in JS can hold elements of any data type (numbers, strings, objects, etc.), and they are dynamic, meaning their size can change as elements are added or removed. 

    **B**. False

      Javascript arrays can contain mixed data types. Unlike some other programming languages, JavaScript arrays are flexible and can store elements of different types, such as numbers, strings, booleans, objects, or even other arrays. For example:

      ```javascript
      const mixedArr = [49, "Week9", true, { name: "Alice" }, [1, 2, 3]];
      ```
      This array contains a number, a string, a boolean, an object, and another array,


    **C**. True

     In JavaScript, arrays can be created using either the **array literal** method or the **array constructor function** method. Here’s how each works:

     1. **Array literal method**: This is the most common and recommended way to create an array. It uses square brackets [ ].

     ```javascript
     const myArr = [15, 32, 4, 87];
     ```

     2. **Array Constructor Function Method**: This uses the `Array` constructor function. 

     ```javascript
     let myArr2 = new Array(1, 2, 3, 4);
     ```

    **D**. False

    Creating an empty array in JavaScript will not cause an error. You can create an empty array using the following syntax:

    ```javascript
    let emptyArr = [];
    ```

    You can create an empty array in JavaScript and populate it later in your program. This is a common practice when you want to initialize a container for data that will be added dynamically during the execution of your program. 

    **E**. False

     JavaScript arrays are zero-indexed, valid indeces range from `0` (the first element) to `fruits.length - 1`. The expression `fruits[fruits.length]` would attempt to access an element one position past the end of the array, which results in `undefined`.

    **F**. False

     The `includes()` method is **case-sensitive**. 

    **G**. True

    Arrays in JavaScript are **mutable**, meaning you can change their content after they are created. You can add, remove, or modify elements in an array.

    ```javascript
    const fruits = ["Apple", "Banana", "Cherry"];
    fruits[1] = "Blueberry"; // Modifies the second element
    fruits.push("Orange"); // adds an element to the end of array
    
   console.log(fruits); // Outputs: ["Apple", "Blueberry", "Cherry", "Orange"]
   ```
   Arrays are **ordered**, elements in an array maintain their insertion order, meaning they stay in the order they were added unless explicitly modified.
   Note: In the above array, elements that were not modified maintained their insertion order. 

   </p>
 </details>

 ---


2. ### What is the output? 

   ```javascript
   let a = [1, 2, 3];
   let b = [4, 5, 6];
   console.log(a + b);
   ```
   <details><summary><b>Answer</b></summary>
   <p>

   ### Answer: 1, 2, 34, 5, 6

   Using the `+` operator on two arrays converts the arrays to strings and then concatenates them end to end, resulting in a single string (type coercion). If you wish to concatenate two arrays, use the `concat()` method.

   ```javascript
   let a = [1, 2, 3];
   let b = [4, 5, 6];
   let c = a.concat(b); 
   console.log(c); // outputs: [1, 2, 3, 4, 5, 6]
   ```

   **Note**: the `concat()` method can concatenate 2 or more arrays at once.

   </p>
 </details>

---

3. ### What is the length of 'numbers'?
 
   ```javascript
   let numbers = [20, 40, 60, [80, 100, 120]];
   ```
   
   <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: 4

    The `numbers` array contains 4 elements, element one: 20, element two: 40, element three: 60 and element four: [80, 100, 120]. 

    The nested array is counted as a single element in the outer array. 

    ```javascript
    console.log(numbers.length); // outputs: 4
    ```
   </p>
 </details>

 ---

4. ### Amazon Prime members get free shipping regardless of cart total, while non-Prime members get free shipping only on orders of $50 and more. Otherwise, shipping is $5. Represent this as a conditional statement and calculate the final total, given the following: 

   **Customer1**: cartTotal is $52 and she is a prime member.

   **Customer2**: cartTotal is $15 and she is not a prime member.

   (Use `cartTotal`, `shippingCost`, `isPrimeMember` and `finalTotal` in your program) 

   **Note**: each customer must have their own conditional statement. 

   <details><summary><b>Answer</b></summary>
    <p>

    ```javascript
    // Customer 1
    let cartTotal1 = 52;
    let isPrimeMember1 = true;
    let shippingCost1;

   if (isPrimeMember1 || cartTotal1 >= 50) {
      shippingCost1 = 0;
   } else {
      shippingCost1 = 5;
   }

   let finalTotal1 = cartTotal1 + shippingCost1;
   console.log(`Customer 1 final total is: $${finalTotal1}.`); // outputs: Customer 1 final total is $52.

   // Customer 2
   let cartTotal2 = 15;
   let isPrimeMember2 = false;
   let shippingCost2;

   if (isPrimeMember2 || cartTotal2 >= 50) {
      shippingCost2 = 0;
   } else {
      shippingCost2 = 5;
   }

   let finalTotal2 = cartTotal2 + shippingCost2;
    console.log(`Customer 2 final total is: $${finalTotal2}.`); // outputs: Customer 2 final total is $20.
    ```
   </p>
 </details>

 ---

5. ### What is logged and why? 

   ```javascript
   let java = 'JavaScript';
   java.length = 4;

   let colours = ['red', 'blue', 'yellow', 'green', 'pink', 'brown'];
   colours.length = 4;

   console.log(java);
   console.log(colours);
   ```
   
   <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: 'JavaScript' and ['red', 'blue', 'yellow', 'green']

    1. Strings are **immutable** 

    Strings in JavaScript are immutable, meaning their values cannot be altered after creation.

    The `length` property of a string is **read-only**, changing it doesn't do anything. 

    ```javascript
    let java = 'JavaScript';
    java.length = 4; // this line has no effect on the string
    console.log(java); // outputs: JavaScript
    ```

    2. Arrays are **mutable** in JS

    Arrays in JavaScript are mutable, meaning you can change their content after they are created. The `length` property of arrays can be used to modify the content of an array. 

    ```javascript
    let colours = ['red', 'blue', 'yellow', 'green', 'pink', 'brown']; // the array has 6 elements
    colours.length = 4; // this truncates the array to the first 4 elements
    console.log(colours); // outputs: ['red', 'blue', 'yellow', 'green']
    ```

    The `length` property behaves differently for strings and arrays. 

   </p>
 </details>

 ---
   
6. ### What is logged and why?

   ```javascript
   const a = [4, 8, 12];
   const b = [4, 8, 12];
   const c = 16 ** 2;
   const d = 64 * 4;

   console.log(a === b);
   console.log(c === d);
   ```

   <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: false and true

    `a` and `b` are both arrays with the same elements: `[4, 8, 12]`.
    In JavaScript arrays are compared by reference (location in memory) not value. So, for two arrays to be equal, they would have to point to the same location in memory. `a` and `b` are two arrays that point to different locations in memory, even though they have the same elements. So, `a === b` evaluates to `false`.

    These two arrays are considered equal:
    ```javascript
    const array1 = [5, 10, 15];
    const array2 = array1; 

    console.log(array1 === array2); // outputs: true, these two arrays point to the same location in memory. 
    ```

    Primitive types are compared based on value. Both `c` and `d` evaluate to `256` and they are primitive numbers, so their `strict equality` comparison evaluates to `true`, they have the same type and value. 

    **Note**: This distinction between reference types and primitive types is key to understanding how equality works in JavaScript. 
   </p>
 </details>

 ---
   
7. ### True or false? 

   **A**. In JavaScript an `if statement` can be used without an `else statement`. 

   **B**. The condition `if(0);` will execute the **if** block. 

   <details><summary><b>Answer</b></summary>
    <p>

    **A**. True

    In JavaScript, an `if` statement can be used without an `else` statement. 
    The `else` block is optional and is only used when you need to handle the case where the `if` condition is `false`. If you don't need to handle that case, you can omit the `else` block entirely.

    If the `if` condition is `true`, the code inside the `if` block runs, and if there is no `else` block, the program simply continues executing the rest of the code.

    **B**. False

    The condition `if (0)` will not execute the `if` block because `0` is a **falsy** value in JavaScript. When a falsy value is used as the condition in an `if` statement, the condition evaluates to `false`, and the code inside the `if` block is **not executed**. 

    The `if` block is skipped, and the program moves to the `else` block (if one exists) or continues executing the rest of the code.

    The following values are considered falsy:
     
     - false
     - 0 (zero)
     - "" (empty string)
     - NaN
     - null 
     - undefined

   </p>
 </details>

 ---

8. ### What is logged? 

   ```javascript
   let arr = Array(5);
   console.log(arr);

   let arr2 = Array(8, 60);
   console.log(arr2);
   ```

      <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: [<5 empty items>] and [8, 60]

    The `Array()` constructor function is one method that can be used to create arrays in JavaScript. 

    It has different behaviours depending on how you call it: 

    - **When called with a single numeric argument**: creates an array with that length. When `Array(5)` is called, this creates a new array with a length of `5`, but the array is empty (no elements defined).
    
    ```javascript
    let arr = Array(5);
    console.log(arr); // outputs: [<5 empty items>]
    console.log(arr.length); // outputs: 5, the array has 5 empty elements
    ```

    **Note**: It is recommended to use the array literal method when creating an array with a single numeric element. 

    - **When called with multiple arguments**: creates an array containing those elements. When `Array(8, 60)` is called, it creates a new array with the elements `8` and `60` as its contents.

    ```javascript
    let arr2 = Array(8, 60);
    console.log(arr2); // outputs [8, 60]
    ```

   </p>
 </details>

 ---

9. ### Why does this code throw a SyntaxError?

   The following code is supposed to update the variable 'counter' multiple times.

   ```javascript
   let counter = 20;
   let counter = 40;
   counter = 50;
   ```

      <details><summary><b>Answer</b></summary>
    <p>

    The code throws a `SyntaxError` because of this line: `let counter = 40`. 

    In JavaScript the `let` keyword is used to declare a variable. However, a variable declared with `let` **cannot be redeclared in the same scope,** this code is attempting to redeclare `counter` in the same scope it was declared in. 

    To successfully update the value of `counter`, reassign it. 

    ```javascript
    let counter = 20; // counter is declared and  initialised
    counter = 40; // counter is reassigned a new value
    counter = 50; // counter is reassigned another value
    ```

   </p>
 </details>

 ---

10. ### What value is logged? 

    ```javascript
    let x = 100;

    if (x < 100){
     x = 20;
    }
    console.log(x);
    ```

     <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: 100

    The variable `x` is initialised with the value `100`. 

    The `if` condition checks whether `x < 100`:

    - Since `x` is `100`, the condition `x < 100` evaluates to `false`.

    - Therefore, the code inside the if block `x = 20` (which is a reassignment of the value of `x`) is not executed.
  
    Thus the value of `x` remains `100` and  `console.log(x)` displays `100`.  

   </p>
 </details>

 ---

11. ###  True or false? These two conditions are equivalent.

    ```javascript
    if (a >= 0);
    if (a == 0 || a > 0);
    ```

     <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: True

    The two conditions are logically equivalent:

    `if (a >= 0);`

    This checks whether `a` is greater than or equal to `0`.

    `if (a == 0 || a > 0);`

    This checks whether `a` is equal to `0` OR greater than `0`.
    Since the `>=` operator already includes both cases `(a == 0 and a > 0)`, the two conditions are the same in terms of logic.

   </p>
 </details>

 ---

12. ### The 'nums' array is now (choose options given)

    ```javascript
    const nums = [208, 60, 7];
    nums.push(100, 36, 15);
    ```
    **A**. [208, 60, 7, [100, 36, 15]]

    **B**. [208, 60, 7, 15, 100, 36]

    **C**. [208, 60, 7, 100, 36, 15]

       <details><summary><b>Answer</b></summary>
    <p>

    #### Answer: [208, 60, 7, 100, 36, 15]

    The `push()` method adds one or more elements to the end of an array and returns the new length of the array.
    In this case: 
    
     - The `push(100, 36, 15)` method adds the elements `100`, `36`, and `15` to the end of the array **in the order they are passed**.

     - Here, `100` is added first, followed by `36` and then `15`.

   </p>
 </details>

