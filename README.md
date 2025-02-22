# 100 JavaScript Programs

---

## Program 1: Hello World
```javascript
console.log("Hello, World!");
```

---

## Program 2: Sum of Two Numbers
```javascript
const a = 5, b = 7;
console.log("Sum:", a + b);
```

---

## Program 3: Factorial (Recursive)
```javascript
function factorial(n) {
  return n === 0 ? 1 : n * factorial(n - 1);
}
console.log("Factorial of 5:", factorial(5));
```

---

## Program 4: Fibonacci Series
```javascript
function fibonacci(n) {
  let a = 0, b = 1, result = [];
  for (let i = 0; i < n; i++) {
    result.push(a);
    [a, b] = [b, a + b];
  }
  return result;
}
console.log("Fibonacci series:", fibonacci(10));
```

---

## Program 5: Prime Number Checker
```javascript
function isPrime(n) {
  if (n < 2) return false;
  for (let i = 2, limit = Math.sqrt(n); i <= limit; i++) {
    if (n % i === 0) return false;
  }
  return true;
}
console.log("Is 29 prime?", isPrime(29));
```

---

## Program 6: Reverse a String
```javascript
const str = "JavaScript";
console.log("Reversed:", str.split("").reverse().join(""));
```

---

## Program 7: Palindrome Checker
```javascript
function isPalindrome(s) {
  const rev = s.split("").reverse().join("");
  return s === rev;
}
console.log("Is 'radar' a palindrome?", isPalindrome("radar"));
```

---

## Program 8: Find Largest in an Array
```javascript
const numbers = [3, 67, 2, 89, 34];
console.log("Largest:", Math.max(...numbers));
```

---

## Program 9: Find Smallest in an Array
```javascript
const nums = [3, 67, 2, 89, 34];
console.log("Smallest:", Math.min(...nums));
```

---

## Program 10: Even or Odd Check
```javascript
const num = 42;
console.log(num, "is", num % 2 === 0 ? "Even" : "Odd");
```

---

## Program 11: Square Numbers Using Map
```javascript
const arr = [0, 1, 2, 3, 4];
const squares = arr.map(x => x * x);
console.log("Squares:", squares);
```

---

## Program 12: Bubble Sort
```javascript
function bubbleSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
    }
  }
  return arr;
}
console.log("Bubble Sorted:", bubbleSort([64, 34, 25, 12, 22, 11, 90]));
```

---

## Program 13: Merge Sort
```javascript
function mergeSort(arr) {
  if (arr.length <= 1) return arr;
  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));
  let merged = [], i = 0, j = 0;
  while (i < left.length && j < right.length) {
    merged.push(left[i] < right[j] ? left[i++] : right[j++]);
  }
  return merged.concat(left.slice(i)).concat(right.slice(j));
}
console.log("Merge Sorted:", mergeSort([38, 27, 43, 3, 9, 82, 10]));
```

---

## Program 14: Binary Search
```javascript
function binarySearch(arr, target) {
  let low = 0, high = arr.length - 1;
  while (low <= high) {
    const mid = Math.floor((low + high) / 2);
    if (arr[mid] === target) return mid;
    else if (arr[mid] < target) low = mid + 1;
    else high = mid - 1;
  }
  return -1;
}
console.log("Index of 7:", binarySearch([1, 3, 5, 7, 9, 11], 7));
```

---

## Program 15: Tower of Hanoi
```javascript
function towerOfHanoi(n, source, auxiliary, target) {
  if (n === 1) {
    console.log(`Move disk 1 from ${source} to ${target}`);
    return;
  }
  towerOfHanoi(n - 1, source, target, auxiliary);
  console.log(`Move disk ${n} from ${source} to ${target}`);
  towerOfHanoi(n - 1, auxiliary, source, target);
}
towerOfHanoi(3, "A", "B", "C");
```

---

## Program 16: Sum of Digits
```javascript
const number = 12345;
const sumDigits = number.toString().split("").reduce((sum, d) => sum + Number(d), 0);
console.log("Sum of digits:", sumDigits);
```

---

## Program 17: Count Vowels in a String
```javascript
function countVowels(s) {
  const vowels = "aeiouAEIOU";
  return s.split("").filter(char => vowels.includes(char)).length;
}
console.log("Vowels count in 'Hello World':", countVowels("Hello World"));
```

