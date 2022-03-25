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


## Functions

You can declare functions like so

```
func do_something () {

};
// Note the ';'

```
Or anonymously like this
```
let do_something = func () {};
```

## Classes

Declare classes like so
```
class MyClass {};
// or
let MyOtherClass = class {};
```

All classes and types should be in `PascalCase`

### Methods
The body of the class can only contain methods, which are declared like so:
```
let MyClass = class {
    // method
    do_something () {
        // do something
    }
};
```
All methods and properties are public.

### Constructor
The constructor gets called once when the instance is created.
```
class MyClass {
    // constructor 
    init () {
        this.a = 1;
    }
    
    // method
    get_a () {
        return this.a;
    }
};

let my_instance = MyClass();
my_instance.get_a(); // 1
```
Simply call the class like a function to create an instance. No `new` keyword.

### Operator overrides
```
class Num {
    init (n: Number) {
        this.a = n;
    }
    
    __add__ (to: Number) {
    
    }
};

Num(1) + Num(2);
// Num(3);
```

The overrideable methods are:

| Method Name        | Operator                           |
|--------------------|------------------------------------|
| `__add__`          | `+`                                |
| `__subtract__`     | `-`                                |
| `__multiply__`     | `*`                                |
| `__divide__`       | `/`                                |
| `__pow__`          | `^`                                |
| `__eq__`           | `==`                               |
| `__gt__`           | `>`                                |
| `__lt__`           | `<`                                |
| `__or__`           | <code>&#124;&#124;</code>          |
| `__and__`          | `&&`                               |
| `__pipe__`         | <code>&#124;</code>                |
| `__ampersand__`    | `&`                                |
| `__bool__`         | `!!` and any other bool conversion |
| `__set_property__` | `[]` and `.`                       |
| `__get_property__` | `[]` and `.`                       |
| `__call__`         | ()                                 |
          