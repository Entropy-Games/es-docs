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