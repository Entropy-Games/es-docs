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

## Inheritance

Classes can inherit from other classes using the `extends` keyword.

```
class A {};

class B extends A {};
// or 
let C = class extends A {};
```

If a class extends another class, you get access to the `super` function inside the `init` function on the child class,
which calls the `init` function on the parent class.
```
class A {
    a;
    init (a) {
        this.a = a;
    }
};

class B extends A {
    b;
    init (a, b) {
        super(a);
        this.b = b;
    }
};

let b = B(1, 2);
b.a; // 1
b.b; // 2
```

You can extend classes many layers down:
```
class GrandParent {};
class Parent extends GrandParent {};
class Child extends Parent {};
// and so on...
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

Abstract classes are used
to declare what fields classes should have and declare common properties and methods between classes.
```
abstract class A {

    get_thing: func (*, **) Num;
    a: Num;
    
    init (a: Num = 0) {
        this.a = a;
    }
    
    do_common_thing () {
        this.a += 2;
    }
};

class B extends A {
    b: Num;
    init (a, b) {
        super(a);
        this.b = b;
    }
    
    // if this was not defined it would throw an error
    get_thing (): Num {
        return this.a + this.b;
    }
};

let b = B(1, 2);
b.do_common_thing();
b.get_thing(); // 5
```