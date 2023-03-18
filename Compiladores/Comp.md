# Compiladores - 2023.1

![Compiladores - meme](https://i.pinimg.com/originals/11/1d/8b/111d8bf7b6a290071bf6c9052379c5ff.png)

## Aula 01 - Introdução - 14.04.2024

### Métodos de avaliação

- Um trabalho - front-end do compilador.
- Uma prova - front-end do compilador.
- Um trabalho - back-end do compilador.
- Uma prova - back-end do compilador.

As 3 maiores notas são computadas.

### Livros

- Modern Compiler in Java - 2.ed.
- Compiladores: Princípios, Técnicas e Ferramentas.

### Introdução

---
Programa fonte -> Compilador -> Programa alvo

---


## Aula 02 - Análise Léxica -  15.03.2023
---
### Introdução

- Compilador traduz de uma linguagem (fonte) para outra (de máquina).
- Esse processo demanda sua quebra em várias partes, o entendimento de sua estrutura e significado.
- O responsável por esse tipo de análise é o front-end.
- A análise léxica ocorre no front-end do compilador.

#### Front-end
- Análise Léxica:
  - Quebra a entrada em palavras conhecidas como símbolos (tokens).
- Análise Sintática:
  - Analisa a estrutura de frases do programa.
- Análise Semântica:
  - Calcula o significado do programa.

### Cadeias e Linguagens

- Alfabeto: conjunto finito e não vazio de símbolos.
  - Exemplo: Σ1 = {0,1}
- Cadeia: sequência de símbolos de um alfabeto (pode ser infinito).
   - 010010 é cadeia sobre o alfabeto Σ1 de tamaho 6
- O símbolo ε denota cadeia vazia de comprimento 0.
- Dado uma cadeia _w_ sobre um alfabeto:
  - _w_^0 = ε
  - _w_^_k_ = _w_^(_k_-1)_w_ para _k_ > 0 (concatenação _k_ vezaes)
- Dado um alfabeto Σ:
  - Σ^* é o conjunto de todas as cadeias finitas sobre Σ.
  - Σ^+ é o conjunto de todas as cadeias finitas sobre Σ menos a cadeia vazia.
- Linguagem
    - Subconjunto de Σ^*
- Linguagem sobre Σ
  - Conjunto de cadeias em Σ.
  - Subconjunto de Σ^*.
- Dadas L1 e L2 linguagens sobre Σ:
  - L1 U L2 = {x | x ∈ L1 ou x ∈ L2}.
  - L1 . L2 = {xy | x ∈ L1 e y ∈ L2}.
  - L1^* = {x1, x2, ..., xk | k >= 0 e cada xi ∈ L1}.
- Linguagem livre de contexto:
  - Linguagens descritas por uma gramática livre de contexto.
  - Úteis para especificar linguagens de programação. 
  - Vamos estudar com mais detalhes a seguir.
- Linguagens regulares:
  - Caso particular de linguagens livres de contexto.
  - Linguagens que podem ser descritas através de expressões regulares reconhecidas por autômatos finitos.

### Analisador Léxico
- Recebe uma sequência de caracteres e produz uma sequência de palavras chaves, pontuação e nomes.
- Descarta comentários e espaços em branco.

### Símbolos Léxicos

<div>
  <img src="./imgs/A02-img01.png" alt="A02-img01"/>
</div>

### Não símbolos

<div>
  <img src="./imgs/A02-img02.png" alt="A02-img02"/>
</div>

### Exemplo

```
float match0(char *s) { /* find a zero */
        if (!strncmp(s, "0.0", 3))
    return .0;
}
```

Retorno do analisador léxico:

```
FLOAT ID(match0) LPAREN CHAR STAR ID(s) RPAREN LBRACE IF LPAREN BANG ID(strncmp) LPAREN ID(s) COMMA STRING(0.0) COMMA NUM(3) RPAREN RPAREN RETURN REAL(0.0) SEMI RBRACE EOF
```

---