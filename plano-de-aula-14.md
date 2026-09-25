# 📚 Plano de Aula — Encontro 14 (100 minutos)

**Tema:** Paradigma Funcional I — Funções Básicas (Iniciais) e Operador de Composição (Substituição).

**Objetivo da Aula:** Compreender a mudança de paradigma computacional, dominar as três funções primitivas atômicas e aplicar a composição de funções para construir transformações mais complexas sobre os naturais.

---

## ⏱️ Cronograma Sugerido (100 min)

| Tempo | Etapa | Foco Pedagógico |
| --- | --- | --- |
| **10 min** | **Contextualização & Quebra de Paradigma** | Comparar o modelo mecanicista (MT/Norma) com o modelo funcional de Gödel/Kleene. |
| **25 min** | **As Três Funções Iniciais (Básicas)** | Formalização matemática e equivalência com primitivas de programação. |
| **25 min** | **O Operador de Composição (Substituição)** | Definição formal de $C(g; h_1, \dots, h_k)$ e regras de aridade/dimensão. |
| **20 min** | **Exemplos Resolvidos no Quadro** | Construção passo a passo de funções constantes e manipulação de parâmetros. |
| **15 min** | **Atividade Prática em Sala (Duplas)** | Exercícios curtos de fixação para garantir que entenderam a formalização. |
| **05 min** | **Fechamento e Gancho para o Encontro 15** | Antecipar a necessidade da *Recursão Primitiva* (como construir adição sem laços?). |

---

## 💡 Roteiro de Conteúdo e Lousa (Quadro Negro)

### 1. Contextualização: A Mudança de Paradigma (10 min)

* **O que viram até aqui (Modelo Operacional/Mecanicista):**
* Computação = Estados + Memória (Fita/Registradores) + Instruções de transição.


* **O que veremos a partir de agora (Modelo Funcional/Aritmético):**
* Computação = Avaliação de expressões matemáticas.
* O domínio de estudo é **exclusivamente** os números naturais ($\mathbb{N} = \{0, 1, 2, 3, \dots\}$).
* Trabalharemos com funções **totais** $f: \mathbb{N}^k \to \mathbb{N}$.


* **Ponte com o 4º ano:** É exatamente a base teórica da **Programação Funcional Pura** (Lisp, Haskell, Lambdas), onde não há estado mutável nem efeitos colaterais.

---

### 2. As Três Funções Básicas / Iniciais (25 min)

Toda a teoria das funções recursivas é construída a partir de apenas três funções atômicas:

#### A. Função Zero ($Z$)

* **Definição:** $Z: \mathbb{N} \to \mathbb{N}$ tal que:

$$Z(x) = 0, \quad \forall x \in \mathbb{N}$$


* **Intuição em código:**
```python
def Z(x: int) -> int:
    return 0

```



#### B. Função Sucessor ($S$)

* **Definição:** $S: \mathbb{N} \to \mathbb{N}$ tal que:

$$S(x) = x + 1, \quad \forall x \in \mathbb{N}$$


* **Intuição em código:**
```python
def S(x: int) -> int:
    return x + 1

```



#### C. Funções Projeção (ou Identidade) ($U_i^n$)

* **Definição:** Para $n \ge 1$ e $1 \le i \le n$, a função $U_i^n: \mathbb{N}^n \to \mathbb{N}$ projeta o $i$-ésimo argumento de uma tupla de $n$ elementos:

$$U_i^n(x_1, x_2, \dots, x_n) = x_i$$


* **Intuição em código:**
```python
def U(i, n, *args):
    return args[i - 1] # Seleciona o parâmetro na posição i

```


* **Atenção Didática:** Explique aos alunos o significado do sobrescrito ($n = \text{aridade/número de entradas}$) e subscrito ($i = \text{posição do elemento selecionado}$).
* *Exemplo:* $U_2^3(x, y, z) = y$.



---

### 3. Operador de Composição / Substituição (25 min)

A composição é o primeiro mecanismo para criar novas funções combinando funções existentes.

#### Definição Formal

Seja $g$ uma função de aridade $k$ ($g: \mathbb{N}^k \to \mathbb{N}$) e sejam $h_1, h_2, \dots, h_k$ funções de aridade $m$ ($h_j: \mathbb{N}^m \to \mathbb{N}$).

