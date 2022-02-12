https://www.codecademy.com/courses/introduction-to-javascript/lessons/introduction-to-javascript/exercises/math-operators

var, let e const, decisão, loops, JSON, Functions, arrow functions, callbacks, import, export, arrays (forEach, map, reduce, filter, spread operator), manipulação do DOM, event loop, Fetch, async e await, promises, LocalStorage, Web RTC, TypeScript, babel

# JavaScript

## Console
O console é o painel que mostra mensagens para os desenvolvedores.

```javascript
console.log('Olá, mundo!')
```

## Comentários
### Comentário simples
```javascript
//console.log('Hello world!')
console.log('Olá, mundo!')
```

### Comentário de Múltiplas linhas
```javascript
/* console.log('Hello world!')
este é um comentário de 
múltiplas linhas */
console.log('Olá, mundo!')
```

## Variáveis

var, let e const

### var
Podem possuir escopo global ou local
- escopo global: declarações com var fora de uma função
- escopo local: escopo da função quando declarada dentro da função

```javascript
var oi = 'oi'
function digaOla() {
    var ola = "Olá";
    console.log(ola);
}
```

Variáveis **var** podem ser redeclaradas ou atualizadas sem gerar erro.

```javascript
var oi = 'Oi';
var oi = 'Olá';
oi = 'Olá de novo';
```

### Var Hoisting
Declarações de variáveis são movidas para o topo do escopo automaticamente, o que permite:

```javascript
console.log (oi);
var oi = "diga olá";
```

Neste caso, se a variável não tiver sido inicializada seu valor é atualizada com o valor **undefined**.

### Problema com **var**
```javascript
var ola = "diga olá";
var cont = 4;
if (cont > 3) {
   var ola = "diga oi";
}
    
console.log(ola); // o resultado será "diga oi"
```

### let 
Possui escopo de bloco. Um bloco é um trecho de código dentro circundado por {}. Tudo que estiver cercado por {} é um bloco de código.

Uma variável let declarada dentro de um bloco de código estará disponível somente dentro deste bloco.

```javascript
let times = 4;

if (times > 3) {
    let oi = "diga oi";
    console.log(oi);
}
/* a variável oi somente está acessível dentro do if */
```

**let** pode ser atualizado mas não pode ser declarado novamente.

```javascript
let oi = "oi";
oi = "olá"; //ok
let oi = "o quê?"; //erro
```

No entanto, lembrando que variáveis declaradas com let possuem escopo de bloco, duas variáveis com o mesmo nome podem ser declaradas em escopos diferentes.

```javascript
let oi = "oi";
if (true){
    let oi = "olá";
    console.log(oi);
}
console.log(oi);
```

### let Hoisting
Assim como **var**, as variáveis declaradas com **let** também sofrem hoisting para o topo do escopo. No entanto, ao contrário do que acontece vom **var**, variáveis  **let** não possuem valor **undefined** e tentar utilizar uma variável **let** não inicializada resultará em erro.

Todas as características supracitadas fazem de **let** uma opção mais apropriada, geralmente, do que **var**. Isso porque não há necessidade de se preocupar com variáveis já declaradas ou redeclaração.

## Tipos de Dados
Em JavaScript existem 7 tipos de dados fundamentais.
 - **Número**: qualquer número, incluindo números decimais.
    - 1
    - 3.14
 - **String**: qualquer agrupamento de caracteres cincundado por 'aspas simples' ou "aspas duplas"
    - 'Uma string'
    - "Outra string"
 - **Booleano** (lógico): só admite dois valores possíveis **true** ou **false**
 - **Null**: este tipo representa a ausência __intencional__ de valor e é representado pela palavra-chave **null**
 - **Undefined**: também representa a ausência de valor. Não é uma palavra-chave, é uma variável global somente leitura (isso implica que undefined pode ser um nome de variável em escopos que não sejam globais)
 - **Symbol**: de forma simples são identificadores únicos.
 - **Object**: uma coleção de dados (propriedades) e/ou funções (métodos) relacionados(as). 

 Os seis primeiros tipos são considerados tipos primitivos da linguagem JavaScript.

## Operadores Aritméticos
 - Adição (+)
 - Subtração (-)
 - Multiplicação (*)
 - Divisão (/)
 - Resto da divisão (%)

 ```javascript
 console.log(10 + 3); //imprime 13
 console.log(10 - 3); //imprime 7
 console.log(30/3); //imprime 10
 console.log(3*3); //imprime 9
 console.log(13%3); //imprime 1
 console.log(27%4); //imprime 3
 ```

 ## Operadores Lógicos

 - &&: AND lógico
 - ||: OR lógico
 - !: NOT (negação)


 ## Operadores Comparação
 
 | Operador |                  Descrição                 |           Exemplo          |    Resultado    |
