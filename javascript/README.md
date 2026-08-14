# Learn JavaScript

A comprehensive collection of JavaScript learning exercises, examples, and concept implementations with detailed code comments. Each file demonstrates core JavaScript concepts through practical examples and clear explanations.

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)



### 1. What is JavaScript?

JavaScript is a **programming language used to make web pages interactive**.

It runs in:

* **Browsers** (Chrome, Firefox, etc.)
* **Servers** (via Node.js)

JavaScript is:

* **Interpreted** (not compiled like Java)
* **Dynamically typed**
* **Single-threaded**
* **Event-driven**

For now, remember this:

> JavaScript code is executed **line by line**, from top to bottom.

---

### 2. Where JavaScript Code Runs

#### Option 1: Browser Console

* Open Chrome
* Press `F12` → Console tab
* You can write JavaScript directly

Example:

```js
console.log("Hello, JavaScript");
```

This prints text to the console.

---

### 3. Your First JavaScript Program

```js
console.log("Hello World");
```

* `console` → built-in object
* `log()` → function
* `"Hello World"` → string (text)

JavaScript statements usually end with `;`
(semicolon is optional, but **we will use it**)

---

### 4. Comments (Very Important)

Comments are ignored by JavaScript.

```js
// This is a single-line comment

/*
This is a
multi-line comment
*/
```

Use comments to explain **why**, not **what**.

---

### 5. Variables (Basics)

Variables store data.

```js
let age = 20;
```

* `let` → keyword
* `age` → variable name
* `20` → value

You can change it:

```js
age = 21;
```

---

### 6. Rules for Variable Names

✅ Valid:

```js
let userName;
let _count;
let $price;
```

❌ Invalid:

```js
let 1name;
let user-name;
```

Rules:

* Letters, numbers, `_`, `$`
* Cannot start with a number
* Case-sensitive (`age` ≠ `Age`)

---

### 7. Data Types (Introduction)

JavaScript has **dynamic typing**.

```js
let x = 10;        // number
x = "hello";      // string
```

Basic types:

* `number`
* `string`
* `boolean`
* `undefined`
* `null`

Check type:

```js
typeof x;
```

---

### 8. `let`, `const`, `var` (Basic Overview)

For now:

* Use **`let`** for changeable values
* Use **`const`** for fixed values
* Avoid **`var`** (we’ll explain later)

```js
const pi = 3.14;
let count = 0;
```

---

### 1. `console.log()`

> Used to print output to the browser’s console.

---

### 2. Variable declaration

```js
let city = "Colombo";
```

---

### 3. Comment vs Code

* **Comments**: Used to explain the code to humans; they are ignored by the JavaScript engine.
* **Code**: Instructions that are executed by the JavaScript engine when the program runs.

---

## Numbers, Strings, and Operators

## 1. Numbers in JavaScript

JavaScript has **only one number type**:

* No `int`, `float`, `double`
* Everything is `number`

```js
let a = 10;
let b = 3.14;
let c = -5;
```

Check type:

```js
typeof a; // "number"
```

---

## 2. Arithmetic Operators

| Operator | Meaning             |
| -------- | ------------------- |
| `+`      | Addition            |
| `-`      | Subtraction         |
| `*`      | Multiplication      |
| `/`      | Division            |
| `%`      | Modulus (remainder) |

Example:

```js
let x = 10;
let y = 3;

console.log(x + y); // 13
console.log(x % y); // 1
```

---

## 3. Strings (Text)

Strings are text wrapped in quotes.

```js
let name1 = "JavaScript";
let name2 = 'JS';
```

Both are valid.

### String concatenation

```js
let firstName = "John";
let lastName = "Doe";

let fullName = firstName + " " + lastName;
```

---

## 4. Template Literals (Very Important)

