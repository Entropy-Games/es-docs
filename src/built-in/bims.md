# Built In Modules

(\* node CLI only)

Use these by importing them, for example, to use the 'json' module:

```
let json = import('json');
json.stringify({}); // '{}'

// or 
let [ stringify ] = import('json');
stringify({}); // '{}'
```

## json
```
json: <native 'JSON'>;
```

## ascii

```
// converts number representing ascii character to a string
ascii.asciiToChar: func (n: Num) Str;

// other way round
ascii.charToAscii: func (n: Str): Num; 
```

## time
```
time.now: func () Num;
time.date: <native 'Date'>;
```

## math
```
math: <native 'Math'>;
```

## promise
```
promise: <native 'Promise'>
```

# All the following modules act exactly like their node.js counterparts

## fs *

## https *

## http *

## mysql *

## path *