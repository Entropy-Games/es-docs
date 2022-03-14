# Array

```
Array: Type;
```

Arrays can be declared with square brackets, elements delimited by a comma.

For example, an array of numbers:
```
let my_array = [0, 1, 2, 3];
```

You can mix types in array and even nest arrays.
```
let my_nested_array = [0, 'hello world', [2, 3, [4]]];
```

To type an array use this syntax:
```
let my_array_of_numbers: Array[Numbers] = [0, 1, 2];

// throws a TypeError
let my_erronious_array_of_numbers: Array[Numbers] = [0, 1, 'hi'];

// And then nested types
let my_nested_array_of_numbers: Array[Array[Numbers]] = [[0, 2], [1, 3]];
```


You can also declare Tuple types with arrays like so:

```
let tuple = [String, Number];

let my_tuple: tuple = ['hello', 0];

// TypeError
let my_bad_tuple: tuple = ['hello', 'world'];

```

## Methods

### len
```
len: func () Number;
```
The length of the array

### contains
```
contains: func (element: Any): Bool;
```
Returns true if the array contains an element which is equivalent to `element`

## Properties

