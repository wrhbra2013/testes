# 15 Exercicios de JavaScript

## Basico (1-5)

### Exercicio 1: Soma de Numeros

Solicite dois numeros ao usuario e exiba a soma.

**Solucao:**

```javascript
const num1 = parseFloat(prompt('Digite o primeiro numero:'));
const num2 = parseFloat(prompt('Digite o segundo numero:'));
console.log(`A soma e: ${num1 + num2}`);
```

---

### Exercicio 2: Par ou Impar

Verifique se um numero e par ou impar.

**Solucao:**

```javascript
const numero = parseInt(prompt('Digite um numero:'));
console.log(numero % 2 === 0 ? 'Par' : 'Impar');
```

---

### Exercicio 3: Tabuada

Gere a tabuada de multiplicacao de um numero (1 a 10).

**Solucao:**

```javascript
const numero = parseInt(prompt('Digite um numero:'));
for (let i = 1; i <= 10; i++) {
    console.log(`${numero} x ${i} = ${numero * i}`);
}
```

---

### Exercicio 4: Maior de Tres Numeros

Encontre o maior de tres numeros.

**Solucao:**

```javascript
const numeros = [5, 12, 8];
const maior = Math.max(...numeros);
console.log(`Maior: ${maior}`);
```

---

### Exercicio 5: Contagem Regressiva

Faca uma contagem regressiva de 10 a 0.

**Solucao:**

```javascript
for (let i = 10; i >= 0; i--) {
    console.log(i);
}
console.log('Fogo!');
```

---

## Intermediario (6-10)

### Exercicio 6: Numeros Pares

Crie um array com todos os numeros pares de 1 a 100.

**Solucao:**

```javascript
const pares = Array.from({ length: 100 }, (_, i) => i + 1).filter(n => n % 2 === 0);
console.log(pares);
```

---

### Exercicio 7: Inverter String

Inverta uma string.

**Solucao:**

```javascript
const texto = 'hello';
const invertida = texto.split('').reverse().join('');
console.log(invertida);
```

---

### Exercicio 8: Contagem de Vogais

Conte o numero de vogais em uma frase.

**Solucao:**

```javascript
const frase = 'Hello World';
const vogais = frase
    .toLowerCase()
    .split('')
    .filter(c => 'aeiou'.includes(c)).length;
console.log(`Total de vogais: ${vogais}`);
```

---

### Exercicio 9: Remover Duplicatas

Remova valores duplicados de um array.

**Solucao:**

```javascript
const array = [1, 2, 2, 3, 4, 4, 5];
const unico = [...new Set(array)];
console.log(unico);
```

---

### Exercicio 10: Fibonacci

Gere os primeiros N numeros da sequencia de Fibonacci.

**Solucao:**

```javascript
function fibonacci(n) {
    const fib = [0, 1];
    for (let i = 2; i < n; i++) {
        fib[i] = fib[i - 1] + fib[i - 2];
    }
    return fib.slice(0, n);
}
console.log(fibonacci(10));
```

---

## Avancado (11-15)

### Exercicio 11: Palindromo

Verifique se uma palavra e um palindromo.

**Solucao:**

```javascript
function ePalindromo(palavra) {
    const limpa = palavra.toLowerCase();
    return limpa === limpa.split('').reverse().join('');
}
console.log(ePalindromo('radar'));
```

---

### Exercicio 12: Fatorial Recursivo

Calcule o fatorial de um numero usando recursao.

**Solucao:**

```javascript
function fatorial(n) {
    return n <= 1 ? 1 : n * fatorial(n - 1);
}
console.log(fatorial(5));
```

---

### Exercicio 13: Dicionario de Frequencia

Conte a frequencia de cada palavra em um texto.

**Solucao:**

```javascript
const texto = 'ola mundo ola';
const palavras = texto.toLowerCase().split(' ');
const frequencia = palavras.reduce((acc, p) => {
    acc[p] = (acc[p] || 0) + 1;
    return acc;
}, {});
console.log(frequencia);
```

---

### Exercicio 14: Debounce

Implemente uma funcao debounce.

**Solucao:**

```javascript
function debounce(func, delay) {
    let timeout;
    return (...args) => {
        clearTimeout(timeout);
        timeout = setTimeout(() => func(...args), delay);
    };
}
```

---

### Exercicio 15: Promise.all

Simule operacoes assincronas com Promise.all.

**Solucao:**

```javascript
const promises = [Promise.resolve(1), Promise.resolve(2), Promise.resolve(3)];

Promise.all(promises).then(results => {
    console.log(results);
});
```
