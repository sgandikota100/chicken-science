---
{"dg-publish":true,"permalink":"/operators/"}
---

The things that dictate how code flows, in [[☕️ Java\|Java]]
# Assignment Operators 
instead of writing a "full math equation", use an operator to quickly change the value of a variable

| Operator | Example | Math Equivalent |
| -------- | ------- | --------------- |
| `=`        | `x=5`     | `x=5`             |
| `+=`       | `x+=3`    | `x=x+3`           |
| `-=`       | `x-=3`    | `x=x-3`           |
| `*=`      | `x*=3`    | `x=x*3`          |
| `/=`       | `x/=3`    | `x=x/3`           |
| `%=`       | `x%=3`    | `x=x%3`           |
| `&=`       | `x&=3`    | `x=x&3`           | 
## Assignment Compatibilities 
`byte --> short --> int --> long --> float --> double`
a value of one type can be assigned to a variable of any type further to the right
# Comparison Operators
used to compare two values 

| Name                        | Example |
| --------------------------- | ------- |
| Equal to (`==`)              | `x == y` |
| Not Equal to (`!=`)           | `x!=y`    |
| Greater than (`>`)            | `x>y`     |
| Less than (`<`)               | `x<y`     |
| Greater than/ Equal to (`>=`) | `x>=y`    |
| Less than or Equal to (`<=`)  | `x<=`        |

# Logical Operators 
allows you to compare values or variables using [[👻 Boolean Algebra\|boolean algebra]].  

| Name             | Description                                             | Example     |
| ---------------- | ------------------------------------------------------- | ----------- |
| Logical and (`&&`) | Returns true if ALL statements are true                 | `x<5 && x<10` |
| Logical or (\|\|)    | Returns true if ONE statement(s) is true            |`x<5`\|\|`x<4`             |
| Logical not (`!`)  | Reverse the result, returns false if the result is true | `!(x<5 && x<10)`            |

# Numeric/Arithmetic Operators
These are just the mathematical operations you perform of variables / values

| Name                | Example  | Result |
| ------------------- | -------- | ------ |
| Addition (+)        | 34+1     | 35     |
| Subtration (-)      | 34.0-0.1 | 33.9   |
| Multiplication (\*) | 300\*30  | 9000   |
| Division(/)         | 1.0/2.0  | 0.5    |
| Mod/Remainder (%)   | 20%3     | 2      |
| Increment (++)      | ++5      | 6      |
| Decrement (--)      | --5      | 4      | 
**Increment / Decrement order: IT MATERS**
```java 
int m = 4; 
int result = 3*(++m)
... result = 15 b/c m=5; increment, then multiply 
int m = 4; 
int result = 3*(m++)
...result = 12 b/c m=5; multipy then increment
```
### Parentheses
Parentheses can help communicate the order of arithmetic operators. Without, the expression is evaluated according to the *operator precedence*. ie these 2 aren't the same: 
```java 
(cost+tax)*discount 
cost+(tax*discount)
```
## Precedence Order 
| Operators      | Precedence                                |     |
| -------------- | ----------------------------------------- | --- |
| Postfix        | `expr++`, `expr--`                        |     |
| unary          | `++expr`, `--expr`, `+expr`, `-expr`, `!` |     |
| mutliplicative |                                           |     |
| additive       |                                           |     |
|                |                                           |     |
Operators higher on the list have "high precedence" and vice versa: 
1. Unary Operators: +, -, !, ++, and -- 
2. Binary Arithmetic Operators: **, /, and %
3. Binary Arithmetic Operators: + and - 