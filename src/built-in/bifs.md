# Built-In Functions

\* Only in Node runtimes

## range
```
range: func (from: Number, to: ?Number, step: ?Number) Array[Number];
```
Same as Python's `range` function. Returns an array of numbers.

## parse_num
```
parse_num: func (value: String) Number;
```
Parse floats or integers into numbers

## import
```
import: func (path: String) Any;
```
Imports a module and returns the value.
Slightly different behaviour between Node and browser runtimes:
* All imports must be declared in config file for browsers, which then get preloaded before runtime

## help
```
help: func (value: Any) String;
```
Returns a string with information on the passed object.

## print
```
print: func (*: Array[Any]) nil;
```
Calls the specified print function. Often just native `console.log`.

## log
```
log: func (*: Array[Any]) nil;
```
Calls native `console.log`


## delete
```
delete: func (symbol: String) nil;
```
Removes a symbol with the specified identifier.

## __path__
```
__path__: func () String;
```
Returns The current path

## __symbols__
```
__symbols__: func (recursive: ?Bool) Object;
```
Gets all symbols in the current scope. 
If `recursive` is `true`, then gets all symbols up the global context.

## using
```
using: func (module: Any) nil;
```
Adds all symbols from object or namespace to the current scope.

## throw
```
throw: func (name: String, detail: String) nil;
```
Throws an error of type `name`.

## sleep
```
sleep: func (ms: Number, then: func (*: Array[Any]) Any) nil;
```

## open *
```
open: func (path: String, encoding: ?String = 'utf-8') ({
    str: func () String,
    write: func (data: String) nil,
    append: func (data: String) nil
})};
```

Throws `ImportError` if the file doesn't exist.