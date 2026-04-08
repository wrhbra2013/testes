# 15 Exercicios de Go

## Basico (1-5)

### Exercicio 1: Soma de Numeros

Solicite dois numeros ao usuario e exiba a soma.

**Solucao:**

```go
package main

import "fmt"

func main() {
    var num1, num2 int
    fmt.Scan(&num1, &num2)
    fmt.Println("Soma:", num1+num2)
}
```

---

### Exercicio 2: Par ou Impar

Verifique se um numero e par ou impar.

**Solucao:**

```go
package main

import "fmt"

func main() {
    numero := 10
    if numero%2 == 0 {
        fmt.Println("Par")
    } else {
        fmt.Println("Impar")
    }
}
```

---

### Exercicio 3: Tabuada

Gere a tabuada de multiplicacao de um numero (1 a 10).

**Solucao:**

```go
package main

import "fmt"

func main() {
    numero := 5
    for i := 1; i <= 10; i++ {
        fmt.Printf("%d x %d = %d\n", numero, i, numero*i)
    }
}
```

---

### Exercicio 4: Maior de Tres Numeros

Encontre o maior de tres numeros.

**Solucao:**

```go
package main

import "fmt"

func main() {
    a, b, c := 10, 25, 15
    maior := a
    if b > maior {
        maior = b
    }
    if c > maior {
        maior = c
    }
    fmt.Println("Maior:", maior)
}
```

---

### Exercicio 5: Contagem Regressiva

Faca uma contagem regressiva de 10 a 0.

**Solucao:**

```go
package main

import "fmt"

func main() {
    for i := 10; i >= 0; i-- {
        fmt.Println(i)
    }
    fmt.Println("Fogo!")
}
```

---

## Intermediario (6-10)

### Exercicio 6: Numeros Pares

Crie um slice com todos os numeros pares de 1 a 100.

**Solucao:**

```go
package main

import "fmt"

func main() {
    var pares []int
    for i := 1; i <= 100; i++ {
        if i%2 == 0 {
            pares = append(pares, i)
        }
    }
    fmt.Println(pares)
}
```

---

### Exercicio 7: Inverter String

Inverta uma string.

**Solucao:**

```go
package main

import "fmt"

func main() {
    texto := "hello"
    runes := []rune(texto)
    for i, j := 0, len(runes)-1; i < j; i, j = i+1, j-1 {
        runes[i], runes[j] = runes[j], runes[i]
    }
    fmt.Println(string(runes))
}
```

---

### Exercicio 8: Contagem de Vogais

Conte o numero de vogais em uma frase.

**Solucao:**

```go
package main

import "fmt"
import "strings"

func main() {
    frase := "Hello World"
    vogais := "aeiouAEIOU"
    count := 0
    for _, c := range frase {
        if strings.ContainsRune(vogais, c) {
            count++
        }
    }
    fmt.Println("Vogais:", count)
}
```

---

### Exercicio 9: Ordenar Slice

Receba um slice e ordene em ordem crescente.

**Solucao:**

```go
package main

import (
    "fmt"
    "sort"
)

func main() {
    numeros := []int{64, 34, 25, 12, 22, 11}
    sort.Ints(numeros)
    fmt.Println(numeros)
}
```

---

### Exercicio 10: Fibonacci

Gere os primeiros N numeros da sequencia de Fibonacci.

**Solucao:**

```go
package main

import "fmt"

func main() {
    n := 10
    a, b := 0, 1
    for i := 0; i < n; i++ {
        fmt.Print(a, " ")
        a, b = b, a+b
    }
}
```

---

## Avancado (11-15)

### Exercicio 11: Palindromo

Verifique se uma palavra e um palindromo.

**Solucao:**

```go
package main

import "fmt"

func ePalindromo(s string) bool {
    runes := []rune(s)
    for i, j := 0, len(runes)-1; i < j; i, j = i+1, j-1 {
        if runes[i] != runes[j] {
            return false
        }
    }
    return true
}

func main() {
    fmt.Println(ePalindromo("radar"))
}
```

---

### Exercicio 12: Fatorial Recursivo

Calcule o fatorial de um numero usando recursao.

**Solucao:**

```go
package main

import "fmt"

func fatorial(n int) int {
    if n <= 1 {
        return 1
    }
    return n * fatorial(n-1)
}

func main() {
    fmt.Println(fatorial(5))
}
```

---

### Exercicio 13: Map de Frequencia

Conte a frequencia de cada palavra em um texto.

**Solucao:**

```go
package main

import (
    "fmt"
    "strings"
)

func main() {
    texto := "ola mundo ola"
    palavras := strings.Fields(texto)
    freq := make(map[string]int)
    for _, p := range palavras {
        freq[p]++
    }
    fmt.Println(freq)
}
```

---

### Exercicio 14: Goroutine e Channel

Implemente um exemplo basico de并发 (concurrency) com goroutines.

**Solucao:**

```go
package main

import "fmt"

func fibonacci(c chan int) {
    a, b := 0, 1
    for i := 0; i < 10; i++ {
        c <- a
        a, b = b, a+b
    }
    close(c)
}

func main() {
    c := make(chan int)
    go fibonacci(c)
    for n := range c {
        fmt.Println(n)
    }
}
```

---

### Exercicio 15: Interface e Polimorfismo

Implemente polimorfismo usando interfaces.

**Solucao:**

```go
package main

import "fmt"

type Forma interface {
    Area() float64
}

type Circulo struct {
    raio float64
}

type Retangulo struct {
    largura, altura float64
}

func (c Circulo) Area() float64 {
    return 3.14 * c.raio * c.raio
}

func (r Retangulo) Area() float64 {
    return r.largura * r.altura
}

func main() {
    formas := []Forma{
        Circulo{raio: 5},
        Retangulo{largura: 10, altura: 5},
    }
    for _, f := range formas {
        fmt.Println(f.Area())
    }
}
```
