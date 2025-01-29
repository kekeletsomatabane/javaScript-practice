## 📄JavaScript questions 

> **Note:**
>These questions test concepts covered in week 10 and assume knowledge of concepts from week 8 and 9. 

---
1. ### Would you use a 'for' or 'while' loop? 

   You want to write a program that asks the user to input numbers randomly until they enter a number less than 10 and greater than 0. Which type of loop is most appropriate for this task?
  
2. ### Write a loop that sums numbers from 1 to 20

   ```javascript
   let sum = 0;
   // write your loop here

   console.log(sum) // should output 210 
   ```
  
    Why is it important for `sum` to have a value of `0` before we loop?
    
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
   
4. ### Given

   ```javascript
   const nums = [21, 45, 100, 12, 11, 78, 61, 4, 39, 2];
   ```
   Write a program that logs to the console: 
    
      a. Only the even numbers

      b. Only those greater than 10 and less than 60

     c. Those greater than 10 and less than 60 that are even. 


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


   
