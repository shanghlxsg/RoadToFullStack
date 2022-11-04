# Brief introduction to JavaScript

## JavaScript

JavaScript is a high-level, object-oriented, multi-paradigm programming langauge.

* High-level: do not have to worry about complex issues like memory management.

* Object-oriented programming (OOP): based on objects, for storing most kinds of data.

* JavaScript can run outside of web browsers - such as using JavaScript on web servers.

  * `Node.js` is another very popular framework that does not need any browser at all, allowing the creation of `backend` applications (i.e., applications that run on web servers).

  * JavaScript on web browsers creates `frontend` applications.

* JavaScript can also build native mobile applications as well as native desktop applications.

## JavaScript releases

* Huge update to JavaScript in 2015 officially called `ES2015` or simply `ES6` (as it was released after `ES5`).

* All releases from `ES6` onwards are known as `Modern JavaScript`.

## Modern JavaScript libraries and frameworks

* `React`, `Angular`, `Vue`.

* Get really good at JavaScript before jumping into any framework.

* Your library of choice might not always be as popular as it is today.

## Commenting

* Single line comment uses `//`.

* Multi-line comment uses `/*` to start and `*/` to end.

## Development platforms

* VS Code is the primary tool used by coders.

* The developer console for each web browser previews the HTML and JavaScript code.

  * Chrome = `Ctrl + Shift + J`.

  * Firefox = `Ctrl + Shift + I`.

## Linking a JavaScript file

* HTML document `.html` is always needed because JavaScript `.js` needs to be attached to an `.html`.

* Within `.html`, you can place `<script>` after `<style>`.

* JavaScript code embedded within `<html>` are called `inline scripts` and it's not recommended.

* Separating the logic (JavaScript) from the presentation (HTML) allows the code to be cleaner and easier to maintain. To separate the logic, simply create a `.js` file containing the JavaScript code and link the source `src` to the `.HTML` file.

```html
<script src="script.js"></script>
```

## Values and variables

* Value is the smallest unit of information available in JavaScript.

* Variables are declared and can be assigned values using `let variable = "value"`.

## Conventions and rules for naming variables

* `camelCase` is the naming convention used in the JavaScript world where creating variables with more than one word should be created with the first word in lowercase and all subsequent words in uppercase (e.g., `firstNamePerson`).

* Other conventions can also be used, such as using underscore `first_name_person` as found in Ruby and other languages.

* Variables must start with alphabets, but can contain numbers for subsequent characters. Underscores `_` and dollar signs `$` are also allowed.

* The convention for writing constant variables is to use uppercase for the entire variable `let PI = 3.14`.

* The last convention used in JavaScript is to make sure the variables are descriptive.

```javascript
let myFirstJob = "Engineer";
let myCurrentJob = "Programmer";
//compared to
let job1 = "Engineer";
let job2 = "Programmer";
```

## Data types

* In JavaScript, every value is either an `object` or a `primitive value`.

* The 7 types of `primitive values` are:
  * Number - always floating point numbers.
  * String - sequence of characters defined either using single `'` or double `"` quotes.
  * Booelean - a logical type.
  * Undefined - a variable whose value is not yet defined.
  * Null - empty value.
  * Symbol - a value that is unique and cannot be changed (`ES2015`).
  * BigInt - integers that are too large for the `Number` type (`ES2020`).

* Dynamic typing in JavaScript means you do not have to manually define the data type as JavaScript automatically determines the data type of value when it is stored as a variable.

* To show the data type of a variable, use the operator `typeof`.

## Declaring variables

* `let` and `const` were introduced in `ES6` while `var` is the old way of declaring variables.

* `let` creates a dynamic/mutable variable (data type changes) while `const` creates an immutable variable (data type does not change).

* `const` immutable variables also means it cannot be declared empty.

* Good coding practice suggests to always use `const` by default unless you are very sure the variable needs to change at some point in the future.

* `var` should be completed avoided in modern JavaScript but good to know for legacy reasons.

