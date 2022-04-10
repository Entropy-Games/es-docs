# Operator overrides

Override the default functionality of an operator by replacing the method called for that operator. 
```
class NumberWrapper {
    a: Num;
    init (n: Num) {
        this.a = n;
    }
    
    __add__ (to) {
        return Num(this.a + to.a);
    }
};

NumberWrapper(1) + NumberWrapper(2);
// NumberWrapper(3);
```

The overrideable methods are:

| Method Name     | Operator                           |
|-----------------|------------------------------------|
| `__add__`       | `+`                                |
| `__subtract__`  | `-`                                |
| `__multiply__`  | `*`                                |
| `__divide__`    | `/`                                |
| `__pow__`       | `^`                                |
| `__eq__`        | `==`                               |
| `__gt__`        | `>`                                |
| `__lt__`        | `<`                                |
| `__or__`        | <code>&#124;&#124;</code>          |
| `__and__`       | `&&`                               |
| `__pipe__`      | <code>&#124;</code>                |
| `__ampersand__` | `&`                                |
| `__bool__`      | `!!` and any other bool conversion |
| `__set__`       | `[]` and `.`                       |
| `__get__`       | `[]` and `.`                       |
| `__call__`      | ()                                 |
          