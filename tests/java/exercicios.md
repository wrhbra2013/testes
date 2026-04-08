# 15 Exercicios de Java

## Basico (1-5)

### Exercicio 1: Soma de Numeros

Solicite dois numeros ao usuario e exiba a soma.

**Solucao:**

```java
import java.util.Scanner;

public class Soma {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int num1 = scanner.nextInt();
        int num2 = scanner.nextInt();
        System.out.println("Soma: " + (num1 + num2));
    }
}
```

---

### Exercicio 2: Par ou Impar

Verifique se um numero e par ou impar.

**Solucao:**

```java
public class ParImpar {
    public static void main(String[] args) {
        int numero = 10;
        System.out.println(numero % 2 == 0 ? "Par" : "Impar");
    }
}
```

---

### Exercicio 3: Tabuada

Gere a tabuada de multiplicacao de um numero (1 a 10).

**Solucao:**

```java
public class Tabuada {
    public static void main(String[] args) {
        int numero = 5;
        for (int i = 1; i <= 10; i++) {
            System.out.println(numero + " x " + i + " = " + (numero * i));
        }
    }
}
```

---

### Exercicio 4: Maior de Tres Numeros

Encontre o maior de tres numeros.

**Solucao:**

```java
public class MaiorDeTres {
    public static void main(String[] args) {
        int a = 10, b = 25, c = 15;
        int maior = Math.max(a, Math.max(b, c));
        System.out.println("Maior: " + maior);
    }
}
```

---

### Exercicio 5: Contagem Regressiva

Faca uma contagem regressiva de 10 a 0.

**Solucao:**

```java
public class ContagemRegressiva {
    public static void main(String[] args) {
        for (int i = 10; i >= 0; i--) {
            System.out.println(i);
        }
        System.out.println("Fogo!");
    }
}
```

---

## Intermediario (6-10)

### Exercicio 6: Numeros Pares

Crie um array com todos os numeros pares de 1 a 100.

**Solucao:**

```java
import java.util.ArrayList;

public class NumerosPares {
    public static void main(String[] args) {
        ArrayList<Integer> pares = new ArrayList<>();
        for (int i = 1; i <= 100; i++) {
            if (i % 2 == 0) pares.add(i);
        }
        System.out.println(pares);
    }
}
```

---

### Exercicio 7: Inverter String

Inverta uma string.

**Solucao:**

```java
public class InverterString {
    public static void main(String[] args) {
        String texto = "Hello";
        String invertida = new StringBuilder(texto).reverse().toString();
        System.out.println(invertida);
    }
}
```

---

### Exercicio 8: Contagem de Vogais

Conte o numero de vogais em uma frase.

**Solucao:**

```java
public class ContarVogais {
    public static void main(String[] args) {
        String frase = "Hello World";
        int count = 0;
        String vogais = "aeiouAEIOU";
        for (char c : frase.toCharArray()) {
            if (vogais.indexOf(c) != -1) count++;
        }
        System.out.println("Vogais: " + count);
    }
}
```

---

### Exercicio 9: Ordenar Array

Receba um array e ordene em ordem crescente.

**Solucao:**

```java
import java.util.Arrays;

public class OrdenarArray {
    public static void main(String[] args) {
        int[] numeros = {64, 25, 12, 22, 11};
        Arrays.sort(numeros);
        System.out.println(Arrays.toString(numeros));
    }
}
```

---

### Exercicio 10: Fibonacci

Gere os primeiros N numeros da sequencia de Fibonacci.

**Solucao:**

```java
public class Fibonacci {
    public static void main(String[] args) {
        int n = 10;
        int a = 0, b = 1;
        for (int i = 0; i < n; i++) {
            System.out.print(a + " ");
            int temp = a + b;
            a = b;
            b = temp;
        }
    }
}
```

---

## Avancado (11-15)

### Exercicio 11: Palindromo

Verifique se uma palavra e um palindromo.

**Solucao:**

```java
public class Palindromo {
    public static void main(String[] args) {
        String palavra = "radar";
        String invertida = new StringBuilder(palavra).reverse().toString();
        System.out.println(palavra.equalsIgnoreCase(invertida));
    }
}
```

---

### Exercicio 12: Fatorial Recursivo

Calcule o fatorial de um numero usando recursao.

**Solucao:**

```java
public class FatorialRecursivo {
    public static int fatorial(int n) {
        return n <= 1 ? 1 : n * fatorial(n - 1);
    }

    public static void main(String[] args) {
        System.out.println(fatorial(5));
    }
}
```

---

### Exercicio 13: Lista Encadeada

Implemente uma lista encadeada simples.

**Solucao:**

```java
class Node {
    int data;
    Node next;
    Node(int data) { this.data = data; }
}

class ListaEncadeada {
    Node head;

    void add(int data) {
        Node newNode = new Node(data);
        newNode.next = head;
        head = newNode;
    }
}
```

---

### Exercicio 14: Ordenacao Bolha

Implemente o algoritmo Bubble Sort.

**Solucao:**

```java
public class BubbleSort {
    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11};
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr.length - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
}
```

---

### Exercicio 15: Singleton

Implemente o padrao de projeto Singleton.

**Solucao:**

```java
public class Singleton {
    private static Singleton instancia;

    private Singleton() {}

    public static Singleton getInstancia() {
        if (instancia == null) {
            instancia = new Singleton();
        }
        return instancia;
    }
}
```
