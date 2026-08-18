# Aula 7.5 — Revisão: Juntando as Peças

Até agora aprendemos vários conceitos diferentes de Python.

Nesta aula não vamos aprender uma grande função nova. A ideia é **revisar e combinar os conteúdos que já vimos**.

Até aqui aprendemos:

* `print()` → mostrar informações;
* variáveis → armazenar informações;
* `int`, `float` e `str` → tipos de valores;
* operadores matemáticos;
* `input()` → receber informações;
* `if`, `elif` e `else` → tomar decisões;
* `while` → repetir um processo;
* `for` → repetir processos uma quantidade determinada de vezes;
* `break` → interromper um loop;
* `continue` → voltar para o início do loop;
* listas → armazenar vários valores;
* `.append()` → adicionar elementos;
* `.remove()` → remover elementos;
* `.clear()` → limpar uma lista;
* `len()` → descobrir o tamanho de uma lista;
* `enumerate()` → percorrer uma lista mantendo sua numeração;
* listas paralelas → relacionar informações por posição;
* dicionários → organizar informações através de chaves.

O objetivo de hoje é descobrir como juntar todas essas ferramentas para criar programas completos.

---

# Aquecimento

Antes dos programas maiores, vamos fazer alguns exercícios rápidos.

## Exercício 1 — Positivo ou negativo

Crie um programa para informar se o número é:

* positivo;
* negativo;
* zero.

---

## Exercício 2 — Contagem

Utilize um `for` para imprimir os números de 1 até 10.

Depois modifique o programa para imprimir somente os números pares.

---

## Exercício 3 — Lista

Crie uma lista chamada `nomes`.

Adicione cinco nomes utilizando `.append()`.

Depois utilize um `for` para mostrar todos os nomes.

---
## Programa 4 - Amor ao próximo
crie um programa que permita que seu colega mande uma mensagem para você
---

## Exercício 5 — Contador regressivo

Utilizando um `for`, faça uma contagem regressiva:

```text
10
9
8
7
6
5
4
3
2
1

BOOM!
```

### Desafio

Faça o usuário escolher de onde a contagem deve começar.

Exemplo:

```text
Digite o número inicial: 5

5
4
3
2
1

BOOM!
```

---

## Exercício 6 — Somando números

Peça ao usuário **5 números** e calcule a soma deles.

### Dica

Crie uma variável para armazenar a soma:

```python
soma = 0
```

Depois utilize um `for` para repetir a entrada cinco vezes.

### Desafio

Além da soma, mostre a média dos números.

---

## Exercício 7 — Qual é o maior?

Peça ao usuário cinco números e descubra qual foi o maior.

### Desafio 1

Tente resolver utilizando apenas `if` e variáveis.

### Desafio 2

Depois tente resolver utilizando uma lista e a função:

```python
max()
```

> Existem várias maneiras de resolver o mesmo problema em programação. Nem sempre a primeira solução é a melhor solução.

---

## Exercício 8 — Lista de compras

Crie uma lista vazia:

```python
compras = []
```

Peça ao usuário **5 produtos** e adicione todos à lista.

Depois mostre a lista:

```text
=== LISTA DE COMPRAS ===

1 - Arroz
2 - Feijão
3 - Café
4 - Leite
5 - Macarrão
```

### Você provavelmente precisará utilizar:

- `input()`
- `.append()`
- `for`
- `enumerate()`

---

## Exercício 9 — Procurando na lista

Utilize a lista de compras criada anteriormente.

Peça ao usuário para informar um produto e verifique se ele está cadastrado.

Se estiver:

```text
Produto encontrado!
```

Caso contrário:

```text
Produto não encontrado.
```

### Dica

Podemos verificar se um elemento está dentro de uma lista utilizando:

```python
if produto in compras:
```

---

## Exercício 10 — Boletim rápido

Crie duas listas:

```python
alunos = ["Ana", "João", "Carlos", "Maria"]

notas = [8, 5, 9, 4]
```

Utilize um `for` para mostrar:

```text
Ana - 8 - APROVADA
João - 5 - APROVADO
Carlos - 9 - APROVADO
Maria - 4 - REPROVADA
```

Considere aprovado o aluno com nota maior ou igual a `5`.

### Dica

Você precisará combinar:

- listas paralelas;
- `for`;
- `if`.

---

# Parte 3 — Repetição

Agora vamos revisar `while`.

---

## Exercício 11 — Senha

Crie um programa que peça uma senha ao usuário.

Enquanto a senha estiver errada, o programa deverá continuar perguntando.

Quando a senha estiver correta:

```text
Acesso autorizado!
```

### Dica

Você provavelmente precisará utilizar:

```python
while
```

e:

```python
break
```

### Desafio

Informe ao usuário quando a senha estiver incorreta:

```text
Senha incorreta. Tente novamente.
```

---

## Exercício 12 — Menu

Crie um programa com o seguinte menu:

```text
=== MENU ===

1 - Dizer bom dia
2 - Dizer boa tarde
3 - Dizer boa noite
4 - Sair
```

O menu deverá continuar aparecendo até que o usuário escolha a opção `4`.

Exemplo:

```text
=== MENU ===

1 - Dizer bom dia
2 - Dizer boa tarde
3 - Dizer boa noite
4 - Sair

Escolha: 1

Bom dia!
```

Depois disso, o menu deverá aparecer novamente.

### Dica

Aqui você precisará combinar:

```python
while True
```

com:

```python
if / elif / else
```

e:

```python
break
```

---



## Programa 1 - Sistema de Pedidos

Crie um programa capaz de gerenciar os pedidos de uma açaoteria

O programa deve funcionar de forma continua e só será encerrado caso o usuário desejar

O primeiro menu vai permitir:
- Novo Pedido
- Histórico
- Sair

O sistema de pedido será composto por alguns menus.

O primeiro passo é pedir para o usuário inserir seu nome

Depois vamos para o menu de escolha de tamanho de copo. Mostre os 3 tamanhos disponíveis e seus repectivos preços.

Após a seleção do tamanho, pe

Em cada etapa você deve salvar a opção escolhida pelo cliente e o preço dos intens.

