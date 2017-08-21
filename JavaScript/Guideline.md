# JavaScript Guideline



## Variables, constants and function names

* Variable and function names must always be written in *camelCase*.
* All variable and constant names must start with a letter.
* Underscores in variable and constant names may be used when necessary.
* Hyphens must not be used.
* All local variables in a function must be declared with the `var` keyword.
* Global variables and constants must be written in *UPPERCASE*.
* The use of global variables should be minimized.

```javascript
var firstName = 'John';
var lastName = 'Doe';
```


## Operators

* Always put spaces around operators ( `=` `+` `-` `*` `/` ), and after commas:
* Calculations should be used in brackets.

```javascript
var x = (y + z);
var values = ["Volvo", "Saab", "Fiat"];
```


## Statements

* Statements must end with a semicolon

```javascript
var name = "John Doe";
```


## Complex statements

* Complex statements must always use brackets.
* The opening bracket must be set at the end of the first line.
* Before the opening bracket one space must be set.
* The closing bracket must be set on a new line, without leading spaces.
* Do not end a complex statement with a semicolon.

*Functions:*
```javascript
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
```

*Loops:*
```javascript
for (i = 0; i < 5; i++) {
    x += i;
}
```


*Conditionals:*
```javascript
if (time < 20) {
    greeting = "Good day";
} else {
    greeting = "Good evening";
}
```



## Objects

* The opening bracket must be placed on the same line as the object name.
* Use colon plus one space between each property and its value.
* Quotes must be placed around string values and must not be placed around numeric or boolean values.
* Do not add a comma after the last property-value pair.
* Place the closing bracket on a new line, without leading spaces.
* Always end an object definition with a semicolon.
* Short objects can be written in one line, using spaces only between properties.

```javascript
var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
};
```

```javascript
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

* Never declare Number, String, or Boolean Objects

```javascript
var x = "John";             
var y = new String("John");
(x === y) // is false because x is a string and y is an object.
```

```javascript
var x = new String("John");             
var y = new String("John");
(x == y) // is false because you cannot compare objects.
```


## Declarations

* Declarations must be placed on top

```javascript
// Declare at the beginning
var firstName, lastName, price, discount, fullPrice;

// Use later
firstName = "John";
lastName = "Doe";

price = 19.90;
discount = 0.10;

fullPrice = price * 100 / discount;
```


## Do Not use `new Object()`

* Use `{}` instead of `new Object()`
* Use `""` instead of `new String()`
* Use `0` instead of `new Number()`
* Use `false` instead of `new Boolean()`
* Use `[]` instead of `new Array()`
* Use `/()/` instead of `new RegExp()`
* Use `function (){}` instead of `new Function()`


## Comparison

* Comparison with value and type `===` is strongly recommended.

```javascript
"1" === 1 // false
1 === 1   // true
```


## Security

* `eval()` must be avoided, if possible.


## Sources

* [W3Schools (Conventions)](http://www.w3schools.com/js/js_conventions.asp)
* [W3Schools (Best practices)](http://www.w3schools.com/js/js_best_practices.asp)


