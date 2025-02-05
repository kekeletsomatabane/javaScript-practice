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

2. ### What's wrong with this code? 

This function is suppoed to return the price with the tax added. 

```javascript
function addTax(price){
  price * 1.2;
}

console.log(addTax(80));
```

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