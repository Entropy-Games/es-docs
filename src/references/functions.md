# Functions

## Declare a function

```
func do_thing () {
    // do something
};

// or 

let do_other_thing = func () {
    // do something else
};
```

And call a function:
```
// the last expression is returned by default in a function, and curly braces are optional
func a (b) b;
a(1) // 1;

// is the same as
func b (p) {
    return p;
};
b(2); // 2
```

## Type a function
Type the parameters of a function with `:` after the parameter name
```
func run (a: Any, b: Num) {
    return a && b;
}
```

Type the return value of a function again with a `:`
```
func run (a, b): Bool {
    return a && b;
}
```

## Type Check
```
let my_func: Func = func () {};

// TypeError
let not_a_func: Func = 0;
```

Or you can do a deeper type heck and check against the parameters and return type:
```

let my_func: (func () Undefined) = func (): Undefined {};

/*
  Note the lack of a colon after the brackets in the type description.
  The return type of the type function is simply a function which 
  returns the desired return type.
  Technically, you could have side effects inside the type function, 
  although this is ill-advised.
*/


// TypeError
let my_func: (func () Null) = func (): Null { 
    return 1;
};


// Note that you must explicitely type the return value and parameters 
// of both the type and the value:

// TypeError
let my_func: (func () Num) = func () 0;

// ok
let my_func: (func () Num) = func (): Num 0;
```

## Args

Allow any number of arguments with the `*` argument.
Access the arguments with the `args` variable automatically made in the functions scope.
```
func fn (*) {
    return args;
};
```
Will return an array of all the arguments passed in

## Default arguments

Adding a `=` after an argument gives it a default value:
```
func run (level = 1): Str {
    return 'hello world ' + level.str();
};
```

This can be mixed with parameter types:
```
func run (level: (Num | Str) = 1): Str {
    return 'hello world ' + level.str();
};
```

## Kwargs

Similarly to python, functions can also take key-word arguments.
Kwargs are specified with the `*` operator before the name.
```
func fn (*a) {
    return a;
};
```
Pass kwargs again with `*`
```
func fn (a, *b) {
    return [a, b];
};

fn(1, *a=2); // [1, 2]
```

Adding a `:` after a kwarg will give it a type restriction, and `=` gives it a default value
```
func run (*level: Num = 1): Str {
    return 'hello world ' + level.str();
};
run(); // 'hello world 1'
run(2); // 'hello world 2'
```

Allow any number of kwargs with the `**` argument, which must be the last argument.
Access the kwargs with the `kwargs` variable automatically made in the functions scope.
```
func fn (**) {
    return kwargs;
};
```

returns an object with all the kwargs passed through in.

```
func fn (*, **) {};
```
This function takes any number of arguments or kwargs.

Note that the order of parameters is:
* Positional (normal)
* Kwargs
* \*
* \*\*