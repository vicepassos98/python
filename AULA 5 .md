# Aula 5 — Explorando o `for`

Na aula anterior aprendemos a utilizar o `for` juntamente com a função `range()`.

```python
for i in range(5):
    print(i)
```

Porém, o `for` é muito mais poderoso.

Ele pode percorrer praticamente qualquer conjunto de informações.

Nesta aula conheceremos algumas das formas mais comuns de utilizá-lo.

---

# O `for` com `range()`

Já conhecemos este formato.

```python
for i in range(5):
    print(i)
```

Resultado:

```
0
1
2
3
4
```

Também podemos definir início e fim.

```python
for i in range(10,16):
    print(i)
```

Resultado:

```
10
11
12
13
14
15
```

---

## Exercício

Imprima os números de 20 até 30.

---

# Definindo o passo

Também podemos informar de quanto em quanto queremos contar.

```python
for i in range(0,21,2):
    print(i)
```

Resultado:

```
0
2
4
6
8
...
20
```

O terceiro número do `range()` é chamado de **passo**.

---

## Exercício

Faça uma contagem:

- de 5 em 5 até 100;
- de 10 em 10 até 200;
- regressiva de 100 até 0.

---

# Percorrendo uma String

Uma string nada mais é do que uma sequência de caracteres.

Podemos percorrê-la utilizando o `for`.

```python
nome = "Python"

for letra in nome:
    print(letra)
```

Resultado:

```
P
y
t
h
o
n
```

---

## Exercício

Peça um nome ao usuário e imprima uma letra por linha.

---

# Contando letras

Também podemos utilizar o `for` para contar determinadas letras.

```python
texto = input("Digite uma frase: ")

contador = 0

for letra in texto:

    if letra == "a":
        contador += 1

print(contador)
```

---

## Exercício

Conte quantas letras "e" existem em uma frase.

---

# Introdução às listas

Até agora nossas variáveis armazenavam apenas um valor.

```python
nome = "João"
```

Mas podemos guardar vários valores ao mesmo tempo.

```python
frutas = [
    "Maçã",
    "Banana",
    "Laranja",
    "Morango"
]
```

Isso é chamado de **lista**.

---

# Percorrendo listas

```python
for fruta in frutas:
    print(fruta)
```

Resultado

```
Maçã
Banana
Laranja
Morango
```

Observe que não precisamos saber quantas frutas existem.

O `for` percorre todos os elementos automaticamente.

---

## Exercício

Crie uma lista contendo cinco cidades.

Utilize um `for` para imprimi-las.

---

# Somando números de uma lista

```python
numeros = [12,8,15,30,42]

soma = 0

for numero in numeros:

    soma += numero

print(soma)
```

---

## Exercício

Calcule a média dos números da lista.

---


# Criando uma lista

Para criar uma lista vazia utilizamos colchetes `[]`.

```python
destinos = []
```

Observe que a variável continua sendo criada com o sinal de igualdade (`=`), porém agora o valor atribuído é uma lista vazia.

---

## Exercício 1

Crie uma lista chamada `filmes`.

Em seguida, utilize `print()` para verificar seu conteúdo.

```python
filmes = []

print(filmes)
```

Resultado esperado:

```text
[]
```

---

# Adicionando itens

Para adicionar novos elementos utilizamos o método `.append()`.

```python
destinos.append("Dubai")
destinos.append("Alasca")
destinos.append("Irã")
destinos.append("Xique-Xique - BA")
```

Agora podemos visualizar a lista.

```python
print(destinos)
```

Resultado:

```text
['Dubai', 'Alasca', 'Irã', 'Xique-Xique - BA']
```

---

## Exercício 2

Crie uma lista chamada `jogos`.

Adicione cinco jogos diferentes utilizando `.append()`.

Depois exiba a lista.

---

# Adicionando itens com `input()`

Também podemos adicionar informações digitadas pelo usuário.

```python
destinos = []

novo = input("Digite um destino: ")

destinos.append(novo)

print(destinos)
```

---

## Exercício 3

Faça o usuário cadastrar três frutas.

Ao final, exiba a lista.

---

# Removendo itens

Para remover um elemento utilizamos `.remove()`.

```python
destinos.remove("Irã")
```

Agora a lista ficará assim:

```text
['Dubai', 'Alasca', 'Xique-Xique - BA']
```

---

## Exercício 4

Remova um dos itens da lista criada anteriormente.

Observe o resultado.

> **Importante:** o item precisa existir na lista. Caso contrário ocorrerá um erro.

---

# Limpando toda a lista

Para apagar todos os elementos utilizamos `.clear()`.

```python
destinos.clear()
```

Agora:

```python
print(destinos)
```

Resultado:

```text
[]
```

---

## Exercício 5

Crie uma lista com cinco cidades.

Depois utilize `.clear()`.

Confira se a lista ficou vazia.

---

# Percorrendo listas

Já conhecemos o `for`.

Ele também funciona perfeitamente com listas.

```python
destinos = [
    "Dubai",
    "Alasca",
    "Irã"
]

for destino in destinos:
    print(destino)
```

Resultado:

```text
Dubai
Alasca
Irã
```

---

## Exercício 6

Crie uma lista contendo cinco animais.

Utilize um `for` para imprimir um animal por linha.

---

# Numerando os elementos

Às vezes queremos mostrar a posição de cada elemento.

Para isso utilizamos `enumerate()`.

```python
for i, destino in enumerate(destinos, start=1):
    print(f"{i} - {destino}")
```

Resultado:

```text
1 - Dubai
2 - Alasca
3 - Irã
```

O parâmetro `start=1` faz com que a numeração comece em 1.

Caso ele seja omitido, a contagem começará em 0.

---

## Exercício 7

Crie uma lista contendo cinco filmes.

Utilize `enumerate()` para numerá-los.

---

# Programa completo — Gerenciador de Destinos

Agora que conhecemos:

- listas;
- `.append()`;
- `.remove()`;
- `.clear()`;
- `for`;
- `enumerate()`;

podemos construir um pequeno sistema para gerenciar destinos de viagem.

```python
print("=== GERENCIADOR DE DESTINOS 6.7 ===")

destinos = []

while True:

    print("\nEscolha uma opção:")
    print("1 - Adicionar destino")
    print("2 - Remover destino")
    print("3 - Visualizar destinos")
    print("4 - Limpar lista")
    print("5 - Encerrar")

    entrada = input("Opção: ")

    if entrada == "1":

        item = input("Digite o destino: ")

        destinos.append(item)

        print(f"{item} foi adicionado.")

    elif entrada == "2":

        retirar = input("Destino a remover: ")

        if retirar in destinos:
            destinos.remove(retirar)
            print(f"{retirar} foi removido.")
        else:
            print("Destino não encontrado.")

    elif entrada == "3":

        if len(destinos) == 0:
            print("Nenhum destino cadastrado.")
        else:
            for i, item in enumerate(destinos, start=1):
                print(f"{i} - {item}")

    elif entrada == "4":

        destinos.clear()

        print("Lista limpa.")

    elif entrada == "5":

        print("Até a próxima!")

        break

    else:

        print("Digite uma opção válida.")
```

---

# Desafio

Modifique o programa para que:

- o usuário não consiga cadastrar o mesmo destino duas vezes;
- o programa informe quantos destinos existem na lista;
- antes de apagar toda a lista, o programa pergunte:
