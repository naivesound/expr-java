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

