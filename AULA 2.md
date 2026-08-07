# Aula 2 — Entrada de dados e condicionais

Na aula anterior aprendemos os três principais tipos de valores do Python:

- `int` — números inteiros;
- `float` — números decimais;
- `str` — textos (strings).

Também aprendemos a:

- realizar operações matemáticas;
- criar variáveis;
- utilizar a função `print()`.

Nesta aula vamos aprender como interagir com o usuário utilizando **entradas de dados** e **condicionais**.

---

# Mesclando variáveis e textos (f-strings)

Muitas vezes queremos exibir um texto junto com o valor de uma variável.

Para isso utilizamos as **f-strings**.

Uma *f-string* é apenas uma forma de escrever um texto que permite inserir variáveis diretamente dentro da mensagem.

Basta colocar a letra **`f`** antes das aspas.

Dentro do texto, toda variável deve ficar entre **chaves `{}`**.

## Exemplo

Na primeira célula do notebook, escreva:

```python
nome = "Seu Nome"      # Substitua pelo seu nome
idade = 18             # Digite apenas o número
```

Execute a célula com **Ctrl + Alt + Enter**.

Na célula seguinte, escreva:

```python
print(f"Bom dia, {nome}! Como você está? Pelos meus cálculos você tem {idade} anos.")
```

O resultado será semelhante a:

```text
Bom dia, João! Como você está? Pelos meus cálculos você tem 18 anos.
```

---

## Símbolos importantes

| Símbolo | Nome |
|---------|------|
| `( )` | Parênteses |
| `{ }` | Chaves |
| `[ ]` | Colchetes |

---

# Input

**Input** significa **entrada de dados**.

É a forma que o programa utiliza para receber informações do usuário.

Com essas informações, o programa pode produzir resultados diferentes.

Vamos criar uma nova versão do nosso programa.

Agora o usuário informará seu próprio nome e sua idade.

```python
NOME = input("Insira seu nome, por obséquio: ")
```

Quando executar a célula, aparecerá uma caixa para digitar o nome.

Agora peça também a idade:

```python
IDADE = int(input("Insira sua idade: "))
```

Observe que utilizamos:

```python
int(...)
```

Isso faz com que a informação digitada seja convertida para um número inteiro.

Agora podemos utilizar novamente uma *f-string*:

```python
print(f"Bom dia, {nome}! Como você está? Pelos meus cálculos você tem {idade} anos.")
```

---

# Condicionais

As condicionais permitem que um programa tome decisões.

Dependendo do valor de uma variável ou da resposta do usuário, o programa poderá executar comandos diferentes.

No Python utilizamos principalmente quatro estruturas:

| Palavra | Significado |
|----------|-------------|
| `if` | Se |
| `elif` | Senão, se... |
| `else` | Caso contrário |
| `not` | Não |

---

# Operadores de comparação

As condicionais normalmente utilizam operadores de comparação.

| Operador | Significado |
|-----------|-------------|
| `==` | Igual a |
| `!=` | Diferente de |
| `>` | Maior que |
| `<` | Menor que |
| `>=` | Maior ou igual a |
| `<=` | Menor ou igual a |

---

# Exercício 1 — Explorando os operadores de comparação

Até agora aprendemos diversos operadores de comparação.

Antes de utilizá-los em estruturas condicionais, vamos observar como eles funcionam.

Crie as seguintes variáveis:

```python
a = 15
b = 20
```

Agora execute, **uma por vez**, as expressões abaixo:

```python
a == b
```

```python
a != b
```

```python
a > b
```

```python
a < b
```

```python
a >= b
```

```python
a <= b
```

Observe que o Python responde apenas com dois possíveis valores:

- `True` → Verdadeiro
- `False` → Falso

Esses dois valores representam o resultado de uma comparação lógica.

Experimente alterar os valores de `a` e `b` e execute novamente as comparações.

> **Desafio:** descubra uma combinação de valores para que `a >= b` retorne `True`.

---

# Exercício 2 — Comparando a idade do usuário

Agora vamos realizar comparações utilizando uma informação fornecida pelo usuário.

Primeiro, peça a idade:

```python
idade = int(input("Digite sua idade: "))
```

Em seguida, execute cada uma das comparações abaixo:

```python
idade >= 18
```

```python
idade < 18
```

```python
idade == 30
```

```python
idade != 50
```

Altere a idade digitada algumas vezes e observe como os resultados mudam.

Perceba que cada comparação sempre retorna apenas um dos dois valores possíveis:

- `True`
- `False`

Esses valores serão muito importantes na próxima etapa, quando utilizarmos estruturas condicionais (`if`, `elif` e `else`).

> **Desafio:** experimente criar outras comparações, como:
>
> ```python
> idade > 60
> ```
>
> ```python
> idade <= 12
> ```
>
> Tente prever o resultado antes de executar cada expressão.


# Nosso terceiro programa

Vamos criar uma nova versão do programa.

Primeiro, pergunte ao usuário se ele deseja conhecer uma previsão do futuro.

```python
prev = input("Quer que eu fale sobre seu futuro? (S/N): ")
```

Agora utilizaremos uma estrutura condicional.

```python
if prev == "S":
    futuro = idade + 100
    print(f"Daqui a 100 anos você terá {futuro} anos de idade.")

elif prev == "N":
    print("Que pena! A previsão era bombástica.")

else:
    print("Digite apenas S ou N em letras maiúsculas.")
```

---

# Entendendo a indentação

Observe que algumas linhas ficaram mais para a direita.

Esse recuo é chamado de **indentação**.

No Python, a indentação é obrigatória.

Ela indica quais comandos pertencem a cada condição.

Por exemplo:

```python
if prev == "S":
    futuro = idade + 100
    print(f"Daqui a 100 anos você terá {futuro} anos.")
```

As duas linhas recuadas só serão executadas se a condição for verdadeira.

> **Importante:** utilize sempre a tecla **Tab** para criar a indentação. Evite utilizar vários espaços manualmente, pois isso pode causar erros em programas maiores.

---

# Resumo da aula

Ao final desta aula você aprendeu:

- utilizar `input()` para receber informações do usuário;
- converter textos para números com `int()`;
- utilizar **f-strings** para combinar textos e variáveis;
- criar decisões utilizando `if`, `elif` e `else`;
- comparar valores utilizando operadores lógicos;
- compreender a importância da indentação no Python.
