# An intro to programming (using JS)

When programming, you should first spend some time doing *analysis*, meaning working out on paper how your program is going to work, the different moving parts and how they’ll interact, how you’re going to make each of them. However, to be able to do that you need a solid understanding of the tools you’ll have to make your program, so let’s start with that. 

## Types of data
Programming is, fundamentally, finding a way of automating math. Computers are just fancy and powerful calculators. In practice, this means you’ve got to solve the exercise, and the computer will repeat the solving for a large amount of data. 

#### Text
```JS
String textVariable = "Some text"
```

#### Numbers
```JS
int a = 3
float b = 3.5
```

#### Arrays
```JS
array c = ["some text", 7, anotherVariable]

// Getting a value in particular : 
newVar = c[0]
```

#### Objects
```JS
myObject = {
	key: “value”,
	subObject: {
		anotherKey: “anotherValue”,
		againKey: “againValue”,
	}
}
```

#### Booleans
```JS
bool e = true;
```

#### Undefined

#### Null

### TypeOf

## Declaring variables
### Scope
```JS
let b = 1;
var a = 1;
c = 1;
```
These are the 3 ways of declaring a variable in JS.

`let` allows you to declare variables with *block scope*. This means that a variable declared with `let` inside a block of code is only accessible within that block, and not outside of it.
```JS
if (true) { 
	console.log(x); // ReferenceError: x is not defined 
	let x = 10; console.log(x); // Output: 10 
} 

console.log(x); // ReferenceError: x is not defined
```

`var` has *function scope*. This means that a variable declared with `var` inside a function is only accessible within the function, and not outside of it. In addition, `var` variables are hoisted, which means that they are moved to the top of their scope and are accessible even before they are declared.
```JS
function myFunction() {
  console.log(x); // Output: undefined
  var x = 10;
  console.log(x); // Output: 10
}

myFunction();
console.log(x); // ReferenceError: x is not defined
```

No keyword acts like `var`.
```JS
function myFunction() {
  console.log(x); // Output: undefined
  x = 10;
  console.log(x); // Output: 10
}

myFunction();
console.log(x); // ReferenceError: x is not defined
```

## Operators 
1.  Arithmetic operators:
```JS
a + b
a - b
a * b 
a / b
a % b // modulus
a ** b // exponentiation
```

2.  Assignment operators:
```JS
a = b 
a += b // addition assignment
a -= b // subtraction assignment
a *= b // multiplication assignement
a /= b // division assignment
a %= b // modulus assignment
a **= b // exponentiation assignment
```

3.  Comparison operators:
```JS
a == b // equal to
a != b // not eual to
a === b // strict equal to
a !== b // strict not equal to
a > b // greater than
a < b // less than
a >= b // greater than or equal to
a <= b // less than or equal to
```

4.  Logical operators:
```JS
a && b
a || b
!a
```

5.  String operator:
```JS
    "Hello" + "World"
```

## Conditions 
```JS
if(test === "test"){
	//do this
}
```

```JS
if(test === "test"){
	// do this
} 

else { 
	// do this
}
```

```JS
if(test === "test"){
	// do this
} else { 
	// do this
}
```

```JS
var x = 3;

if (x > 5) {
  console.log("x is greater than 5");
} else if (x < 5) {
  console.log("x is less than 5");
} else {
  console.log("x is equal to 5");
}
```

## Loops
```JS
for(let i = 0; i < var ; i++){
	// do this
}
```

```JS
for(elements in object){

}
```

```JS
while(test === "test"){

}
```

## Functions
```JS
myFunction = function(a,b){
	d = a + b;
	return d;
}
```

## Multidimensional arrays (arrays of arrays)
```JS
var matrix = [ [1, 2, 3], [4, 5, 6], [7, 8, 9] ];

console.log(matrix[0][0]); // Output: 1 
console.log(matrix[1][1]); // Output: 5
```

```JS
var threeDimensionalArray = [ [ [1, 2, 3], [4, 5, 6] ], [ [7, 8, 9], [10, 11, 12] ] ]; 

console.log(threeDimensionalArray[0][0][0]); // Output: 1 
console.log(threeDimensionalArray[1][1][2]); // Output: 12
```


# Obscure stuff
### Bitwise operators:
```JS
a & b
a | b
a ^ b
a ~ b
a << b // left shift
a >> b // right shift
a >>> b // zero-fill rightshift
```





