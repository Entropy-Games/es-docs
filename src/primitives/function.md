# Function
```
Func: Type;
```

Declare a function with the `func` keyword. 

To type check against a function, you can simply check if something is a function:
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
let my_func: (func () Undefined) = func (): Undefined { 
    return 1;
};


// Note that you must explicitely type the return value and parameters 
// of both the type and the value:

// TypeError
let my_func: (func () Number) = func () 0;

// ok
let my_func: (func () Number) = func (): Number 0;
```

Allow any number of arguments with the `*` argument.
Access the arguments with the `args` variable automatically made in the functions scope.
```
func fn (*) {
    return args;
};
```
Will return an array of all the arguments passed in

# Kwargs

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