# JavaScript

#### Data Types

- Boolean (true, false)
- Number (-1, 10.3, etc.)
- String ("Hello", "10.3", etc)
- Null
- Undefined

#### Operators

- Notice equals sign. 
  - 10.2 === "10.2" is false
  - 10.2 == "10.2" is true
  - == performs type coercion
  - So use === and !== only!

#### Defining Variables
- let variableNmae = value
- const constantName = value

#### Null vs Undefined

- Undefined means "declared but not yet assigned a value"
- Null means "no value"

```js
let firstName;
// firstNmae is now undefined.
firstName = "Albert";

firstName = null;
// we can explicitly "empty" the variable.
```

#### Output

- console.out() writes to the JavaScript console.
```js
const a = 5;
const b = 10;
console.log(`a * b = ${a * b}`);
```
- Alert() generates a pop-up notification with the given content.


#### Strings

- ' ' and " " are basiaclly the same. 
  - Both of them cannot define multiple-line strings.
  - Cannot nest a pair of ' in another pair of '. But 'a"b"c' and 'a\'b\'c' are fine. " is the same.
- \` \` can define template strings.
  - Template strings can be multiple lines long.
  - Embed the expressions using ${}.
  ```js
  function simpleTag(strings, ...values) {
    console.log(strings); // ["Hello, ", " is ", " years old."]
    console.log(values);  // ["Alice", 25]
    return `${strings[0]}${values[0]}${strings[1]}${values[1]}${strings[2]}`;
  }

  let name = "Alice";
  let age = 25;

  let result = simpleTag`Hello, ${name} is ${age} years old.`;
  console.log(result); // "Hello, Alice is 25 years old."
  ```

#### Arrays
- Basic operations:
```js
let a = [10, "Bird", false];
console.log(a[2]); //false
a[2] = true;
a.pop();
a.push("rabbit"); // [10, "Bird", "rabbit"]
```

#### Conditionals

```js
if (a === 0) {

} else if (a > 0) {

} else {

}
```

#### Loops

```js
while (z < 100) {
    z = z * 2;
}

const pet = ["cat", "bird", "dog"];
for (let i = 0; i < pet.length; i++) {
    const phrase = 'I love my' + pet[i];
    console.log(phrase);
}

for (const animal of pets) {
    const phrase = 'I love my' + animal;
    console.log(phrase);
}
```

#### Objects
- A JavaScript object is a collection of name:value pairs.
```js
const myCar = {
    make    : "Ford",
    model   : "Mustang",
    year    : 2005,
    color   : "red"
};

console.log(myCar["color"]);
console.log(myCar.model);

const { make, model } = myCar;
// This is object destructuring. It's equal to "const make = myCar.make;
// const model = myCar.model;"
```

#### Array and Object
- They are both references. 
```js
let arr1 = [1,2,3];
let arr2 = [1,2,3];
console.log(arr1 === arr2); //false
let arr3 = arr1;
let arr4 = [...arr1];
arr1[1] = 10;
// arr3 will be [1,10,3]; arr4 will be [1,2,3];
// Objects are the same. Just change [...arr] to {...obj}
```

#### Functions
```js
//1
function greet(name) {
    return `hello, ${name}`;
}
//2
const greet = function(name) {
    return `hello, ${name}`;
};
//3
const greet = (name) => {
    return `hello, ${name}`;
};
//4, if the function body only contains one statement
const greet = (name) => `hello, ${name}`;
//It's also ok to assign a function to a variable.
const somefunc = greet;
```

#### Classes
```js
class rectangle {
    constructor(width, height) {
        this.width = width;
        this.height = height;
    }

    getArea = () => {
        return this.width * this.height;
    };
}

const rect = new rectangle(6, 18);
console.log(rect.getArea());
```

#### connect js to html

add <script src="game.js" defer></script> in the head tag.

#### How do we use a variable from another js file

Define a function to return the variable and call it.

#### Constant loops with a delay

- setInterval(func, delay, [arg1, arg2, ...]);
- clearInterval(intervalID);
```js
let loop = setInterval(main, 1000); //1000 = 1 sec
clearInterval(loop);
```