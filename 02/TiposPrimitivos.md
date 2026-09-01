# Tipos Primitivos em Java

## 1. Introdução

Em Java, uma variável precisa possuir um **tipo de dado**. Esse tipo determina quais valores poderão ser armazenados na variável, quanto espaço aproximadamente será necessário para representá-los e quais operações poderão ser realizadas.

Os tipos de dados em Java podem ser divididos, de maneira geral, em dois grandes grupos:

* **Tipos primitivos**
* **Tipos por referência**

Os **tipos primitivos** representam os dados mais básicos da linguagem, como números inteiros, números decimais, caracteres e valores lógicos.

Java possui exatamente **8 tipos primitivos**:

| Categoria       | Tipos                          |
| --------------- | ------------------------------ |
| Inteiros        | `byte`, `short`, `int`, `long` |
| Ponto flutuante | `float`, `double`              |
| Caractere       | `char`                         |
| Lógico          | `boolean`                      |

---

# 2. O que é uma variável?

Uma variável é uma área identificada utilizada por um programa para manter determinado valor durante sua execução.

Exemplo:

```java
int idade = 36;
```

Podemos dividir essa declaração em três partes:

```text
int     idade     = 36;
│        │          │
tipo     nome      valor
```

Nesse exemplo:

* `int` é o tipo;
* `idade` é o nome da variável;
* `36` é o valor armazenado.

Depois da declaração, podemos utilizar a variável:

```java
System.out.println(idade);
```

Saída:

```text
36
```

---

# 3. Tipos primitivos x objetos

Uma característica importante de Java é a diferença entre tipos primitivos e objetos.

Por exemplo:

```java
int numero = 10;
```

`numero` possui o tipo primitivo `int`.

Já:

```java
String nome = "Victor";
```

`String` **não é um tipo primitivo**.

`String` é uma classe.

Isso significa que:

```java
int
double
boolean
char
```

são tipos primitivos, enquanto:

```java
String
Scanner
ArrayList
Pessoa
Integer
Double
```

representam tipos por referência.

---

# 4. Os oito tipos primitivos

## 4.1 `byte`

O tipo `byte` representa números inteiros pequenos.

Possui **8 bits** e seus valores possíveis vão de:

```text
-128 até 127
```

Exemplo:

```java
byte idade = 36;
```

Outro exemplo:

```java
byte quantidade = 100;

System.out.println(quantidade);
```

Saída:

```text
100
```

Porém:

```java
byte numero = 200;
```

gera erro de compilação, porque `200` está fora do intervalo suportado pelo `byte`.

### Quando usar?

Pode ser utilizado quando se deseja representar valores inteiros muito pequenos ou trabalhar diretamente com dados binários.

Entretanto, em aplicações Java comuns, costuma-se utilizar `int` para números inteiros mesmo quando os valores são pequenos.

---

# 5. `short`

O tipo `short` representa números inteiros utilizando **16 bits**.

Seu intervalo é:

```text
-32.768 até 32.767
```

Exemplo:

```java
short quantidadeFuncionarios = 1500;
```

Outro exemplo:

```java
short ano = 2026;

System.out.println(ano);
```

Saída:

```text
2026
```

Embora exista, `short` também é relativamente pouco utilizado em aplicações Java convencionais.

---

# 6. `int`

`int` é o tipo inteiro mais utilizado em Java.

Possui **32 bits**.

Seu intervalo é:

```text
-2.147.483.648
até
2.147.483.647
```

Exemplo:

```java
int idade = 36;
```

Outros exemplos:

```java
int quantidadeClientes = 250;

int anoAtual = 2026;

int saldoPontos = 15000;
```

É normalmente a escolha padrão para representar números inteiros.

### Exemplo prático

```java
public class Main {

    public static void main(String[] args) {

        int idade = 36;
        int anoAtual = 2026;

        System.out.println(idade);
        System.out.println(anoAtual);
    }
}
```

---

# 7. `long`

O tipo `long` também representa números inteiros, porém consegue armazenar valores muito maiores que `int`.

Possui **64 bits**.

Seu intervalo é aproximadamente:

```text
-9,22 × 10¹⁸
até
9,22 × 10¹⁸
```

Exemplo:

```java
long populacao = 8000000000L;
```

Observe o `L`:

```java
8000000000L
```

Isso indica ao compilador que o literal deve ser tratado como `long`.

