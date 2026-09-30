# 📚 Plano Curricular Completo — Trilha do Paradigma Funcional & Funções Recursivas

**Disciplina:** Teoria da Computação  
**Professor:** Tiago Heineck • IFC  
**Objetivo Geral:** Estudar o modelo computacional algébrico/funcional (Gödel-Kleene-Church), analisar sua evolução a partir de funções atômicas e operadores de repetição até atingir a expressividade universal (Turing-Completude) e demonstrar a equivalência universal com as Máquinas de Turing.

---

## 🗺️ Visão Geral dos Módulos

```
  ┌─────────────────────────────────────────────────────────────┐
  │ MÓDULO 1: Fundamentos e Composição (C)                      │
  │ • Funções Iniciais: Zero (Z), Sucessor (S), Projeção (U)    │
  │ • Pipeline sequencial de funções: f = C(g; h1, ..., hk)     │
  │ • Limite: Não permite laços dinâmicos baseados em variáveis │
  └──────────────────────────────┬──────────────────────────────┘
                                 │
                                 ▼
  ┌─────────────────────────────────────────────────────────────┐
  │ MÓDULO 2: Recursão Primitiva (R) & Laço for                 │
  │ • Esquema: f(x, 0) = g(x); f(x, y+1) = h(x, y, f(x, y))     │
  │ • Adição, Multiplicação, Fatorial, Exponenciação, Subtração │
  │ • Garantia: 100% Funções TOTAIS (sempre terminam)           │
  │ • Limite: Função de Ackermann (crescimento super-rápido)    │
  └──────────────────────────────┬──────────────────────────────┘
                                 │
                                 ▼
  ┌─────────────────────────────────────────────────────────────┐
  │ MÓDULO 3: Minimização Não-Limitada (μ) & Laço while         │
  │ • Esquema: f(x) = μ y [ g(x, y) == 0 ]                      │
  │ • Busca linear dinâmica incremental                         │
  │ • Emergência das Funções Parciais e Divergência (⊥)         │
  │ • Minimização Limitada (for/break) vs Ilimitada (while)     │
  └──────────────────────────────┬──────────────────────────────┘
                                 │
                                 ▼
  ┌─────────────────────────────────────────────────────────────┐
  │ MÓDULO DE FECHAMENTO: Equivalência & Turing-Completude      │
  │ • Tese de Church-Turing (MTs ≡ Funções μ-Recursivas)        │
  │ • Aritmetização de Gödel: codificação de MTs em números     │
  │ • Teorema da Forma Normal de Kleene: f(x) = U(μ y [T(e,x,y)])│
  │ • Hierarquia da Computabilidade e Problema da Parada        │
  └─────────────────────────────────────────────────────────────┘
```

---

## 📁 Estrutura de Arquivos da Plataforma

| Arquivo | Descrição |
| --- | --- |
| [index.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/index.html) | **Portal Principal / Menu Inicial:** Seleção dos 4 módulos e acesso ao simulado ENADE |
| [material-interativo.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/material-interativo.html) | **Módulo 1 (Apostila):** Funções Iniciais ($Z, S, U$) e Composição ($C$) |
| [slides-aula14.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/slides-aula14.html) | **Módulo 1 (Slides):** Apresentação Reveal.js com simuladores |
| [modulo2-material.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/modulo2-material.html) | **Módulo 2 (Apostila):** Recursão Primitiva ($R$), mapeamento para `for`, Ackermann |
| [modulo2-slides.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/modulo2-slides.html) | **Módulo 2 (Slides):** Apresentação Reveal.js do Módulo 2 |
| [modulo3-material.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/modulo3-material.html) | **Módulo 3 (Apostila):** Minimização ($\mu$), mapeamento para `while`, funções parciais |
| [modulo3-slides.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/modulo3-slides.html) | **Módulo 3 (Slides):** Apresentação Reveal.js do Módulo 3 |
| [modulo-fechamento-material.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/modulo-fechamento-material.html) | **Fechamento (Apostila):** Tese de Church-Turing, Forma Normal de Kleene, Equivalência com MTs |
| [modulo-fechamento-slides.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/modulo-fechamento-slides.html) | **Fechamento (Slides):** Apresentação Reveal.js do Módulo de Fechamento |
| [questoes-enade.html](file:///c:/Users/Usuario/OneDrive%20-%20ifc.edu.br/ENSINO/Teoria%20da%20Computa%C3%A7%C3%A3o/Aula14/questoes-enade.html) | **Simulado Geral Estilo ENADE:** 10 questões com filtros e gabarito interativo |
