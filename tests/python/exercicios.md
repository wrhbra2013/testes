# 15 Exercicios de Python

## Basico (1-5)

### Exercicio 1: Soma de Numeros

Solicite dois numeros ao usuario e exiba a soma.

**Solucao:**

```python
num1 = float(input("Digite o primeiro numero: "))
num2 = float(input("Digite o segundo numero: "))
print(f"A soma e: {num1 + num2}")
```

---

### Exercicio 2: Par ou Impar

Verifique se um numero e par ou impar.

**Solucao:**

```python
numero = int(input("Digite um numero: "))
if numero % 2 == 0:
    print("Par")
else:
    print("Impar")
```

---

### Exercicio 3: Tabuada

Gere a tabuada de multiplicacao de um numero (1 a 10).

**Solucao:**

```python
numero = int(input("Digite um numero: "))
for i in range(1, 11):
    print(f"{numero} x {i} = {numero * i}")
```

---

### Exercicio 4: Maior de Tres Numeros

Encontre o maior de tres numeros.

**Solucao:**

```python
a, b, c = map(int, input("Digite tres numeros: ").split())
print(f"Maior: {max(a, b, c)}")
```

---

### Exercicio 5: Contagem Regressiva

Faca uma contagem regressiva de 10 a 0.

**Solucao:**

```python
for i in range(10, -1, -1):
    print(i)
print("Fogo!")
```

---

## Intermediario (6-10)

### Exercicio 6: Lista de Numeros Pares

Crie uma lista com todos os numeros pares de 1 a 100.

**Solucao:**

```python
pares = [i for i in range(1, 101) if i % 2 == 0]
print(pares)
```

---

### Exercicio 7: Inverter String

Inverta uma string fornecida pelo usuario.

**Solucao:**

```python
texto = input("Digite uma string: ")
print(texto[::-1])
```

---

### Exercicio 8: Contagem de Vogais

Conte o numero de vogais em uma frase.

**Solucao:**

```python
frase = input("Digite uma frase: ")
vogais = sum(1 for c in frase.lower() if c in 'aeiou')
print(f"Total de vogais: {vogais}")
```

---

### Exercicio 9: Ordenar Lista

Receba uma lista de numeros e ordene em ordem crescente.

**Solucao:**

```python
numeros = list(map(int, input("Digite numeros: ").split()))
print(sorted(numeros))
```

---

### Exercicio 10: Fibonacci

Gere os primeiros N numeros da sequencia de Fibonacci.

**Solucao:**

```python
n = int(input("Quantos numeros? "))
a, b = 0, 1
for _ in range(n):
    print(a, end=" ")
    a, b = b, a + b
```

---

## Avancado (11-15)

### Exercicio 11: Palindromo

Verifique se uma palavra e um palindromo.

**Solucao:**

```python
palavra = input("Digite uma palavra: ").lower()
print(palavra == palavra[::-1])
```

---

### Exercicio 12: Fatorial Recursivo

Calcule o fatorial de um numero usando recursao.

**Solucao:**

```python
def fatorial(n):
    if n <= 1:
        return 1
    return n * fatorial(n - 1)

numero = int(input("Digite um numero: "))
print(fatorial(numero))
```

---

### Exercicio 13: Dicionario de Frequencia

Conte a frequencia de cada palavra em um texto.

**Solucao:**

```python
from collections import Counter

texto = input("Digite um texto: ").lower()
palavras = texto.split()
print(Counter(palavras))
```

---

### Exercicio 14: Numeros Primos

Encontre todos os primos ate N usando Crivo de Eratostenes.

**Solucao:**

```python
def primos_ate(n):
    sieve = [True] * (n + 1)
    sieve[0] = sieve[1] = False
    for i in range(2, int(n**0.5) + 1):
        if sieve[i]:
            for j in range(i*i, n+1, i):
                sieve[j] = False
    return [i for i in range(n+1) if sieve[i]]

print(primos_ate(50))
```

---

### Exercicio 15: Merge Sort

Implemente o algoritmo de ordenacao Merge Sort.

**Solucao:**

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result

print(merge_sort([64, 34, 25, 12, 22, 11, 90]))
```