### Por que isso é necessário?

Por padrão, um literal inteiro é interpretado como `int` quando possível.

Por exemplo:

```java
long numero = 100;
```

funciona porque `100` cabe dentro de um `int`.

Entretanto:

```java
long numero = 8000000000;
```

não funciona.

Deve-se escrever:

```java
long numero = 8000000000L;
```

### Boa prática

Prefira utilizar `L` maiúsculo:

```java
1000L
```

em vez de:

```java
1000l
```

porque a letra `l` minúscula pode ser facilmente confundida com o número `1`.

---

# 8. Comparação dos tipos inteiros

| Tipo    | Tamanho |               Valor mínimo |              Valor máximo |
| ------- | ------: | -------------------------: | ------------------------: |
| `byte`  |  8 bits |                       -128 |                       127 |
| `short` | 16 bits |                    -32.768 |                    32.767 |
| `int`   | 32 bits |             -2.147.483.648 |             2.147.483.647 |
| `long`  | 64 bits | -9.223.372.036.854.775.808 | 9.223.372.036.854.775.807 |

Na maioria dos programas:

```java
int
```

será utilizado como padrão para números inteiros.

---

# 9. `float`

`float` é utilizado para representar números com casas decimais utilizando o padrão IEEE 754 de ponto flutuante.

Possui **32 bits** e aproximadamente **6 a 7 dígitos decimais significativos de precisão**.

Exemplo:

```java
float altura = 1.75F;
```

É necessário utilizar `F` ou `f`.

Por exemplo:

```java
float temperatura = 36.5F;
```

### Por que colocar `F`?

Porque Java considera um literal decimal como `double` por padrão.

Portanto:

```java
float numero = 10.5;
```

provoca erro.

Já:

```java
float numero = 10.5F;
```

funciona corretamente.

---

# 10. `double`

`double` também representa números em ponto flutuante.

Possui **64 bits** e aproximadamente **15 a 16 dígitos decimais significativos de precisão**.

É normalmente a escolha padrão para cálculos com valores fracionários.

Exemplo:

```java
double altura = 1.75;
```

Outro exemplo:

```java
double peso = 82.4;

double temperatura = 36.7;

double media = 9.25;
```

---

# 11. `float` x `double`

| Característica      |     `float` |      `double` |
| ------------------- | ----------: | ------------: |
| Tamanho             |     32 bits |       64 bits |
| Precisão aproximada | 6–7 dígitos | 15–16 dígitos |
| Literal             |     `10.5F` |        `10.5` |
| Uso geral           | menos comum |   muito comum |

Na maioria das situações, prefira:

```java
double
```

Exemplo:

```java
double nota = 9.5;
```

---

# 12. Atenção: `float` e `double` não possuem precisão decimal exata

Esse é um dos conceitos mais importantes para um programador Java iniciante.

Considere:

```java
double resultado = 0.1 + 0.2;

System.out.println(resultado);
```

O resultado normalmente será parecido com:

```text
0.30000000000000004
```

Isso acontece porque muitos números decimais não possuem representação binária exata usando ponto flutuante.

Portanto, valores `double` e `float` não devem ser tratados como representações decimais perfeitamente exatas.

---

# 13. Dinheiro: cuidado com `double`

Considere:

```java
double preco = 0.1;
double taxa = 0.2;

System.out.println(preco + taxa);
```

O resultado pode não ser exatamente:

```text
0.3
```

Em sistemas financeiros, normalmente é mais apropriado utilizar:

```java
BigDecimal
```

Exemplo:

```java
import java.math.BigDecimal;

public class Main {

    public static void main(String[] args) {

        BigDecimal valor1 = new BigDecimal("0.1");
        BigDecimal valor2 = new BigDecimal("0.2");

        BigDecimal resultado = valor1.add(valor2);

        System.out.println(resultado);
    }
}
```

Saída:

```text
0.3
```

Observe que `BigDecimal` **não é um tipo primitivo**.

É uma classe.

---

# 14. `char`

O tipo `char` representa uma unidade de código UTF-16.

Possui **16 bits**.

Exemplo:

```java
char letra = 'A';
```

Observe as aspas simples:

```java
'A'
```

Outro exemplo:

```java
char simbolo = '@';
```

Também podemos trabalhar com determinados caracteres Unicode:

```java
char letra = '\u0041';

System.out.println(letra);
```

