# Syntax

The syntax of EntropyScript is very similar to JavaScript, except that is has slightly fewer brackets.

An EntropyScript script is a list of statements (a statements) seperated by the `;`. 
All lines must have semicolons except the last line in a statements.

## Declaration

To declare a mutable variable, simply say 
```
var n = something;
```

You must declare variables before using them.
This would result in an InvalidSyntaxError:
```
n = something;
```

To declare a constant, say
```
let n = something;
```

You should default to declaring constants.

You can also declare global variables like this:
```
// global constant
global n = something;

// global mutable variable
global var n2 = somethingelse;
```

## Loops

### for

```
for i in something {
    
}
```
The for loop is very versatile, as it can be used to iterate over an array but also over numbers, strings and the keys of objects.

```
// iterate from 0-9
for i in 10 {
	
}

// iterate from 3-9 with a step of 2
for i in range(3, 9, 2) {
	
}

let my_object = { a: 1, b: 2 };
// iterate over the array ['a', 'b']
for i in my_object {
	
}
```

## Comments

Like JavaScript, you write comments as follows
```js
// single line comment

/*
    Multi-line comment
 */
```