---

## Program 18: Generate a Random Number (1-100)
```javascript
const randomNum = Math.floor(Math.random() * 100) + 1;
console.log("Random number (1-100):", randomNum);
```

---

## Program 19: Calculate GCD (Euclid’s Algorithm)
```javascript
function gcd(a, b) {
  return b === 0 ? a : gcd(b, a % b);
}
console.log("GCD of 48 and 180:", gcd(48, 180));
```

---

## Program 20: Calculate LCM
```javascript
function lcm(a, b) {
  return Math.abs(a * b) / gcd(a, b);
}
console.log("LCM of 12 and 15:", lcm(12, 15));
```

---

## Program 21: Armstrong Number Checker
```javascript
function isArmstrong(num) {
  const digits = num.toString().split("").map(Number);
  const power = digits.length;
  const sum = digits.reduce((acc, d) => acc + Math.pow(d, power), 0);
  return sum === num;
}
console.log("Is 153 an Armstrong number?", isArmstrong(153));
```

---

## Program 22: Perfect Number Checker
```javascript
function isPerfect(num) {
  const sum = Array.from({ length: num - 1 }, (_, i) => i + 1)
                   .filter(i => num % i === 0)
                   .reduce((acc, cur) => acc + cur, 0);
  return sum === num;
}
console.log("Is 28 perfect?", isPerfect(28));
```

---

## Program 23: Simple Calculator
```javascript
function calculator(a, b, op) {
  switch (op) {
    case "+": return a + b;
    case "-": return a - b;
    case "*": return a * b;
    case "/": return b !== 0 ? a / b : "Division by zero";
    default: return "Invalid operator";
  }
}
console.log("Calculator (10 + 5):", calculator(10, 5, "+"));
```

---

## Program 24: Celsius to Fahrenheit Converter
```javascript
function cToF(celsius) {
  return (celsius * 9/5) + 32;
}
console.log("25°C =", cToF(25), "°F");
```

---

## Program 25: Currency Converter (USD to EUR)
```javascript
function usdToEur(usd, rate = 0.85) {
  return usd * rate;
}
console.log("$100 =", usdToEur(100), "EUR");
```

---

## Program 26: List Factors of a Number
```javascript
function factors(n) {
  let fac = [];
  for (let i = 1; i <= n; i++) {
    if (n % i === 0) fac.push(i);
  }
  return fac;
}
console.log("Factors of 28:", factors(28));
```

---

## Program 27: Leap Year Checker
```javascript
function isLeapYear(year) {
  return (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);
}
console.log("2024 is a leap year?", isLeapYear(2024));
```

---

## Program 28: Area of a Circle
```javascript
function areaCircle(radius) {
  return Math.PI * radius * radius;
}
console.log("Area of a circle with radius 5:", areaCircle(5));
```

---

## Program 29: Area of a Triangle (Heron’s Formula)
```javascript
function areaTriangle(a, b, c) {
  const s = (a + b + c) / 2;
  return Math.sqrt(s * (s - a) * (s - b) * (s - c));
}
console.log("Area of triangle (3, 4, 5):", areaTriangle(3, 4, 5));
```

---

## Program 30: Even or Odd with Arrow Function
```javascript
const evenOrOdd = x => x % 2 === 0 ? "Even" : "Odd";
console.log("17 is", evenOrOdd(17));
```

---

## Program 31: Array Map to Square Numbers
```javascript
const numbersArr = [1, 2, 3, 4, 5];
const squared = numbersArr.map(x => x * x);
console.log("Squared numbers:", squared);
```

---

## Program 32: Filter Even Numbers from an Array
```javascript
const mixedNumbers = [1, 2, 3, 4, 5, 6];
const evens = mixedNumbers.filter(x => x % 2 === 0);
console.log("Even numbers:", evens);
```

---

## Program 33: Multiply Array Items Using Reduce
```javascript
const numsForProduct = [1, 2, 3, 4];
const product = numsForProduct.reduce((acc, cur) => acc * cur, 1);
console.log("Product:", product);
```

---

## Program 34: Zip Two Arrays into an Object
```javascript
const keys = ['a', 'b', 'c'];
const values = [1, 2, 3];
const obj = keys.reduce((acc, key, i) => ({ ...acc, [key]: values[i] }), {});
console.log("Zipped object:", obj);
```

