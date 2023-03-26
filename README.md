# My Programming Language


```js
function soma_valores:
  param m, param n, // representam os parâmetros que a função recebe
  {
    const soma = m + n;
    const sub = m - n;
    if (m > n) {
      return soma;
    }
    else {
      return sub;
    }
  }

function concatenate:
  param u, param v, 
  {
    return u + v; // representa a string m + n
  }

function f_without_parameters:
  {
    stdout("Olá mundo");
  }

const a = 1;
const b = 2;
const c = soma_valores(a, b); // c recebe o valor de 1 + 2

stdout(c); // printa o valor, assim como o print() em python
stdout(concatenate("Judson", "Oliveira")); // printa o valor "JudsonOliveira"
stdout(10 + (121/11) - (5 / (1 + 2)));

f_without_parameters(); // executa o conteúdo da função

const index = 10;

while (index > 0) {
  const x = 0;
  if (x < index) {
    stdout(x);
  }
  else {
    stdout(index);
  }
  index = index - 1;
}
```


```ts
PROGRAM = { STATEMENT | FUNCTION } ;
CONST_DECLARATION = "const", IDENTIFIER, "=", EXPRESSION, ";" ;

FUNCTION_CALL = IDENTIFIER, "(", { EXPRESSION, { ",", EXPRESSION } }, ")" ;
FUNCTION = "function", IDENTIFIER, ":", FUNCTION_PARAM_LIST, "{", BLOCK, "}"
FUNCTION_PARAM_LIST = λ | FUNCTION_PARAM, { ",", FUNCTION_PARAM }
FUNCTION_PARAM = "param", IDENTIFIER ;

BLOCK = "{", { STATEMENT }, "}" ;
STATEMENT = ( EXPRESSION | STDOUT | IF_STATEMENT | WHILE_STATEMENT | CONST_DECLARATION ), ";" ;

IF_STATEMENT = "if", "(", EXPRESSION, ")", BLOCK, { "else", "(", BLOCK, ")" } ;
WHILE_STATEMENT = "while", "(", EXPRESSION, ")", BLOCK ;

STDOUT = "stdout", "(", EXPRESSION, ")" ;

EXPRESSION = SIMPLE_EXPRESSION | SIMPLE_EXPRESSION, COMPARISON_OPERATOR, SIMPLE_EXPRESSION ;
SIMPLE_EXPRESSION = TERM, { ("+" | "-"), TERM } ;
TERM = FACTOR, { ("*" | "/"), FACTOR } ;
FACTOR = IDENTIFIER | "(" EXPRESSION ")" | NUMBER | STRING | FUNCTION_CALL ;

IDENTIFIER = ( LETTER | "_" ), { LETTER | DIGIT | "_" } ;
STRING = '"', CHARACTER, { CHARACTER }, '"' ;
CHARACTER = ( LETTER | DIGIT | MATH_OPERATOR | CHARACTER ) ;
MATH_OPERATOR = ( "+" | "-" | "/" | "*" ) ;
COMPARISON_OPERATOR = "<" | "<=" | ">" | ">=" | "==" | "!=";
SYMBOL = ( "." | "_" | "@" | "#" | "!" | "&" | "(" | ")" | "{" | "}" | "[" | "]" ) ;
LETTER = ( a | ... | z | A | ... | Z ) ;
NUMBER = DIGIT, { DIGIT }, ( λ | ( ".", DIGIT, {DIGIT} ) );
DIGIT = ( 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 ) ;
```