JavaScript supports **template strings** using backticks `` ` ``

```js
let age = 20;
let msg = `I am ${age} years old`;
```

Why this matters:

* Cleaner than `+`
* Supports multi-line strings

---

## 5. The `+` Operator (Special Case)

In JavaScript, `+` is **both**:

* Addition (numbers)
* Concatenation (strings)

Example:

```js
console.log(10 + 5);      // 15
console.log("10" + 5);   // "105"
```

⚠️ This behavior is **unique and dangerous** if misunderstood.

---

## 6. Boolean Values

Booleans represent true/false.

```js
let isLoggedIn = true;
let isAdmin = false;
```

Used heavily in conditions.

---

## 7. Comparison Operators

| Operator          | Meaning          |
| ----------------- | ---------------- |
| `==`              | loose equality   |
| `===`             | strict equality  |
| `!=`              | loose not equal  |
| `!==`             | strict not equal |
| `>` `<` `>=` `<=` | comparisons      |

Example:

```js
5 == "5";   // true
5 === "5";  // false
```

Rule:

> **Always use `===`**, not `==`.

---

## Mini Practice

### 1. Output of `"5" + 2`

Your answer:

> `"52"`

---

### 2. Output of `5 === "5"`

> `false`

---

### 3. Template literal

```js
let score = 85;
console.log(`Your score is ${score}`);
```



# Lesson 3 — Conditions and Control Flow

## 1. `if` Statement

Syntax:

```js
if (condition) {
  // runs if condition is true
}
```

Example:

```js
let age = 18;

if (age >= 18) {
  console.log("You are an adult");
}
```

---

## 2. `if...else`

```js
let marks = 40;

if (marks >= 50) {
  console.log("Pass");
} else {
  console.log("Fail");
}
```

Execution rule:

* Condition is evaluated
* Only **one block** runs

---

## 3. `else if`

```js
let score = 85;

if (score >= 90) {
  console.log("A");
} else if (score >= 75) {
  console.log("B");
} else {
  console.log("C");
}
```

Conditions are checked **top to bottom**.

---

## 4. Truthy and Falsy Values (Very Important in JS)

In Java, conditions must be `boolean`.
In JavaScript, **any value** can be used in a condition.

### Falsy values (only these are false):

* `false`
* `0`
* `""` (empty string)
* `null`
* `undefined`
* `NaN`

Everything else is **truthy**.

Example:

```js
if ("hello") {
  console.log("This runs");
}

if (0) {
  console.log("This does NOT run");
}
```

---

## 5. Common Beginner Bug

```js
let username = "";

if (username) {
  console.log("User exists");
} else {
  console.log("No username");
}
```

This prints:

```
No username
```

Because empty string is falsy.

---

## 6. Logical Operators

| Operator | Meaning |   |    |
| -------- | ------- | - | -- |
| `&&`     | AND     |   |    |
| `        |         | ` | OR |
| `!`      | NOT     |   |    |

Example:

```js
let age = 20;
let hasID = true;

if (age >= 18 && hasID) {
  console.log("Allowed");
}
```

---

## 7. Short-Circuit Behavior (JS-specific)

```js
let name = "";
let displayName = name || "Guest";

console.log(displayName); // "Guest"
```

This pattern is used **everywhere** in real projects.

---
## Mini Practice

### 1. Empty string condition

Reason: `""` is a **falsy** value, so the `else` block runs.

---

### 2. Logical OR

Reason: `0` is falsy, so `||` returns the next truthy value.

---

### 3. `isLoggedIn` program

```js
let isLoggedIn = false;

if (isLoggedIn) {
  console.log("Welcome");
} else {
  console.log("Please login");
}
```

This is an important lesson:

> JavaScript does **not forgive syntax errors** — one missing quote stops execution.

---

## Lesson 4 — Loops (Repeating Code)

Loops allow you to run code multiple times.

---

## 1. `for` Loop (Most Common)

Syntax:

```js
for (initialization; condition; update) {
  // code
}
```

Example:

```js
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

Output:

```
1
2
3
4
5
```

How it works:

1. `let i = 1` → runs once
2. `i <= 5` → checked before each iteration
3. `i++` → runs after each iteration

---

## 2. `while` Loop

```js
let i = 1;

while (i <= 5) {
  console.log(i);
  i++;
}
```

Use when:

* You don’t know the number of iterations in advance

---

## 3. `do...while` Loop

Runs **at least once**, even if condition is false.

```js
let i = 10;

do {
  console.log(i);
} while (i < 5);
```

Output:

```
10
```

---

## 4. `break` and `continue`

