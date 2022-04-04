# Error
```
Err: Type;
```


Throw an error with the `throw` build in function. 
Create an error by calling an error constructor, such as `TypeError`:
```
// expected string, but got bool
let my_err = TypeError('Str', 'Bool');
throw(my_err);
```

## Methods

(None)


## Properties

### name
```
Err.name: Str;
```
The name of the error, for example, 'TypeError' or 'InvalidSyntaxError'

### detail
```
Err.detail: Str;
```
More details about the error

### traceback
```
Err.traceback: Arr[Str];
```
An array of strings which are the name and location of function from which the error was generated.