---

## Program 35: Sort Object by Value
```javascript
const data = { apple: 3, banana: 1, cherry: 2 };
const sortedEntries = Object.entries(data).sort(([, a], [, b]) => a - b);
const sortedObj = Object.fromEntries(sortedEntries);
console.log("Sorted object:", sortedObj);
```

---

## Program 36: Count Words in a String
```javascript
function countWords(text) {
  return text.trim().split(/\s+/).length;
}
console.log("Word count:", countWords("This is a simple test."));
```

---

## Program 37: (Node.js) Read a File
```javascript
// Run with Node.js
const fs = require('fs');
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) console.error(err);
  else console.log("File content:\n", data);
});
```

---

## Program 38: (Node.js) Write to a File
```javascript
const fsWrite = require('fs');
fsWrite.writeFile('output.txt', 'Hello, file!', err => {
  if (err) console.error(err);
  else console.log("File written.");
});
```

---

## Program 39: (Node.js) Append to a File
```javascript
const fsAppend = require('fs');
fsAppend.appendFile('output.txt', '\nAppending a new line.', err => {
  if (err) console.error(err);
  else console.log("File appended.");
});
```

---

## Program 40: (Node.js) Delete a File
```javascript
const fsDelete = require('fs');
fsDelete.unlink('output.txt', err => {
  if (err) console.error("Deletion failed:", err);
  else console.log("File deleted.");
});
```

---

## Program 41: (Node.js) Create a Directory
```javascript
const fsMkdir = require('fs');
fsMkdir.mkdir('new_folder', err => {
  if (err) console.error("Directory exists or error:", err);
  else console.log("Directory created.");
});
```

---

## Program 42: (Node.js) List Files in a Directory
```javascript
const fsReaddir = require('fs');
fsReaddir.readdir('.', (err, files) => {
  if (err) console.error(err);
  else console.log("Files in directory:", files);
});
```

---

## Program 43: (Node.js) Rename a File
```javascript
const fsRename = require('fs');
fsRename.rename('old.txt', 'new.txt', err => {
  if (err) console.error("Rename error:", err);
  else console.log("File renamed.");
});
```

---

## Program 44: Try/Catch Error Handling
```javascript
try {
  let result = 10 / 0;
  console.log(result);
} catch (error) {
  console.error("Error:", error);
}
```

---

## Program 45: Custom Error Class
```javascript
class MyError extends Error {
  constructor(message) {
    super(message);
    this.name = "MyError";
  }
}
function checkValue(x) {
  if (x < 0) throw new MyError("Negative value!");
  return x;
}
try {
  console.log(checkValue(-5));
} catch (e) {
  console.error("Caught error:", e.message);
}
```

---

## Program 46: Simple Class and Object
```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}
const p = new Person("Alice");
p.greet();
```

---

## Program 47: Inheritance Example
```javascript
class Animal {
  speak() {
    console.log("Animal sound");
  }
}
class Dog extends Animal {
  speak() {
    console.log("Woof!");
  }
}
const d = new Dog();
d.speak();
```

---

## Program 48: Polymorphism Example
```javascript
class Bird {
  sound() {
    console.log("Tweet");
  }
}
class Cat {
  sound() {
    console.log("Meow");
  }
}
function makeSound(animal) {
  animal.sound();
}
makeSound(new Bird());
makeSound(new Cat());
```

---

## Program 49: Encapsulation via Closures
```javascript
function createBankAccount(initialBalance) {
  let balance = initialBalance;
  return {
    deposit(amount) { balance += amount; },
    getBalance() { return balance; }
  };
}
const account = createBankAccount(100);
account.deposit(50);
console.log("Balance:", account.getBalance());
```

---

## Program 50: Abstraction (Simulated Abstract Class)
```javascript
class Shape {
  constructor() {
    if (new.target === Shape) throw new Error("Cannot instantiate abstract class");
  }
  area() {
    throw new Error("Abstract method 'area' must be implemented");
  }
}
class Square extends Shape {
  constructor(side) {
    super();
    this.side = side;
  }
  area() {
    return this.side * this.side;
  }
}
const s = new Square(4);
console.log("Area of square:", s.area());
```

---

