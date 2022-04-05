# Enhancements

A list of things to try to do to write consistent Entropy Script code.

* Identifiers
  * Reserved properties are written with `__dunderscores__`, and so should be not used
  * Classes, namespaces and types would be in `PascalCase`
  * Functions and variables should be in `snake_case`
  * Global constants in `SCREAMING_SNAKE_CASE`
  * Imported modules should be in `flatcase` or `snake_case` for long names
* `Any` should be avoided, ideally use with `noAny: true`
* Functions, classes and objects should be declared without `var`
* `.property` preferred over `['property']`
* Calls to `super` on first line of `init`
* `global` used sparingly
* Spaces
  * Around operators, except unary
  * Around `[` and `]` when destructuring
  * Before and after `=` except for default parameters
  * after `,`
  * After keywords and identifiers
  * Between `()` and `{` for functions
