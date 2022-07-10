# JavaSciript

JavaScript files have the extension .js similar to .css for stylesheets. External JavaScript files are used for more complex scripts.

console.log() is the command to print something to the developer console in your browser. 
You can use this to print the results from any of the following articles and exercises to the console.

Variables are simply “storage containers” for data in your code. Until recently there was only one way 
to create a variable in JavaScript — the var statement. But in the newest JavaScript versions we have two more ways — let and const.

- we can combine the variable declaration and assignment into a single line
- We can also declare multiple variables in one line
- The var keyword is almost the same as let. It also declares a variable, but in a slightly different, “old-school” way.

There are two limitations on variable names in JavaScript:

- The name must contain only letters, digits, or the symbols $ and _.
- The first character must not be a digit.

Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point etc.
JavaScript numbers are always stored as double precision floating point numbers,This format stores numbers in 64 bits.
Floating point arithmetic is not always 100% accurate: for example by adding 0.2 + 0.1 it gives 0.30000000000000004, 
so to prevent this we can add by (0.2 * 10 + 0.1 * 10) / 10 so it gives 0.3 as answer.
If you add two strings, the result will be a string concatenation.
JavaScript will try to convert strings to numbers in all numeric operations, but + is an exception since it is used for concatenation.

NaN is a JavaScript reserved word indicating that a number is not a legal number.
Trying to do arithmetic with a non-numeric string will result in NaN (Not a Number).
You can use the global JavaScript function isNaN() to find out if a value is a not a number.
If you use NaN in a mathematical operation, the result will also be NaN Or the result might be a concatenation.
NaN is a number: typeof NaN returns number

Infinity (or -Infinity) is the value JavaScript will return if you calculate a number outside the largest possible number.
Division by 0 (zero) also generates Infinity, Infinity is a number: typeof Infinity returns number.

Never write a number with a leading zero (like 07).
Some JavaScript versions interpret numbers as octal if they are written with a leading zero.

JavaScript interprets numeric constants as hexadecimal if they are preceded by 0x.

By default, JavaScript displays numbers as base 10 decimals.
But you can use the toString() method to output numbers from base 2 to base 36.
Hexadecimal is base 16. Decimal is base 10. Octal is base 8. Binary is base 2.

Normally JavaScript numbers are primitive values created from literals,
But numbers can also be defined as objects with the keyword new. example: let y = new Number(123);
Comparing two JavaScript objects always returns false.

Difference between == and ===

- 0==false // true, because false is equivalent of 0 
- 0===false // false, because both operands are of different type 
- 2=="2" // true, auto type coercion, string converted into number 
- 2==="2" // false, since both operands are not of same type
- === is known as strictly equality operator.

You may see some people using == and != in their tests for equality and non-equality. These are valid operators in JavaScript, but they differ from ===/!==. The former versions test whether the values are the same but not whether the values' datatypes are the same. The latter, strict versions test the equality of both the values and their datatypes. The strict versions tend to result in fewer errors, so we recommend you use them.

An *operator* is unary if it has a single operand. For example, the unary negation - reverses the sign of a number
The unary plus or, in other words, the plus operator + applied to a single value, doesn’t do anything to numbers. But if the operand is not a number, the unary plus converts it into a number. unary pluses are applied first, they convert strings to numbers, and then the binary plus sums them up.

Chained assignments evaluate from right to left.
example: a = b = c = 2 + 2;