### `break` → stop the loop

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    break;
  }
  console.log(i);
}
```

Output:

```
1
2
```

---

### `continue` → skip current iteration

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log(i);
}
```

Output:

```
1
2
4
5
```

---

### 3. Even numbers from 1 to 10


```js
for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) {
    console.log(i);
  }
}
```

---

## Functions 

Functions allow you to **group code**, **reuse logic**, and **organize programs**.

---

## 1. Function Declaration

```js
function greet() {
  console.log("Hello");
}
```

Call the function:

```js
greet();
```

---

## 2. Functions with Parameters

```js
function greet(name) {
  console.log("Hello " + name);
}

greet("Alex");
```

* `name` → parameter
* `"Alex"` → argument

---

## 3. Returning Values

```js
function add(a, b) {
  return a + b;
}

let result = add(3, 4);
console.log(result);
```

Key rule:

> Code after `return` does **not execute**.

---

## 4. Function Expression

Functions can be stored in variables.

```js
const multiply = function (a, b) {
  return a * b;
};
```

Difference:

* Declaration → hoisted
* Expression → not hoisted

---

## 5. Arrow Functions (Modern JS)

```js
const subtract = (a, b) => {
  return a - b;
};
```

Short version:

```js
const square = x => x * x;
```

---

## 6. Default Parameters

```js
function greet(name = "Guest") {
  console.log("Hello " + name);
}

greet(); // Hello Guest
```

---

## Mini Practice (Answer Next)

1. Write a function `isEven` that:

   * Takes a number
   * Returns `true` if even, else `false`

2. Convert this function into an arrow function:

```js
function double(x) {
  return x * 2;
}
```

3. What will this print?

```js
function test() {
  return 10;
  console.log("Hi");
}

console.log(test());
```


## Arrays 

Arrays store **multiple values in a single variable**.

---

## 1. Creating an Array

```js
let numbers = [1, 2, 3, 4, 5];
```

* Index starts at **0**
* `numbers[0]` → `1`

```js
console.log(numbers[2]); // 3
```

---

## 2. Array Length

```js
console.log(numbers.length); // 5
```

`length` is used heavily in loops.

---

## 3. Modifying Arrays

```js
numbers[0] = 10;
```

Arrays declared with `const` are still mutable:

```js
const arr = [1, 2];
arr.push(3); // valid
```

---

## 4. Common Array Methods

### `push` → add at end

```js
numbers.push(6);
```

### `pop` → remove last

```js
numbers.pop();
```

### `shift` → remove first

```js
numbers.shift();
```

### `unshift` → add at start

```js
numbers.unshift(0);
```

---

## 5. Looping Through Arrays

### `for` loop

```js
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}
```

### `for...of`

```js
for (let value of numbers) {
  console.log(value);
}
```

---

## 6. Arrays Can Store Anything

```js
let mixed = [1, "hello", true, null];
```

Even functions:

```js
let funcs = [
  function () { console.log("Hi"); }
];
```

---

## 7. Reference Behavior

```js
let a = [1, 2];
let b = a;

b.push(3);

console.log(a); // [1, 2, 3]
```

Arrays are **reference types**, not copied by value.

---

## Mini Practice (Answer Next)

1. Create an array `fruits` with 3 values.
2. Print the last element of the array.
3. Use a loop to print all elements.
4. What will this output?

```js
let x = [1, 2];
let y = x;
y.push(3);
console.log(x);
```

## Objects

Objects store **key–value pairs**.
They are used everywhere in JavaScript.

---

## 1. Creating an Object

```js
let user = {
  name: "Kabilesh",
  age: 23,
  isStudent: true
};
```

* `name`, `age`, `isStudent` → properties
* Keys are strings (usually written without quotes)

---

## 2. Accessing Properties

### Dot notation

```js
console.log(user.name);
```

### Bracket notation

```js
console.log(user["age"]);
```

Bracket notation is useful when:

* Property name is dynamic
* Property name has spaces

```js
let key = "name";
console.log(user[key]);
```

---

## 3. Modifying Objects

```js
user.age = 21;
user.city = "Colombo";
```

Deleting a property:

```js
delete user.isStudent;
```

---

## 4. Objects with Methods

```js
let person = {
  name: "Sam",
  greet: function () {
    console.log("Hello");
  }
};

person.greet();
```

