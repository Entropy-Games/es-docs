# CLI

The CLI can be accessed with either `entropy-script` or `jses` commands.
Note that `jses` is used where either could be used.

Start the REPL with `jses`.
Type `exit` to exit the REPL.

```bash
jses [script] [args]
```

The most common use case is, of course, a simple invocation of a script:

```bash
jses <myscript>.es
```

You can exclude the `.es`, as this is added automatically if is not the file extension.
Note that this forces you to use the `.es` extension.

## Compilation

To compile, simply use the `-compile` option. This defaults to JavaScript. To compile to python, add the `--python` flag.

```bash
jses -compile <myscript>.es out.[js|py] [--python]?
```