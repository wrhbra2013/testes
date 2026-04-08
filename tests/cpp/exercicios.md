# 15 Exercicios de C++

## Basico (1-5)

### Exercicio 1: Soma de Numeros

Solicite dois numeros ao usuario e exiba a soma.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2;
    cin >> num1 >> num2;
    cout << "Soma: " << num1 + num2 << endl;
    return 0;
}
```

---

### Exercicio 2: Par ou Impar

Verifique se um numero e par ou impar.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 10;
    cout << (numero % 2 == 0 ? "Par" : "Impar") << endl;
    return 0;
}
```

---

### Exercicio 3: Tabuada

Gere a tabuada de multiplicacao de um numero (1 a 10).

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 5;
    for (int i = 1; i <= 10; i++) {
        cout << numero << " x " << i << " = " << numero * i << endl;
    }
    return 0;
}
```

---

### Exercicio 4: Maior de Tres Numeros

Encontre o maior de tres numeros.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 25, c = 15;
    int maior = max(a, max(b, c));
    cout << "Maior: " << maior << endl;
    return 0;
}
```

---

### Exercicio 5: Contagem Regressiva

Faca uma contagem regressiva de 10 a 0.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 10; i >= 0; i--) {
        cout << i << endl;
    }
    cout << "Fogo!" << endl;
    return 0;
}
```

---

## Intermediario (6-10)

### Exercicio 6: Numeros Pares

Crie um vetor com todos os numeros pares de 1 a 100.

**Solucao:**

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> pares;
    for (int i = 1; i <= 100; i++) {
        if (i % 2 == 0) pares.push_back(i);
    }
    for (int p : pares) cout << p << " ";
    return 0;
}
```

---

### Exercicio 7: Inverter String

Inverta uma string.

**Solucao:**

```cpp
#include <iostream>
#include <algorithm>
#include <string>
using namespace std;

int main() {
    string texto = "hello";
    reverse(texto.begin(), texto.end());
    cout << texto << endl;
    return 0;
}
```

---

### Exercicio 8: Contagem de Vogais

Conte o numero de vogais em uma frase.

**Solucao:**

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string frase = "Hello World";
    string vogais = "aeiouAEIOU";
    int count = 0;
    for (char c : frase) {
        if (vogais.find(c) != string::npos) count++;
    }
    cout << "Vogais: " << count << endl;
    return 0;
}
```

---

### Exercicio 9: Ordenar Vetor

Receba um vetor e ordene em ordem crescente.

**Solucao:**

```cpp
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

int main() {
    vector<int> numeros = {64, 34, 25, 12, 22, 11};
    sort(numeros.begin(), numeros.end());
    for (int n : numeros) cout << n << " ";
    return 0;
}
```

---

### Exercicio 10: Fibonacci

Gere os primeiros N numeros da sequencia de Fibonacci.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n = 10;
    int a = 0, b = 1;
    for (int i = 0; i < n; i++) {
        cout << a << " ";
        int temp = a + b;
        a = b;
        b = temp;
    }
    return 0;
}
```

---

## Avancado (11-15)

### Exercicio 11: Palindromo

Verifique se uma palavra e um palindromo.

**Solucao:**

```cpp
#include <iostream>
#include <algorithm>
#include <string>
using namespace std;

bool ePalindromo(string s) {
    string invertida = s;
    reverse(invertida.begin(), invertida.end());
    return s == invertida;
}

int main() {
    cout << boolalpha << ePalindromo("radar") << endl;
    return 0;
}
```

---

### Exercicio 12: Fatorial Recursivo

Calcule o fatorial de um numero usando recursao.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

int fatorial(int n) {
    return n <= 1 ? 1 : n * fatorial(n - 1);
}

int main() {
    cout << fatorial(5) << endl;
    return 0;
}
```

---

### Exercicio 13: Classe Lista Encadeada

Implemente uma lista encadeada com classes.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
    Node(int d) : data(d), next(nullptr) {}
};

class ListaEncadeada {
    Node* head;
public:
    ListaEncadeada() : head(nullptr) {}

    void add(int data) {
        Node* newNode = new Node(data);
        newNode->next = head;
        head = newNode;
    }

    void print() {
        Node* current = head;
        while (current) {
            cout << current->data << " ";
            current = current->next;
        }
    }
};

int main() {
    ListaEncadeada lista;
    lista.add(1);
    lista.add(2);
    lista.print();
    return 0;
}
```

---

### Exercicio 14: Ordenacao Quick Sort

Implemente o algoritmo Quick Sort.

**Solucao:**

```cpp
#include <iostream>
using namespace std;

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pivot = arr[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                swap(arr[i], arr[j]);
            }
        }
        swap(arr[i + 1], arr[high]);
        int pi = i + 1;
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);
    quickSort(arr, 0, n - 1);
    for (int i : arr) cout << i << " ";
    return 0;
}
```

---

### Exercicio 15: Smart Pointer

Demonstre o uso de unique_ptr.

**Solucao:**

```cpp
#include <iostream>
#include <memory>
using namespace std;

class MinhaClasse {
public:
    MinhaClasse() { cout << "Construtor" << endl; }
    ~MinhaClasse() { cout << "Destrutor" << endl; }
    void saudacao() { cout << "Ola!" << endl; }
};

int main() {
    unique_ptr<MinhaClasse> ptr = make_unique<MinhaClasse>();
    ptr->saudacao();
    return 0;
}
```