Shorter syntax:

```js
let person = {
  name: "Sam",
  greet() {
    console.log("Hello");
  }
};
```

---

## 5. The `this` Keyword

`this` refers to **the current object**.

```js
let person = {
  name: "Sam",
  greet() {
    console.log("Hello " + this.name);
  }
};

person.greet(); // Hello Sam
```

⚠️ `this` behaves differently in JavaScript than in Java.

---

## 6. Looping Through Objects

```js
for (let key in user) {
  console.log(key, user[key]);
}
```

* `key` → property name
* `user[key]` → property value

---

## 7. Objects Are Reference Types

```js
let a = { value: 10 };
let b = a;

b.value = 20;

console.log(a.value); // 20
```

Same behavior as arrays.

---

## Mini Practice

1. Create an object `book` with:

   * `title`
   * `author`
   * `price`

2. Print the `title` using dot notation.

3. Add a method `discount()` that prints:

   ```
   Discount applied
   ```

4. What will this print?

```js
let x = { count: 1 };
let y = x;
y.count = 5;
console.log(x.count);
```

## Arrays of Objects

This is where JavaScript starts to look like **real applications**, not toy programs.

---

## 1. Why Arrays of Objects?

In real life, data is rarely just numbers or strings.

Example:

* Users
* Products
* Students
* Tasks

Each item has **multiple properties** → object
Multiple items → array

---

## 2. Creating an Array of Objects

```js
let students = [
  { name: "Alex", marks: 85 },
  { name: "Sam", marks: 72 },
  { name: "John", marks: 90 }
];
```

* `students` → array
* Each element → object

---

## 3. Accessing Data

```js
console.log(students[0].name);   // Alex
console.log(students[2].marks);  // 90
```

Breakdown:

* `students[0]` → first object
* `.name` → property of that object

---

## 4. Looping Through Arrays of Objects

### Using `for`

```js
for (let i = 0; i < students.length; i++) {
  console.log(students[i].name);
}
```

### Using `for...of` (preferred)

```js
for (let student of students) {
  console.log(student.name, student.marks);
}
```

---

## 5. Updating Objects Inside an Array

```js
students[1].marks = 80;
```

Objects are **mutable**, even inside arrays.

---

## 6. Adding New Objects

```js
students.push({ name: "Emma", marks: 88 });
```

---

## Practice Problems (5)

1. Create an array `books` with at least 3 objects. Each object should have `title` and `price`.
2. Print the title of the second book.
3. Use a loop to print **all book titles**.
4. Change the price of the first book.
5. Add a new book object to the array.

---

## Functions + Objects (Methods & Behavior)

Objects don’t just store data — they store **behavior**.

---

## 1. Methods Inside Objects

```js
let user = {
  name: "Alex",
  greet() {
    console.log("Hello " + this.name);
  }
};

user.greet();
```

* `greet` → method
* `this` → refers to the object calling the method

---

## 2. Why `this` Exists

Without `this`:

```js
console.log("Hello " + name); // ❌ name not defined
```

With `this`:

```js
console.log("Hello " + this.name); // ✔
```

---

## 3. Objects Acting Like Blueprints (Manual)

```js
function createUser(name, age) {
  return {
    name: name,
    age: age,
    info() {
      console.log(this.name + " is " + this.age);
    }
  };
}

let u1 = createUser("Sam", 22);
u1.info();
```

This is how **object creation patterns** start.

---

## 4. Objects Inside Arrays with Methods

```js
let users = [
  {
    name: "Alex",
    login() {
      console.log(this.name + " logged in");
    }
  }
];

users[0].login();
```

---

## Practice Problems (5)

1. Create an object `car` with properties `brand` and `speed`.
2. Add a method `drive()` that prints `"Car is moving"`.
3. Create an array `cars` with at least 2 car objects.
4. Loop through the array and call `drive()` for each car.
5. Add a new property `year` to one car.

---

## `this` Keyword

This topic is **critical** and often misunderstood.

---

## 1. Rule 1: `this` Depends on How a Function Is Called

```js
let obj = {
  name: "JS",
  show() {
    console.log(this.name);
  }
};

obj.show(); // JS
```