A **composição** de $g$ com $h_1, \dots, h_k$, denotada por $f = C(g; h_1, \dots, h_k)$, é uma função $f: \mathbb{N}^m \to \mathbb{N}$ definida por:

$$f(x_1, \dots, x_m) = g\Big(h_1(x_1, \dots, x_m),\, h_2(x_1, \dots, x_m),\, \dots,\, h_k(x_1, \dots, x_m)\Big)$$

#### Diagrama Mental para Explicar no Quadro:

$$\begin{array}{ccc} (x_1, \dots, x_m) & \xrightarrow{\quad h_1, \dots, h_k \quad} & \big(h_1(\vec{x}), \dots, h_k(\vec{x})\big) \\ & & \downarrow g \\ & & f(x_1, \dots, x_m) \end{array}$$

* **Ponte com Engenharia de Software:** É a operação de *Pipeline* ou encadeamento de chamadas de funções: `f(x) = g(h1(x), h2(x))`.

---

## ✏️ Exemplos Resolvidos no Quadro (20 min)

### **Exemplo 1: Função Constante Um ($f(x) = 1$)**

* **Objetivo:** Definir a função $f(x) = 1$ usando apenas $Z, S, U_i^n$ e Composição.
* **Resolução:**
1. $Z(x) = 0$
2. $S(Z(x)) = S(0) = 1$


* **Formalização por Composição:**
* $f = C(S; Z)$
* Aridades: $S$ tem aridade $k=1$; $Z$ tem aridade $m=1$.
* $f(x) = S(Z(x)) = 1$.



---

### **Exemplo 2: Função Constante Dois com Dois Argumentos ($f(x_1, x_2) = 2$)**

* **Objetivo:** Demonstrar como lidar com ajuste de aridade usando Projeções.
* **Resolução:**
1. Precisamos pegar $(x_1, x_2)$, descartar um deles (ou selecionar um) e transformar em $0$:

$$Z(U_1^2(x_1, x_2)) = 0$$


2. Aplicar o sucessor duas vezes:

$$S(S(Z(U_1^2(x_1, x_2)))) = 2$$




* **Formalização por Composição:**
* Define $h_1(x_1, x_2) = Z(U_1^2(x_1, x_2))$
* Define $h_2(x_1, x_2) = S(h_1(x_1, x_2))$
* $f(x_1, x_2) = S(h_2(x_1, x_2)) = 2$.



---

### **Exemplo 3: Inversão / Troca de Argumentos**

* **Objetivo:** Dadas $g(x_1, x_2)$, construir $f(x_1, x_2) = g(x_2, x_1)$.
* **Resolução:**
* $f(x_1, x_2) = g(U_2^2(x_1, x_2), U_1^2(x_1, x_2))$
* Formalmente: $f = C(g; U_2^2, U_1^2)$.



---

## 📝 Atividade Prática em Sala (15 min)

Proponha estes dois exercícios rápidos para os alunos resolverem em duplas enquanto você circula pela sala:

1. **Exercício A:** Defina formalmente a função $f(x_1, x_2, x_3) = x_2 + 1$ usando apenas as Funções Básicas e Composição.
2. **Exercício B:** Dada a função $g(x_1, x_2)$, escreva a formalização da função $h(x) = g(x, x)$.

### **Gabarito para o Professor:**

* **Exercício A:**

$$f(x_1, x_2, x_3) = S(U_2^3(x_1, x_2, x_3))$$


* *Composição:* $f = C(S; U_2^3)$.


* **Exercício B:**

$$h(x) = g(U_1^1(x), U_1^1(x))$$


* *Composição:* $h = C(g; U_1^1, U_1^1)$.



---

## 🎯 Fechamento da Aula e Provocação (5 min)

Encerre a aula com o seguinte questionamento para os alunos:

> *"Conseguimos fazer constantes e reordenar parâmetros. Mas como construiríamos a operação de Adição $add(x, y) = x + y$ usando apenas Funções Iniciais e Composição?"*

Mostre que a composição pura **não é suficiente** para expressar iterações/laços de repetição. É justamente essa limitação que motivará o **Encontro 15 (Recursão Primitiva)**, onde apresentaremos o equivalente formal aos laços `for`.