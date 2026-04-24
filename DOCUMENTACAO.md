# 📖 Guia de Documentação - Praticando C

Este documento estabelece o padrão de documentação para todos os arquivos do repositório **praticando-C**.

---

## 1️⃣ Estrutura de Um Arquivo C Bem Documentado

```c
/*
 * ============================================================================
 * Nome do Arquivo: nome_do_arquivo.c
 * Descrição: Descrição clara e concisa do que o programa faz
 * 
 * Autor: Nome do autor
 * Data: DD/MM/YYYY
 * Versão: 1.0
 * 
 * Conceitos Abordados:
 *   - Conceito 1
 *   - Conceito 2
 *   - Conceito 3
 * 
 * Entrada: Descrever que tipo de entrada é esperada
 * Saída: Descrever o resultado/output esperado
 * 
 * Exemplo de Uso:
 *   Entrada: 5
 *   Saída: 120
 * ============================================================================
 */

#include <stdio.h>
#include <stdlib.h>

/* Função: descricao_funcao
 * Descrição: O que a função faz
 * 
 * Parâmetros:
 *   - param1 (int): Descrição do primeiro parâmetro
 *   - param2 (float): Descrição do segundo parâmetro
 * 
 * Retorno: int - Descrição do valor retornado
 *                (ou void se a função não retorna nada)
 * 
 * Exemplo:
 *   int resultado = funcao_exemplo(10, 2.5);
 *   printf("Resultado: %d\n", resultado);
 */
int funcao_exemplo(int param1, float param2)
{
    // Inicializar variáveis
    int resultado = 0;
    
    // Lógica principal
    resultado = param1 * (int)param2;
    
    return resultado;
}

int main()
{
    int a, b;
    
    // Solicitar entrada do usuário
    printf("Digite um número: ");
    scanf("%d", &a);
    
    // Processar dados
    b = funcao_exemplo(a, 2.0);
    
    // Exibir resultado
    printf("Resultado: %d\n", b);
    
    return 0;
}
```

---

## 2️⃣ Padrão de Comentários

### Cabeçalho de Arquivo
```c
/*
 * ============================================================================
 * Nome do Arquivo: basico.c
 * Descrição: Programa que realiza operações aritméticas básicas
 * 
 * Conceitos: Variáveis, scanf, printf, operadores aritméticos
 * ============================================================================
 */
```

### Comentário de Função
```c
/* Função: somar
 * Descrição: Soma dois números inteiros
 * Parâmetros: a (int), b (int)
 * Retorno: int - A soma de a + b
 */
int somar(int a, int b)
{
    return a + b;
}
```

### Comentários em Linhas Complexas
```c
// Converter para inteiro e multiplicar por 100
int percentual = (int)(valor * 100);

// Verificar se o número é divisível por 3
if (numero % 3 == 0)
    printf("Divisível por 3\n");
```

### Comentários de Variáveis Importantes
```c
// Armazena o maior valor encontrado
int maior = 0;

// Contador para o loop de preenchimento
int i = 0;
```

---

## 3️⃣ Padrão de Nomes

### Variáveis
- Use nomes descritivos em **minúsculas**
- Separe palavras com underscore `_`

```c
int numero_maior;        // ✅ Bom
int maior;              // ✅ Aceitável
int n;                  // ❌ Evitar (muito genérico)
int nm;                 // ❌ Evitar (abreviação confusa)
```

### Funções
- Use nomes descritivos em **minúsculas**
- Use verbos que descrevem a ação

```c
int calcular_media(int n1, int n2);    // ✅ Bom
void preencher_vetor(int v[], int n);  // ✅ Bom
int calc(int a, int b);                // ❌ Evitar (abreviado)
```

### Constantes
- Use **MAIÚSCULAS**

```c
#define PI 3.14159
#define TAM_VETOR 100
#define DESCONTO_PERCENTUAL 20
```

---

## 4️⃣ Estrutura de Indentação