## Program 51: Fibonacci with Recursion (Arrow Function)
```javascript
const fib = n => n <= 1 ? n : fib(n - 1) + fib(n - 2);
console.log("Fibonacci numbers:", Array.from({length: 10}, (_, i) => fib(i)));
```

---

## Program 52: Binary to Decimal Conversion
```javascript
function binaryToDecimal(binaryStr) {
  return parseInt(binaryStr, 2);
}
console.log("Decimal of '1010':", binaryToDecimal("1010"));
```

---

## Program 53: Decimal to Binary Conversion
```javascript
function decimalToBinary(n) {
  return n.toString(2);
}
console.log("Binary of 10:", decimalToBinary(10));
```

---

## Program 54: Matrix Addition
```javascript
function addMatrices(A, B) {
  return A.map((row, i) => row.map((val, j) => val + B[i][j]));
}
const A = [[1, 2], [3, 4]];
const B = [[5, 6], [7, 8]];
console.log("Matrix Sum:", addMatrices(A, B));
```

---

## Program 55: Matrix Multiplication
```javascript
function multiplyMatrices(A, B) {
  const result = Array.from({ length: A.length }, () => Array(B[0].length).fill(0));
  for (let i = 0; i < A.length; i++)
    for (let j = 0; j < B[0].length; j++)
      for (let k = 0; k < B.length; k++)
        result[i][j] += A[i][k] * B[k][j];
  return result;
}
const M1 = [[1, 2], [3, 4]];
const M2 = [[2, 0], [1, 2]];
console.log("Matrix Product:", multiplyMatrices(M1, M2));
```

---

## Program 56: Transpose of a Matrix
```javascript
function transpose(matrix) {
  return matrix[0].map((_, colIndex) => matrix.map(row => row[colIndex]));
}
const matrix = [[1, 2, 3], [4, 5, 6]];
console.log("Transpose:", transpose(matrix));
```

---

## Program 57: Check if Matrix is Symmetric
```javascript
function isSymmetric(matrix) {
  return matrix.every((row, i) =>
    row.every((val, j) => val === matrix[j][i])
  );
}
const symMatrix = [
  [1, 2, 3],
  [2, 4, 5],
  [3, 5, 6]
];
console.log("Is symmetric?", isSymmetric(symMatrix));
```

---

## Program 58: Multiplication Table
```javascript
function multiplicationTable(n) {
  for (let i = 1; i <= n; i++) {
    let row = "";
    for (let j = 1; j <= n; j++) {
      row += (i * j).toString().padStart(4, " ");
    }
    console.log(row);
  }
}
multiplicationTable(5);
```

---

## Program 59: Count Frequency of Array Elements
```javascript
function countFrequency(arr) {
  return arr.reduce((freq, item) => {
    freq[item] = (freq[item] || 0) + 1;
    return freq;
  }, {});
}
console.log("Frequency:", countFrequency([1, 2, 2, 3, 3, 3]));
```

---

## Program 60: Convert JSON String to Object
```javascript
const jsonString = '{"name": "Alice", "age": 30}';
const objFromJson = JSON.parse(jsonString);
console.log("Converted object:", objFromJson);
```

---

## Program 61: Convert Object to JSON String
```javascript
const objData = { name: "Bob", age: 25 };
const jsonStr = JSON.stringify(objData);
console.log("JSON string:", jsonStr);
```

---

## Program 62: Using Regular Expressions
```javascript
const text = "The rain in Spain";
const regex = /\bS\w+/;
const match = text.match(regex);
console.log("Regex match:", match ? match[0] : "No match");
```

---

## Program 63: Basic API Call with Fetch
```javascript
fetch("https://api.github.com")
  .then(response => response.json())
  .then(data => console.log("GitHub API response:", data))
  .catch(error => console.error("Error:", error));
```

---

## Program 64: Generate a Random Password
```javascript
function randomPassword(length = 8) {
  const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()";
  let password = "";
  for (let i = 0; i < length; i++) {
    password += chars.charAt(Math.floor(Math.random() * chars.length));
  }
  return password;
}
console.log("Random Password:", randomPassword(12));
```

---

