## 📄JavaScript questions

> **Note:**
>These questions test concepts covered in week 11 (Funtions) and assume knowledge of concepts from week 8, 9 and 10. 

---

1. ### What is the output of the last 3 lines?

```javascript
let number = 25;

function chnageNumber(){
  number = 32;
}

console.log(number);
changeNumber();
console.log(number);
```

<details><summary><b>Answer</b></summary>
   <p>

   Let's breakdown what the code does:

   `let number = 25` declares a variable and assigns it a value of `25`.

   The function `changeNumber`, when called will change (reassign) the value of `number` to `32`. 
   After the function is called the `number` variable is permanently changed to `32`. 

   So the last 3 lines: 
    
  - The first `console.log(number)` outputs `25`, at this point number still has the same value it was initialised with. 
  - The `changeNumber()` function call reassigns the value of the variable `number` to `32`
  - The second `console.log(number)` outputs `32` because now `number` has been reassigned a new value. 

  **What's important here??** To remember that functions only execute their code when called, not when they are declared. 
   </p>
 </details>

---
  

2. ### What's wrong with this code? 

This function is suppoed to return the price with the tax added. 

```javascript
function addTax(price){
  price * 1.2;
}

console.log(addTax(80));
```

<details><summary><b>Answer</b></summary>
   <p>

   The issue with the code is that the function `addTax` does not return the calculated value. It calculates the price with added tax but never returns it. 

   In JavaScript, if a function does not **explicitly** return a value, it implicitly returns `undefined`.

   How to fix the code: 
   ```javascript
   function addTax(price){
     return price * 1.2; // Return the calculated value
   }

   console.log(addTax(80)); // outputs: 96
   ```

   </p>
 </details>

---
  

3. ### Declare a function called `calculateResult` that:

 - Takes an array of 4 test marks (assume marks are from 0-100)
 - Calculates the semester average (rounded to the nearest integer use `Math.round()`)
 - Assigns a symbol based on this grading scale:
  
    - **A**: 75+
    - **B**: 70 - 74
    - **C**: 60 - 69
    - **D**: 50 - 59
    - **F**: Below 50
    
  - Returns a formatted multiline string containing:
    
    - The calculated average
    - The symbol
    - Status: 
      
      - Passed (for symbol B, C and D)
      - Passed with Distinction (for symbol A) 
      - Failed (for symbol F)
  
  Example output:
  ```
  Semester 1 2025
  Mark: 68%
  Symbol: C
  Status: Passed

  or

  Semester 1 2025
  Mark: 82%
  Symbol: A 
  Status: Passed with Distinction
  ```
  Test your function with these arrays:
  ```javascript
  const student1 = [65, 75, 90, 82];
  const student2 = [42, 50, 33, 49];
  const student3 = [58, 66, 72, 62];

  console.log(calculateResult(student1));
  console.log('\n-----\n')
  console.log(calculateResult(student2));
  console.log('\n-----\n')
  console.log(calculateResult(student3));
  ```

  <details><summary><b>Answer</b></summary>
   <p>

   ```javascript
   function calculateResults(marks){
  let average = 0, sum = 0;
 
  for (let mark of marks){
   sum += mark;
  }
 
  average = Math.round(sum / marks.length);
 
  let symbol;
   if (average >= 75) {
       symbol = 'A';
   } else if (average >= 70) {
       symbol = 'B';
   } else if (average >= 60) {
       symbol = 'C';
   } else if (average >= 50) {
       symbol = 'D';
   } else {
       symbol = 'F';
   }
  
   let status;
   if (average >= 50){
     status = average >= 75 ? 'Passed with Distinction' : 'Passed'; // Ternary operator, look it up. 
   }else{
     status = 'Failed';
   }
 
   return `Semester 1 2025 \nMark: ${average}% \nSymbol: ${symbol} \nStatus: ${status}`
  }
   ```
   #### Additional: 
   - Add validation to handle cases where the input array is not an array or contains non-numeric values. 
---
   </p>
 </details>

  
  

4. ### What does this function do? 

Function takes an array of numbers as its argument. 

```javascript
function findSomething(array){
  if (array.length === 0){
     return null; 
  } 

  let something = array[0];
  for (let i = 1; i < array.length; i++) {
      if (array[i] < something) {
          something = array[i];
      }
  }
  return something;
}

// example test cases
findSomething([3, 1, 4, 1, 5]);
findSomething([-2, 0, -5, 1]);
```

  **a**. Finds the maximum number in an array

  **b**. Finds the minimum number in an array

  **c**. Finds the first negative number in an array

<details><summary><b>Answer</b></summary>
   <p>

   ### Answer: b. Finds the minimum number in an array

   The function `findSomething` is designed to find the smallest (minimum) number in an array of numbers. 

   Here is how it works:
    
  - The function first checks if the input array is empty `(array.length === 0)`. If it is, the function returns `null` because there is no smallest number to find.

  - If the array is not empty, the function initializes a variable `something` with the first element of the array `(array[0])`. This assumes that the first element is the smallest number initially.

  - The function then iterates through the array starting from the second element `(i = 1)`.

  - During each iteration, it compares the current element `(array[i])` with the value stored in `something` and if the current element is smaller than `something`, it updates `something` to the current element.

  - After the loop finishes, the function returns the value of `something`, which is now the smallest number in the array.

  - When using the **example test cases**: it outputs `1` and `-5`, those are the smallest numbers in their arrays. 

  Function with semantic identifiers:
  
  ```javascript
  function findMinValue(numbersArray) {
  if (numbersArray.length === 0) {
    return null;
  }

  let minValue = numbersArray[0];
  for (let i = 1; i < numbersArray.length; i++) {
    if (numbersArray[i] < minValue) {
      minValue = numbersArray[i];
    }
  }

  return minValue;
  }
  ```

  #### Did you know that JavaScript has a `Math.min()` function you can use to find the smallest number among a set of values or an array of numbers? 

   </p>
 </details>