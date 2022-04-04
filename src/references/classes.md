# Classes

Create a class like in many other languages, like so:
```
class MyClass {};
```

Or anonymouslyL

```
let MyClass = class {};
```

Define the constructor with the `init' method:
```
class A {
    init (*, **) {
    
    }
}
```

Construct classes (with or without a constructor) by calling the type:
```
class A {
    init () {
        print('Constructed!');
        
        // return value ignored
        return 'anything';
    }
};

let a = A();
```

Define properties on the class like so:
```
class A {
    my_prop: Any;
    // or just
    // my_prop;
    
    init () {
        this.my_prop = 1;
        this.my_prop = 'hello world';
    }
};

let a = A();
a.my_prop; // 'hello world'
```

Define methods either in the constructor or in the class definition:
```
class A {
    a: Num;
    
    // have to declare here if we define in the constructor
    do_thing: Func;
    
    init () {
        this.a = 0;
        
        // preserve 'this' context
        let self = this;
        this.do_thing = func (*, **) { 
            self.a = 1;
        };
    }
    
    do_other_thing () {
        this.a = 2;
    }
};

let a = A();
a.a; // 0
a.do_thing();
a.a; // 1
a.do_other_thing();
a.a; // 2
```

## Abstract classes

Declare abstract classes with the `abstract` keyword:
```
abstract class A {};
// or
let B = abstract class {};
```

Abstract classes cannot be directly constructed.

```
abstract class A {};
// TypeError
A();
```