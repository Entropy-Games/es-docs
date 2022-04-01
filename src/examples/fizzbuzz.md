# FizzBuzz to n

```
let now = import('time').now;

func main (n) {
    for i in range(1, n+1) {

        div3 = i % 3 == 0;
        div5 = i % 5 == 0;

        if div3 && div5 {
            print('fizzbuzz');
        } else if div3 {
            print('fizz');
        } else if div5 {
            print('buzz');
        } else {
            print(i);
        }
    }
};

// time how long it takes
let start = now();
main(1000);
print(now() - start, 'ms');
```

This typically runs in ~150ms, compared to ~50ms for Python and JavaScript