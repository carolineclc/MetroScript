# MetroScript

## Introducao
A Linguagem MetroScript foi desenvolvida com o objetivo d facilitat a criacao e execucao de rotas e instrucoes para trens de metro. Ela oferece uma sintaxe simples e intuitiva, permitindo que usuarios definam trens, suas rotas, suas paradas e outras aplicacoes como velocidade e rotacao de rodas para os trens.

## Desenvolvedores
Caroline Chaim de Lima Carneiro

Luca Machado

## Como executar
python main.py

### Arquivo de teste
teste.m

## EBNF

```
BLOCK = '{' , STATEMENT , '}';

STATEMENT = ASSIGNMENT | PRINT | WHILE | IF | PARAM | START |STOP|FINISH;

ASSIGNMENT = IDENTIFIER,( CREATE | SET);

CREATE = "=>", TYPE, ["=", (RELEXP | MATH_FUNC)], ";";

SET = "=", (RELEXP | MATH_FUNC),";";

PRINT = 'printLog','(',RELEXP,')';

WHILE = "while","(", RELEXP,")",BLOCK, ";";

IF = "if","(", RELEXP,")",BLOCK,["else",BLOCK], ";";

MATH_FUNC = MATHFUNC_N, "(", RELEXP, ")", ";";

MATH_FUNC_N = "sqrt" |"sin" | "cos" | "tan"| "log" | "exp" | "pow";

START = "START","(","id",":", IDENTIFIER , "," , "station", ":" , IDENTIFIER , ",", "region" , IDENTIFIER, ")",";";

STOP = "STOP" , "(","name", ":" , IDENTIFIER, ",", "speed", ":", NUMBER, "," , "rotation", ":", NUMBER,")",";";

FINISH= "FINISH","(","id",":", IDENTIFIER , "," , "station", ":" , IDENTIFIER , ",", "region" , IDENTIFIER, ")",";";

RELEXPR = EXPRESSION, { ("==" | ">" | "<"), EXPRESSION };

EXPRESSION = TERM, { ("+" | "-" | "||" | "."), TERM };

TERM = FACTOR, { ("*" | "/" | "&&"), FACTOR };

FACTOR = (("+" | "-" | "!"), FACTOR) | NUMBER | STRING | "(", RELEXPR, ")" | IDENTIFIER, ["(", RELEXPR, {",", RELEXPR} ,")"] | ("READLN", "(", ")");

IDENTIFIER = LETTER, { LETTER | DIGIT | "_" };

NUMBER = DIGIT, { DIGIT };

LETTER = ( a | ... | z | A | ... | Z );

DIGIT = ( 1* | 2* | 3* | 4* | 5* | 6* | 7* | 8* | 9* | 0* );

```
