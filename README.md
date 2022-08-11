This is the reference implementation [chibicc](https://github.com/rui314/chibicc)

```
program = stmt*

stmt = "return" expr ";"
     | "if" "(" expr ")" stmt ("else" stmt)?
     | "for" "(" expr-stmt expr? ";" expr? ")" stmt
     | "while" "(" expr ")" stmt
     | "{" compound-stmt
     | expr-stmt

compound-stmt = stmt* "}"

expr-stmt = expr? ";"

expr = assign

assign = equality ("=" assign)?

equality = relational ("==" relational | "!=" relational)*

relational = add ("<" add | "<=" add | ">" add | ">=" add)*

add = mul ("+" mul | "-" mul)*

mul = unary ("*" unary | "/" unary)*

unary = ("+" | "-") unary
      | primary

primary = "(" expr ")" | ident | num
```