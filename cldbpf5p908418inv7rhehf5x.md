# Operator Precedence in JavaScript

Scared of assignments? Assignments of your variables? Learning about OPs will set you free of fears. So let's get right into it.

"Operator Precedence" in JavaScript determines the order in which operations are performed in an expression. It is like the order of operations (PEMDAS) that you learned in mathematics class. Operators (symbols) with higher precedence (importance) are evaluated before operators with lower precedence.

JavaScript has a set of predefined precedence levels for its operators. These levels are determined by the order of the operators in the table of precedence. For example, the multiplication operator (`_`) has higher precedence than the addition operator (`+`), so an expression such as `2 * 3 + 4` would be evaluated as `(2 * 3) + 4 = 6 + 4 = 10`.

The highest precedence level is assigned to operators that are enclosed in parentheses, such as `(2 + 3) * 4`. These operators are always evaluated first. Next, the unary operators (e.g. ++, --, delete, typeof, etc.) are evaluated. Followed by the arithmetic and bitwise operators (e.g. `+, -, *, /, %, etc.`) and then the comparison, logical and ternary operators.

It's important to understand operator precedence in order to correctly interpret and write expressions in JavaScript. If an expression is not written in the correct order, the result can be unexpected.

For example, the expression `2 + 3 * 4` would be evaluated as `2 + (3 * 4) = 2 + 12 = 14`, but if the intention was to multiply 2 and 3 first, and then add 4, the expression should have been written as `(2 + 3) * 4 = 5 * 4 = 20`.

If you want to change the order of operations in an expression, you can use parentheses to group operators and force a specific order of evaluation. For example, `2 * (3 + 4)` will be evaluated as `2 * 7 = 14`.

It's also important to note that JavaScript has left-to-right associativity for operators with the same precedence level. This means that when two or more operators with the same precedence level are used in an expression, they will be evaluated from left to right.

For example, the expression `2 + 3 - 4`, the addition operator (`+`) and the subtraction operator (`-`) have the same precedence level, so they will be evaluated from left to right resulting in `(2 + 3) - 4 = 5 - 4 = 1`.

The assignment operator (`=`) has lower precedence than most other operators. When the assignment operator is used in a chain of assignments, as in the example, `a = b = c` it is evaluated from right to left.

The rightmost assignment `c` is evaluated first. The value of `c` is then assigned to the variables `b` and `a` . This is called 'Chaining Assignments'.

Chaining assignment is a technique in JavaScript that allows multiple variables to be assigned the same value in a single line of code by chaining the assignment operator (`=`). The assignment is evaluated from right to left.

For example, consider the following code:

```javascript
let a, b, c;
c = 5;
b = c;
a = b;
```

The same result can be achieved using chaining assignment as follows:

```javascript
let a, b, c;
a = b = c = 5;
```

Here, the variable `c` is assigned the value of 5. Then, the value of `c` is assigned to the variable `b`. Finally, the value of `b` is assigned to the variable `a`.

Chaining assignments can be useful for simplifying your code and making it more readable when you want to assign the same value to multiple variables.

So, operator precedence in JavaScript determines the order in which operations are performed in an expression. It is essential to understand it in order to correctly interpret and write expressions in JavaScript. When in doubt, use parentheses to group operators and force a specific order of evaluation.

Or don't be a wuss and write your code without fear and arming yourself with knowledge. Here's a table for you:

| Precedence | Operator |
| --- | --- |
| 1 | \[\] . () |
| 2 | ! ~ ++ -- typeof void delete |
| 3 | \*\* |
| 4 | \\\* / % |
| 5 | \+ - |
| 6 | &lt;&lt; &gt;&gt; &gt;&gt;&gt; |
| 7 | &lt; &lt;= &gt; &gt;= instanceof in |
| 8 | \== != === !== |
| 9 | & |
| 10 | ^ |
| 11 | | |
| 12 | && |
| 13 | || |
| 14 | ? : |
| 15 | \`= += -= \_= /= %= \*\*= &lt;&lt;= &gt;&gt;= &gt;&gt;&gt;= &= ^= |
| 16 | yield |
| 17 | , |