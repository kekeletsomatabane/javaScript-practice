## 📄JavaScript questions

> **Note:**
>These questions test concepts covered in week 12 (Objects ans Classes) and assume knowledge of concepts from previous weeks. 

---

1. ### When should you use a class vs. an object literal in JS? 

<details><summary><b>Answer</b></summary>
   <p>

   The decision to use a **class** or an **object literal** in JavaScript depends on the complexity and reusability of your data structure. 

   #### Use an object literal when:
    
  - You need a single object: : Object literals are perfect for creating once-off objects with a fixed set of properties and methods.

  - You don't need to create multiple instances of similar objects: If you only need one instance of an object and don't plan to create more, an object literal is simpler and more concise. 

  - You need a lightweight data structure: Object literals are lightweight and easy to create, making them ideal for configuration objects, data transfer objects or simple key-value pairs.

  
  #### Use a class when:

  - You need multiple instances: Classes are ideal when you need to create multiple objects with the same structure and behavior. Each instance of a class can have its own state while sharing methods.

  - You need inheritance: Classes support inheritance, allowing you to create a hierarchy of objects with shared functionality.

  - You need encapsulation: Classes allow you to define private fields and methods (using # or WeakMap), which can help encapsulate data and behavior.

  | Feature | Class    | Object Literal |
| ---- | ------------------- | ------------------------------------------------------------------ |
| Instances  | Can create multiple instances |Single instance only |
| Inheritance   | Supports inheritance       | No inheritance support  |
| Encapsulation   | Supports private fields/methods | No built-in encapsulation |
| Structure   | 	Formal and scalable               | 	Simple and lightweight  |
| Use case  | Complex, reusable objects             | Simple, one-off objects  |

   </p>
 </details>

---

2. ### What is wrong with this loop?

What is logged to the console? 

```javascript
const obj1 = {
  a: 100,
  b: 200,
  c: 300
}

for (let key in obj1){
  console.log(`${key}: ${obj1.key}`);
}
```

<details><summary><b>Answer</b></summary>
   <p>

   The issue with the loop lies in the use of **dot notation** `obj1.key` instead of **bracket notation** `obj1[key]`.

   - `obj1.key` tries to access a property named `key` on the `obj1` object. Since `obj1` does not have a property named `key`, it will always return `undefined`.

   - What you actually want is to access the property whose name is stored in the variable `key`. This requires **bracket notation**. 

   #### The fix:
   ```javascript
   for (let key in obj1) {
    console.log(`${key}: ${obj1[key]}`);
   }
   ```

   #### Why the bracket notation works:

   Bracket notation evaluates the expression inside the brackets `key` and uses its value (e.g., `'a'`, `'b'`, `'c'`) to look up the corresponding property in the object. Dot notation, on the other hand, treats `key` as a literal property name, not as a variable.

   </p>
 </details>

---

3. ### True or false? 

The static object methods: `Objects.keys()`, `Object.values()` and `Object.entries()` return JS arrays.

<details><summary><b>Answer</b></summary>
   <p>

   ### Answer: True

   The static object methods `Object.keys()`, `Object.values()`, and `Object.entries()` all return JavaScript arrays.

   Example:
   ```javascript
   const user = { name: "Alice", age: 30, city: "NYC" };

   // Returns an array of property names (keys)
   console.log(Object.keys(user)); // outputs: ["name", "age", "city"]

   // Returns an array of property values
   console.log(Object.values(user)); // outputs: ["Alice", 30, "NYC"]

   // Returns an array of key-value pairs as arrays
   console.log(Object.entries(user)); // outputs: [["name", "Alice"], ["age", 30], ["city", "NYC"]]

   ```

   </p>
 </details>

---

4. ### What is logged and why?

```javascript
const player1 = {
  fullName: 'Cristiano Ronaldo',
  age: 40,
  country: 'Portugal',
  club: 'Manchester United',
  goals: {
    natioal: 135,
    club: 789
  },
  club: 'Al Nassr'
}

console.log(player1.goals.club); 
console.log(player1.club);
```

<details><summary><b>Answer</b></summary>
   <p>

   ### Answer: 789 and 'Al Nassr'

   JavaScript objects don't allow duplicate keys. If you attempt to define an object with multiple identical keys (like with the `club` key in this object), the last occurance of the key will overwrite any previous ones. Thus the final value of `player1.club` is `Al Nassr`. 

   </p>
 </details>

---

5. ### Destructuring objects

Extract `country` and rename it `birthCountry` and the first sports hobby as `firstSports` from `user1`. 

```javascript
const user1 = {
  name: 'Jane Doe',
  age: 33,
  location: {
    street: `156 Melba Avenue`,
    city: 'Brimmingham',
    country: 'England'
  },
  hobbies: {
    sports: ['football', 'sprinting'],
    culinary: ['baking', 'cooking']
  }
};
```
<details><summary><b>Answer</b></summary>
   <p>

   Destructuring in JavaScript is a syntax that allows you to unpack values from arrays or properties from objects into distinct variables. 

   ```javascript
   let {location: {country: birthCountry}, hobbies: {sports: [firstSports]}} = user1;

   console.log(birthCountry); // outputs: England
   console.log(firstSports); // outputs: football

   ```


   </p>
 </details>

---

6. ### True or false? 

A JavaScript class is a special kind of function used as a template for creating objects. 

<details><summary><b>Answer</b></summary>
   <p>

   ### Answer: True

   When you define a class, JavaScript internally creates a function.
   Classes provide a blueprint for creating objects with shared properties and methods.
   You can create multiple instances of a class using the new keyword, and each instance will have the structure defined by the class.

   For example:

   ```javascript
   class Person{
    constructor(name){
      this.name = name;
    }

    greeting(){
      return `Hello, I am ${this.name}.`;
    }
   }

   console.log(typeof Person);; // outputs: function
   ```
   </p>
 </details>

---

7. ### Find the bugs in this code

This code is supposed to declare a class `Dog` and create 2 instances of it (`dog67` and `dog68`) then display information about one of the instance's identity. 

```javascript
class Dog{ 
  constructor(name, sex, breed){ 
    this.name = name; 
    this.sex = sex; 
    this.breed = breed; 
    this.birthYear = birthYear;   
  }  

  identify(){ 
    return `${this.name} is a ${this.sex} ${this.breed} born in ${this.birthYear}.`; 
  }
 } 
 
 let dog67 = new Dog('Daisy', 'female', 'Labrador Retriever', 2023); 
 let dog68 = new Dog('Rex', 'male', 'German Sherpard', 2021); 

console.log(dog70.identify()); 
```

<details><summary><b>Answer</b></summary>
   <p>

   This code has several issues:

   1. **The missing `birthYear` parameter in the constructor**: The birthYear parameter is used in the constructor but is not included in the parameter list. This will cause a `ReferenceError` because `birthYear` is not defined.

   1. **Incorrect Object Reference**: The code tries to call `identify()` on `dog70`, but `dog70` is not defined (this causes a `ReferenceError`). The correct object should be either `dog67` or `dog68`.

   ```javascript
   class Dog { 
     constructor(name, sex, breed, birthYear) {  // Added birthYear parameter
       this.name = name; 
       this.sex = sex; 
       this.breed = breed; 
       this.birthYear = birthYear;   
     }  

     identify() { 
       return `${this.name} is a ${this.sex} ${this.breed} born in ${this.birthYear}.`; 
     }
   } 
 
   let dog67 = new Dog('Daisy', 'female', 'Labrador Retriever', 2023); 
   let dog68 = new Dog('Rex', 'male', 'German Shepherd', 2021); 

   // Corrected object reference
   console.log(dog67.identify());  // outputs: Daisy is a Female Labrador Retriever born in 2023.
   ```

   </p>
 </details>

---

8. ### Create a `LibraryBook` class

With the following properties: 

 - `title` (the title of the book)
 - `author` (the author of the book)
 - `year` (The year the book was published)
 - `totalCopies` ( The total number of copies available in the library (default is 1))
 - `checkedOutCopies` (The number of copies currently checked out (default is 0))

 Methods: 

 - `checkOut()` 

   - Allows a user to check out a book **only if copies are available.**
   - If no copies are left, display: "Sorry! All copies of [Title] are checked out."

  - `returnBook()`

    - Returns a book **only if at least one copy is checked out**.
    - If no copies are checked out, display: "Error: No checked-out copies of [Title] to return."

- `getAvailableCopies()`
    
     - Returns the number of available copies

- `getBookInfo()` 

   - Returns book details, including availability, e.g: `The Devil Wears Prada by Lauren Weisberger, published in 2003. Available copies: 2`

Then create the following library book instances:

```javascript
let book100 = new LibraryBook('Basic Mathematics', 'Serge Lang', 1971, 5); // 5 copies of this book, 0 checked out
let book200 = new LibraryBook('Book of Proof', 'Richard Hammack', 2009, 2); // 2 copies of this book, 0 checked out
```

- display the book info for both books
- do 6 checkouts for 'Basic Mathematics' the last checkout should not be successful (Can you do these with a loop??). 
- Return one 'Basic Mathematics' book, this should display a successful return message.
- do 1 checkout of 'Book of Proof' and display the book info, it should say that only 1 copy is available. 

### Additional:
  - Think about how you would add a **'due date'** calculation system for this library. (You can add this if you know how to work with dates in JavaScript). 

  <details><summary><b>Answer</b></summary>
   <p>

   ```javascript
   class LibrabryBook{
     constructor(title, author, year, totalCopies = 1, checkedOutCopies = 0){
       this.title = title;
       this.author = author;
       this.year = year;
       this.totalCopies = totalCopies;
       this.checkedOutCopies = checkedOutCopies
      }

     checkOut(){
       if (this.checkedOutCopies < this.totalCopies){
         this.checkedOutCopies++;
         console.log(`You have successfully checked out ${this.title}.`);
       }else{
         console.log(`Sorry! All copies of ${this.title} are checked out.`);
       }
      }

     returnBook(){
       if (this.checkedOutCopies > 0){
         this.checkedOutCopies--;
         console.log(`You have successfully returned ${this.title}.`);
       }else{
         console.log(`Error: No checkedout copies of ${this.title} to return.`);
       }
     }

     getAvailableCopies(){
       console.log(`Available copies: ${this.totalCopies - this.checkedOutCopies}`);
     }

     getBookInfo(){
       console.log(`${this.title} by ${this.author}, published in ${this.year}. \n Available copies: ${this.totalCopies - this.checkedOutCopies} \n-----`)
     }
  }


   let book100 = new LibrabryBook('Basic Mathematics', 'Serge Lang', 1971, 5);
   let book200 = new LibrabryBook('Book of Proof', 'Richard Hammack', 2009, 2);

   // dispying book info for both books
   book100.getBookInfo(); 
   book200.getBookInfo(); 

   // 6 checkouts for Basic Mathematics
   for (let i = 1; i < 7; i++){
     book100.checkOut();
   }

   // returning one Basic Mathematics book
   book100.returnBook();

   // checkout 1 Book of Proof and display info
   book200.checkOut();
   book200.getBookInfo();
   ```

   This code uses **default parameters** (look them up).
   </p>
 </details>
