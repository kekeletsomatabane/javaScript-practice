## 📄JavaScript questions 

> **Note:**
>These questions test concepts covered in week 10 and assume knowledge of concepts from week 8 and 9. 

---
1. ### Would you use a 'for' or 'while' loop? 

   You want to write a program that asks the user to input numbers randomly until they enter a number less than 10 and greater than 0. Which type of loop is most appropriate for this task?

   <details><summary><b>Answer</b></summary>
   <p>

   ### Answer: A `while` loop is the most appropriate choice.

   You want to use the `while` loop because you don't know the number of iterations beforehand, only the condition when the loop should stop (Which depends on user input). You want to ask the user for input until they enter a number less than 10 and greater than 0. 

   **Why not a `for` loop?**  A for loop is not suitable here because it is designed for situations where the number of iterations is known in advance (e.g., iterating over an array or a fixed range).

   </p>
 </details>

---
  
2. ### Write a loop that sums numbers from 1 to 20

   ```javascript
   let sum = 0;
   // write your loop here

   console.log(sum) // should output 210 
   ```
  
    Why is it important for `sum` to have a value of `0` before we loop?

     <details><summary><b>Answer</b></summary>
   <p>

   ```javascript
   let sum = 0;

   for (let i = 1; i < 21; i++){
      sum += i;
   }

   console.log(sum); // outputs: 210
   ```

   It is important to initialise `sum` to `0` before we loop because inside the loop, we perform arithmetic operations (addition) on `sum`. 

   If `sum` was just declared without initialisation, it would have a default value of `undefined` and the value of `sum` would be `NaN` as we would attepmt to perform arithmetic operations on `undefined`. 

   The same principle applies to other operations:

    - For building strings, you might initialize with an empty string `""`.
    - For building arrays, you'd start with an empty array `[]`.
   </p>
 </details>

---
    
3. ### True or false? 

   These two loops do the exact same thing.

   ```javascript
   const teams = ['Liverpool', 'Juventus', 'AC Milan', 'FC Bayern'];

   // loop1
   for (let team of teams){
    console.log(team);
   }

   // loop2
   for (let i = 0; i <= teams.length; i++){
    console.log(teams[i]);
   }
   ```

   <details><summary><b>Answer</b></summary>
   <p>

   ### Answer: False

   These two loops do **not** do the same thing. 

   **Loop 1**: `for...of` loop
    
   - Iterates over the elements of the `teams` array directly.
   - It will print each element exactly once

   - It logs: 
    ```
    Liverpool
    Juventus
    AC Milan
    FC Bayern
    ```

   **Loop 2**: `for` loop

   - This loop uses `i` to access elements of the `teams` array (starting from the element at index `0` represented by `let i = 0`).
   - The last iteration, when `i = teams.length`, in this case `teams[4]` will log `undefined` because the last valid index of this array is `teams.length -1`
   - It logs:
   ```
   Liverpool
   Juventus
   AC Milan
   FC Bayern
   undefined
   ```

   - To make Loop 2 behave the same as Loop 1, you should change the condition to `i < teams.length`:
   ```javascript
   for (let i = 0; i < teams.length; i++) {
    console.log(teams[i]);
   }
   ```
   
   </p>
 </details>

---
   
4. ### Given

   ```javascript
   const nums = [21, 45, 100, 12, 11, 78, 61, 4, 39, 2];
   ```
   Write a program that logs to the console: 
    
      a. Only the even numbers

      b. Only those greater than 10 and less than 60

     c. Those greater than 10 and less than 60 that are even. 

     <details><summary><b>Answer</b></summary>
   <p>

    **a.**
    ```javascript 
    // a. even numbers
    for (let num of nums){
      if (num % 2 === 0){
        console.log(num);
      }
    }

    // b. Numbers between 10 and 60
    for (let num of nums){
      if (num > 10 && num < 60){
        console.log(num);
      }
    }

    // c. Even numbers between 10 and 60
    for (let num of nums){
      if (num > 10 && num < 60 && num % 2 === 0){
        console.log(num);
      }
    }
    ```

    Outputs:
    ```javascript
    // even numbers
    100
    12
    78
    4
    2

    // numbers between 10 and 60
    21
    45
    12
    11
    39

    // even numbers between 10 and 60
    12
    ```

   </p>
 </details>

---


5. ### Vowel counter: 

   Write a program that counts the number of vowels (a, e, i, o, u) in a given string. 

   Count the vowels in the string and log the count.

   Test your program using: 

   ```javascript
   const text = 'Hello world'; // count is 3
   const text2 = 'Glory glory Man United!'; // count is 6
   ```

   #### Extra requirement: 

     - Can you modify your program to also show which vowels were found?

   <details><summary><b>Answer</b></summary>
   <p>

   ```javascript
   // to test text
   const text = 'Hello world';
   let vowelCount = 0;
   let vowels = ['a', 'e', 'i', 'o', 'u'];

   for (let char of text.toLowerCase()){
     if (vowels.includes(char)){
       vowelCount++;
       console.log(`Vowel found: ${char}`);
     }
   }

   console.log(vowelCount);

   // te test text2
   const text2 = 'Glory glory Man United!';
   let vowelCount2 = 0; 

   for (let char of text2.toLowerCase()){
     if (vowels.includes(char)){
       vowelCount2++;
       console.log(`Vowel found: ${char}`);
     }
   }

   console.log(vowelCount2);
   ```
   </p>
 </details>



   