|:--------:|:------------------------------------------:|:--------------------------:|:---------------:|
|    ==    |                    Igual                   | '1' == 1 1 == 1 '1' == '1' |  true true true |
|    ===   | Estritamente igual. Igual e do mesmo tipo. |  '1' == 1 1 == 1 '1' == 1  | false true true |
|    !=    |                  Diferente                 |           1 != 2           |       true      |
|   !===   |        Diferentes ou tipo diferentes       |          '1' != 1          |       true      |
|     >    |                    Maior                   |            1 > 1           |      false      |
|    >=    |               Maior ou igual               |           1 >= 1           |       true      |
|     <    |                    Menor                   |            1 < 2           |       true      |
|    <=    |               Menor ou igual               |           1 <= 0           |      false      |

 ## String Operations
 ### Concatenação

 ```javascript
console.log('Olá, ' + 'mundo');//imprime Olá, mundo
console.log('Concatenando' + ' strings');//imprime Concatenando strings
 ```
 ### slice(start, end) 
 ```javascript
 let str = "Apple, Banana, Kiwi"
 let part = str.slice(7, 13);
 console.log(part);//Banana
 ```

### charAt(index) 
 - index: um inteiro entre 0 e str.length - 1. Se nenhum index for passado, charAt() usará 0 como índice.

 ```javascript
let str = '100 anos de solidão';
console.log("A letra no índice 0 é '" + anyString.charAt(0)   + "'");
 ```

 ### endsWith(substr [, tamanho]) 
 - substr: a substring a ser pesquisada no final da string.
 - tamanho: parâmetro opcional que, se passado, substitui o tamanho da string

 ```javascript
let str = '100 anos de solidão';
str.endsWith('solidão');//true
str.endsWith('anos');//false
str.endsWith('anos', 8);//true
 ```

### indexOf(substr [, inicio])
Retorna o índice da primeira ocorrência do valor fornecido em substr.
 - substr: uma string representando o valor a ser buscado
 - inicio: um número inteiro representando o índice a partir do qual a busca deve ser iniciada.

 ```javascript
"Blue Whale".indexOf("Blue");// retorna  0
"Blue Whale".indexOf("Whale");// retorna  5
"Blue Whale".indexOf("Blute");// retorna -1
"Blue Whale".indexOf("Whale", 0);// retorna  5
"Blue Whale".indexOf("Whale", 5);// retorna  5
"Blue Whale".indexOf("Whale", 7);// retorna -1
 ```


### lastIndexOf(substr [, inicio])
Retorna o índice da primeira ocorrência do valor fornecido em substr.
 - substr: uma string representando o valor a ser buscado
 - inicio: um número inteiro representando o índice a partir do qual a busca deve ser iniciada de trás para frente. Se início >= str.length, toda a string é pesquisada.

 ```javascript
'ricardo'.lastIndexOf('r');     // retorna 4
'ricardo'.lastIndexOf('a', 3);  // retorna 3
'ricardo'.lastIndexOf('a', 0);  // retorna -1
'ricardo'.lastIndexOf('x');     // retorna -1
'ricardo'.lastIndexOf('r', -5); // retorna 0
'ricardo'.lastIndexOf('r', 0);  // retorna 0
'ricardo'.lastIndexOf('');      // retorna 7
'ricardo'.lastIndexOf('', 2);   // retorna 2
 ```

### repeat(count)
- count: um número inteiro indicando quantas vezes a string deve ser repetida

```javascript
'abc'.repeat(0);    // ''
'abc'.repeat(1);    // 'abc'
'abc'.repeat(2);    // 'abcabc'
'abc'.repeat(3.5);  // 'abcabcabc' 
```

### replace(target, newValue)
Procura uma string por um valor (target) e substitui-o por outro, retornando uma nova string.

```javascript
"O IFRO é legal".replace('IFRO', 'mundo'); // O mundo é legal
```

### replaceAll(target, newValue)
Procura uma string por um valor (target) e substitui todas as ocorrências deste valor por outro, retornando uma nova string.

```javascript
"O IFRO é legal ou o IFRO não é legal?".replace('IFRO', 'mundo'); // O mundo é legal ou o mundo não é legal?
```

### toUpperCase()
```javascript
'ifro'.toUpperCase();//IFRO
``` 

### trim()
Retorna a string sem espaços em branco no início ou no fim.

```javascript
'   ifro   '.trim();//'ifro'
```

### trimEnd() ou trimRight()
Retorna a string sem espaços em branco no final.

### trimStart() ou trimLeft()
Retorna a string sem espaços em branco no começo.