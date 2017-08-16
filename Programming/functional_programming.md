### Dynamics vs Lexical Scoping
- Under dynamic scope, if an “unknown” variable is referred to in a function, the idea is to use the version of the variable that is in scope at the time that the function was called (and apply this rule recursively)
- Under lexical scoping rules, if an “unknown” variable is referred to in a function, the idea is to use the version that is “in scope” in the enclosing piece of code (and apply this rule recursively)
  ```
  a = 1
  b = 2
  f <- function(x) {
    a * x + b
  }
  g <- function(x) {
    a = 2
    b = 1
    f(x)
  }
  g(2)
  ```
- In dynamical scoping answer is 5 in lexical scoping answer is 4
- In lexical scoping variable bindings can be all resolved, checked and verified at compile-time – this is safer, and in many other ways better. Most modern languages adopt lexical scoping, including most functional languages