## Program 65: Find Duplicates in an Array
```javascript
function findDuplicates(arr) {
  const seen = new Set(), duplicates = new Set();
  arr.forEach(item => {
    if (seen.has(item)) duplicates.add(item);
    else seen.add(item);
  });
  return [...duplicates];
}
console.log("Duplicates:", findDuplicates([1, 2, 3, 2, 4, 5, 1]));
```

---

## Program 66: Remove Duplicates from an Array
```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}
console.log("Unique Array:", removeDuplicates([1, 2, 3, 2, 4, 5, 1]));
```

---

## Program 67: Merge Two Arrays
```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
console.log("Merged Array:", arr1.concat(arr2));
```

---

## Program 68: Find Intersection of Two Arrays
```javascript
function intersection(arr1, arr2) {
  return arr1.filter(item => arr2.includes(item));
}
console.log("Intersection:", intersection([1, 2, 3, 4], [3, 4, 5, 6]));
```

---

## Program 69: Flatten a Nested Array
```javascript
function flatten(nestedArray) {
  return nestedArray.flat();
}
console.log("Flattened:", flatten([[1, 2], [3, 4], [5]]));
```

---

## Program 70: Destructuring an Object
```javascript
const person = { name: "Alice", age: 30 };
const { name, age } = person;
console.log("Name:", name, "Age:", age);
```

---

## Program 71: Destructuring an Array
```javascript
const rgb = [255, 200, 150];
const [red, green, blue] = rgb;
console.log("Red:", red, "Green:", green, "Blue:", blue);
```

---

## Program 72: Function Decorator (Higher-Order Function)
```javascript
function decorator(func) {
  return function(...args) {
    console.log("Before function call");
    const result = func(...args);
    console.log("After function call");
    return result;
  }
}
const greet = decorator(name => `Hello, ${name}!`);
console.log(greet("Alice"));
```

---

## Program 73: Generator Function
```javascript
function* numberGenerator(n) {
  for (let i = 0; i < n; i++) {
    yield i;
  }
}
for (const num of numberGenerator(5)) {
  console.log(num);
}
```

---

## Program 74: Fibonacci Using Generator
```javascript
function* fibGenerator(n) {
  let a = 0, b = 1;
  for (let i = 0; i < n; i++) {
    yield a;
    [a, b] = [b, a + b];
  }
}
console.log("Fibonacci:", [...fibGenerator(10)]);
```

---

## Program 75: Permutations of an Array (Recursive)
```javascript
function permute(arr) {
  if (arr.length <= 1) return [arr];
  const result = [];
  for (let i = 0; i < arr.length; i++) {
    const current = arr[i];
    const remaining = arr.slice(0, i).concat(arr.slice(i + 1));
    permute(remaining).forEach(p => result.push([current, ...p]));
  }
  return result;
}
console.log("Permutations of [1,2,3]:", permute([1, 2, 3]));
```

---

## Program 76: Combinations of Array Elements (2-combinations)
```javascript
function combinations(arr) {
  const result = [];
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      result.push([arr[i], arr[j]]);
    }
  }
  return result;
}
console.log("Combinations of [1,2,3,4]:", combinations([1, 2, 3, 4]));
```

---

## Program 77: Count Frequency Using Reduce
```javascript
const frequency = [1,2,2,3,3,3].reduce((acc, cur) => {
  acc[cur] = (acc[cur] || 0) + 1;
  return acc;
}, {});
console.log("Frequency using reduce:", frequency);
```

---

## Program 78: Using Map and Set
```javascript
const map = new Map();
map.set("a", 1);
map.set("b", 2);
console.log("Map:", Array.from(map.entries()));

const set = new Set([1, 2, 2, 3]);
console.log("Set:", Array.from(set));
```

---

## Program 79: DOM Manipulation Example
```javascript
// In a browser environment:
document.body.innerHTML += "<p>New paragraph added to the DOM!</p>";
```

---

## Program 80: Add Event Listener to a Button
```javascript
// In a browser environment:
const btn = document.createElement("button");
btn.textContent = "Click Me";
btn.addEventListener("click", () => alert("Button clicked!"));
document.body.appendChild(btn);
```

---

## Program 81: Async/Await Fetch Data
```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.github.com");
    const data = await response.json();
    console.log("Async/Await fetch:", data);
  } catch (err) {
    console.error(err);
  }
}
fetchData();
```

---

## Program 82: Promise Example
```javascript
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Promise resolved!"), 1000);
});
myPromise.then(result => console.log(result));
```

