# AULA 6B - Exercício Prático — Sistema Bancário em Python

## Objetivo

Você deverá criar, em Python, um pequeno **sistema bancário de terminal**.

O programa deverá permitir que o usuário consulte seu saldo, faça depósitos, realize saques e encerre o programa.

A atividade será desenvolvida em **várias etapas**. Não tente fazer tudo de uma vez: cada etapa acrescentará uma nova funcionalidade ao programa.

---

# Etapa 1 — Criando o saldo inicial

Comece criando uma variável chamada `saldo`.

O cliente deverá começar o programa com:

> **R$ 6.700,00**

Crie a variável utilizando um valor numérico.

### Requisitos

* Criar a variável `saldo`.
* A variável deve armazenar o valor `6700`.

### Exemplo

```python
saldo = 6700
```

---

# Etapa 2 — Criando o menu

Agora vamos transformar o programa em um sistema que o usuário possa utilizar várias vezes.

O programa deverá apresentar o seguinte menu:

```text
== Sistema de Saque 23 horas ==

..Menu Principal..

1 - Ver Saldo
2 - Depositar
3 - Sacar
4 - Encerrar
```

Depois de apresentar o menu, o programa deverá perguntar:

```text
Selecione uma das operações:
```

O usuário deverá digitar o número correspondente à operação.

---

# Etapa 3 — Fazendo o menu funcionar continuamente

O sistema bancário não deve executar apenas uma operação e depois fechar.

Depois que uma operação for realizada, o menu deverá aparecer novamente.

Para isso, utilize uma estrutura de repetição:

```python
while True:
```

### O comportamento esperado

O programa deverá funcionar aproximadamente assim:

```text
== Sistema de Saque 23 horas ==

..Menu Principal..

1 - Ver Saldo
2 - Depositar
3 - Sacar
4 - Encerrar

Selecione uma das operações:
1

Seu saldo atual é de R$6700

..Menu Principal..

1 - Ver Saldo
2 - Depositar
3 - Sacar
4 - Encerrar

Selecione uma das operações:
```

O programa deverá continuar funcionando até que o usuário escolha a opção **4**.

---

# Etapa 4 — Opção 1: consultar o saldo

Quando o usuário digitar:

```text
1
```

o programa deverá mostrar o saldo atual.

Por exemplo:

```text
Seu saldo atual é de R$6700
```

### Importante

O saldo precisa ser mostrado utilizando a variável `saldo`.

Não escreva diretamente:

```python
print("Seu saldo atual é de R$6700")
```

Utilize a variável criada anteriormente.

Uma possibilidade é utilizar uma **f-string**:

```python
print(f"Seu saldo atual é de R${saldo}")
```

---

# Etapa 5 — Opção 4: encerrar o programa

Quando o usuário escolher:

```text
4
```

o programa deverá apresentar uma mensagem informando que foi encerrado.

Por exemplo:

```text
............Programa Encerrado............

Banco Bamerindus agradece a preferência!
```

Depois disso, o programa deverá realmente parar.

### Desafio

Como estamos utilizando:

```python
while True:
```

você precisará utilizar o comando:

```python
break
```

para interromper o looping.

---

# Etapa 6 — Opção 2: realizar um depósito

Agora vamos criar uma das principais funções do sistema.

Quando o usuário escolher:

```text
2
```

o programa deverá perguntar:

```text
Insira o valor do depósito:
```

O usuário poderá informar, por exemplo:

```text
500
```

Nesse caso, o saldo deverá passar de:

```text
R$6700
```

para:

```text
R$7200
```

### O que o programa precisa fazer?

1. Pedir o valor do depósito.
2. Receber o valor utilizando `input()`.
3. Converter o valor para um número.
4. Somar o valor ao saldo.
5. Mostrar uma mensagem informando que o depósito foi realizado.
6. Voltar para o menu principal.

### Exemplo

```text
Insira o valor do depósito:
500

O depósito de R$500 foi adicionado à sua conta.
```

Depois disso:

```text
Seu saldo atual é de R$7200
```

---

# Etapa 7 — Validando o depósito

Existe um problema no programa.

O que aconteceria se o usuário digitasse:

```text
abc
```

ou:

```text
quinhentos
```

O programa tentaria transformar esse texto em número e poderia apresentar um erro.

Antes de realizar a conversão, verifique se o usuário realmente digitou apenas números.

Uma possibilidade é utilizar:

```python
isdigit()
```

### Exemplo

```python
valor = input("Digite um valor: ")

if not valor.isdigit():
    print("Valor inválido, digite apenas números")
```

Caso o valor seja inválido, o programa deverá:

* informar o erro;
* não realizar o depósito;
* voltar ao menu principal.

### Dica

O comando:

```python
continue
```

pode ser utilizado para retornar imediatamente ao início do `while`.

---

# Etapa 8 — Opção 3: realizar um saque

Agora vamos implementar a operação de saque.

Quando o usuário escolher:

```text
3
```

