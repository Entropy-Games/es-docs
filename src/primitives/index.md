# Primitives

Everything in EntropyScript is a primitive.
There are a few built in primitives, and then all new types inherit from primitive.

## Methods

### str
```
str: func () String;
```

Returns a stringified version of the primitive

### cast
```
cast: func (t: Any) t | Error;
```

Tries to cast to that type.
If you cannot cast the object or cannot cast to that type, then it will throw an error.

### bool
```
bool: func () Bool
```

Evaluates the object as a boolean.

### is
```
is: func (o: Any) Bool;
```

Returns true if the two are the same object.

```
let a = 1;
a.is(a); // true
a.is(1); // false
let b = a;
a.is(b); // true
b.is(a); // true
```

### isa
```
isa: func (type: Any) Bool;
```

Returns true if the object is of type `type`


### has_property
```
has_property: func (key: Any) Bool;
```
Returns true if the object has a key which is equal to `key`

### describe
```
describe: func (description: String) Undefined;
```

Adds a description to the object.
Does nothing when run on built in objects.

### type_check
```
type_check: func (obj: Any) Bool;
```
Reverse of `isa`. Returns true if `obj` is of type of whatever was called on.

### clone
```
clone: func () Any;
```
Returns a clone of the object

## Properties

### __type__
The object's type.

### _
The object

### __value__
The object, same as `_` and just not putting it.

### __info__
The metadata about the object, including its description