*Concatenate* just means "join together". To join together strings in JavaScript you can use a different type of string, called a template literal.
A template literal looks just like a normal string, but instead of using single or double quote marks (' or "), you use backtick characters (`)
Example:

```javascript
const name = 'Chris';
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris"
```

You can use the same technique to join together two variables:

```javascript
const one = 'Hello, ';
const two = 'how are you?';
const joined = `${one}${two}`;
console.log(joined); // "Hello, how are you?"
```

You can also concatenate strings using the + operator

The Number object converts anything passed to it into a number, if it can. 
every number has a method called toString() that converts it to the equivalent string.

Template literals respect the line breaks in the source code, so you can write strings that span multiple lines like this:

```javascript
const output = `I like the song.
I gave it a score of 90%.`;
console.log(output);  // I like the song.
                      // I gave it a score of 90%.
```

We can also use \n to break the line.

By default, the replace() method replaces only the first match

All string methods return a new string. They don't modify the original string.
Formally said:
Strings are immutable: Strings cannot be changed, only replaced.

text.split(",")    // Split on commas
text.split(" ")    // Split on spaces
text.split("|")    // Split on pipe

To see whether a string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.
In other words, strings are compared letter-by-letter.
When comparing values of different types, JavaScript converts the values to numbers.

In JavaScript we have the following conditional statements:

- Use if to specify a block of code to be executed, if a specified condition is true
- Use else to specify a block of code to be executed, if the same condition is false
- Use else if to specify a new condition to test, if the first condition is false
- Use switch to specify many alternative blocks of code to be executed

Any value that is not false, undefined, null, 0, NaN, or an empty string ('') actually returns true when tested as a conditional statement, therefore you can use a variable name on its own to test whether it is true, or even that it exists (that is, it is not undefined.)

## Ternary Operator

The ternary or conditional operator is a small bit of syntax that tests a condition and returns one value/expression if it is true, and another if it is false — this can be useful in some situations, and can take up a lot less code than an if...else block if you have two choices that are chosen between via a true/false condition.
The pseudocode looks like this:

( condition ) ? run this code : run this code instead
The ternary operator is not just for setting variable values; you can also run functions, or lines of code — anything you like.
A sequence of question mark operators ? can return a value that depends on more than one condition.

## Slicing

The slice() method extracts parts of a string and returns the extracted parts in a new string.
The substr() method extracts parts of a string, beginning at the character at the specified position, and returns the specified number of characters.
The substring() method extracts parts of a string and returns the extracted parts in a new string.

## Functions

Functions are values. They can be assigned, copied or declared in any place of the code.
If the function is declared as a separate statement in the main code flow, that’s called a “Function Declaration”.
If the function is created as a part of an expression, it’s called a “Function Expression”.
Function Declarations are processed before the code block is executed. They are visible everywhere in the block.
Function Expressions are created when the execution flow reaches them.
As a rule of thumb, when we need to declare a function, the first to consider is Function Declaration syntax. It gives more freedom in how to organize our code, because we can call such functions before they are declared.
That’s also better for readability, as it’s easier to look up function f(…) {…} in the code than let f = function(…) {…};. Function Declarations are more “eye-catching”.
…But if a Function Declaration does not suit us for some reason, or we need a conditional declaration, then Function Expression should be used.

Example of function Declaration:

```javascript
function sayHi() {
  alert( "Hello" );
}
```

Example of function Expression:

```javascript
let sayHi = function() {
  alert( "Hello" );
};
```

## Arrow Functions

It’s called “arrow functions”, because it looks like this:
let func = (arg1, arg2, ..., argN) => expression;

In other words, it’s the shorter version of:
let func = function(arg1, arg2, ..., argN) {
  return expression;
};

Sometimes we need something a little bit more complex, like multiple expressions or statements. It is also possible, but we should enclose them in curly braces. Then use a normal return within them.
like this

```javascript
let sum = (a, b) => {  // the curly brace opens a multiline function
  let result = a + b;
  return result; // if we use curly braces, then we need an explicit "return"
};
alert( sum(1, 2) ); // 3
```

## Default Parameters

If you're writing a function and want to support optional parameters, you can specify default values by adding = after the name of the parameter, followed by the default value:

```javascript
function hello(name='Chris') {
  console.log(`Hello ${name}!`);
}
hello('Ari'); // Hello Ari!
hello();      // Hello Chris!
```

## Anonymous function

```javascript
function() {
  alert('hello');
}
```

This is called an anonymous function, because it has no name. You'll often see anonymous functions when a function expects to receive another function as a parameter. In this case the function parameter is often passed as an anonymous function.

## For Loop

For loop is syntax is:
for(initialisation;test condition;increment or decrement){ }
we can also for loop like this:
for (const cat of cats) {
  console.log(cat);
}
To traverse the array.

You can use map() to do something to each item in a collection and create a new collection containing the changed items.
example: 

```javascript
const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Caracal', 'Lion'];
const upperCats = cats.map(toUpper);
console.log(upperCats);
// [ "LEOPARD", "SERVAL", "JAGUAR", "TIGER", "CARACAL", "LION" ]
```

## While Loop

it's loop's syntax looks like so:

initializer
while (condition) {
  // code to run

  final-expression
}

## Do While Loop

The do...while loop is very similar, but provides a variation on the while structure:

initializer
do {
  // code to run

  final-expression
} while (condition)

The main difference between a do...while loop and a while loop is that the code inside a do...while loop is always executed at least once. That's because the condition comes after the code inside the loop. So we always run that code, then check to see if we need to run it again. In while and for loops, the check comes first, so the code might never be executed.

we can get a nodelist of all of the items matching a specific selector with querySelectorAll('selector').
for single selector we can use querySelector('selector')
While using selector use quotes and identify class or id or tag like you select in CSS.

For using querySelector on a tag which has attribute; example: <audio data-key="65">
we can select like this querySelector("audio[data-key]")

If you want to use a function value which is in with attribute value example <audio data-key="65"> in which the value 65 is returned from an function
we can use querySelector(`audio[data-key]="${e.keyCode}"`) in this backtick and ${} is used to differentiate the return value and a selector.
Because single and double quotes only contains normal strings and we can't include a expression within it.
Backticks represent template literals, which also contain other parts called placeholders, which are embedded expressions delimited by a dollar sign and curly braces: ${expression}.

When we use querySelectorAll, it returns a nodelist not an array so we can't traverse through it by slicing. 
We can traverse through it by using forEach function.

When a function is used as an event handler, its this is set to the element on which the listener is placed (some browsers do not follow this convention for listeners added dynamically with methods other than addEventListener()).

## Bubbling

Event bubbling is a method of event propagation in the HTML DOM API when an event is in an element inside another element, and both elements have registered a handle to that event. It is a process that starts with the element that triggered the event and then bubbles up to the containing elements in the hierarchy. In event bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.
To Stop Bubbling we can use <event>.stopPropagation();

To make the eventlistener listen only once, we can use addEventListener('event','function or anything',{once:true})
the once parameter makes sure that it only done once.

## Objects

An object can be created with figure brackets {…} with an optional list of properties. A property is a “key: value” pair, where key is a string (also called a “property name”), and value can be anything.
We can imagine an object as a cabinet with signed files. Every piece of data is stored in its file by the key. It’s easy to find a file by its name or add/remove a file.
It is like Dictionary in Python.
The syntax always follows this pattern:

const objectName = {
  member1Name: member1Value,
  member2Name: member2Value,
  member3Name: member3Value
};

To walk over all keys of an object, there exists a special form of the loop: for..in. This is a completely different thing from the for(;;) construct that we studied before.
The syntax:
for (key in object) {
  // executes the body for each key among object properties
}

In objects, the integers are default sorted in ascending order even when we are creating it in a unordered manner.
As an example, let’s consider an object with the phone codes:

```javascript
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};

for (let code in codes) {
  alert(code); // 1, 41, 44, 49
}
```

The phone codes go in the ascending sorted order, because they are integers. So we see 1, 41, 44, 49.

On the other hand, if the keys are non-integer, then they are listed in the creation order

## Constructor

A constructor is just a function called using the new keyword. When you call a constructor, it will:

i)create a new object
ii)bind this to the new object, so you can refer to this in your constructor code
iii)run the code in the constructor
iv)return the new object.

