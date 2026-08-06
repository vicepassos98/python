# Introdução ao Python

## O que é Python?

O **Python** é uma linguagem de programação entre milhares que existem atualmente, como **Java**, **JavaScript**, **C**, **C++** e **HTML**.

Ela não é a linguagem mais utilizada, nem a mais nova ou a mais antiga. O motivo de utilizarmos Python neste curso é principalmente por dois fatores:

- **Acessibilidade:** sua sintaxe é simples e fácil de aprender.
- **Versatilidade:** permite criar praticamente qualquer tipo de programa.

A linguagem foi criada em **1991** e seu nome é uma homenagem ao grupo de humor britânico **Monty Python**. Ela foi desenvolvida tendo como base a linguagem **C** e, atualmente, é mantida pela **Python Software Foundation**, uma organização sem fins lucrativos.

O Python é totalmente gratuito.

---

## Onde o Python é utilizado?

O Python possui inúmeras aplicações, entre elas:

- 📊 Análise e visualização de dados;
- 🤖 Machine Learning (um ramo da Inteligência Artificial focado no aprendizado de padrões);
- 💻 Desenvolvimento de softwares;
- 🌐 Desenvolvimento Web (Back-end);
- ⚙️ Automação de tarefas.

> Um dos livros mais famosos sobre automação com Python chama-se [**Automate the Boring Stuff with Python**](https://drive.google.com/file/d/1bQufTCf3gcGgWgOzPM-qzpeKo-LJ1bzN/view?usp=sharing).
> Outra bibliografia que você pode usar como apoio e para avançar mais é o livro ["Pense em Python"](https://penseallen.github.io/PensePython2e/)

Neste curso, nosso foco será a criação de pequenos programas e o uso do Python para resolver problemas matemáticos e estatísticos simples.

---

# O que é um programa?

Um programa é uma aplicação como qualquer outra que você utiliza no dia a dia:

- Calculadora;
- Agenda;
- Navegador;
- Instagram;
- Excel.

Todos são programas, mas podem ter sido desenvolvidos utilizando linguagens diferentes, como:

- Python
- Java
- JavaScript
- C
- C++

Apesar disso, praticamente todos os programas possuem cinco características em comum.

## 1. Entrada (Input)

O usuário fornece informações ao programa por meio de:

- teclado;
- mouse;
- tela do celular;
- câmera;
- microfone.

## 2. Saída (Output)

O programa responde às informações recebidas exibindo resultados na tela, emitindo sons, gravando arquivos, enviando dados pela internet etc.

## 3. Processamento

Todo programa realiza operações matemáticas e lógicas para produzir seus resultados.

## 4. Execução condicional

É o famoso **SE** (ou **SES**, no Excel).

O programa verifica uma condição e executa determinadas ações somente quando essa condição é verdadeira.

## 5. Repetição

Um computador consegue repetir automaticamente um mesmo processo milhares ou milhões de vezes.

---

## Linguagem humana × linguagem computacional

A linguagem humana permite:

- interpretações;
- ambiguidades;
- humor;
- ironia;
- sarcasmo.

Já a linguagem computacional precisa ser extremamente objetiva.

O computador interpreta exatamente aquilo que foi escrito. Por isso, cada caractere, espaço e símbolo possui importância.

---

# Como começar a programar em Python?

O Python é gratuito e pode ser baixado em:

https://python.org

Ao instalar o Python, são instalados diversos componentes importantes:

- O interpretador da linguagem Python;
- O terminal (Prompt), utilizado para executar comandos e instalar bibliotecas;
- O IDLE, editor oficial do Python.

Neste curso, utilizaremos o **Jupyter Web**, um ambiente baseado em células.

Sua principal vantagem é permitir executar um pequeno trecho de código por vez, facilitando o aprendizado, os testes e a identificação de erros.

---

# Nosso primeiro programa

Crie um novo notebook e digite:

```python
print("O horário de retorno do intervalo é 15 horas e 15 minutos")
```

Ao executar a célula, o Python exibirá exatamente o texto que está entre aspas.

Observe que:

- `print()` é uma função;
- os parênteses indicam os parâmetros da função;
- as aspas indicam que o conteúdo é um texto.

---

# Operadores aritméticos

Assim como no Excel, podemos realizar operações matemáticas.

| Operador | Significado |
|-----------|-------------|
| `+` | Adição |
| `-` | Subtração |
| `*` | Multiplicação |
| `/` | Divisão |
| `**` | Exponenciação |

Experimente:

```python
25 + 18
```

```python
8 * 5
```

```python
2 ** 10
```

---

# Valores e tipos

No Python existem diferentes tipos de valores.

Execute:

```python
55 + 12
```

Depois:

```python
134 / 2
```

Os dois resultados representam o número **67**, mas aparecem de maneiras diferentes.

```text
55 + 12 → 67
```

Esse resultado é do tipo:

- `int` (Integer) → número inteiro.

Já:

```text
134 / 2 → 67.0
```

é do tipo:

- `float` → número decimal.

Outro tipo muito importante é o texto.

```python
print("O horário de retorno é 15h15")
```

Esse valor pertence ao tipo:

- `str` (String), que representa uma sequência de caracteres.

---

# Bugs, debugging e frustração

Você vai errar.

Não é uma possibilidade: é uma certeza.

Erros de programação são completamente normais. Você pode esquecer uma aspas, um parêntese, digitar uma palavra incorretamente ou cometer um erro lógico.

Isso faz parte do aprendizado.

Encontrar e corrigir esses erros é chamado de **debugging**.

Um erro em um programa é conhecido como **bug**.

No começo, a maioria dos bugs será causada por erros de digitação. Com o tempo, eles passarão a envolver problemas de lógica, organização do código e funcionamento do programa.

Todo programador passa por isso.

---

# Variáveis

Digite:

```python
texto = "Hoje o dia está ensolarado e quente"
v = 42
pi = 3.14159265
```

Acabamos de criar três variáveis.

Cada variável armazena uma informação que poderá ser utilizada posteriormente.

Experimente:

```python
print(texto)
```

O Python imprimirá o conteúdo armazenado na variável.

Agora tente:

```python
print(TEXTO)
```

Perceba que ocorre um erro.

O Python diferencia letras maiúsculas e minúsculas.

Assim, estas são variáveis diferentes:

- `texto`
- `Texto`
- `TEXTO`
- `tEXTO`

---

# Expressões

Também podemos utilizar variáveis em operações matemáticas.

Experimente:

```python
25 + v
```

```python
pi * v
```

O Python respeita a prioridade das operações matemáticas:

1. Parênteses
2. Exponenciação
3. Multiplicação e divisão
4. Soma e subtração

Quando quiser alterar essa ordem, utilize parênteses.

Exemplo:

```python
(10 + 5) * 3
```

---

# Strings também são valores

Crie duas variáveis:

```python
fruta1 = "laranja"
fruta2 = "banana"
```

Agora faça:

```python
fruta1 + fruta2
```

O resultado será:

```text
laranjabanana
```

Nesse caso, o operador `+` não realiza uma soma.

Ele apenas **concatena** (une) os textos.

Isso acontece porque ambos os valores são do tipo `str`.

