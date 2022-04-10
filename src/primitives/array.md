# Array

```
Arr: Type;
```

Is iterable.

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
let my_array_of_numbers: Arr[Num] = [0, 1, 2];

// throws a TypeError
let my_erronious_array_of_numbers: Arr[Num] = [0, 1, 'hi'];

// And then nested types
let my_nested_array_of_numbers: Arr[Arr[Num]] = [[0, 2], [1, 3]];
```


You can also declare Tuple types with arrays like so:

```
let tuple = [Str, Num];

let my_tuple: tuple = ['hello', 0];

// TypeError
let my_bad_tuple: tuple = ['hello', 'world'];

```

Concatenate arrays using the `+` operator.

Arrays can be `cast` to `Str`, `Num` (number of elements), or `Bool` (num of elements > 0).

## Methods

### len
```
Arr.len: func () Num;
```
The length of the array

### contains
```
Arr.contains: func (element: Any): Bool;
```
Returns true if the array contains an element which is equivalent to `element`

## Properties

