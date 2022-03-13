# Fibonacci series up to n

```
let fib = func (n) {
    var a = 0;
    var b = 1;

    while a < n {
        print(a);
        let t = a;
        a = b;
        b = t + b;
    }
};

fib(1000);
```