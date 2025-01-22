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

2. ### What is the output? 

   ```javascript
   let a = [1, 2, 3];
   let b = [4, 5, 6];
   console.log(a + b);
   ```

3. ### What is the length of 'numbers'?
 
   ```javascript
   let numbers = [20, 40, 60, [80, 100, 120]];
   ```

4. ### Amazon Prime members get free shipping regardless of cart total, while non-Prime members get free shipping only on orders of $50 and more. Otherwise, shipping is $5. Represent this as a conditional statement and calculate the final total, given the following: 

   **Customer1**: cartTotal is $52 and she is a prime member.

   **Customer2**: cartTotal is $15 and she is not a prime member.

   (Use `cartTotal`, `shippingCost`, `isPrimeMember` and `finalTotal` in your program) 

   **Note**: each customer must have their own conditional statement. 

5. ### What is logged and why? 

   ```javascript
   let java = 'JavaScript';
   java.length = 4;

   let colours = ['red', 'blue', 'yellow', 'green', 'pink', 'brown'];
   colours.length = 4;

   console.log(java);
   console.log(colours);
   ```

6. ### What is logged and why?

   ```javascript
   const a = [4, 8, 12];
   const b = [4, 8, 12];
   const c = 16 ** 2;
   const d = 64 * 4;

   console.log(a === b);
   console.log(c === d);
   ```

7. ### True or false? 

   **A**. In JavaScript an `if statement` can be used without an `else statment`. 

   **B**. The condition `if(0);` will execute the **if** block. 

8. ### What is logged? 

   ```javascript
   let arr = Array(5);
   console.log(arr);

   let arr2 = Array(8, 60);
   console.log(arr2);
   ```

9. ### Why does this code throw a SyntaxError?

   The following code is supposed to update the variable ‘counter’ multiple times.

   ```javascript
   let counter = 20;
   let counter = 40;
   counter = 50;
   ```

10. ### What value is logged? 

    ```javascript
    let x = 100;

    if (x < 100){
     x = 20;
    }
    console.log(x);
    ```

11. ###  True or false? These two conditions are equivalent.

    ```javascript
    if (a >= 0);
    if (a == 0 || a > 0);
    ```

12. ### The 'nums' array is now (choose options given)

    ```javascript
    const nums = [208, 60, 7];
    nums.push(100, 36, 15);
    ```
    **A**. [208, 60, 7, [100, 60, 15]]

    **B**. [208, 60, 7, 15, 100, 36]

    **C**. [208, 60, 7, 100, 36, 15]