## Operators

* Arithmetic operators.
  * `a + b` addition.
  * `a - b` subtraction.
  * `a * b` multiplication.
  * `a / b` division.
  * `a % b` modulus - outputs remainder of an integer division.
  * `a ** b` exponentiation - `a` to the power of `b`.
  * `a++` or `++a` increment - increase integer value by one.
  * `a--` or `--a` decrement - decrease integer value by one.
  * `-a` unary negation operator - negation of an operand.
  * `+a` unary operator - converts non-number to number.

* Comparison operators.
  * `x == y` equality - compares the value of two operands (if equal, true).
  * `x != y` inequality.
  * `x === y` strict equality - compares both value and type of two operands.
  * `x !== y` strict inequality.
  * `x > y` greater than.
  * `x >= y` greater than or equal to.
  * `x < y` less than.
  * `x <= y` less than or equal to.

* Logical operators.
  * `a && b` logical AND.
  * `a || b` logical OR.
  * `a ! b` logical NOT.

* Bitwise operators - performs the specified operator in each bit of its integer arguments.
  * `a & b` bitwise AND.
  * `a | b` bitwise OR.
  * `a ^ b` bitwise XOR.
  * `~a` bitwise NOT.
  * `a << b` left shift - move all the bits in the first operand to the left by the number of places specified in the second operand, new bits are filled with zero.
  * `a >> b` signed right shift (with sign-extension).
  * `a >>> b` unsigned right shift (with zero-extension).

* Assignment operators.
  * `a = b` simple assignment.
  * `a += b` addition assignment `a = a + b`.
  * `a -= b` subtraction assignment `a = a - b`.
  * `a /= b` division assignment `a = a / b`.
  * `a %= b` remainder assignment `a = a % b`.
  * `a **= b` exponentiation assignment `a = a ** b`.
  * `a <<= b` left shift assignment `a = a << b`.
  * `a >>= b` right shift assignment `a = a >> b`.
  * `a &= b` bitwise AND assignment `a = a & b`.
  * `a |= b` bitwise OR assignment `a = a | b`.
  * `a ^= b` bitwise XOR assignment `a = a ^ b`.

* `delete` operator.
  * Deletes the specified property of a JavaScript object.
  * Avoid using `delete` for arrays.

```javascript
delete object
// or
delete object.property
// or
delete object['property']

delete variable // false
delete function // false
```

* `,` comma operator.
  * Evaluates operands from left to right sequentially and returns value of the rightmost operand.
  * Used as a separator for multiple expressions at a place that requires a single expression.
  * Most useful for multiple variables in loop functions.

* `( )` grouping operator.
  * Overrides the normal operator precedence so that the expressions with lower precendence within the parenthesis `(...)` can be evaluated first.
  * Controls the precendence of evaluation of expressions.

* Short circuiting operators.
  * In JavaScript, an expression is evaluted from left to right until it is confirmed that the remaining conditions will not affect the already evaluted results.
  * E.g., evaluting `false && true` will short circuit before `true` is evaluated, as `false && ...` will always return `false` regardless of subsequent conditions.

* `a = a ?? b` nullish coalescing operator.
  * Returns the right hand value if the left hand value is `null` or `undefined`.

```javascript
<script>
function foo(bar){
    bar = bar ?? 42;
    console.log(bar);
}

foo(); // 42
foo(69); //69
foo(0); // 0
```

* `a ? b : c` ternary operator.
  * Functions similar to `if else` statement.
  * Evaluates condition `a`. Outputs `b` if true. Outputs `c` if false.
  * Nested ternary operators:

```javascript
a ? b :
    c ? d :
    e ? f : g ;
```

* `var x = objectName instanceof objectType`  instanceof operator.
  * Checks the type of an object at run time. Returns boolean `true` if `objectName` is an instance of a specified class `objectType`.

* `...` spread operator.
  * Expands an iterable object into the list of its arguments.