---

## 2. Losing `this`

```js
let fn = obj.show;
fn(); // undefined
```

Why?

* `fn()` is not called as an object method
* So `this` is not `obj`

---

## 3. Fixing `this` (Preview)

```js
let fn = obj.show.bind(obj);
fn(); // JS
```

We’ll fully cover `bind`, `call`, `apply` later.

---

## Practice Problems (5)

1. Create an object with a property `value` and a method that prints it using `this`.
2. Assign the method to another variable and call it. Observe the result.
3. Write what you *expect* `this` to be in that case.
4. Explain (in words) why `this` changes.
5. Try fixing it using `bind` (even if it feels unclear — attempt it).

---


## Scope (Global, Function, Block)

Scope defines **where a variable can be accessed**.

---

## 1. Global Scope

Declared **outside** any function or block.

```js
let x = 10;

function test() {
  console.log(x);
}
```

* Accessible everywhere
* Overuse is dangerous (name conflicts, bugs)

---

## 2. Function Scope

Variables declared inside a function exist **only there**.

```js
function demo() {
  let y = 5;
  console.log(y);
}

demo();
// console.log(y); ❌ error
```

---

## 3. Block Scope (`let` and `const`)

Blocks are `{ }` used in:

* `if`
* `for`
* `while`

```js
if (true) {
  let a = 10;
}
// console.log(a); ❌ error
```

Important:

* `let` and `const` → block-scoped
* `var` → NOT block-scoped (we’ll cover later)

---

## 4. Scope Chain

JavaScript looks for variables:

1. Local scope
2. Parent scope
3. Global scope

```js
let x = 1;

function outer() {
  let y = 2;

  function inner() {
    console.log(x, y);
  }

  inner();
}
```

---

## 5. Shadowing

```js
let value = 10;

function test() {
  let value = 20;
  console.log(value);
}

test(); // 20
```

Inner variable **shadows** outer one.

---

## Practice Problems (5)

1. Declare a global variable and access it inside a function.
2. Try accessing a function variable outside the function. What happens?
3. Write an `if` block with a `let` variable and try to access it outside.
4. Create nested functions and access an outer variable from the inner function.
5. Create two variables with the same name in different scopes and print both.

---

## Closures 

A **closure** is when a function **remembers variables from its outer scope**, even after that scope is finished.

---

## 1. Basic Closure Example

```js
function outer() {
  let count = 0;

  function inner() {
    count++;
    console.log(count);
  }

  return inner;
}

let counter = outer();
counter(); // 1
counter(); // 2
```

Why this works:

* `inner()` **remembers** `count`
* `count` is not destroyed

---

## 2. Closures Are Created Automatically

You don’t “create” closures.
They happen when:

* A function accesses variables from its parent scope

---

## 3. Practical Use Case: Data Privacy

```js
function createBankAccount() {
  let balance = 0;

  return {
    deposit(amount) {
      balance += amount;
    },
    getBalance() {
      return balance;
    }
  };
}

let acc = createBankAccount();
acc.deposit(100);
console.log(acc.getBalance());
```

You **cannot** access `balance` directly.

---

## 4. Closures in Loops (Common Pitfall Preview)

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

This prints:

```
3
3
3
```


---

## Practice Problems (5)

1. Write a function that returns another function.
2. Inside the inner function, access a variable from the outer function.
3. Call the returned function multiple times and observe the result.
4. Explain in words why the outer variable is not destroyed.
5. Create a simple counter using a closure.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

<div align="center">
  
**Happy Coding!** 🚀

*"Any application that can be written in JavaScript, will eventually be written in JavaScript."* - Jeff Atwood

[![GitHub stars](https://img.shields.io/github/stars/KabileshwaranKabil/learn-javascript?style=social)](https://github.com/KabileshwaranKabil/learn-javascript/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/KabileshwaranKabil/learn-javascript?style=social)](https://github.com/KabileshwaranKabil/learn-javascript/network/members)

**Connect**: [GitHub](https://github.com/KabileshwaranKabil) • [LinkedIn](https://www.linkedin.com/in/m-kabileshwaran-4018a5378/) • [Portfolio](https://kabileshwaran-portfolio.vercel.app/)

</div>
