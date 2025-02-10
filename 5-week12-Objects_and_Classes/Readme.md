## 📄JavaScript questions

> **Note:**
>These questions test concepts covered in week 12 (Objects ans Classes) and assume knowledge of concepts from previous weeks. 

---

1. ### When should you use a class vs. an object literal in JS? 

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

3. ### True or false? 

The static object methods: `Objects.keys()`, `Object.values()` and `Object.entries()` return JS arrays. 

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

6. ### True or false? 

A JavaScript class is a special kind of function used as a template for creating objects. 

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