Constructors, by convention, start with a capital letter and are named for the type of object they create. 
Example:

```javascript
function Person(name) {
  this.name = name;
  this.introduceSelf = function() {
    console.log(`Hi! I'm ${this.name}.`);
  }
}
```

To call Person() as a constructor, we use new:

```javascript
const salva = new Person('Salva');
salva.name;
salva.introduceSelf();

const frankie = new Person('Frankie');
frankie.name;
frankie.introduceSelf();
Copy to Clipboard
```

## Methods To use

1. array.sort()
syntax array.sort(function () {
  conditon{
    statement
    return 1 -1 or 0}
})

The sort method takes an optional comparison function that determines the resulting sort order based on the following:
if its return value is less than zero, then sort value1 to a lower index than value2
if its return value is zero, then leave the indices of value1 and value2 unchanged with respect to each other
if its return value is greater than zero, then sort value1 to a higher index than value2

2. array.map()
The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.
Syntax:
map(function(element) { /* ... */ })

Since map builds a new array, using it when you aren't using the returned array is an anti-pattern; use forEach or for...of instead.
You shouldn't be using map if:
you're not using the array it returns; and/or
you're not returning a value from the callback.

3. array.filter()
The filter() method creates a new array with all elements that pass the test implemented by the provided function.
Syntax:
filter((element) => { /* ... */ } )

4. array.reduce()
The reduce() method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.
The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).
Syntax:
reduce(function(previousValue, currentValue, currentIndex, array) { /* ... */ }, initialValue)
initialValue is used when it is not initialised, or the value can be given directly while using function. It is also optional.
CurrentIndex and array are optional.

Example:
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  initialValue
);
console.log(sumWithInitial);
// expected output: 10

5. array.some()
The some() method tests whether at least one element in the array passes the test implemented by the provided function. It returns true if, in the array, it finds an element for which the provided function returns true; otherwise it returns false. It doesn't modify the array.
Syntax
some((element) => { /* ... */ } )

6. array.every()
The every() method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.
Syntax
every((element) => { /* ... */ } )

7. array.find()
The find() method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

If you need the index of the found element in the array, use findIndex().
If you need to find the index of a value, use Array.prototype.indexOf(). (It's similar to findIndex(), but checks each element for equality with the value instead of using a testing function.)
If you need to find if a value exists in an array, use Array.prototype.includes(). Again, it checks each element for equality with the value instead of using a testing function.
If you need to find if any element satisfies the provided testing function, use Array.prototype.some().

Syntax
find((element) => { /* ... */ } )