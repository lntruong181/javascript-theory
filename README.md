# javascript-thory
# 01. Value - Type
`EASY TO LEARN`

  - [Data types](#data-types)
  - [typeof operator](#typeof-operator)
  - [Primitive and Reference type](#primitive-and-reference-type)
  - [Primitive wrapper objects in JavaScript](#primitive-wrapper-objects-in-javascript)
  - [References](#references)

## Data types
-	Number
```js
    123456
    2.45    // fractional
    2.993e6 // --> 2.993 x 10^6   //exponent
```
-	String
```js
    '' // single quotes
    "" // double quotes
    `` // backticks

    /* Concatenate */
   'hello' + 'world' // --> 'helloworld'
```
-	Boolean
```js
    true
    false
```
-	Object `{}`
-	Array `[]`
-	Function
```js
    function fnName() {
    	// do something
    }
```
-	Special values
```js
    Infinity   -Infinity    NaN

    typeof NaN;  // "number"
    typeof Infinity;  // "number"
```

-	Empty values
```js
    null    undefined

    typeof null // "object"
    typeof undefined    // "undefined"
```

## typeof operator
```js
    typeof "Hello";    // --> "string"
```

## Primitive and Reference type
The differences between primitive types and reference types is how they are stored in memory.
-	Primitive
    -	A primitive (primitive value, primitive data type) is data that is **not an object**.
    -	Primitive values have **no properties**.
    -	In JavaScript, there are 6 primitive data types:
        		string, number, boolean, null, undefined, symbol

    -	Primitive values are **immutable**, but it **can be replaced**.
    ```js
        var str = 'dat';
        str.toUpperCase();
        console.log(str);       // dat
        str = 'Hello';
        console.log(str);       // Hello

        var num = 12;
        function minusOne(val) {
            val -= 1;
        }
        minusOne(num);
        console.log(num);       // 12
    ```

-	Reference
    -	Reference values are references to objects (addresses where they will be found).
    -	A property can be a reference (object) or a primitive.
    ```js
        var arr = [2, 4, 6];
        var refArr = arr;
        console.log(arr === refArr);    // true

        var arr = [2, 4, 6];
        var anotherArr = [2, 4, 6];
        console.log(arr === anotherArr);    // false

        var obj = {
            a: 2,
            c: {
                d:12
            }
        };

        var refObj = obj.c;
        refObj.d = 1;
        console.log(obj.c.d);   // 1
    ```

## Primitive wrapper objects in JavaScript
    String  Number  Boolean Symbol


## References
https://stackoverflow.com/questions/13266616/primitive-value-vs-reference-value

https://developer.mozilla.org/en-US/docs/Glossary/Primitive

https://medium.com/@ctrlalt_diljeet/primitive-types-vs-reference-types-in-javascript-8503259c30ca





# 02. Operator

  - [JavaScript Operator Precedence Values](#javascript-operator-precedence-values)
  - [Arithmetic](#arithmetic)
  - [Comparison operators](#comparison-operators)
  - [Unary & Binary & Ternary](#unary--binary--ternary)
  - [Logical operators](#logical-operators)
  - [Automatic type conversion](#automatic-type-conversion)
  - [Short-circuiting of logical operators](#short-circuiting-of-logical-operators)
  - [typeof operator](#typeof-operator)
  - [delete operator](#delete-operator)
  - [References](#references)

## JavaScript Operator Precedence Values
|	OPERATOR  |			NAME			|		EXAMPLE		|
|:-----------:|:---------------------------:|:-------------:|
|	( )    |  Expression grouping		|    (3 + 4)  |
|-----------|---------------------------|-------------|
|	.		|	Member					|	person.name		|
|	[]		|		Member				|	person["name"]	|
|	()		|		Function call		|	myFunction()	|
|	new		|		Create				|	new Date()		|
|-----------|---------------------------|-------------------|
|	<<	    |	Shift left				|	x << 2	|
|	>>	    |	Shift right				|	x >> 2	|
|	>>>	    |	Shift right (unsigned)	|	x >>> 2	|
|-----------|---------------------------|-----------|
|	in  		|	Property in Object			|	"PI" in Math		|
|	instanceof  |	Instance of Object			|	instanceof Array	|
|-----------|---------------------------|-------------------------------|
|	&	    |		Bitwise AND			|	x & y		|
|	^	    |		Bitwise XOR			|	x ^ y		|
|   &#124;  |		Bitwise OR			|	x &#124; y	|
|-----------|---------------------------|---------------|
|	+=	   |  Assignment			|	x += y		|
|	-=	   |  Assignment			|	x -= y		|
|	*=	   |  Assignment			|	x *= y		|
|	%=	   |  Assignment			|	x %= y		|
|	<<=	   |  Assignment			|	x <<= y		|
|	>>=	   |  Assignment			|	x >>= y		|
|	>>>=   |  Assignment			|	x >>>= y	|
|	&=	   |  Assignment			|	x &= y		|
|	^=	   |  Assignment			|	x ^= y		|
|  &#124;= |  Assignment			|	x &#124;= y	|
|-----------|---------------------------|-----------|
|	yield	|  Pause Function		|	yield x	|
|	,	   	|  Comma				|	5 , 6	|
|-----------|-----------------------|-----------|

## Arithmetic
```js
+ - * / --> easy
**  --> Exponentiation (ES6)
++  --> Postfix/Prefix Increment
--  --> Postfix/Prefix Decrement
%   --> Remainder
()  --> Expression grouping (Priority)
/*
Note: ++num   // increase before expressing
        num++ // express, then increasing
*/
```

## Comparison operators
```js
/*
<   >   ==  !=  <=  >=      // easy
===     // Strict equal (equal type and equal value)
!==     // Strict unequal
*/

1 > 3   // --> false
'Aardvark' < 'Zoroaster' // --> true
NaN == NaN  //	--> false
```


## Unary & Binary & Ternary
- Unary : 1 value
    `Ex: -(1)`
- Binary : 2 values
    `Ex: (1 + 2)`
- Ternary : 3 values
```js
1st ? 2nd : 3rd
condition ? true : false
Ex: true ? 1 : 0;   // --> 1
    false ? 1 : 0;  // --> 0
    console.log(true ? 'yes' : 2);  // --> yes
```

## Logical operators
```js
&& -- and
|| -- or
!  -- not

Ex: 1 + 1 == 2 && 10 * 10 > 50  // --> true
Note:   NaN == NaN  // false
```

## Automatic type conversion
-	JavaScript is a **loosely typed** language, which means that whenever an operator or statement is expecting a particular data-type, JavaScript will automatically convert the data to that type.
-	JavaScript values are often referred to as being `truthy` or `falsy`, according to what the result of such a conversion would be (i.e. true or false).
-	In fact there are only six falsy values:

	        false   undefined   null    0 (numeric zero)    "" (empty string)   NaN (Not A Number)

```js
8 * null   // --> 0
"5" - 1    // --> 4
"5" + 1    // --> 51
"five" * 2     // --> NaN
false == 0     // --> true
null == undefined     // --> true
null == 0     // --> false
0 == false  // --> true
"" == false // --> true
"" === false        // --> false
```

## Short-circuiting of logical operators
-	The **&&** and **||** operators **short-circuit**, meaning they don't evaluate the right hand side if it isn't necessary.
-	They will return either the original left-hand value or the right-hand value.

## typeof operator
```js
console.log(typeof "Hello");    // --> "string"
```

## delete operator
The [delete operator (See MDN)][delete-operator] removes a given property from an object.
On successful deletion, it will return true, else false will be returned.

-   If the property which you are trying to delete does **not exist**, return **true**
-   If a property with the same name exists on the object's prototype chain, then, after deletion, the object will use the **property from the prototype chain**.
-   Any property declared with var cannot be deleted from the global scope or from a function's scope.
    -   As such, delete cannot delete any functions in the global scope.
    -   Functions which are part of an object (apart from the global scope) can be deleted with delete.
-   Any property declared with let or const cannot be deleted from the scope within which they were defined.
-   **Non-configurable** properties cannot be removed. (see Object)

## References
https://www.sitepoint.com/automatic-type-conversion/

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete

[delete-operator]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete


# 03. Program structure

  - [Expressions and Statements](#expressions-and-statements)
  - [Binding / Variables](#binding--variables)
  - [Scope](#scope)
  - [The environment](#the-environment)
  - [Flow of control](#flow-of-control)
  - [Hoisting](#hoisting)
  - [Side Effects](#side-effects)
  - [References](#references)

## Expressions and Statements
-	A fragment of code that produces a value is called an expression.
-	An expression corresponds to a sentence fragment
-	A JavaScript statement corresponds to a full sentence.
-	A program is a list of statements.

## Binding / Variables
-	To catch and hold values, JavaScript provides a thing called a binding, or variable
```js
/*
    keywords:   let const   var
*/

var a = 1;
var a = 2;  // this's okay
let a = 3;  // Uncaught SyntaxError: Identifier 'a' has already been declared
const c;    // Uncaught SyntaxError: Missing initializer in const declaration

const b = 12;   // primitive value
b = 5;  // Uncaught TypeError: Assignment to constant variable.
```

## Scope
Bindings declared with **let** and **const** are in fact **local** to the block that they are declared in, so if you create one of those inside of a loop, the code before and after the loop cannot “see” it.
```js
// Ex 1:
const halve = function(n) {
    return n / 2;   //  local binding
};
let n = 10; // global binding
console.log(halve(100));    // --> 50
console.log(n); // --> 10

// Ex 2:
let x = 10;
if (true) {
    let y = 20;
    var z = 30;
    console.log(x + y + z); // --> 60
}
// y is not visible here
console.log(x + z); // --> 40
```

## The environment
The collection of bindings and their values that exist at a given time is called the environment. When a program starts up, this environment is not empty. It always contains bindings that are part of the language standard, and most of the time,it also has bindings that provide ways to interact with the surrounding system. For example, in a browser, there are functions to interact with the currently loaded website and to read mouse and keyboard input.

## Flow of control
-	Loops
```js
while (*condition*) {
    // code block to be executed
}

do {
    // code block to be executed
} while (*condition*) 

for (statement 1; statement 2; statement 3) {
    // code block to be executed
}
/*
Note: break;    // Breaking out of loop
        continue;  // Continue looping
*/
```

-	Condition execution
```js
if (*condition*) {
    // code block to be executed // true
} else {
    // code block to be executed // false
}
```

-	Switch case
```js
switch (*condition*) {
    case *value1*:
        // code block to be executed
        break;
    case *value2*:
        // code block to be executed
        break;
    default:
        // code block to be executed
        break;
}
```

## Hoisting
```js
var x = 5;
function run() {
    console.log(x);   // output --> undefined
    //
    var x = 12;
}
run();

var x = 5;
function run() {
    console.log(x);
    //
    let x = 12;
}
run();  // Uncaught ReferenceError: x is not defined
```

## Side Effects
-	A side effect is any application state change that is observable outside the called function other than its return value. Side effects include:
    -	Modifying any external variable or object property (e.g., a global variable, or a variable in the parent function scope chain)
    -	Logging to the console
    -	Writing to the screen
    -	Writing to a file
    -	Writing to the network
    -	Triggering any external process
    -	Calling any other functions with side-effects

-	Side effects are mostly avoided in functional programming, which makes the effects of a program much easier to understand, and much easier to test.

-	Haskell and other functional languages frequently isolate and encapsulate side effects from pure functions using monads. The topic of monads is deep enough to write a book on, so we’ll save that for later.

-	What you do need to know right now is that side-effect actions need to be isolated from the rest of your software. If you keep your side effects separate from the rest of your program logic, your software will be much easier to extend, refactor, debug, test, and maintain.

-	This is the reason that most front-end frameworks encourage users to manage state and component rendering in separate, loosely coupled modules.

## References
https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0

https://eloquentjavascript.net/02_program_structure.html


# 04. Function

 * [Definition](#definition)
 * [Defining](#defining)
 * [Arguments](#arguments)
 * [Lexical scope](#lexical-scope)
 * [Execution context](#execution-context)
 * [Lexical Environment](#lexical-environment)
 * [Closure](#closure)
 * [Recursion](#recursion)
 * [References](#references)

## Definition
A function is a piece of program wrapped in a value.
Executing a function is called **invoking**, **calling**, or **applying** it.
- Values given to functions are called `arguments`.
- Functions may also produce values. (Expression)

In JavaScript, functions are **first-class objects**, which means they can be:
-   stored in a variable, object, or array
-   passed as an argument to a function
-   returned from a function

## Defining
```js
function fn_name(*...args*) {
    // code block to be executed
}

const fn_name = function (*...args*) {
    // code block to be executed
}

// Arrow function
const fn_name = (*...args*) => {
    // code block to be executed
}
```

## Arguments
-   Optional arguments
  ```js
function power(base, exponent = 2) {
    let result = 1;
    for (let count = 0; count < exponent; count++) {
        result *= base;
    }
    return result;
}
console.log(power(4));  // --> 16
console.log(power(2, 6));   // --> 64
```

-   Rest parameters
```js
function max(...numbers) {
    let result = -Infinity;
    for (let number of numbers) {
        if (number > result) result = number;
    }
    return result;
}
console.log(max(4, 1, 9, -2));  // --> 9
```

- An Array-like object (arguments)
```js
function f() {
    return arguments;
}
console.log(f(1, 2, 3));
//      Arguments(3) [1, 2, 3, callee: ƒ, Symbol(Symbol.iterator): ƒ]
//                     0: 1
//                     1: 2
//                     2: 3
//                     callee: ƒ f()
//                     length: 3
//                     Symbol(Symbol.iterator): ƒ values()
//                     __proto__: Object
```
## Lexical scope
A lexical scope or static scope in JavaScript refers to the accessibility of the variables, functions, and objects based on their physical location in the source code.
```js
let a = 'global';
function outer() {
    let b = 'outer';
    function inner() {
        let c = 'inner'
        console.log(c);   // prints 'inner'
        console.log(b);   // prints 'outer'
        console.log(a);   // prints 'global'
    }
    console.log(a);     // prints 'global'
    console.log(b);     // prints 'outer'
    inner();
}
outer();
console.log(a);         // prints 'global'
```

## Execution context
- An execution context is an abstract environment where the JavaScript code is evaluated and executed.
- When the global code is executed, it’s executed inside the global execution context,
and the function code is executed inside the function execution context.
- There can only be one currently running execution context (Because JavaScript is single threaded language)
- The call stack is a collection of execution contexts.

## Lexical Environment
- Every time the JavaScript engine creates an execution context to execute the function or global code,
it also creates a new lexical environment to store the variable defined in that function during the execution of that function.

- A lexical environment is a data structure that holds identifier-variable mapping.
(here identifier refers to the name of variables/functions,
and the variable is the reference to actual object [including function type object] or primitive value).

- A Lexical Environment has two components: 
    - The environment record is the actual place where the variable and function declarations are stored.
    - The reference to the outer environment means it has access to its outer (parent) lexical environment.
    This component is the most important in order to understand how closures work.
```js
// make sure you write it in global scope
let a = 'Hello World!';
function first() {
    let b = 25;  
    console.log('Inside first function');
}
first();    // execute the "first" function
console.log('Inside global execution context');

// //   the lexical environment for the global scope
//     globalLexicalEnvironment = {
//         environmentRecord: {
//             a     : 'Hello World!',
//             first : < reference to function object >
//         }
//         outer: null
//     }

// // the lexical environment for "first" function when executed
//     functionLexicalEnvironment = {
//         environmentRecord: {
//             b    : 25,
//         }
//         outer: <globalLexicalEnvironment>
//     }
```

## Closure
- This feature—being able to reference a specific instance of a local binding in an enclosing scope—is called closure.
- A closure is a function that has access to its outer function scope even after the outer function has returned. This means a closure can remember and access variables and arguments of its outer function even after the function has finished.
- When called, the function body sees the environment in which it was created, not the environment in which it is called.

```js
function multiplier(factor) {
    return function(number) {
        return number * factor;
    };
}
let twice = multiplier(2);
console.log(twice(5));  // --> 10
```

## Recursion
A function that calls itself is called recursive.
```js
function power(base, exponent) {
    if (exponent == 0) {
        return 1;
    } else {
        return base * power(base, exponent - 1);
    }
}

console.log(power(2, 3));   // 8
```

## References
https://blog.bitsrc.io/a-beginners-guide-to-closures-in-javascript-97d372284dda

https://medium.freecodecamp.org/discover-the-power-of-first-class-functions-fd0d7b599b69


# 05. Built-in Object

  - [Value properties](#value-properties)
  - [Function properties](#function-properties)
  - [Fundamental objects](#fundamental-objects)
  - [Numbers and dates](#numbers-and-dates)
  - [Text processing](#text-processing)
  - [Indexed collections](#indexed-collections)
  - [Keyed collections](#keyed-collections)
  - [Structured data](#structured-data)
  - [Control abstraction objects](#control-abstraction-objects)
  - [Reflection](#reflection)
  - [Other](#other)
  - [Do this in your browser console](#do-this-in-your-browser-console)
  - [References](#references)

![Built-in Object][built-in-object]

## Value properties
These global properties return a simple value; they have no properties or methods.
```js
Infinity
NaN
undefined
null
globalThis, self, window, frames // browser
global // nodejs
```
## Function properties
These global functions—functions which are called globally rather than on an object—directly return their results to the caller.
```js
eval()
isFinite()
isNaN()
parseFloat()
parseInt()
decodeURI()
decodeURIComponent()
encodeURI()
encodeURIComponent()
```

## Fundamental objects
These are the fundamental, basic objects upon which all other objects are based. This includes objects that represent general objects, functions, and errors.
```js
Object
Function
Boolean
Symbol
Error
EvalError
InternalError
RangeError
ReferenceError
SyntaxError
TypeError
URIError
```

## Numbers and dates
These are the base objects representing numbers, dates, and mathematical calculations.
```js
Number
BigInt
Math
Date
```

## Text processing
These objects represent strings and support manipulating them.
```js
String
RegExp
```
## Indexed collections
These objects represent collections of data which are ordered by an index value. This includes (typed) arrays and array-like constructs.
```js
Array
Int8Array
Uint8Array
Uint8ClampedArray
Int16Array
Uint16Array
Int32Array
Uint32Array
Float32Array
Float64Array
```

## Keyed collections
These objects represent collections which use keys; these contain elements which are iterable in the order of insertion.
```js
Map
Set
WeakMap
WeakSet
```

## Structured data
These objects represent and interact with structured data buffers and data coded using JavaScript Object Notation (JSON).
```js
ArrayBuffer
DataView
JSON
```

## Control abstraction objects
```js
Promise
Generator
GeneratorFunction
AsyncFunction 
```

## Reflection
```js
Reflect
Proxy
```

## Other
```js
arguments
```

## Do this in your browser console
```js
Object.getOwnPropertyNames(Object);
// (24) ["length", "name", "prototype", "assign", "getOwnPropertyDescriptor", "getOwnPropertyDescriptors", "getOwnPropertyNames", "getOwnPropertySymbols", "is", "preventExtensions", "seal", "create", "defineProperties", "defineProperty", "freeze", "getPrototypeOf", "setPrototypeOf", "isExtensible", "isFrozen", "isSealed", "keys", "entries", "values", "fromEntries"]
Object.getOwnPropertyNames(Object.prototype);
// (12) ["constructor", "__defineGetter__", "__defineSetter__", "hasOwnProperty", "__lookupGetter__", "__lookupSetter__", "isPrototypeOf", "propertyIsEnumerable", "toString", "valueOf", "__proto__", "toLocaleString"]
Object.getOwnPropertyNames(Object.__proto__);
// (9) ["length", "name", "arguments", "caller", "constructor", "apply", "bind", "call", "toString"]

Object.getOwnPropertyNames(Function);
// (3) ["length", "name", "prototype"]
Object.getOwnPropertyNames(Function.prototype);
// (9) ["length", "name", "arguments", "caller", "constructor", "apply", "bind", "call", "toString"]
Object.getOwnPropertyNames(Function.__proto__);
// (9) ["length", "name", "arguments", "caller", "constructor", "apply", "bind", "call", "toString"]
Function.__proto__ === Function.prototype
// true

Function instanceof Object
// true
Object instanceof Function
// true

function fn() {}
fn instanceof Function
// true
fn.__proto__ === Function.prototype
// true
Object.getOwnPropertyNames(fn);
// (5) ["length", "name", "arguments", "caller", "prototype"]
```

## References
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects


[built-in-object]: /assets/images/built-in-object.png


# 06. String

  - [Syntax](#syntax)
  - [Escape notation](#escape-notation)
  - [Long literal strings](#long-literal-strings)
  - [String conversion](#string-conversion)
  - [Distinction between string primitives and String objects](#distinction-between-string-primitives-and-string-objects)
  - [Character access](#character-access)
  - [String object](#string-object)
    - [I. Properties](#i-properties)
    - [II. Methods](#ii-methods)
  - [String instances](#string-instances)
    - [I. Properties](#i-properties-1)
    - [II. Methods](#ii-methods-1)
  - [References](#references) 



## Syntax
    '' single quotes
    "" double quotes
    `` backticks

## Escape notation
|                   |                                   |
|--------------|------------------------|
|\XXX	    |       an octal Latin-1 character.     |
|\'            |       	single  quote       |
|\"	           |       double  quote       |
|\\\\	          |       backslash       |
|\n 	    |       new line        |
|\r 	    |       carriage return     |
|\v 	    |       vertical tab        |
|\t 	    |       tab     |
|\b 	    |       backspace       |
|\f 	    |       form feed       |
|\uXXXX 	    |       unicode codepoint       |
|\u {X} ... \u{XXXXXX}	    |       unicode codepoint       |
|\xXX   |       the Latin-1 character       |

## Long literal strings
```js
let longString = "This is a very long string which needs " +
"to wrap across multiple lines because " +
"otherwise my code is unreadable.";

let longString = "This is a very long string which needs \
to wrap across multiple lines because \
otherwise my code is unreadable.";

// including linefeed
let longString = `This is a very long string which needs
to wrap across multiple lines because
otherwise my code is unreadable.`;
```

## String conversion
    String(*something*)

## Distinction between string primitives and String objects
```js
var s_prim = 'foo';
var s_obj = new String(s_prim);
console.log(typeof s_prim); // Logs "string"
console.log(typeof s_obj);
    //    String {"foo"}
    //             0: "f"
    //             1: "o"
    //             2: "o"
    //             length: 3
    //             __proto__: String
    //                 [[PrimitiveValue]]: "foo"
```

- String primitives and String objects also give different results when using **eval()**
- Primitives passed to eval are treated as source code
- String objects are treated as all other objects are, by returning the object

```js
var s1 = '2 + 2';             // creates a string primitive
var s2 = new String('2 + 2'); // creates a String object
console.log(eval(s1));        // returns the number 4
console.log(eval(s2));        // returns the string "2 + 2"
console.log(eval(s2.valueOf())); // returns the number 4
```

## Character access
```js
'master'.charAt(2);    // "s"
'master'[2];   // "s"
```

For character access using **bracket notation**, attempting to delete or assign a value to these properties will **not succeed**.

The properties involved are **neither writable nor configurable**. `Object.defineProperty()`

## String object
The **String global object** is a **constructor** for strings or a sequence of characters.
```js
    String(*thing*) // thing : Anything to be converted to a string.
```

### I. Properties
**String.prototype**
- Allows the addition of properties to a String object.
```js
var str = 'hello';
delete str.__proto__.charAt;
String.prototype.charAt;    // undefined
```

### II. Methods
**String.fromCharCode(*number*)**
- Returns a string created by using the specified sequence of Unicode values.
```js
String.fromCharCode(65);    // 'A'
```

**String.fromCodePoint(*number*)**   up to 21-bit
- Return such a pair and thus adequately represent these higher valued characters.
```js
String.fromCodePoint(9063, 1258, 3245, 1246);   // "⍧ӪಭӞ"
```

**String.raw()**
- Returns a string created from a raw template string.
        
## String instances
All String instances inherit from String.prototype.

Changes to the String prototype object are propagated to all String instances.

```js
var str = 'dat';
delete str.__proto__.charAt;
String.prototype.charAt();  // Uncaught TypeError: String.prototype.charAt is not a function
```

### I. Properties

These properties are read-only.

**String.prototype.constructor**
- Specifies the function that creates an object's prototype.

**String.prototype.length**
- Reflects the length of the string.

**[*N*]**
- Used to access the character in the Nth position where N is an integer between 0 and one less than the value of length.
        
### II. Methods 
**String.prototype.charAt(*index*)**
- Returns the character (exactly one UTF-16 code unit) at the specified index.

**String.prototype.charCodeAt(*index*)**
- Returns a number that is the UTF-16 code unit value at the given index.
- Note that charCodeAt() will always return a value that is less than 65536.
```js
'quangdatpham'.charCodeAt(3);   // 65
```

**String.prototype.codePointAt(*index*)**
- Returns a nonnegative integer Number that is the code point value of the UTF-16 encoded code point starting at the specified index.
```js
"⍧ӪಭӞ".codePointAt(2);  // 3245
```

**String.prototype.concat(*...otherStrings*)**
```js
'Hello'.concat(' ', 'World!');  // 'Hello World!'
```

**String.prototype.includes(*string*, *from*)**
- *from* at which to begin searching for *string*
```js
'quangdatpham'.includes('atpha');   // true
```

**String.prototype.endsWith(*string*)**
```js
'quangdatpham'.endsWith('ham'); // true
```

**String.prototype.indexOf(*string*, *from*)**
- return -1 if not found
```js
'quangdatpham'.indexOf('at', 4)  // 6
```

**String.prototype.lastIndexOf(*string*, *from*)**
- return -1 if not found
```js
'quangdatpham'.lastIndexOf('a', 8); // 6
```

**String.prototype.localeCompare()**
- Returns a number indicating whether a reference string comes before or after or is the same as the given string in sort order.

**String.prototype.match(*RegExp*)**
- Used to match a regular expression against a string.
```js
'QuangDatPham'.match(/[A-Z]/g);  // Array ['Q', 'D', 'P']
```

**String.prototype.normalize()**
- Returns the Unicode Normalization Form of the calling string value.

**String.prototype.padEnd(*length*, *string*)**
```js
'quangdatpham'.padEnd(15, '=');  // 'quangdatpham==='
```

**String.prototype.padStart(*string*)**
```js
'quangdatpham'.padStart(15, '=');    // '===quangdatpham'
```

**String.prototype.repeat(*times*)**
- RangeError: repeat count must be non-negative, less than infinity and not overflow maximum string size.**
```js
'dat'.repeat(3);    // 'datdatdat'
```

**String.prototype.replace(*RegExp*|*string*, *newString*|*function*)**
```js
'quangdatpham'.replace(/dat/gi, 'master');  // 'quangmasterpham'

'dat123!@#'.replace(/([^\d]*)([\d]*)([^\d]*)/, function(match, m1, m2, m3, offset, str) {
    return [m1, m2, m3].join('_');
});     // 'dat_123_!@#'
```

**String.prototype.search(*RegExp*|*string*, *newString*|*function*)**
- return -1 if not found
```js
'quangdat#pham$'.search(/[\W]/);    // 8
```

**String.prototype.slice(*beginIndex*, *endIndex*)**
- Extracts a section of a string and returns a new string.
```js
var str = 'quangdatpham';
str.slice(2); // 'angdatpham'
str.slice(2, 5);    // 'ang'
str.slice(4, -3);   // 'gdatp'
str.slice(-3);  // 'ham'
str.slice(-5, -2);  // 'tph'
```

**String.prototype.split(*RegExp*|*string*, *limit*)**
- Splits a String object into an array of strings by separating the string into substrings.
```js
var str = 'quang 1 dat 2 pham';
str.split(/\d/);    // ["quang ", " dat ", " pham"]
str.split('a', 2);    // ["qu", "ng 1 d"]
```

**String.prototype.startsWith(*string*, *position*)**
```js
var str = 'quangdatpham';
str.startWith('qua'); // true
str.startWith('dat', 6);    // true
```

**String.prototype.substr(*start*, *length*)**
```js
var str = 'quangdatpham';
str.substring(2, 5);    // 'angda'
str.substring(5, 2);    // 'da'
```

**String.prototype.substring(*start*, *end*)**
```js
var str = 'quangdatpham';
str.substring(2, 5);    // 'ang'
str.substring(5, 2);    // 'ang'
```

**String.prototype.toLocaleLowerCase()**
- The characters within a string are converted to lower case while respecting the current locale. For most languages, this will return the same as toLowerCase().

**String.prototype.toLocaleUpperCase()**
- The characters within a string are converted to upper case while respecting the current locale. For most languages, this will return the same as toUpperCase().

**String.prototype.toLowerCase()**
```js
'QUANGDATPHAM'.toLowerCase()    // 'quangdatpham'
```

**String.prototype.toString()**
- Returns a string representing the specified object. Overrides the Object.prototype.toString() method.
```js
var str = new String('dat');
console.log(str);   // expected output: String { "dat" }
console.log(str.toString());    // expected output: "dat"
```

**String.prototype.toUpperCase()**
```js
'quangdatpham'.toUpperCase();   // 'QUANGDATPHAM'
```

**String.prototype.trim()**
- Trims whitespace from the beginning and end of the string. Part of the ECMAScript 5 standard.
```js
'   quangdatpham   '.trim();    // 'quangdatpham'
```

**String.prototype.trimStart()**

**String.prototype.trimLeft()**
 
**String.prototype.trimEnd()**

**String.prototype.trimRight()**

**String.prototype.valueOf()**
- Returns the primitive value of the specified object. Overrides the Object.prototype.valueOf() method.
```js
var stringObj = new String("foo");
console.log(stringObj); // expected output: String { "foo" }
console.log(stringObj.valueOf());   // expected output: "foo"
```
**String.prototype\[@@iterator\]\(\)**
- Returns a new Iterator object that iterates over the code points of a String value, returning each code point as a String value.
```js
const str = 'The quick red fox jumped over the lazy dog\'s back.';

let iterator = str[Symbol.iterator]();
let theChar = iterator.next();

while(!theChar.done && theChar.value !== ' ') {
    console.log(theChar.value);
    theChar = iterator.next();
    // expected output: "T"
    //                  "h"
    //                  "e"
}  
```

## References

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String


# 07. Array

`typeof []    // "object"`

  - [Clone an array](#clone-an-array)
  - [The "Array" object](#the-%22array%22-object)
    - [I. Properties](#i-properties)
    - [II. Methods](#ii-methods)
  - [Array instances](#array-instances)
    - [I. Properties](#i-properties-1)
    - [II. Methods](#2-methods)
    - [`MUTATOR METHODS`](#mutator-methods)
    - [`ACCESSOR METHODS`](#accessor-methods)
    - [`ITERATION METHODS`](#iteration-methods)
  - [References](#references)


## Clone an array
- Shallow-cloning
```js
var numbers = [1, 2, 3, 4, [10, 11, 12]];

var nums = numbers.slice();

var nums = [...numbers];

var nums = Array.from(numbers);

var nums = [].concat(numbers);
```

- Deep clone
    (See chapter object)

## The "Array" object
### I. Properties
**Array.length**
- The Array constructor's length property whose value is 1.
```js
var arr = [];
arr.length = 12;
```

**get Array[@@species]**
- The constructor function that is used to create derived objects.
```js
Array[Symbol.species]; // function Array()
```

**Array.prototype**
- Allows the addition of properties to all array objects.
```js
typeof Array.prototype; // "object"
```

### II. Methods
**Array.from(*arrayLike*, *mapFn(val, index)*)**
- Creates a new Array instance from an array-like or iterable object.
```js
Array.from('123');  // ['1', '2', '3']
const range = (start, stop, step) => 
    Array.from(
        { length: (stop - start) / step },
        function(_, i) {
            return start + (i * step);
        });
range(0, 5, 1); // [0, 1, 2, 3, 4]
range('A'.charCodeAt(0), 'Z'.charCodeAt(0) + 1, 1).map(x => String.fromCharCode(x));    // ["A", ..., "Z"]

Array.isArray()
Returns true if a variable is an array, if not false.
Array.isArray(Array.prototype); // true
Array.prototype instanceof Array; // false

Array.of(*...args*)
Creates a new Array instance with a variable number of arguments, regardless of number or type of the arguments.
Array.of(7);       // [7] 
Array.of(1, 2, 3); // [1, 2, 3]

Array(7);          // [ , , , , , , ]
Array(1, 2, 3);    // [1, 2, 3]
```

## Array instances
### I. Properties
**Array.prototype.constructor**
- Specifies the function that creates an object's prototype.

**Array.prototype.length**
- Reflects the number of elements in an array.
- writable

**Array.prototype[@@unscopables]**
- A symbol containing property names to exclude from a with binding scope.

### II. Methods
### `MUTATOR METHODS`
These methods `modify` the array and return it:

**Array.prototype.copyWithin(*target*, *start = 0*, *end = arr.length*)**
- Copies a sequence of array elements within the array.
```js
[1, 2, 3, 4, 5].copyWithin(-2); // [1, 2, 3, 1, 2]
[1, 2, 3, 4, 5].copyWithin(0, 3);   // [4, 5, 3, 4, 5]
[1, 2, 3, 4, 5].copyWithin(0, 3, 4);    // [4, 2, 3, 4, 5]
[1, 2, 3, 4, 5].copyWithin(-2, -3, -1); // [1, 2, 3, 3, 4]
[].copyWithin.call({length: 5, 3: 1}, 0, 3);    // {0: 1, 3: 1, length: 5}

// ES2015 Typed Arrays are subclasses of Array
var i32a = new Int32Array([1, 2, 3, 4, 5]);
i32a.copyWithin(0, 2);  // Int32Array [3, 4, 5, 4, 5]
// On platforms that are not yet ES2015 compliant: 
[].copyWithin.call(new Int32Array([1, 2, 3, 4, 5]), 0, 3, 4);
// Int32Array [4, 2, 3, 4, 5]
```
**Array.prototype.fill(*value*, *start*, *end*)**
- Fills all the elements of an array from a start index to an end index with a static value.
```js
[1, 2, 3, 4, 5].fill(4);               // [4, 4, 4, 4, 4]
[1, 2, 3, 4, 5].fill(5, 2);            // [1, 2, 5, 5, 5]
[1, 2, 3, 4, 5].fill(4, 1, 2);         // [1, 4, 3, 4, 5]
[1, 2, 3, 4, 5].fill(6, 2, 2);         // [1, 2, 3, 4, 5]
[1, 2, 3, 4, 5].fill(4, -3, -2);       // [1 , 2, 4, 4, 5]
[1, 2, 3, 4, 5].fill(2, 5, 8);         // [1, 2, 3, 4, 5]
Array(3).fill(4);                // [4, 4, 4]
[].fill.call({ length: 3 }, 4);  // {0: 4, 1: 4, 2: 4, length: 3}
// Objects by reference.
var arr = Array(3).fill({}) // [{}, {}, {}];
arr[0].hi = "hi"; // [{ hi: "hi" }, { hi: "hi" }, { hi: "hi" }]
```

**Array.prototype.pop()**
- Removes the last element from an array and returns that element.
```js
var plants = ['broccoli', 'cauliflower', 'cabbage', 'kale', 'tomato'];
console.log(plants.pop());  // expected output: "tomato"
console.log(plants);    // expected output: Array ["broccoli", "cauliflower", "cabbage", "kale"]
```

**Array.prototype.push(*...elements*)**
- Adds one or more elements to the end of an array and returns the new length of the array.
```js
var animals = ['pigs', 'goats', 'sheep'];
console.log(animals.push('cows'));  // expected output: 4
console.log(animals);   // expected output: Array ["pigs", "goats", "sheep", "cows"]
```

**Array.prototype.reverse()**
- Reverses the order of the elements of an array in place — the first becomes the last, and the last becomes the first.
- Careful: reverse is destructive. It also changes the original array
```js
const a = [1, 2, 3];
console.log(a.reverse());   // expected output: [1, 2, 3]
console.log(a); // expected output: [3, 2, 1]
```

**Array.prototype.shift()**
- Removes the first element from an array and returns that element.
```js
var arr = [1, 2, 3];
console.log(arr.shift());  // expected output: 1    // first element
console.log(arr);   // expected output: Array [2, 3]
```

**Array.prototype.sort(*compareFunction(a, b)*)**
- Sorts the elements of an array in place and returns the array.
```js
var numbers = [4, 2, 5, 1, 3];
numbers.sort(function(a, b) {
    return a - b;   // a > b ? 1 : -1
});
console.log(numbers);   // expected output [1, 2, 3, 4, 5]
```

**Array.prototype.splice(*start*, *count*, *...items*)**
- Adds and/or removes elements from an array.
```js
var myFish = ['angel', 'clown', 'trumpet', 'sturgeon'];
var removed = myFish.splice(0, 2, 'parrot', 'anemone', 'blue');
// myFish now is ["parrot", "anemone", "blue", "trumpet", "sturgeon"] 
// removed is ["angel", "clown"]
myFish.splice(-2, 1);
// myFish is ["parrot", "anemone", "blue", "sturgeon"] 
myFish(1);
// myFish is ["parrot"] 
```

**Array.prototype.unshift(*...elements*)**
- Adds one or more elements to the front of an array and returns the new length of the array.
```js
var array1 = [1, 2, 3];
console.log(array1.unshift(4, 5));  // expected output: 5
console.log(array1);    // expected output: Array [4, 5, 1, 2, 3]
```

### `ACCESSOR METHODS`
These methods do `not modify` the array and return some representation of the array.

**Array.prototype.concat(*...arrays*)**
- Returns a new array that is this array joined with other array(s) and/or value(s).
```js
const letters = ['a', 'b', 'c'];
const num1 = [[1]];
const alphaNumeric = letters.concat(1, [2, 3], num1);
console.log(alphaNumeric); 
// results in ['a', 'b', 'c', 1, 2, 3, [1]]
```

**Array.prototype.includes(*value*, *from*)**
- Determines whether an array contains a certain element, returning true or false as appropriate.
```js
[1, 2, 3].includes(3, -1); // true
[1, 2, NaN].includes(NaN); // true
arr.includes(1, -100); // true
[1, 2, 3].includes(3, 3);  // false
```

**Array.prototype.indexOf(*element*, *from*)**
- Returns the first (least) index of an element within the array equal to the specified value, or -1 if none is found.
```js
var array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0
```

**Array.prototype.join(*separator*)   // default: a comma (",")**
- Joins all elements of an array into a string.
```js
var a = ['Wind', 'Rain', 'Fire'];
a.join();      // 'Wind,Rain,Fire'
a.join(', ');  // 'Wind, Rain, Fire'
a.join('');    // 'WindRainFire'
```

**Array.prototype.lastIndexOf(*search*, *from*)**
- Returns the last (greatest) index of an element within the array equal to the specified value, or -1 if none is found.
- BACK to FRONT
```js
var numbers = [2, 5, 9, 2];
numbers.lastIndexOf(2);     // 3
numbers.lastIndexOf(7);     // -1
numbers.lastIndexOf(2, 3);  // 3
numbers.lastIndexOf(2, 2);  // 0
numbers.lastIndexOf(2, -2); // 0
numbers.lastIndexOf(2, -1); // 3
```

**Array.prototype.slice(*begin*, *end*)**
- Extracts a section of an array and returns a new array.
```js
var arr = [1, 2, 3, 4, 5];
arr.slice(2, 4);    // [3, 4]
arr.slice(2);   // [3, 4, 5]
arr.slice(-3, 4);   // [3, 4]
```

**Array.prototype.toString()**
- Returns a string representing the array and its elements. Overrides the Object.prototype.toString() method.
```js
var array1 = [1, 2, 'a', '1a'];
console.log(array1.toString()); // expected output: "1,2,a,1a"
```

**Array.prototype.toLocaleString()**
- Returns a localized string representing the array and its elements. Overrides the Object.prototype.toLocaleString() method.

### `ITERATION METHODS`

**Array.prototype.entries()**
- Returns a new Array Iterator object that contains the key/value pairs for each index in the array.
```js
var array1 = ['a', 'b', 'c'];
var iterator1 = array1.entries();
console.log(iterator1.next());  // expected output: {value: Array(2), done: false}
console.log(iterator1.next().value);    // expected output: Array [1, "b"]
// Using for of loop
```

**Array.prototype.every(*callback(element, index, array)*, *thisArg*) // thisArg when executing callback**
- Returns true if every element in this array satisfies the provided testing function.
```js
['0', true, [], {}].every(function (e, i, a) {
    return e;
}); // true
```

**Array.prototype.filter(*callback(element, index, array)*, *thisArg*)**
- Creates a new array with all of the elements of this array for which the provided filtering function returns true.
```js
[2, 4, 5, 7, 8].filter(function (val) {
    return (val % 2);
}); // [5, 7]
```

**Array.prototype.find(*callback(element, index, array)*, *thisArg*)**
- Returns the found value in the array, if an element in the array satisfies the provided testing function or undefined if not found.
```js
const inventory = [
    {name: 'apples', quantity: 2},
    {name: 'bananas', quantity: 0},
    {name: 'cherries', quantity: 5}
];
const result = inventory.find( fruit => fruit.name === 'cherries' );
console.log(result) // { name: 'cherries', quantity: 5 }
```

**Array.prototype.findIndex(*callback(element, index, array)*, *thisArg*)**
- Returns the found index in the array, if an element in the array satisfies the provided testing function or -1 if not found.
```js
const fruits = ["apple", "banana", "cantaloupe", "blueberries", "grapefruit"];
const index = fruits.findIndex(fruit => fruit === "blueberries");
console.log(index); // 3
console.log(fruits[index]); // blueberries
```

**Array.prototype.forEach(*callback(element, index, array)*)**
- Calls a function for each element in the array.
```js
const items = ['item1', 'item2', 'item3'];
const copy = [];
items.forEach(function(item){
    copy.push(item)
});
```

**Array.prototype.keys()**
- Returns a new Array Iterator object that contains the keys for each index in the array.
```js
var arr = ['a', , 'c'];
var sparseKeys = Object.keys(arr);
var denseKeys = arr.keys();
console.log(sparseKeys); // Array ['0', '2']
console.log(denseKeys);  // Array Iterator {}
console.log([...denseKeys]);    // Array [0, 1, 2]
```

**Array.prototype.map(*callback(element, index, array)*)**
- Creates a new array with the results of calling a provided function on every element in this array.
```js
var numbers = [1, 4, 9];
var doubles = numbers.map(function(num) {
    return num * 2;
});
// doubles is now [2, 8, 18]
// numbers is still [1, 4, 9]
['1.1', '2.2e2', '3e300'].map(Number); // [1.1, 220, 3e+300]
```

**Array.prototype.reduce(*callback(accumulator, currentValue, currentIndex, array)*, *initialValue*)**
- Apply a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value.
- initialValue:   Value to use as the first argument to the first call of the callback.
```js
const arr = ['cat', 'mouse', 'cat', 'pig', 'buffalo', 'mouse',  'pig', 'cat'];
arr.reduce(function (count, item) {
    count[item] = (count[item] || 0) + 1;
    return count;
}, {}); // {cat: 3, mouse: 2, pig: 2, buffalo: 1}
```

**Array.prototype.reduceRight(*callback(accumulator, currentValue, currentIndex, array)*, *initialValue*)**
- Apply a function against an accumulator and each value of the array (from right-to-left) as to reduce it to a single value.
```js
var flattened = [[0, 1], [2, 3], [4, 5]].reduceRight(function(a, b) {
    return a.concat(b);
}, []); // flattened is [4, 5, 2, 3, 0, 1]
```

**Array.prototype.some(*callback(element, index, array)*, *thisArg*)**
- Returns true if at least one element in this array satisfies the provided testing function.
```js
[1, 2, 3, 4, 5, 6].some(function (val) {
    return val > 3;
}); // true
```

**Array.prototype.values()**
- Returns a new Array Iterator object that contains the values for each index in the array.
**Array.prototype.values === Array.prototype[Symbol.iterator]**
```js
const arr = ['a', 'b', 'c'];
const iterator = arr.values();
for (let val of iterator) {
    console.log(val); // expected output: "a" "b" "c"
}
```
**Array.prototype\[@@iterator\]\(\)**
- Returns a new Array Iterator object that contains the values for each index in the array.

## References
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array


# 08. Object

  - [Object constructor](#object-constructor)
  - [Deleting a property](#deleting-a-property)
  - [Property attributes](#property-attributes)
  - [Flags](#flags)
  - [Accessor Properties (getter & setter)](#accessor-properties-getter--setter)
  - [Iteration (Enumeration)](#iteration-enumeration)
  - [Define a property and Change its flags](#define-a-property-and-change-its-flags)
  - [Protecting objects](#protecting-objects)
  - [Mutability](#mutability)
  - [Clone a object](#clone-a-object)
  - [The `Object` object](#the-object-object)
    - [I. Properties](#i-properties)
    - [II. Methods](#ii-methods)
  - [Object instances and Object prototype object](#object-instances-and-object-prototype-object)
    - [I. Properties](#i-properties-1)
    - [II. Methods](#ii-methods-1)
  - [References](#references)

## Object constructor
- The Object constructor creates an object wrapper for the given value.
- If the value is null or undefined, it will create and return an empty object, otherwise, it will return an object of a Type that corresponds to the given value.
- If the value is an object already, it will return the value.
- To indicate a property a private put an underscore (_) character at the start of the property name.

- When called in a non-constructor context, Object behaves identically to `new Object()`.
```js
new Object();   // {}
new Object(undefined);  // {}
new Object(null);   // {}
new Object(true);   // Boolean {true}
new Object(1)   // Number  {1}
```

## Deleting a property
- The delete operator removes a given property from an object.
- On successful deletion, it will return true, else false will be returned.
```js
delete obj.propertyName
delete obj['propertyName']
```

## Property attributes
- At first glance, it might look like there is a one-to-one mapping between keys and values of an object. However, that’s not entirely true.
- Property Attributes :
    - Every key of an object contains a set of property attributes that define the characteristics of the value associated with the key.
    - There are six property attributes:
            `[[Value]]  [[Get]]     [[Set]]     [[Writable]]    [[Enumerable]]  [[Configurable]]`

- Why have we wrapped the attribute names in `[[]]`? Double square brackets mark internal properties used by the ECMA specifications.
- These are properties that JS programmer cannot touch directly from within the code.

## Flags
Data properties have three special attributes (so-called `flags`):
    - `writable` – if true, can be changed, otherwise it’s **read-only**.
    - `enumerable` – if true, then listed in loops, otherwise **not listed**.
    - `configurable` – if true, the property **can be deleted** and these attributes **can be modified**, **otherwise not**.

```js
const dog = {
    color: 'black'
};
console.log(Object.getOwnPropertyDescriptor(dog, 'color'));
    // expected output:
    // {
    //     value: "black",
    //     writable: true,
    //     enumerable: true,
    //     configurable: true
    // }
```

## Accessor Properties (getter & setter)
- Reading accessor properties do not need to use parentheses to invoke the function.
```js
var obj = {
    _name: 'Quang Dat', // private property
    get name() {
        return this._name;
    },
    set name(val) {
        this._name = val;
    }
};
```

## Iteration (Enumeration)
- for-in loop will return all string properties which is enumerable.
- all enumerable properties of prototype are also returned.
```js
for (let property in obj) {
    // Read the value 
    let value = obj[property];
}
```

- **Object.keys()** is similar to for-in loop except that it only returns the object’s own keys in an array.
- **Object.values()** returns an array of values.
- **Object.entries()** returns an array of [key, value] pairs.

## Define a property and Change its flags
- If the property exists, defineProperty updates its flags.
- Otherwise, it creates the property with the given value and flags;
- if a flag is not supplied, it is assumed false.
```js
var person = {
    age: 18
};

Object.defineProperty(person, 'name', {
    value: 'Dat',
    "writable": false,  // read-only
    "enumerable": false,    // non enumerable
    "configurable": false   // non configurable
});

// read-only  //
person.name = 'abc';    // Error: Cannot assign to read only property 'name'...

// non enumerable   //
for (let property in person) {
    console.log(property);  // age
}
console.log(Object.keys(person));   // age

// non configurable //
Object.defineProperty(person, 'name', {
    "writable": true,
}); // won't able to change
delete person.name; // won't able to delete

// Define many properties at once.
Object.defineProperties(user, {
    name: { value: "Dat", writable: false },
    surname: { value: "Pham", writable: false },
    // ...
});

// Together with Object.defineProperties it can be used as a “flags-aware” way of cloning an object:
let clone = Object.defineProperties({}, Object.getOwnPropertyDescriptors(obj));

// Normally when we use an assignment to copy properties:
for (let key in user) {
    clone[key] = user[key]  // that does not copy flags
}
```

- Another difference is that **for..in ignores symbolic properties**,
- but **Object.getOwnPropertyDescriptors** returns all property descriptors **including symbolic ones**.

## Protecting objects
- `Preventing extension (non-extensible)` : prevents new properties from ever being added to an object.
- `Sealing (non-extensible, non-configurable)` : prevents extensions and makes all properties **“non-configurable”**
- `Freezing (non-writable, sealing)` : seals the object, prevents modifying any existing properties at all, prevents the descriptors from being changed

## Mutability
- When we have two numbers, 120 and 120, we can consider them precisely the same number, whether or not they refer to the same physical bits.
- With objects, there is a difference between having two references to the same object and having two different objects that contain the same properties.
```js
let object1 = {value: 10};
let object2 = object1;
let object3 = {value: 10};

console.log(object1 == object2);    // true
console.log(object1 == object3);    //  false

object1.value = 15;
console.log(object2.value); // 15
console.log(object3.value); // 10
```

- Bindings can also be changeable or constant
```js
const score = {visitors: 0, home: 0};
// This is okay
score.visitors = 1;
// This isn't allowed
score = {visitors: 1, home: 1};
```

## Clone a object
```js
var person = {
    name: 'Dat',
    gender: true,
    school: {
        tqk: 'Done',
        vtt: 'Done',
        fpt: 'Not yet'
    }
};
console.log(person);
    //    {name: "Dat", gender: true, school: {…}}
    //             gender: true
    //             name: "Dat"
    //             school:
    //                 fpt: "Not yet"
    //                 tqk: "Done"
    //                 vtt: "Done"
    //                 __proto__: Object   // "__proto__" of the "school" reference
    //             __proto__: Object       // "__proto__" of the "person" reference
```

- Spread operator (Shallow-cloning)
```js
var newObj = {...person};
person.name = '';
console.log(newObj.name);   // Dat
person.school.tqk = '';
console.log(newObj.school.tqk); //  ''
```

- Object.assign (Shallow-cloning)
```js
Object.assign({}, person);
```

- JSON (deep clone)
- JSON can not clone object method (function)
```js
var clone = JSON.stringify(person);
var newPerson = JSON.parse(clone);
```

- Deep clone
```js
function cloneDeep(obj) {
    var newObj = {};
    for (pro in obj) {
        newObj[pro] = 
            (typeof obj[pro]) === 'object' ?
                cloneDeep(obj[pro]) :
                obj[pro];
    }
    return newObj;
}
```

## The `Object` object
### I. Properties
**Object.length**
- Has a value of 1.

**Object.prototype**
- Allows the addition of properties to all objects of type Object.

### II. Methods
**Object.assign(*target*, *...objects*)**
- Copies the values of all enumerable own properties from one or more source objects to a target object.
- Both String and Symbol properties are copied.
- Getters are copied and turned into properties
```js
var o1 = {a: 1} // target
var o2 = {
    a: 12,
    b: {c: 5},  // referrence
    [Symbol('a')]: 10,  // property named symbol
    get d() { retrun 6; }   // getter
};    // source

var o3 = Object.assign(o1, o2);
console.log(o3);  // expected output: {a: 12, b: {c: 5}, d: 6, [Symbol('a')]: 10}
console.log(o1);  // expected output: {a: 12, b: {c: 5}, d: 6, [Symbol('a')]: 10}

o3.a = 0;
console.log(o2.a);    // expected output: 12
console.log(o3.a);    // expected output: 0

o2.b.c = 8;
console.log(o2.b.c);    // expected output: 8
console.log(o3.b.c);    // expected output: 8

// primitives wrapped
var v1 = 'abc';
var v2 = true;
var v3 = 10;
var v4 = Symbol('foo');
var obj = Object.assign({}, v1, null, v2, undefined, v3, v4); 
console.log(obj); // { "0": "a", "1": "b", "2": "c" }
```

**Object.create(*prototypedObject*, *...propertiesObject*)**
- Creates a new object with the specified prototype object and properties.
```js
Object.create(null);    // {}   // No properties // nothing inside
Object.create(Object.prototype);    // {}   // normal
Object.create({});  // {}   // proto: { proto: Object}   // look at your console

Object.create({}, {
    name: {
        value: 'Dat',
        writable: true,
        configurable: true
    },
    isBoy: {
        get() {
            return true;
        }
        set(value) {
            console.log('This property is non-configurable.');
        }
    }
});
```

**Object.defineProperty(*obj*, *propertyName*, *descriptor*) // see Define a property and Change its flags**
- Adds the named property described by a given descriptor to an object.
```js
// define Getter and Setter
const Person = (function() {
function Person() {
    this._name = '';
}
Object.defineProperty(Person.prototype, 'name', {
    get () {
    return this._name;
    },
    set (val) {
    this._name = val;
    },
    enumerable: false,
    configurable: false,
});
return Person;
})();
```

**Object.defineProperties(*obj*, *properties*)   // see Define a property and Change its flags**
- Adds the named properties described by the given descriptors to an object.

**Object.entries(*obj*)**
- Returns an array containing all of the [key, value] pairs of a given object's own enumerable string properties.
```js
// array like object with random key ordering
const anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.entries(anObj)); // [ ['2', 'b'], ['7', 'c'], ['100', 'a'] ]

// getFoo is property which isn't enumerable
const myObj = Object.create({}, { getFoo: { value() { return this.foo; } } });
myObj.foo = 'bar';
console.log(Object.entries(myObj)); // [ ['foo', 'bar'] ]

// non-object argument will be coerced to an object
console.log(Object.entries('foo')); // [ ['0', 'f'], ['1', 'o'], ['2', 'o'] ]
```

**Object.freeze(*obj*)**
- Freezes an object(array is also an object): other code can't delete or change any properties.
- Non-writable, non-configurable, non-extensible.
- Freeze is shallow (non-deep effect).
```js
var obj = {
    foo: 'foo',
    deep: {
        a: 5
    }
};
obj.bar = 'bar';
delete obj.foo; // true
var freeze = Object.freeze(obj);
freeze === obj; // true
obj.bar = 'foo';    // nothing happened
delete obj.bar; // false
obj.deep.a = 1; // a now is changed to 1
Object.isFreeze(obj);   //true
Object.defineProperty(obj, 'number', { value: 17 });  // throw a TypeError
Object.setPrototypeOf(obj, { x: 20 })   // throw a TypeError
```

**Object.fromEntries(*iterable*)**
- Returns a new object from an iterable of key-value pairs (reverses Object.entries).
```js
const map = new Map([ ['foo', 'bar'], ['baz', 42] ]);
Object.fromEntries(map);    // { foo: "bar", baz: 42 }
const arr = [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ];
Object.fromEntries(arr);    // { 0: "a", 1: "b", 2: "c" }
```

**Object.getOwnPropertyDescriptor(*obj*, *propertyName*)   // see Property flags**
- Returns a property descriptor for a named property on an object.
```js
// look up getter setter
var obj = {
    name: 'dat',
    get getName() {
        return this.name;
    }
};
Object.getOwnPropertyDescriptor(obj, "getName").get;
//  ƒ getName() {   return this.name;   }
```

**Object.getOwnPropertyDescriptors(*obj*)**
- Returns an object containing all own property descriptors for an object.

**Object.getOwnPropertyNames(*obj*)**
- Returns an array containing the names of all of the given object's own enumerable and non-enumerable properties.
```js
var obj = Object.create({}, {
    getName: {
        value() { return 'Dat';},
        enumerable: false
    }
});
obj.name = 1;
Object.getOwnPropertyNames(my_obj); // ["getName", "name"]

Object.getOwnPropertyNames('foo');  // ["0", "1", "2", "length"]  (ES2015 code)
```

**Object.getOwnPropertySymbols(*obj*)**
- Returns an array of all symbol properties found directly upon a given object.
```js
var obj = {
    [Symbol('a')]: 'a',
    [Symbol('b')]: 'b'
};
Object.getOwnPropertySymbols(obj);  // [Symbol(a), Symbol(b)]
```

**Object.getPrototypeOf(*obj*)**
- Returns the prototype of the specified object.
```js
var obj1 = {};
var obj2 = Object.create(obj1); // {} // proto: { proto: Object}
Object.getPrototypeOf(obj2) === obj1; // true
```

**Object.is(*value1*, *value2*)**
- Compares if two values are the same value. Equates all NaN values
- (which differs from both Abstract Equality Comparison and Strict Equality Comparison).
```js
Object.is(0, -0);   // false
Object.is(NaN, 0/0);    // true // 0/0 --> NaN
0/0 === NaN // false
```

**Object.isExtensible(*obj*)**
- Determines if extending of an object is allowed.
-  New objects are extensible.
```js
var obj = {};
var sealedObj = Object.seal({});
Object.isExtensible(obj);   // true
Object.isExtensible(sealedObj);    // false
Object.preventExtensions(obj);
Object.isExtensible(obj); // false
Object.isExtensible(10);    // false
```

**Object.isFrozen(*obj*)**
- Determines if an object was frozen.
```js
var obj = Object.preventExtensible({}); // empty obj
Object.isFrozen(obj);   // true

var oneProp = { p: 42 };    // obj has one property
Object.preventExtensions(oneProp);
Object.isFrozen(oneProp); // === false
delete oneProp.p;   // delete property
Object.isFrozen(oneProp); // === true

Object.isFrozen(2); // true
```

**Object.isSealed()**
- Determines if an object is sealed.
```js
var emptyObj = {};
Object.preventExtensions(emptyObj);
Object.isSealed(emptyObj);  // 

var obj = {name: 'cat'};
Object.seal(obj);
Object.isSealed(obj);   // true
Object.isExtensible(obj);   // false
```

**Object.keys(*obj*)**
- Returns an array containing the names of all of the given object's own enumerable string properties.
```js
var obj = {12: 'a', 8: 'b', 30: 'c'};
Object.keys(obj);   // ['8', '12', '30']
```

**Object.preventExtensions(*obj*)**
- Prevents any extensions of an object.
- Properties can be changed or deleted, but you can not defined new properties.
```js
var obj = {type: 'pet'};
var preExt = Object.preventExtensions(obj);
obj === preExt; // true
Object.definedProperty(obj, 'weight', {
    value: 24
}); // throw a TypeError
Object.preventExtensions(1);    // 1
```

**Object.seal(*obj*)**
- Prevents other code from deleting properties of an object.
- Non-extensible, non-configurable.
```js
var obj = {name: 'cat'};
Object.seal(obj);
delete obj.name;    // do nothing
obj.weight = 12;    // do nothing
obj.name = 'dog';   // name's value has changed to 'dog'
Object.isSealed(obj);   // true
Object.isExtensible(obj);   // false
Object.seal(1); // 1
```

**Object.setPrototypeOf(*obj*, *prototype*)**
- Sets the prototype (i.e., the internal [[Prototype]] property).
- Not recommended, use Object.create() instead.

**Object.values(*obj*)**
- Returns an array containing the values that correspond to all of a given object's own enumerable string properties.
```js
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.values(obj)); // ['a', 'b', 'c']
Object.value('dat');    // ['d', 'a', 't']
```

## Object instances and Object prototype object
### I. Properties 
**Object.prototype.constructor**
- Specifies the function that creates an object's prototype.

**Object.prototype.\_\_proto\_\_**
- Points to the object which was used as prototype when the object was instantiated.
        https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/proto
    
### II. Methods
**Object.prototype.hasOwnProperty(*property*)**
- Returns a boolean indicating whether an object contains the specified property as a direct property of that object and not inherited through the prototype chain.
```js
var obj = {};
obj.empty = undefined;
obj.hasOwnProperty('empty');    // true
obj.hasOwnProperty('toString'); // false
```

**Object.prototype.isPrototypeOf(*obj*)**
- Returns a boolean indicating whether the object this method is called upon is in the prototype chain of the specified object.
```js
function Foo() {}
function Bar() {}
function Baz() {}

Bar.prototype = Object.create(Foo.prototype);
Baz.prototype = Object.create(Bar.prototype);

var baz = new Baz();

console.log(Baz.prototype.isPrototypeOf(baz)); // true
console.log(Bar.prototype.isPrototypeOf(baz)); // true
console.log(Foo.prototype.isPrototypeOf(baz)); // true
console.log(Object.prototype.isPrototypeOf(baz)); // true
```

**Object.prototype.propertyIsEnumerable(*property*)**
- Returns a boolean indicating if the internal ECMAScript [[Enumerable]] attribute is set.
```js
var obj = {};
obj.name = 'dat';
obj.propertyIsEnumerable('name');   // true
obj.propertyIsEnumerable('weight');   // false
obj.propertyIsEnumerable('constructor');   // false
```

**Object.prototype.toLocaleString()**
- Calls toString().

**Object.prototype.toString()**
- Returns a string representation of the object
```js
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}

Person.prototype.toString = function () {
    return this.firstName + ' ' + this.lastName;
}

var p = new Person('Dat', 'Pham');
p.toString();   // 'Dat Pham'
```
**Object.prototype.valueOf()**
- Returns the primitive value of the specified object.
        
## References

https://javascript.info/property-descriptors#sealing-an-object-globally

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object

https://toddmotto.com/typescript-setters-getter


# 09. Inheritance - Prototype chain

  - [Object, Array, and Function](#object-array-and-function)
  - [Class notation](#class-notation)
  - [Function constructor](#function-constructor)
  - [Object literals (Manually)](#object-literals-manually)
  - [Inheritance && prototype chain](#inheritance--prototype-chain)
  - [Method overriding](#method-overriding)
  - [References](#references)


## Object, Array, and Function
- JavaScript gives us access to three global functions: Object, Array, and Function. Yes, these are all functions.
- First-class objects in JavaScript.
```js
console.log(Object); // -> ƒ Object() { [native code] }
console.log(Array); // -> ƒ Array() { [native code] }
console.log(Function); // -> ƒ Function() { [native code] }
```

- You don’t know it, but every time you create an object literal, the JavaScript engine is effectively calling `new Object()`.
- An object literal is an object created by writing **{}**, as in `var obj = {};`.
- So an object literal is an **implicit** call to Object. Same goes for arrays and functions. We can think of an array as coming from the Array constructor and a function as coming from the Function constructor.

## Class notation
```js
class Square {
    constructor(a) {
        this.a = a;
    }

    // method
    calculateArea() {
        return this.a ** 2;
    }

    // getter
    get hypotenuse() {
        return this.a * Math.sqrt(2);
    }

    // setter
    set hypotenuse(val) {
        this.a = val / Math.sqrt(2);
    }

    // static
    static fromArea(val) {
        return new Square(Math.sqrt(val));
    }
}

var square = new Square(4);
console.log(square instanceof Square);  // true
console.log(square.calculateArea());    // 16

var square2 = Square.fromArea(36);
square2.hypotenuse = 12;
console.log(square2.a); // 8.48528137423857

console.log(square.__proto__ === Square.prototype);    // true
console.log(square.__proto__.constructor === Square);  // true
    // Square {a: 4}
    //             a: 4
    //             hypotenuse: (...)
    //             __proto__:
    //                 calculateArea: ƒ calculateArea()
    //                 constructor: class Square
    //                 hypotenuse: (...)
    //                 get hypotenuse: ƒ hypotenuse()
    //                 set hypotenuse: ƒ hypotenuse(val)
    //                 __proto__: Object

Object.getOwnPropertyNames(Square);
// ["length", "prototype", "fromArea", "name"]
```

## Function constructor
- When we invoke a function using the **new** keyword, the object bound to **this** in the constructor function is special.
- It sets the returned object’s **\_\_proto\_\_** property equal to the function’s **prototype** property. This is the **key** to **inheritance**.
```js
function Length(metre) {
    this.metre = metre;
}

Object.defineProperty(Length.prototype, 'kilometre', {
    get () {
        return this.metre / 1000;
    },
    set (val) {
        this.metre = val * 1000;
    }
});

// the same to static
Length.fromKilometre = function (val) {
    return new Length(val / 1000);
}

// Using prototypal inheritance // Recommended
Length.prototype.printLength = function () {
    console.log('Metre: ' + this.metre);
    console.log('Kilometre: ' + this.kilometre);
}

var length = new Length(1);
console.log(length.__proto__ === Length.prototype);  // true
console.log(length.__proto__ === Length);   // true
    // Length {metre: 1}
    //             metre: 1
    //             kilometre: (...)
    //             __proto__:
    //                 printLength: ƒ ()
    //                 constructor: ƒ Length(metre)
    //                 kilometre: (...)
    //                 get kilometre: ƒ ()
    //                 set kilometre: ƒ (val)
    //                 __proto__: Object
var obj = {};   // common object
obj.__proto__ = Length.prototype;   // assignment
obj instanceof Length;  // true

Object.getOwnPropertyNames(Length);
// ["length", "name", "arguments", "caller", "prototype", "fromKilometre"]
```

## Object literals (Manually)
```js
const Person = {  // not being a contructor
    run: function () {
        console.log('I\'m running.');
    },
    get sayHello() {
        console.log('Hello!');
    }
};

var person = Object.create(Person);
person.name = 'Dat';
person instanceof Person;   // Uncaught TypeError: Right-hand side of 'instanceof' is not callable
console.log(person);
    //  {name: "Dat"}
    //         name: "Dat"
    //         sayHello: (...)
    //         __proto__:
    //             run: ƒ ()
    //             sayHello: (...)
    //             get sayHello: ƒ sayHello()
    //             __proto__: Object
```

## Inheritance && prototype chain
- When trying to access a property of an object, the property will not only be sought on the object but on the prototype of the object, the prototype of the prototype, and so on until either a property with a matching name is found or the end of the prototype chain is reached.
- The [[Prototype]] is accessed using the accessors **Object.getPrototypeOf()** and **Object.setPrototypeOf()** or  **\_\_proto\_\_** (`non-standard`).
- It should not be confused with the "func.prototype" property of functions, which instead specifies the [[Prototype]] to be assigned to all instances of objects created by the given function when used as a constructor. The **Object.prototype** property represents the "Object" prototype object.

```js
// Consider this code
({}).__proto__ === Object.prototype;    // true
Object.prototype.__proto__; // null
[] instanceof Object;   // true
[].__proto__.__proto__ === Object.prototype;    // true
Array.prototype.__proto__ === Object.prototype; // true

class Mammal {
    constructor(weight) {
        this.weight = weight || 0;
    }

    run() {
        console.log('Running...');
    }
}

class Rabbit extends Mammal {
    constructor(color, weight) {
        super(weight);
        this.color = color || 'none';
    }

    jump() {
        console.log('Jumpping...');
    }
}

var redRabbit = new Rabbit('red', 12);
redRabbit.hasOwnProperty('jump');   // false
redRabbit.hasOwnProperty('weight');   // true
        // Rabbit {weight: 12, color: "red"}
        //         color: "red"
        //         weight: 12
        //         __proto__: Mammal
        //             constructor: class Rabbit
        //             jump: ƒ jump()
        //             __proto__:
        //                 constructor: class Mammal
        //                 run: ƒ run()
        //                 __proto__: Object

// the same with function constructor
function Mammal(weight) {
    this.weight = weight || 0;
}

Mammal.prototype.run = function () {
    console.log('Running...');
};

function Rabbit(color, weight) {
    this.color = color || 'none';
    Mammal.call(this, weight);  // calling Mammal constructor and specifing the "weight" property
}

Rabbit.prototype = Object.create(Mammal.prototype); // Rabbit.prototype = new Mammal();
Rabbit.prototype.constructor = Rabbit;
Rabbit.prototype.jump = function () {
    console.log('Jumpping...');
};
```

## Method overriding
```js
class Animal {
    constructor(color, weight) {
        this.color = color;
        this.weight = weight;
    }

    gainWeight(val) {
        this.weight += val;
    }
}

class Dog extends Animal {
    constructor(name, color, weight) {
        super(color, weight);
        this.name = name;
    }

    gainWeight(val, callback) {
        super.gainWeight(val);  // call the "gainWeight" method from the superclass
        callback();
    }
}

var dog = new Dog('abc', 'blue', 100);
dog.gainWeight(12, function () {
    console.log('Gain Weight.');
}); // Gain Weight
```

## References
https://community.risingstack.com/javascript-prototype-chain-inheritance/

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#Inheritance_with_the_prototype_chain

https://codeburst.io/master-javascript-prototypes-inheritance-d0a9a5a75c4e

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model#Class-based_vs._prototype-based_languages



# Higher order function

        Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions.

## Taking functions as arguments
```js
function buildHouses(quantity, callback) {
    for (let i = 0; i < quantity; i++) {
        callback(i);
    }
}

function check(test, next) {
    if(test % 2 === 0) next();
}

buildHouses(7, function (n) {
    check(n, function () {
        console.log(n);
    });
});
    // expected output: 
    // 0
    // 2
    // 4
    // 6
```

## Returning functions as results
```js
function countDownFrom(from) {
    return function(check) {
        for (let i = from; i >= 0; i--) {
            if (check(i))
                console.log(i);
        }
    };
}

var countDownFrom10 = countDownFrom(10);
countDownFrom10(function(val) {
    return val % 2 == 0;
});

// expected output:
// 10
// 8
// 6
// 4
// 2
// 0
```
## References

https://eloquentjavascript.net/05_higher_order.html

# 11. Regular Expression

        In JavaScript, regular experssion are also objects.

* [Creating regular expressions](#creating-regular-expressions)
* [Character groups](#character-groups)
* [RegExp methods](#regexp-methods)
* [Groups](#groups)
* [Alternation](#alternation)
* [Global and sticky](#global-and-sticky)
* [Replacement and groups](#replacement-and-groups)
* [Word boundary](#word-boundary)
* [Greed](#greed)
* [Dynamically creating RegExp objects](#dynamically-creating-regexp-objects)
* [International characters](#international-characters)
* [Advanced](#advanced)
* [References](#references)

## Creating regular expressions
- Literal — Syntax
```js
var regexp = /a+bcd/;   // forward slash (/)
```

- calling with "RegExp" object
```js
var regexp = new RegExp('a+bcd');
```

## Character groups
- Basics

|               |                                                     |
|:-----------:|---------------------------------------|
|  .	    | Any character except newline              |
|  a	    | The character a                                 |
|  ab	    | The string ab                                    |
|  a|b	    |    a or b  Alternation                         |
|  a*	    | 0 or more a's                                    |
|  \	    | Escapes a special character               |

- Quantifiers

|                       |                                       |
|:-----------:|---------------------------------------|
|*	   | 0 or more                      |
|+	   | 1 or more                      |
|?	   | 0 or 1                     |
|{2}	|    Exactly 2                      |
|{2, 5}|	    Between 2 and 5                     |
|{2,}	|    2 or more                      |

- Groups

|                       |                                       |
|:-----------:|---------------------------------------|
|(...)	 |   Capturing group        |
|(?:...)|	    Non-capturing group ( Matches and does not remember the match)      |
|\Y	   | Match the Y'th captured group      |

- Meta-Characters

|                       |                                       |
|:-----------:|---------------------------------------|
|[ab-d]	    |       One character of: a, b, c, d        |
|[^ab-d]	    |       One character except: a, b, c, d        |
|[\b]	    |    Backspace character        |
|\d	        |   One digit       |
|\D	        |   One non-digit       |
|\s	        |   One whitespace      |
|\S	        |   One non-whitespace      |
|\w	        |   One word character  [A-Za-z0-9_]        |
|\W	        |   One non-word character      |

- Assertions

|                       |                                       |
|:-----------:|---------------------------------------|
|^	        |   Start of string     |
|$	        |   End of string       |
|\b	    |    Word boundary      |
|\B	    |    Non-word boundary      |
|x(?=y)	    |       Matches 'x' only if 'x' is followed by 'y' (Positive lookahead)     |
|x(?!y)	    |       Matches 'x' only if 'x' is not followed by 'y' (Negative lookahead)     |

- Flags

|                       |                                       |
|:-----------:|---------------------------------------|
|   g   |	    Global Match        |
|   i   |	    Ignore case     |
|   m   |	    ^ and $ match start and end of line     |
|   y   |       sticky      |
|   u   |       Unicode     |

- Special characters

|                       |                                       |
|:-----------:|---------------------------------------|
|   \n  |	    Newline (Line feed LF)      |
|   \r  |	    Carriage return (CR)        |
|   \f  |      Form feed (FF)       |
|   \t  |	    Tab     |
|   \0  |	    Null character      |
|   \YYY    |	    Octal character YYY     |
|   \xYY    |	    Hexadecimal character YY        |
|   \uYYYY  |	    Hexadecimal character YYYY      |
|   \cY |	    Control character Y     |

- Replacement

|                       |                                       |
|:-----------:|---------------------------------------|
|   $$  |	    Inserts an  "$" character       |
|   $&  |  	Insert entire match     |
|   $`  |	    Insert preceding string     |
|   $'  |	    Insert following string     |
|   $Y  |	    Insert Y'th captured group      |

## RegExp methods
- `test`   
```js
let reTest = /quang?dat{1,4}/;
console.log(reTest.test("quangdat"));   // true
console.log(reTest.test("quandattt"));  // true
```
- `exec`    
```js
var regExp = /a/;
console.log(regExp.exec('quangdat'));
//  ["a", index: 2, input: "quangdat", groups: undefined]
```
- `source`    
    - The text of the pattern.
    - Updated at the time that the regular expression is created, not executed.

1. String methods
- `match`   
```js
var regExp = /dat/;
console.log('quangdat'.match(regExp));
//  ["dat", index: 5, input: "quangdat", groups: undefined]
```

- `search`  
```js
var regExp = /\D+/;
console.log('342dat14343dddsd43'.search(regExp));   // 3
``

- `replace` 
```js
console.log('quangdat'.replace(/dat/, 'DAT'));  // quangDAT
console.log('quangdat'.replace(/dat/, function(match) {
    return match.toUpperCase();
}));    // quangDAT
```

- `split`   
```js
var str = `quangdatpham
javascript
developer`;
console.log(str.split(/\r?\n/));
//  ["quangdatpham", "javascript", "developer"]
```

## Groups
```js
let quotedText = /'([^']*)'/;
console.log(quotedText.exec("she said 'hello'"));
// ["'hello'", "hello"]

console.log(/(\d)+/.exec("123"));
// ["123", "3"]
```

## Alternation
```js
let animalCount = /\b\d+ (pig|cow|chicken)s?\b/;
console.log(animalCount.test("15 pigs"));
// true
console.log(animalCount.test("15 pigchickens"));
// false
```

## Global and sticky
- When sticky is enabled, the match will succeed only if it starts directly at lastIndex, whereas with global, it will search ahead for a position where a match can start.
```js
var regExp = /a/g;
console.log('quangdat'.match(regExp));
// ["a", "a"]

//  RegExp.prototype.exec
var regExp = /a/g;
console.log(regExp.exec('quangdat'));   // first exec
// ["a", index: 2, input: "quangdat", groups: undefined]
console.log(regExp.lastIndex);  // 3

console.log(regExp.exec('quangdat'));   // second exec
// ["a", index: 6, input: "quangdat", groups: undefined]
console.log(regExp.lastIndex);  // 7

var sticky = /dat/y;
sticky.lastIndex = 2;
console.log(sticky.test('dddat'));    // true
```

## Replacement and groups
```js
var str = 'green-2, red-74, blue-34';
console.log(
    str.replace(/(\w+)-(\d+)/g, '$2 $1')
);
// 2 green, 74 red, 34 blue

str.replace(/(\w+)-(\d+)/g, function(wholeMatch, color, number) {
    return number + ' ' + color;
});
// 2 green, 74 red, 34 blue

console.log(/(\d)+/.exec("123"));
// ["123", "3", index: 0, input: "123", groups: undefined]

let quotedText = /'([^']*)'/;
console.log(quotedText.exec("she said 'hello'"));
// ["'hello'", "hello", index: 9, input: "she said 'hello'", groups: undefined]
```

## Word boundary
- A position between `\w ([a-zA-Z0-9])` and `\W` (non-word char), Or at the beginning or end of a string
```js
console.log(/\bdat\b/.test('dat')); // true
console.log(/\bdat\b/.test('++dat++')); // true
console.log(/\bdat\b/.test('dat++')); // true
console.log(/\bdat\b/.test('dat quang pham')); // true
console.log(/\b\d+\b/.test('abcd 12 ddd')); // true
```

## Greed
- If you put a question mark after them `(+?, *?, ??, {}?)`, they become **nongreedy** and start by matching as little as possible
```js
function stripComments(code) {
    return code.replace(/\/\/.*|\/\*[^]*\*\//g, "");
}
console.log(stripComments("1 /* a */+/* b */ 1"));
// 1  1

function stripComments(code) {
    return code.replace(/\/\/.*|\/\*[^]*?\*\//g, "");
}
console.log(stripComments("1 /* a */+/* b */ 1"));
    // 1 + 1
```

## Dynamically creating RegExp objects
```js
let name = "harry";
let text = "Harry is a suspicious character.";
let regexp = new RegExp("\\b(" + name + ")\\b", "gi");
console.log(text.replace(regexp, "_$1_"));
// _Harry_ is a suspicious character.
```

## International characters
- It is possible to use `\p` in a regular expression (that must have the Unicode option enabled) to match all characters to which the Unicode standard assigns a given property.
```js
console.log(/🍎{3}/.test("🍎🍎🍎"));    // false
console.log(/<.>/.test("<🌹>"));    // false
console.log(/<.>/u.test("<🌹>"));// true

console.log(/\p{Script=Greek}/u.test("α"));// true
console.log(/\p{Script=Arabic}/u.test("α"));// false
console.log(/\p{Alphabetic}/u.test("α"));// true
console.log(/\p{Alphabetic}/u.test("!"));// false
```

## Advanced
```js
//  \Y	    Match the Y'th captured group
var str = "blue+green+red=yellow."

var regexp1 = /blue(\W)green\1/;
console.log(regexp1.exec(str));
//  ["blue+green+", "+", index: 0, input: "blue+green+red=yellow.", groups: undefined]

var regexp2 = /green(\W)red\1/;
console.log(regexp2.exec(str));
//  null

// Assertions
/^dat$/.test('dat');    // true
/^dat$/.test('quangdat');   // false

/quang(?=dat)/.exec('quangdat');
    //    ["quang", index: 0, input: "quangdat", groups: undefined]
/quang(?=dat)/.exec('quangdaa');
    //  null
/(?:foo)bar\1/.test('foobarfoo');
    // false
/(?:foo)bar\1/.test('foobar\1');
    // true
    
//   \r  \n  \f (test in nodejs)
> console.log("stackoverflow\rnine");
//      ninekoverflow
> console.log("stackoverflow\fnine");
//      stackoverflow
//                          nine
> console.log("stackoverflow\nnine");
//      stackoverflow
//      nine
```
## References

https://eloquentjavascript.net/09_regexp.html

https://stackoverflow.com/questions/1324676/what-is-a-word-boundary-in-regexes

https://www.debuggex.com/cheatsheet/regex/javascript

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions

# 12. The `this` keyword

        The simple but extremely important keyword in your JavaScript code.

  - [`this` in Global evironment](#this-in-global-evironment)
  - [`this` inside functions](#this-inside-functions)
  - [`this` inside constructors](#this-inside-constructors)
  - [`this` in Methods](#this-in-methods)
  - [call() and apply()](#call-and-apply)
  - [bind()](#bind)
  - [`this` inside arrow function](#this-inside-arrow-function)
  - [`this` in classes](#this-in-classes)
  - [References](#references)

## `this` in Global evironment
Open a command terminal and run the node command.

        > this === global
        true
    
Inside a JavaScript file

        console.log(this === global);
        // run this file using the node command:
        $ node index.js
        false

The reason for this is that inside a JavaScript file, this equates to module.exports and not global.

## `this` inside functions
```js
function rajat() {
    console.log(this === global);
}
rajat();    // true
```
- If we add **use strict** at the top of the file and run it again, we will get a false output because now the value of **this is undefined**.
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
}

const person = Person('Master', 18);   // without the "new" keyword
console.log(person);    // undefined
```

- The reason behind this is that since the function is **not written in strict mode**, **this** refers to the **global** object.
- If we run this code in **strict mode**, we will get an error because JavaScript does not allow us to assign properties "name" and "age" to undefined. 
- To get the expected output we need to call that function as a constructor by using the "new" operator.

## `this` inside constructors
- We can convert a function call into a constructor call using **new** operator
- When a constructor call is made, a new object is created and set as the function’s this argument.
- The object is then implicitly returned from the function, unless we have another object that is being returned explicitly.

- Adding the "return" statement inside the function will overwrite the constructor call
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    
    return {name, age};     // return a literal object
}

const person = new Person('Master', 18);
console.log(person);    // {name: 'Master', age: 18}
console.log(person instanceof Hero);    // false
// Do not overwrite if return something that's not an object.
```

## `this` in Methods
```js
// The dialogue‘s "this" value then refers to hero itself.
const hero = {
    heroName: "Batman",
    dialogue() {
        console.log(`I am ${this.heroName}!`);
    }
};

hero.dialogue(); // I am Batman

const saying = hero.dialogue;
saying();   // I am undefined!
```

- When storing the reference to "dialogue" inside a variable and calling the variable as a function. The method has lost track of the "hero", "this" now refers to "global" instead of "hero".

- The loss of receiver usually happens when we are passing a method as a callback to another. We can either solve this by adding a wrapper function or by using **bind** method to tie our `this` to a specific object.

## call() and apply()
```js
function dialogue () {
    console.log (`I am ${this.heroName}`);
}

const hero = {heroName: 'Batman'};

dialogue.call(hero)
dialogue.apply(hero)
```

- But if you are using call or apply outside of strict mode, then passing null or undefined using call or apply will be ignored by the JavaScript engine.

## bind()
- When we pass a method as a callback to another function, there is always a risk of losing the intended receiver of the method, making the this argument set to the "global" object instead.
- The **bind()** method allows us to permanently tie a this argument to a value. 
```js
const hero = {
    heroName: "Batman",
    dialogue() {
        console.log(`I am ${this.heroName}`);
    }
};
setTimeOut(hero.dialogue.bind(hero), 1000);
```
- By doing so, our "this" cannot be changed by even "call" or "apply" methods.

## `this` inside arrow function 
- An arrow function uses the this value from its enclosing execution context, since it does have one of its own.
- Preventing apply, call and bind from changing it later on.
- An arrow function can also not be used as a constructor.
```js
const batman = this;
const bruce = () => {
    console.log(this === batman);
};
bruce();    // true

const counter = {
    count: 0,
    increase() {
        setInterval (() => {
            console.log (++this.count);
        }, 1000);
    },
};
counter.increase();    // it's working
```

## `this` in classes
- A class generally contains a constructor, where this would refer to any newly created object.
- And just like a method, classes can also lose track of the receiver.
```js
class Hero {
    constructor(heroName) {
        this.heroName = heroName;
    }
    dialogue() {
        console.log(`I am ${this.heroName}`)
    }
}
const batman = new Hero("Batman");

const say = batman.dialogue;
say();  // Uncaught TypeError: Cannot read property 'heroName' of undefined
```
- The reason for error is that JavaScript classes are implicitly in strict mode.
- We will need to manually bind() to tie this dialogue() function to "batman".

## References
https://blog.bitsrc.io/what-is-this-in-javascript-3b03480514a7

# 13. Asynchronous programming
    There can only be one currently running execution context
        (Because JavaScript is single threaded language)

## Promise
- The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.
```js
function getProductPromise() {
    return new Promise(function (resolve, reject) {
        if (! anyError) {
            resolve('this is a product');   // fulfilled
        } else {
            reject('this is an error');     // rejected
        }
    });
}

getProductPromise() // pending
    .then(function (product) {
        console.log(product);
        return getAnotherProductPromise();  // Chaining
    })
    .then(function (anotherProduct) {
        console.log(anotherProduct);
    })
    .catch(failureCallback);    // Error propagation

// start operations in parallel
Promise.all([ fn1(), fn2(), fn3()])
    .then(function (results) {
        for (let i of results) {
            console.log(i);
        }
    });

// nesting to limit the scope of catch statements
doSomething()
    .then(function () {
        return doSomthingElse()
            .then(function () {
                return doMorething();
            })
            .catch(failureCallback);
    })
    .then(function () {
        return doStuff();
    })
    .catch(anotherFailureCallback);
```

## async / await
- The async/await pattern is a syntactic feature of many programming languages that allows an asynchronous, **non-blocking** function (non-blocking the main thread) to be structured in a way similar to an ordinary synchronous function.
- Async functions are built on top of promises.
```js
async function getProductWithAsync() {
    const product = await getProductPromise();
    // do somthing with product
}
```

- Another benefit of the "async" keyword is it declare that the function "getProductWithAsync" return a promise
- That mean you can call :
```js
getProductWithAsync().then();
// or 
await getProductWithAsync();
```

```js
// the correct way to use async/await in parallel
async getBooksAndAuthor(authorId) {
    const bookPromise = bookModel.fetchAll();
    const authorPromise = authorModel.fetch(authorId);
    const book = await bookPromise;
    const author = await authorPromise;
    return {
        author,
        books: books.filter(book => book.authorId === authorId),
    };
}

// fetch a list of items one by one
async getAuthors(authorIds) {
    // WRONG, this will cause sequential calls
    // const authors = authorIds.map(id => await authorModel.fetch(id));
    // CORRECT
    const promises = authorIds.map(id => authorModel.fetch(id));
    const authors = await Promise.all(promises);
}

// Error handling 
// try {...} catch() {...}
async function getProductWithAsync() {
    try {
        const product = await getProductPromise();
        // do somthing with product
    } catch (err) {
        console.error("ERROR :{}    ", err);
    }
}

// using catch
const product = await getProductPromise()
    .catch(function (err) {
        console.error(err);
    });
```

## References
https://en.wikipedia.org/wiki/Async/await

https://hackernoon.com/javascript-async-await-the-good-part-pitfalls-and-how-to-use-9b759ca21cda

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise

https://blog.grossman.io/how-to-write-async-await-without-try-catch-blocks-in-javascript/