Saída:

```text
A
```

---

# 15. `char` x `String`

Essa diferença é extremamente importante.

## `char`

Representa uma única unidade `char`:

```java
char letra = 'A';
```

Utiliza aspas simples:

```text
'A'
```

## `String`

Representa uma sequência de caracteres:

```java
String nome = "Victor";
```

Utiliza aspas duplas:

```text
"Victor"
```

Portanto:

```java
char letra = 'A';
String nome = "Ana";
```

Não são a mesma coisa.

---

# 16. `boolean`

`boolean` representa valores lógicos.

Possui apenas dois valores possíveis:

```java
true
```

ou:

```java
false
```

Exemplo:

```java
boolean ativo = true;
```

Outro:

```java
boolean usuarioLogado = false;
```

É frequentemente utilizado em condições:

```java
boolean maiorDeIdade = true;

if (maiorDeIdade) {
    System.out.println("Usuário é maior de idade.");
}
```

---

# 17. Expressões booleanas

Muitas vezes um `boolean` é resultado de uma comparação.

Exemplo:

```java
int idade = 36;

boolean maiorDeIdade = idade >= 18;

System.out.println(maiorDeIdade);
```

Saída:

```text
true
```

A expressão:

```java
idade >= 18
```

produz um valor booleano.

---

# 18. Operadores de comparação

Alguns operadores retornam `boolean`.

| Operador | Significado    |
| -------- | -------------- |
| `==`     | igual          |
| `!=`     | diferente      |
| `>`      | maior          |
| `<`      | menor          |
| `>=`     | maior ou igual |
| `<=`     | menor ou igual |

Exemplo:

```java
int idade = 36;

System.out.println(idade > 18);
System.out.println(idade == 36);
System.out.println(idade < 18);
```

Resultado:

```text
true
true
false
```

---

# 19. Resumo dos tipos primitivos

| Tipo      | Categoria | Exemplo                 |
| --------- | --------- | ----------------------- |
| `byte`    | inteiro   | `byte x = 100;`         |
| `short`   | inteiro   | `short x = 2000;`       |
| `int`     | inteiro   | `int x = 50000;`        |
| `long`    | inteiro   | `long x = 9000000000L;` |
| `float`   | decimal   | `float x = 10.5F;`      |
| `double`  | decimal   | `double x = 10.5;`      |
| `char`    | caractere | `char x = 'A';`         |
| `boolean` | lógico    | `boolean x = true;`     |

---

# 20. Valores literais

Um **literal** é um valor escrito diretamente no código.

Exemplo:

```java
int idade = 36;
```

O número:

```text
36
```

é um literal inteiro.

Outro:

```java
double altura = 1.75;
```

`1.75` é um literal de ponto flutuante.

---

# 21. Literais inteiros

Podemos escrever:

```java
int decimal = 100;
```

Também existem representações diferentes.

### Binário

```java
int numero = 0b1010;
```

`1010` em binário corresponde a:

```text
10
```

### Hexadecimal

```java
int numero = 0xFF;
```

Resultado:

```text
255
```

---

# 22. Separador `_` em números

Java permite utilizar `_` para melhorar a legibilidade.

Em vez de:

```java
int populacao = 1000000;
```

podemos escrever:

```java
int populacao = 1_000_000;
```

Os dois possuem exatamente o mesmo valor.

Também:

```java
long dinheiro = 10_000_000_000L;
```

O `_` é ignorado no valor numérico.

---

# 23. Operações matemáticas

Os principais operadores são:

| Operador | Operação         |
| -------- | ---------------- |
| `+`      | soma             |
| `-`      | subtração        |
| `*`      | multiplicação    |
| `/`      | divisão          |
| `%`      | resto da divisão |

Exemplo:

```java
int a = 10;
int b = 3;

System.out.println(a + b);
System.out.println(a - b);
System.out.println(a * b);
System.out.println(a / b);
System.out.println(a % b);
```

Resultado:

```text
13
7
30
3
1
```

---

# 24. Divisão entre inteiros

Observe:

```java
int a = 10;
int b = 3;

int resultado = a / b;
```

O resultado será:

```text
3
```

e não:

```text
3.3333
```

Isso acontece porque ambos os operandos são inteiros.

Se quisermos divisão decimal:

```java
double resultado = 10.0 / 3;
```

Agora teremos aproximadamente:

```text
3.3333333333333335
```

