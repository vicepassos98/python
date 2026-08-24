# Aula 10 — Introdução ao NumPy6️⃣7️⃣ e Pandas🐼🐼

Até agora escrevemos nossos programas utilizando apenas recursos da própria linguagem Python.

Embora seja possível desenvolver praticamente qualquer aplicação dessa forma, muitas tarefas exigiriam centenas de linhas de código.

Para facilitar nosso trabalho, existem as **bibliotecas**.

Uma biblioteca é um conjunto de funções prontas, desenvolvidas por outros programadores, que podem ser utilizadas em nossos programas.

Nesta aula conheceremos duas das bibliotecas mais importantes para análise de dados:

- **NumPy**: cálculos numéricos e estatísticos;
- **Pandas**: manipulação e análise de tabelas de dados.

---

# Baixando as bibliotecas

Para o uso de algumas bibliotecas temos que baixá-las.

Para isso, vamos procurar a guia "Terminal" no Visual Studio e rodar as duas linhas abaixo:

```python
pip install pandas
pip install numpy
```

Essas linhas vão baixar as duas bibliotecas que vamos usar hoje.

LEMBRETE: No seu trabalho final, caso for usar outras bibliotecas, 

# Importando bibliotecas

Antes de utilizar uma biblioteca precisamos importá-la.

```python
import numpy as np
import pandas as pd

print("Bibliotecas carregadas com sucesso!")
```

É comum utilizarmos os apelidos:

- `np` para NumPy;
- `pd` para Pandas.

Esses apelidos apenas tornam o código mais curto.

---

# Trabalhando com NumPy 6️⃣7️⃣ 4️⃣2️⃣

Vamos começar criando uma lista de notas.

```python
notas = [5, 6.5, 7, 8.5, 10, 2, 3.5]

print(notas)
```

Sem utilizar bibliotecas, calcular a média exige algumas etapas.

```python
soma = 5 + 6.5 + 7 + 8.5 + 10 + 2 + 3.5

media = soma / len(notas)

print(media)
```

O NumPy simplifica bastante esse processo.

Primeiro transformamos a lista em um **array**.

```python
notas_np = np.array(notas)

print(notas_np)
```

---

# Soma

```python
print(np.sum(notas_np))
```

---

# Média

```python
print(np.mean(notas_np))
```

---

# Mediana

```python
print(np.median(notas_np))
```

---

# Valor máximo e mínimo

```python
print(np.max(notas_np))
print(np.min(notas_np))
```

---

## Exercício 1

Utilizando NumPy, determine:

- soma;
- média;
- mediana;
- maior valor;
- menor valor.

Da seguinte lista:

```python
temperaturas = [26, 28.5, 30.1, 35, 29.4, 23.5, 19]
```

## Exercício 2 — NumPy

Uma loja registrou a quantidade de produtos vendidos durante 7 dias:

```python
vendas = [12, 18, 15, 21, 17, 25, 20]
```

Utilizando NumPy:

- transforme a lista em um array;
- calcule a média de vendas;
- descubra o maior número de vendas;
- descubra o menor número de vendas;
- calcule quantas vendas ficaram acima da média.

Dica: você pode utilizar uma condição para comparar os valores com a média.



---

# Introdução ao Pandas 🐼🐼🐼🐼



Enquanto o NumPy trabalha principalmente com cálculos numéricos, o **Pandas** foi desenvolvido para trabalhar com tabelas.

Podemos imaginar um DataFrame como uma planilha do Excel criada por código.

---

# Criando um DataFrame

Vamos criar um conjunto de dados simples.

```python
dados = {
    "aluno": ["Ana", "Katia", "Helena", "Mel", "Lua"],
    "nota": [7.2, 8.5, 6.0, 9.0, 4.5],
    "faltas": [2, 0, 5, 1, 8]
}

df = pd.DataFrame(dados)

df
```

Observe que primeiro criamos um dicionário.

Depois utilizamos:

```python
pd.DataFrame()
```

para transformá-lo em uma tabela.

---

# Selecionando uma coluna

Para visualizar apenas uma coluna:

```python
df["nota"]
```

---

## Exercício 2

Exiba apenas a coluna:

- aluno;
- faltas.

---

## Exercício 3 — Filtrando dados

Utilizando o DataFrame df, mostre:

os alunos que possuem nota maior ou igual a 7;
os alunos que possuem menos de 3 faltas;
apenas os nomes dos alunos que possuem nota menor que 5.

Dica:
```python
df[df["nota"] >= 7]
```
Para selecionar apenas uma coluna:

```python
df[df["nota"] >= 7]["aluno"]
```
# Estatísticas de uma coluna

Agora podemos utilizar praticamente as mesmas funções vistas no NumPy.

```python
print("Soma:", df["nota"].sum())
print("Média:", df["nota"].mean())
print("Mediana:", df["nota"].median())
print("Máximo:", df["nota"].max())
print("Mínimo:", df["nota"].min())
```

---


# Describe

O Pandas possui uma função muito útil.

```python
df["nota"].describe()
```

Ela retorna automaticamente diversas estatísticas da coluna.

Observe que várias informações obtidas anteriormente aparecem em apenas um comando.

---

## Exercício 4

Utilize `describe()` para analisar a coluna `faltas`.

---

# Criando novas colunas

Também podemos criar novas informações a partir das existentes.

Por exemplo, uma coluna indicando se o aluno foi aprovado.

```python
df["aprovado"] = df["nota"] >= 5

df
```

A nova coluna será composta por valores lógicos (`True` e `False`).

---

## Exercício 5

Crie uma coluna chamada `frequente`.

Ela deve indicar:

- `True` para alunos com até 3 faltas;
- `False` para os demais.

---

# Agrupando dados com GroupBy

Uma das funções mais poderosas do Pandas é o `groupby()`.

Ela permite agrupar linhas que possuem uma característica em comum.

Vamos criar uma nova coluna indicando a turma de cada aluno.

```python
df["turma"] = [
    "A",
    "A",
    "B",
    "B",
    "A"
]

df
```

Agora podemos calcular a média das notas por turma.

```python
df.groupby("turma")["nota"].mean()
```

Resultado:

```text
turma
A    6.73
B    7.50
```

Também podemos calcular outras estatísticas.

```python
df.groupby("turma")["nota"].max()
```

```python
df.groupby("turma")["faltas"].sum()
```

O `groupby()` é uma das funções mais utilizadas em análise de dados e será bastante explorado nas próximas aulas.

---

## Exercício 6

Utilizando a coluna `turma`, determine:

- média das notas;
- maior nota;
- soma das faltas.

Utilize `groupby()`.

---

# Desafio

Crie um DataFrame contendo:

- nome;
- idade;
- cidade;
- salário.

Depois:

- calcule a média dos salários;
- descubra o maior salário;
- crie uma coluna indicando se o salário é maior que R$ 3.000;
- adicione uma coluna chamada `estado`;
- utilize `groupby()` para calcular a média salarial por estado.

---

# Resumo

Nesta aula aprendemos:

- importar bibliotecas;
- criar arrays com NumPy;
- realizar cálculos estatísticos;
- criar DataFrames;
- selecionar colunas;
- utilizar `describe()`;
- criar novas colunas;
- agrupar informações utilizando `groupby()`.
