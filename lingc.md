# 📘 Principais Comandos da Linguagem C

> Guia de referência rápida para desenvolvimento em C  
> Disciplina: Algoritmos e Práticas de Programação

---

## 📦 1. Bibliotecas e Diretivas

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 1 | `#include` | Importa uma biblioteca | `#include <stdio.h>` |
| 2 | `#define` | Cria uma constante ou macro | `#define PI 3.14` |
| 3 | `#ifdef / #endif` | Compilação condicional | `#ifdef _WIN32` |

---

## 🔢 2. Tipos de Variáveis

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 4 | `int` | Número inteiro | `int idade = 20;` |
| 5 | `float` | Número decimal simples | `float preco = 9.99;` |
| 6 | `double` | Decimal de alta precisão | `double pi = 3.14159265;` |
| 7 | `char` | Um caractere ou string | `char letra = 'A';` |
| 8 | `void` | Sem retorno / sem tipo | `void minhaFuncao()` |
| 9 | `const` | Variável que não pode mudar | `const int MAX = 100;` |

---

## 📥 3. Entrada e Saída

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 10 | `printf()` | Exibe texto no terminal | `printf("Ola %s", nome);` |
| 11 | `scanf()` | Lê entrada do usuário | `scanf("%d", &idade);` |
| 12 | `getchar()` | Lê um único caractere | `char c = getchar();` |
| 13 | `putchar()` | Exibe um único caractere | `putchar('A');` |
| 14 | `fgets()` | Lê uma linha inteira com segurança | `fgets(nome, 50, stdin);` |

---

## 🔀 4. Estruturas de Decisão

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 15 | `if` | Executa se condição for verdadeira | `if (x > 0)` |
| 16 | `else` | Executa se `if` for falso | `else { ... }` |
| 17 | `else if` | Testa outra condição | `else if (x == 0)` |
| 18 | `switch` | Compara valor com vários casos | `switch(opcao)` |
| 19 | `case` | Define cada caso do switch | `case 1: ...` |
| 20 | `default` | Caso padrão do switch | `default: ...` |
| 21 | `break` | Sai do switch ou loop | `break;` |

```c
// Exemplo completo de switch
switch(opcao) {
    case 1:  printf("Um");   break;
    case 2:  printf("Dois"); break;
    default: printf("Outro");
}
```

---

## 🔁 5. Estruturas de Repetição

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 22 | `for` | Loop com contador definido | `for(i=0; i<10; i++)` |
| 23 | `while` | Loop enquanto condição for verdadeira | `while(x > 0)` |
| 24 | `do...while` | Executa ao menos uma vez | `do { } while(x > 0);` |
| 25 | `continue` | Pula para próxima iteração | `continue;` |

```c
// for
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}

// while
while (x > 0) {
    x--;
}

// do...while
do {
    scanf("%d", &opcao);
} while (opcao != 0);
```

---

## 🧮 6. Operadores

| # | Operador | O que faz | Exemplo |
|---|----------|-----------|---------|
| 26 | `+ - * /` | Aritméticos básicos | `x = a + b;` |
| 27 | `%` | Resto da divisão | `x = 10 % 3; // = 1` |
| 28 | `== != > < >= <=` | Relacionais (comparação) | `if (a == b)` |
| 29 | `&& \|\| !` | Lógicos (E, OU, NÃO) | `if (a > 0 && b > 0)` |
| 30 | `++ --` | Incremento e decremento | `i++; // i = i + 1` |
| 31 | `=` | Atribuição | `x = 10;` |
| 32 | `+= -= *= /=` | Atribuição composta | `x += 5; // x = x + 5` |

```c
// Exemplos de operadores
int a = 10, b = 3;
printf("%d", a + b);   // 13
printf("%d", a % b);   // 1
printf("%d", a > b);   // 1 (verdadeiro)
printf("%d", a == b);  // 0 (falso)
```

---

## 🏗️ 7. Funções

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 33 | `return` | Retorna valor de uma função | `return 0;` |
| 34 | `typedef` | Cria apelido para um tipo | `typedef int Inteiro;` |
| 35 | `struct` | Cria estrutura de dados | `struct Carro { ... };` |

```c
// Exemplo de struct com typedef
typedef struct {
    char nome[50];
    int  idade;
    float salario;
} Funcionario;

Funcionario f1;
f1.idade = 30;
```

---

