# jexpr

[![Build Status](https://travis-ci.org/naivesound/jexpr.svg?branch=master)](https://travis-ci.org/naivesound/jexpr)

Fast and lightweight expression evaluator for Java. The whole evaluator is only one class of ~500LOC.

```java
Expr.Builder builder = new Expr.Builder();

Map<String, Variable> vars = .....
Map<String, Func> funcs = ....

vars.get("x").set(42);
Expr e = builder.parse("y=2+f(x)", vars, funcs);
float result = e.eval();
float y = vars.get("y").eval();
```

## Performance

```
parse 1: 56443.277
parse 10: 276689.75
parse 100: 2234274.5
eval 1: 1249.1752
eval 10: 3833.1233
eval 100: 6461.009
```

This means that a large expression of ~3k characters using variables,
assignments and functions takes 2ms to parse (compile) and 6.4us to evaluate.
