# Fibonacci series up to n

```
func fib (n) {
    let var a = 0;
    let var b = 1;

    while a < n {
        print(a);
        let t = a;
        a = b;
        b = t + b;
    }
};

fib(1000);
```