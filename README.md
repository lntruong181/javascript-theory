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