## 💾 8. Memória e Ponteiros

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 36 | `*` | Declara ou acessa ponteiro | `int *p;` |
| 37 | `&` | Endereço de memória | `p = &x;` |
| 38 | `malloc()` | Aloca memória dinamicamente | `malloc(sizeof(int))` |
| 39 | `free()` | Libera memória alocada | `free(p);` |
| 40 | `sizeof()` | Tamanho em bytes de um tipo | `sizeof(int) // = 4` |

```c
// Exemplo de ponteiro
int x = 10;
int *p = &x;
printf("%d", *p);  // imprime 10

// Alocação dinâmica
int *vetor = malloc(5 * sizeof(int));
free(vetor);
```

---

## 📁 9. Arquivos

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 41 | `fopen()` | Abre um arquivo | `fopen("dados.txt", "r")` |
| 42 | `fclose()` | Fecha um arquivo | `fclose(arquivo);` |
| 43 | `fprintf()` | Escreve em arquivo | `fprintf(f, "texto");` |
| 44 | `fscanf()` | Lê de um arquivo | `fscanf(f, "%d", &x);` |

```c
// Escrever em arquivo
FILE *f = fopen("log.txt", "w");
fprintf(f, "Velocidade: %.2f\n", 120.5);
fclose(f);

// Modos de abertura:
// "r"  → leitura
// "w"  → escrita (apaga o existente)
// "a"  → append (adiciona ao final)
```

---

## 🧵 10. Strings (string.h)

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 45 | `strlen()` | Tamanho de uma string | `strlen("Ola") // = 3` |
| 46 | `strcpy()` | Copia uma string | `strcpy(dest, origem);` |
| 47 | `strcmp()` | Compara duas strings | `strcmp(a, b) == 0` |
| 48 | `strcat()` | Concatena strings | `strcat(a, b);` |

```c
#include <string.h>

char nome[50] = "Carro";
printf("%d", strlen(nome));       // 5
strcpy(nome, "Simulador");        // nome = "Simulador"
printf("%d", strcmp("a","a"));    // 0 = iguais
strcat(nome, " C");               // "Simulador C"
```

---

## 🎲 11. Matemática e Aleatório (math.h / stdlib.h)

| # | Comando | O que faz | Exemplo |
|---|---------|-----------|---------|
| 49 | `rand()` | Gera número aleatório | `rand() % 100` |
| 50 | `srand()` | Define semente aleatória | `srand(time(NULL));` |
| 51 | `sqrt()` | Raiz quadrada | `sqrt(25.0) // = 5` |
| 52 | `pow()` | Potência | `pow(2, 3) // = 8` |
| 53 | `abs()` | Valor absoluto inteiro | `abs(-5) // = 5` |
| 54 | `fabs()` | Valor absoluto float | `fabs(-3.14)` |

```c
#include <math.h>
#include <stdlib.h>
#include <time.h>

srand(time(NULL));
int aleatorio = rand() % 100;   // 0 a 99
double raiz   = sqrt(49.0);     // 7.0
double pot    = pow(2.0, 8.0);  // 256.0
```

> ⚠️ Compilar com `-lm` ao usar math.h:
> ```bash
> gcc programa.c -o programa -lm
> ```

---

## 💡 12. Formatadores do printf / scanf

```c
%d    → inteiro (int)
%f    → decimal (float)
%lf   → decimal longo (double)
%c    → caractere (char)
%s    → string (char[])
%p    → endereço de ponteiro
%.2f  → float com 2 casas decimais
%05d  → inteiro com zeros à esquerda
%10s  → string alinhada à direita
\n    → quebra de linha
\t    → tabulação (tab)
\\    → barra invertida literal
\"    → aspas dentro de string
```

---

## 🖥️ 13. Comandos de Compilação (Terminal)

```bash
# Compilar um arquivo simples
gcc programa.c -o programa

# Compilar com math.h
gcc programa.c -o programa -lm

# Executar no Linux/Mac
./programa

# Executar no Windows
programa.exe

# Ver erros detalhados
gcc -Wall programa.c -o programa
```

---

## ✅ Checklist de Elementos Obrigatórios

- [ ] `#include` e `#define`
- [ ] Variáveis com `int`, `float`, `char`
- [ ] `const` para constantes
- [ ] `printf` e `scanf`
- [ ] `if`, `else if`, `else`
- [ ] `switch / case / default`
- [ ] `for`, `while`, `do...while`
- [ ] `break` e `continue`
- [ ] `struct` e `typedef`
- [ ] Operadores aritméticos, relacionais e lógicos
- [ ] Vetores (`int vetor[10]`)
- [ ] Funções com `return`
- [ ] Pelo menos uma função além do `main()`

---

*Referência criada para a disciplina de Algoritmos e Práticas de Programação*