---

# 25. Promoção numérica

Durante operações matemáticas, Java pode converter automaticamente tipos menores.

Considere:

```java
byte a = 10;
byte b = 20;
```

Pode parecer que isso funcionaria:

```java
byte resultado = a + b;
```

Entretanto, ocorre erro.

Isso acontece porque, durante determinadas operações aritméticas, valores de tipos como:

```java
byte
short
char
```

são promovidos para:

```java
int
```

Então:

```java
a + b
```

produz um `int`.

Uma alternativa seria:

```java
int resultado = a + b;
```

---

# 26. Conversões implícitas

Java permite determinadas conversões automaticamente quando existe uma ampliação segura da capacidade numérica.

Exemplo:

```java
int numero = 100;

long numeroGrande = numero;
```

Isso funciona.

Podemos representar uma sequência comum de ampliação aproximadamente como:

```text
byte
 ↓
short
 ↓
int
 ↓
long
 ↓
float
 ↓
double
```

Isso é chamado frequentemente de:

**widening conversion**.

---

# 27. Conversão explícita — casting

Quando queremos converter um tipo de maior capacidade para outro potencialmente menor, normalmente precisamos utilizar um **cast**.

Exemplo:

```java
double numero = 10.8;

int inteiro = (int) numero;
```

Resultado:

```text
10
```

Observe:

```java
(int)
```

Isso é um cast.

---

# 28. Casting pode perder informação

Considere:

```java
double valor = 99.99;

int resultado = (int) valor;

System.out.println(resultado);
```

Resultado:

```text
99
```

A parte decimal foi descartada.

O casting **não faz arredondamento matemático**.

---

# 29. Overflow

Um tipo possui um limite máximo.

Considere:

```java
int numero = 2_147_483_647;
```

Esse é o maior valor de um `int`.

Agora:

```java
numero++;

System.out.println(numero);
```

O valor passa para:

```text
-2147483648
```

Isso é um exemplo de **overflow**.

O valor ultrapassou a capacidade representável pelo tipo.

---

# 30. Underflow em inteiros

Também podemos ultrapassar o limite inferior.

```java
int numero = -2_147_483_648;

numero--;

System.out.println(numero);
```

O resultado será:

```text
2147483647
```

---

# 31. Constantes com `final`

Podemos utilizar `final` quando uma variável não deverá receber outro valor depois de inicializada.

Exemplo:

```java
final double PI = 3.14159;
```

Depois disso:

```java
PI = 5;
```

provocará erro de compilação.

Convenção Java:

```java
final double TAXA_JUROS = 0.05;
```

Constantes geralmente utilizam letras maiúsculas e `_`.

---

# 32. Valores padrão

Existe uma diferença importante entre **atributos de uma classe** e **variáveis locais**.

Considere:

```java
public class Pessoa {

    int idade;
    boolean ativo;
}
```

Como são atributos de uma instância, Java fornece valores padrão.

| Tipo      | Valor padrão |
| --------- | ------------ |
| `byte`    | `0`          |
| `short`   | `0`          |
| `int`     | `0`          |
| `long`    | `0L`         |
| `float`   | `0.0F`       |
| `double`  | `0.0`        |
| `char`    | `'\u0000'`   |
| `boolean` | `false`      |

---

# 33. Variáveis locais não recebem valor automaticamente

Considere:

```java
public static void main(String[] args) {

    int idade;

    System.out.println(idade);
}
```

Isso gera erro.

Uma variável local precisa ser inicializada antes de ser utilizada:

```java
int idade = 36;

System.out.println(idade);
```

---

# 34. Classes wrapper

Cada tipo primitivo possui uma classe correspondente.

| Primitivo | Wrapper     |
| --------- | ----------- |
| `byte`    | `Byte`      |
| `short`   | `Short`     |
| `int`     | `Integer`   |
| `long`    | `Long`      |
| `float`   | `Float`     |
| `double`  | `Double`    |
| `char`    | `Character` |
| `boolean` | `Boolean`   |

Exemplo:

```java
int numero = 10;

Integer numeroObjeto = 10;
```

`int` é primitivo.

`Integer` é uma classe.

---

# 35. Por que wrappers existem?

Objetos são necessários em diversas APIs Java.

Por exemplo, coleções genéricas não armazenam tipos primitivos diretamente.

Isso não funciona:

