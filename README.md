# MetroScript

## Introducao
A Linguagem MetroScript foi desenvolvida com o objetivo d facilitat a criacao e execucao de rotas e instrucoes para trens de metro. Ela oferece uma sintaxe simples e intuitiva, permitindo que usuarios definam trens, suas rotas, suas paradas e outras aplicacoes como velocidade e rotacao de rodas para os trens.

## Desenvolvedor
Caroline Chaim de Lima Carneiro

## Como executar
python main.py

### Arquivo de teste
teste.m

## EBNF

``` c
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

## Exemplo 1: Definindo rota

O seguinte exemplo demonstra como usar a linguagem para definir uma rota de voo com tres paradas. A rota comeca o lugar que o trem estiver estacionado pela noite anterior e passar pelas paradas 1,2,3 e termina no lugar onde ele vai parar pelo dia. Note que neste exemplo o trem passa pelas estacoes sem parar, e no final faz sua parada na estacao do hospital depois de concluir o seu percurso de novo na estacao Santa Rosa.

``` c

{
START (id : "abc_123", station : "Santa Rosa", region : "Norte");

STOP (name : "Pinheiros", speed: 50, rotation: 100);
STOP (name : "Parque", speed : 20, rotation : 50);
STOP (name : "Hospital", speed : 0, rotation : 0);

FINISH (id :  "abc_123", station : "Santa Rosa", region : "Norte); 
}
```


