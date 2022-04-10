# Type
```
Type: Type
```

Every EntropyScript class and built-in type is an instance of Type.
Create an instance of a type by calling it.
Call a built-in type to cast to that type.

Call `Type` to get the string of the type of something, and without any parameters to create a new empty class.
```
Type(String);        // 'Type'
Type('hello world'); // 'String'
Type(Type);          // 'Type'
Type(Type(Type));    // 'String'
Type();              // new type
```

## Methods

`__get_init__: func () nil | Func`

## Properties
`__primordial__: Bool` Is the type primordial (predefined) or user defined.
`__name__: Str` The name of the type
`__extends__: ?Type` The parent type. Defaults to `Obj`
`__methods__: Arr[Func]` An array of the methods the type will add to instance
`__instances__: Arr[cls]` An array containing all instances of the type. Note this is not updated for primordial types.
`__abstract__: Bool` If the class is abstract or not. If true, trying to instantiate the type will result in a `TypeError`
`__fields__: Obj` The types that instances of the class are required to have.

# TypeUnion

Extends `Type`

Is the 'Union' of two types.

Create with the pipe `|` operator.

Resolves true if the resolution of either child type resolves to true.

Holds two additional properties:
`__left__` the left type, and
`__right__` the right type


# TypeIntersection

Is the 'Intersection' of two types.

Create with the pipe `&` operator.

Resolves true if the resolution of both child type resolves to true.

This is different from the TypeScript equivalent `&` as it
does not use the true intersection of the types, operating more like the `&&` operator.

Holds two additional properties:
`__left__` the left type, and
`__right__` the right type

# TypeNot

Is the 'Not' of a type expression.
Create with the `~` before the type expression.
Has the additional property `__val__` which is the expression that it `not`s