```java
List<int> numeros;
```

Utilizamos:

```java
List<Integer> numeros;
```

Exemplo completo:

```java
import java.util.ArrayList;
import java.util.List;

public class Main {

    public static void main(String[] args) {

        List<Integer> numeros = new ArrayList<>();

        numeros.add(10);
        numeros.add(20);
        numeros.add(30);

        System.out.println(numeros);
    }
}
```

---

# 36. Autoboxing

Java consegue converter automaticamente um primitivo em seu wrapper correspondente.

Exemplo:

```java
int numero = 10;

Integer objeto = numero;
```

Essa transformação é chamada:

**autoboxing**.

Conceitualmente:

```text
int → Integer
```

---

# 37. Unboxing

Java também realiza a conversão contrária:

```java
Integer objeto = 10;

int numero = objeto;
```

Isso é chamado:

**unboxing**.

Conceitualmente:

```text
Integer → int
```

---

# 38. Primitivos não podem ser `null`

Isto não funciona:

```java
int idade = null;
```

Tipos primitivos sempre representam algum valor válido do seu domínio.

Por outro lado:

```java
Integer idade = null;
```

é permitido porque `Integer` é uma referência para objeto.

---

# 39. Perigo do unboxing com `null`

Considere:

```java
Integer idade = null;

int numero = idade;
```

O Java tentará realizar unboxing:

```text
Integer → int
```

Porém, como o objeto é `null`, ocorrerá:

```text
NullPointerException
```

Essa situação é comum em aplicações reais e merece atenção.

---

# 40. Exemplo integrado

```java
public class Usuario {

    public static void main(String[] args) {

        String nome = "Carlos";

        int idade = 30;

        double altura = 1.80;

        char categoria = 'A';

        boolean ativo = true;

        long codigo = 1_000_000_000L;

        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade);
        System.out.println("Altura: " + altura);
        System.out.println("Categoria: " + categoria);
        System.out.println("Ativo: " + ativo);
        System.out.println("Código: " + codigo);
    }
}
```

Observe que apenas:

```java
int
double
char
boolean
long
```

são tipos primitivos.

`String` não é.

---

# 41. Escolhendo o tipo adequado

Como regra inicial:

### Números inteiros

Use:

```java
int
```

Exemplo:

```java
int idade = 36;
```

Se o número puder ultrapassar o limite de `int`, considere:

```java
long
```

---

### Números com casas decimais

Normalmente:

```java
double
```

Exemplo:

```java
double altura = 1.75;
```

---

### Valores verdadeiro/falso

Use:

```java
boolean
```

Exemplo:

```java
boolean ativo = true;
```

---

### Caractere individual

Use:

```java
char
```

Exemplo:

```java
char generoClasse = 'A';
```

---

### Valores monetários

Evite confiar em `float` ou `double` quando a aplicação exigir precisão decimal financeira.

Considere:

```java
BigDecimal
```

---

# 42. Erros comuns de iniciantes

## Erro 1 — esquecer `F`

Errado:

```java
float altura = 1.75;
```

Correto:

```java
float altura = 1.75F;
```

---

## Erro 2 — esquecer `L`

Para valores grandes:

```java
long numero = 5_000_000_000L;
```

---

## Erro 3 — confundir `char` com `String`

Errado:

```java
char nome = "A";
```

Correto:

```java
char letra = 'A';
```

Ou:

```java
String nome = "A";
```

---

## Erro 4 — esperar decimal em divisão inteira

```java
int resultado = 5 / 2;
```

Resultado:

```text
2
```

Para obter:

```text
2.5
```

utilize:

```java
double resultado = 5.0 / 2;
```

---

## Erro 5 — utilizar `double` para dinheiro sem compreender as limitações

```java
double dinheiro = 0.1 + 0.2;
```

Pode produzir um valor binário aproximado.

Em sistemas financeiros, considere `BigDecimal`.

---

## Erro 6 — imaginar que `String` é primitivo

Não é:

```java
String nome = "Victor";
```

`String` é uma classe.

---

# 43. Mapa mental

```text
TIPOS DE DADOS EM JAVA
│
├── PRIMITIVOS
│
│   ├── INTEIROS
│   │   ├── byte
│   │   ├── short
│   │   ├── int
│   │   └── long
│   │
│   ├── PONTO FLUTUANTE
│   │   ├── float
│   │   └── double
│   │
│   ├── CARACTERE
│   │   └── char
│   │
│   └── LÓGICO
│       └── boolean
│
└── REFERÊNCIAS
    ├── String
    ├── arrays
    ├── classes
    ├── interfaces
    └── objetos
```