---

## Program 83: Callback Example
```javascript
function doTask(callback) {
  setTimeout(() => {
    callback("Task complete");
  }, 500);
}
doTask(message => console.log(message));
```

---

## Program 84: Using setTimeout
```javascript
setTimeout(() => {
  console.log("Executed after 1 second");
}, 1000);
```

---

## Program 85: Using setInterval and clearInterval
```javascript
const intervalId = setInterval(() => {
  console.log("Interval running...");
}, 1000);
setTimeout(() => {
  clearInterval(intervalId);
  console.log("Interval cleared");
}, 4000);
```

---

## Program 86: Immediately Invoked Function Expression (IIFE)
```javascript
(function() {
  console.log("IIFE executed");
})();
```

---

## Program 87: Arrow Function Example
```javascript
const add = (x, y) => x + y;
console.log("Arrow function add(3,4):", add(3, 4));
```

---

## Program 88: Default Parameters in Functions
```javascript
function greet(name = "Guest") {
  return `Hello, ${name}!`;
}
console.log(greet());
```

---

## Program 89: Spread Operator Example
```javascript
const arr1Spread = [1, 2, 3];
const arr2Spread = [4, 5, 6];
const mergedSpread = [...arr1Spread, ...arr2Spread];
console.log("Merged with spread:", mergedSpread);
```

---

## Program 90: Rest Parameters Example
```javascript
function sumAll(...numbers) {
  return numbers.reduce((acc, cur) => acc + cur, 0);
}
console.log("Sum of all:", sumAll(1, 2, 3, 4, 5));
```

---

## Program 91: Template Literals
```javascript
const nameTpl = "Alice";
console.log(`Hello, ${nameTpl}! Welcome to JavaScript.`);
```

---

## Program 92: Class with Static Method
```javascript
class MathUtil {
  static square(x) {
    return x * x;
  }
}
console.log("Square of 5:", MathUtil.square(5));
```

---

## Program 93: Module Export/Import Simulation (Node.js)
// File: myModule.js
```javascript
// Uncomment and run in Node.js environment
// module.exports = { sayHi: () => console.log("Hi from module!") };
```

// File: main.js
```javascript
// const { sayHi } = require('./myModule');
// sayHi();
```

---

## Program 94: Fetch with Error Handling (Async/Await)
```javascript
async function getData() {
  try {
    const res = await fetch("https://api.github.com/invalid-endpoint");
    if (!res.ok) throw new Error("Network response was not ok");
    const data = await res.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch error:", error);
  }
}
getData();
```

---

## Program 95: Basic Express Server (Node.js)
// Run with Node.js after installing express (npm install express)
```javascript
const express = require('express');
const app = express();
app.get("/", (req, res) => res.send("Hello from Express!"));
app.listen(3000, () => console.log("Server running on port 3000"));
```

---

## Program 96: WebSocket Client Example (Browser)
```javascript
// Run in browser console (requires a running WebSocket server)
const ws = new WebSocket("wss://echo.websocket.org");
ws.onopen = () => {
  console.log("WebSocket connection opened");
  ws.send("Hello WebSocket");
};
ws.onmessage = event => console.log("Received:", event.data);
```

---

## Program 97: Date and Time Formatting
```javascript
const now = new Date();
console.log("Current date and time:", now.toLocaleString());
```

---

## Program 98: JSON Pretty Print
```javascript
const objPretty = { name: "Alice", age: 30, hobbies: ["reading", "gaming"] };
console.log("Pretty JSON:\n", JSON.stringify(objPretty, null, 2));
```

---

## Program 99: Sorting an Array of Objects
```javascript
const users = [
  { name: "Alice", age: 30 },
  { name: "Bob", age: 25 },
  { name: "Charlie", age: 35 }
];
users.sort((a, b) => a.age - b.age);
console.log("Sorted by age:", users);
```

---

## Program 100: Combining Multiple Concepts
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  greet() {
    return `Hello, I'm ${this.name} and I'm ${this.age} years old.`;
  }
}

const people = [
  new Person("Alice", 30),
  new Person("Bob", 25),
  new Person("Charlie", 35)
];

people.forEach(person => console.log(person.greet()));
```

---

Enjoy exploring, testing, and modifying these JavaScript examples!