o programa deverá perguntar:

```text
Insira o valor a ser retirado:
```

Por exemplo:

```text
Insira o valor a ser retirado:
1000
```

Se o saldo for R$7200, o novo saldo deverá ser:

```text
R$6200
```

### O programa deverá:

1. Pedir o valor do saque.
2. Verificar se o usuário digitou um número válido.
3. Converter o valor para número.
4. Verificar se existe saldo suficiente.
5. Se houver saldo suficiente, realizar o saque.
6. Informar o usuário sobre a operação.
7. Voltar ao menu.

---

# Etapa 9 — Impedindo saques maiores que o saldo

Imagine que o cliente possui:

```text
Saldo: R$6200
```

e tenta sacar:

```text
R$8000
```

O programa **não pode permitir o saque**.

Nesse caso, deverá apresentar uma mensagem como:

```text
Impossível sacar valor maior que o saldo disponível.

Seu saldo atual é de R$6200
```

### Dica

Utilize uma estrutura condicional:

```python
if dinheiro > saldo:
```

Se essa condição for verdadeira:

* não altere o saldo;
* mostre uma mensagem de erro;
* volte ao menu.

---

# Etapa 10 — Opções inválidas

E se o usuário digitar:

```text
7
```

ou:

```text
abc
```

no menu?

O programa deverá informar:

```text
Digite apenas o número referente à operação.
```

Depois disso, o menu deverá aparecer novamente.

Para isso, utilize a estrutura:

```python
if
elif
else
```

O `else` poderá ser utilizado para tratar qualquer opção que não seja:

* `1`
* `2`
* `3`
* `4`

---

# Etapa 11 — Estrutura final esperada

Ao terminar todas as etapas, seu programa deverá possuir aproximadamente esta estrutura lógica:

```text
INÍCIO

    Criar saldo inicial

    Enquanto o programa estiver funcionando:

        Mostrar menu

        Pedir opção ao usuário

        SE opção = 1:
            Mostrar saldo

        SENÃO SE opção = 2:
            Pedir depósito
            Validar valor
            Adicionar depósito ao saldo

        SENÃO SE opção = 3:
            Pedir saque
            Validar valor
            Verificar se existe saldo suficiente
            Realizar saque

        SENÃO SE opção = 4:
            Mostrar mensagem de encerramento
            Encerrar o looping

        SENÃO:
            Informar que a opção é inválida

FIM
```

---

# 🧪 Exemplos de funcionamento

## Exemplo 1 — Consultando o saldo

```text
== Sistema de Saque 23 horas ==

..Menu Principal..

1 - Ver Saldo
2 - Depositar
3 - Sacar
4 - Encerrar

Selecione uma das operações:
1

Seu saldo atual é de R$6700
```

---

## Exemplo 2 — Fazendo um depósito

```text
Selecione uma das operações:
2

Insira o valor do depósito:
800

O depósito de R$800 foi adicionado à sua conta.
```

Novo saldo:

```text
R$7500
```

---

## Exemplo 3 — Realizando um saque

```text
Selecione uma das operações:
3

Insira o valor a ser retirado:
1500

Você realizou um saque de R$1500.
```

Novo saldo:

```text
R$6000
```

---

## Exemplo 4 — Tentando sacar mais dinheiro do que possui

```text
Selecione uma das operações:
3

Insira o valor a ser retirado:
10000

Impossível sacar valor maior que o saldo disponível.

Seu saldo atual é de R$6000
```

---

## Exemplo 5 — Digitando uma opção inválida

```text
Selecione uma das operações:
8

Digite apenas o número referente à operação.
```

---

# Desafios extras

Se você terminou o programa antes dos seus colegas, tente implementar algumas melhorias.

### Desafio 1 — Formatação do dinheiro

Faça o programa mostrar:

```text
R$ 6.700,00
```

em vez de:

```text
R$6700
```

---

### Desafio 2 — Depósitos negativos

Tente impedir que o usuário faça um depósito de:

```text
-500
```

---

### Desafio 3 — Saque de valor zero

Impeça que o usuário tente sacar:

```text
0
```

---

### Desafio 4 — Histórico de operações

Crie uma lista para armazenar as operações realizadas.

Por exemplo:

```text
Histórico:

Depósito: R$500
Saque: R$200
Depósito: R$1000
Saque: R$300
```

---

### Desafio 5 — Nova opção no menu

Adicione:

```text
5 - Ver histórico
```

Quando o usuário escolher essa opção, o programa deverá mostrar todas as operações realizadas.

---

# O que você praticou

Ao terminar o exercício, você terá utilizado:

* `input()`
* `print()`
* variáveis
* números e strings
* conversão de tipos
* `if`
* `elif`
* `else`
* `while`
* `break`
* `continue`
* `isdigit()`
* f-strings
* operadores matemáticos
* operadores de comparação

O objetivo não é apenas fazer o programa funcionar, mas **entender como cada estrutura contribui para o funcionamento do sistema**.

        print()
        continue