---

# 44. Exemplo prático: cadastro de produto

```java
public class Produto {

    public static void main(String[] args) {

        long codigo = 1000001L;

        String nome = "Notebook";

        int estoque = 20;

        double peso = 1.85;

        boolean disponivel = true;

        char categoria = 'I';

        System.out.println("Código: " + codigo);
        System.out.println("Produto: " + nome);
        System.out.println("Estoque: " + estoque);
        System.out.println("Peso: " + peso);
        System.out.println("Disponível: " + disponivel);
        System.out.println("Categoria: " + categoria);
    }
}
```

Classificação:

```text
codigo       → long
nome         → String
estoque      → int
peso         → double
disponivel   → boolean
categoria    → char
```

Observe novamente:

```text
String → não é primitivo
```

---

# 45. Exercícios

## Exercício 1

Escolha o tipo mais apropriado para representar:

1. Idade de uma pessoa
2. Salário de um funcionário em um exercício introdutório
3. Situação de cadastro ativo/inativo
4. Uma única letra
5. População mundial
6. Quantidade de produtos em estoque

---

## Exercício 2

O que será exibido?

```java
int a = 5;
int b = 2;

System.out.println(a / b);
```

---

## Exercício 3

Existe algum problema?

```java
float temperatura = 36.5;
```

Corrija o código.

---

## Exercício 4

Qual é a diferença entre:

```java
char letra = 'A';
```

e:

```java
String letra = "A";
```

---

## Exercício 5

Qual será o resultado?

```java
double numero = 15.9;

int resultado = (int) numero;

System.out.println(resultado);
```

---

## Exercício 6

Explique por que isto não funciona:

```java
byte a = 10;
byte b = 20;

byte resultado = a + b;
```

---

# 46. Respostas

### Exercício 1

Uma possível escolha seria:

```text
idade               → int
salário didático    → double
ativo/inativo       → boolean
letra                → char
população mundial   → long
estoque              → int
```

Em sistemas financeiros reais, valores monetários frequentemente devem ser tratados com `BigDecimal`, dependendo dos requisitos.

---

### Exercício 2

Resultado:

```text
2
```

Como ambos são `int`, temos divisão inteira.

---

### Exercício 3

Deve ser:

```java
float temperatura = 36.5F;
```

---

### Exercício 4

```java
char letra = 'A';
```

utiliza o tipo primitivo `char`.

Já:

```java
String letra = "A";
```

utiliza a classe `String`.

---

### Exercício 5

Resultado:

```text
15
```

O casting para `int` elimina a parte fracionária.

---

### Exercício 6

Porque a expressão:

```java
a + b
```

é promovida para `int`.

Portanto, podemos utilizar:

```java
int resultado = a + b;
```

---

# 47. Checklist de conhecimento

Ao terminar este conteúdo, você deve conseguir responder:

* O que é um tipo primitivo?
* Quantos tipos primitivos Java possui?
* Qual a diferença entre `int` e `long`?
* Qual a diferença entre `float` e `double`?
* Por que `float` utiliza `F`?
* Por que determinados valores `long` utilizam `L`?
* Qual a diferença entre `char` e `String`?
* Para que serve `boolean`?
* O que é casting?
* O que é promoção numérica?
* O que é overflow?
* Por que divisão entre dois `int` produz um inteiro?
* Por que `double` pode gerar problemas com valores monetários?
* O que são classes wrapper?
* O que são autoboxing e unboxing?
* Por que um primitivo não pode ser `null`?

---

# 48. Resumo final

Java possui oito tipos primitivos:

```text
byte
short
int
long
float
double
char
boolean
```

Para números inteiros, normalmente utilizamos:

```java
int
```

Para números inteiros muito grandes:

```java
long
```

Para números com casas decimais, normalmente:

```java
double
```

Para valores lógicos:

```java
boolean
```

Para um caractere:

```java
char
```

Os tipos primitivos são fundamentais porque praticamente todos os conceitos posteriores da programação Java — operadores, estruturas condicionais, repetições, métodos, arrays, objetos e algoritmos — dependem da compreensão correta sobre como os dados são representados e manipulados.