```c
#include <stdio.h>

int main()
{
    int x = 0;
    
    // Usar 4 espaços ou 1 tab por nível de indentação
    if (x > 0)
    {
        printf("Positivo\n");
    }
    else if (x < 0)
    {
        printf("Negativo\n");
    }
    else
    {
        printf("Zero\n");
    }
    
    // Loop com indentação adequada
    for (int i = 0; i < 5; i++)
    {
        printf("%d ", i);
    }
    
    return 0;
}
```

---

## 5️⃣ Documentação de Estruturas e Arrays

```c
/* Array de inteiros que armazena os preços dos produtos
 * Tamanho máximo: 100 elementos
 */
int precos[100];

/* Vetor para armazenar nomes dos estudantes
 * Índice 0: primeiro estudante
 * Índice n-1: último estudante
 */
char nomes[50][50];

/* Matriz 3x3 para operações matemáticas
 * linha 0: números da primeira linha
 * linha 1: números da segunda linha
 * linha 2: números da terceira linha
 */
int matriz[3][3];
```

---

## 6️⃣ Exemplo Completo Documentado

```c
/*
 * ============================================================================
 * Nome do Arquivo: maiortrs.c
 * Descrição: Encontra o maior valor entre três números inteiros
 * 
 * Conceitos: Funções, condicionais, parâmetros, retorno
 * 
 * Entrada: Três números inteiros via scanf
 * Saída: O maior número entre os três
 * 
 * Exemplo:
 *   Entrada: 10 25 15
 *   Saída: O maior é: 25
 * ============================================================================
 */

#include <stdio.h>
#include <stdlib.h>

/* Função: maior
 * Descrição: Compara três números inteiros e retorna o maior
 * 
 * Parâmetros:
 *   - a (int): Primeiro número
 *   - b (int): Segundo número
 *   - c (int): Terceiro número
 * 
 * Retorno: int - O maior valor entre a, b e c
 * 
 * Lógica:
 *   1. Verifica se 'a' é maior que 'b'
 *   2. Se sim, verifica se 'a' é maior que 'c'
 *   3. Se não, continua com 'b' ou 'c'
 */
int maior(int a, int b, int c)
{
    // Se a é maior que b, comparar a com c
    if (a > b)
    {
        if (a > c)
            return (a);
    }
    // Se b é maior que c, retornar b
    else
    {
        if (b > c)
            return (b);
    }
    
    // Caso contrário, c é o maior
    return (c);
}

int main()
{
    int w, x, y, z;
    
    // Solicitar os três números
    printf("\nEntre com o primeiro numero: ");
    scanf("%d", &w);
    
    printf("\nEntre com o segundo numero: ");
    scanf("%d", &x);
    
    printf("\nEntre com o terceiro numero: ");
    scanf("%d", &y);
    
    // Chamar função e armazenar resultado
    z = maior(w, x, y);
    
    // Exibir resultado
    printf("\nO maior eh: %d\n", z);
    
    return 0;
}
```

---

## 7️⃣ Checklist de Documentação

Antes de fazer commit, verifique:

- [ ] Cabeçalho do arquivo está presente e completo
- [ ] Todas as funções têm documentação
- [ ] Variáveis importantes têm comentários explicativos
- [ ] Linhas complexas possuem explicação
- [ ] Nomes de variáveis são descritivos
- [ ] Indentação está consistente
- [ ] Sem código comentado desnecessário
- [ ] Programa compila sem erros
- [ ] Programa executa conforme esperado

---

## 8️⃣ Dicas Finais

✅ **Faça:**
- Use português para comentários
- Deixe uma linha em branco entre funções
- Use espaços ao redor de operadores: `a = b + c`
- Documente a intenção, não o óbvio

❌ **Evite:**
- Comentários óbvios: `i = i + 1; // incrementar i`
- Código comentado: remova em vez de comentar
- Variáveis genéricas: `x`, `y`, `z`
- Funções muito longas (máximo 50 linhas)

---

**Versão:** 1.0  
**Última atualização:** 24 de abril de 2026
