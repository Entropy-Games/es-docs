# Destructuring

You can destructure anything iterable or objects. Destructure by declaring multiple variables similarly to an array.

Destructuring arrays:
```
let [] = [];

let [] = [1, 2, 3];

let [ a, b, c ] = [1, 2, 3];
a; // 1
b; // 2
c; // 3

// Error
let [ a, b ] = [1];
```

Destructuring objects and namespaces:
```
let [ a, b ] = {a: 1, b: 2};
a; // 1
b; // 2

// Error
let [ c ] = {};

let my_obj = {
    prop1: 'hello world',
    prop2: 10
};

let [ props2 ] = my_obj;
prop2; // 10

// similar to Node.js' 'require' syntax
let [ asciiToChar ] = import('ascii');
asciiToChar(70); // 'F'

namespace N {
    let g = 2;
    let h = 3;
};

let [ g ] = N;
g; // 2

```

Destructuring other iterables:
```
let [a, b] = 2;
a; // 0
b; // 1;

let [c, d] = 'hello world';
c; // 'h'
d; // 'e'

// Error
let [a] = -1;
```