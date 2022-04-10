# Syntax

The syntax of EntropyScript is very similar to JavaScript, except that is has slightly fewer brackets.

An EntropyScript script is a list of statements (a statements) seperated by the `;`. 
All lines must have semicolons except the last line in a statements.

## Declaration

To declare a constant, say
```
let n = something;
```

To declare a mutable variable, say 
```
let var n = something;
```

You must declare variables before using them.
This would result in an InvalidSyntaxError:
```
n = something;
```

You can also declare global variables like this:
```
// global constant
let global n = something;

// global mutable variable
let global var n2 = somethingelse;
```

## If

```
if expression {
	
}
```
Will run if `expression` evaluates to `true`.
Can be combined with `else` like so:

```
if expression {
	// do something
	
} else if another_expression {
	// do something else
	
} else {
    // do a something different
}
```

You can also use `if`s similarly to ternary operators, such as:
```
let my_val = if true { 'hello' } else { 'bye' };
my_val; // 'hello'
```

## Loops

### For

```
for i in expression {
    
}
```

The for loop is very versatile, as it can be used to iterate over an array but also over numbers, strings and the keys of objects.

```
// iterate from 0-9
for j in 10 {
	
}

// iterate from 3-9 with a step of 2
for l in range(3, 9, 2) {
	
}

let my_object = { a: 1, b: 2 };
// iterate over the array ['a', 'b']
for key in my_object {
	let value = my_object[key];
}
```

### While

```
while expression {
	
}
```

Will repeat until the expression `something` evaluates to `false`

```
var a = false;
while !a {
    a = true;
}
```


You cannot write `for`, `if` or `while` statements in the common C-like way:
```
// InvalidSyntaxError
if (expression) 
	do_something();
```
You must have curly braces.

## Comments

Like JavaScript, you write comments as follows
```js
// single line comment

/*
    Multi-line comment
 */
```

## Try-Catch
```
try {
    throw(TypeError());
} catch {
    // 'err' variable created in this scope
    print(err);
    err.name; // 'TypeError'
}
```