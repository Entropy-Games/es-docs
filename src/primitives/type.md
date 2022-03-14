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

# TypeUnion

Is the 'Union' of two types.
Create with the pipe `|` operator.
Resolves true if the resolution of either child type resolves to true


# TypeIntersection

Is the 'Intersection' of two types.
Create with the pipe `&` operator.
Resolves true if the resolution of both child type resolves to true.

This is different from the TypeScript equivalent `&` as it
does not use the true intersection of the types, operating more like the `&&` operator.


# TypeNot

Is the 'Not' of a type expression.
Create with the `~` before the type expression.