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
- A análise léxica ocorre no front-end do compilador.
  - Quebra a entrada em palavras conhecidas como símbolos (tokens).

### Cadeias e Linguagens

- Alfabeto: conjunto finito e não vazio de símbolos.
  - Exemplo: _sigma1_ = {0,1}
- Cadeia: sequência de símbolos de um alfabeto (pode ser infinito).
   - 010010 é cadeia sobre o alfabeto _sigma1_ de tamaho 6
- O símbolo _epsilon_ denota cadeia vazia de comprimento 0.
- Dado uma cadeia _w_ sobre um alfabeto:
  - _w_^0 = _epsilon_
  - _w_^_k_ = _w_^(_k_-1)_w_ para _k_ > 0 (concatenação _k_ vezaes)
- Dado um alfabeto _sigma_:
  - _sigma_^* é o conjunto de todas as cadeias finitas sobre _sigma_.
  - _sigma_^+ é o conjunto de todas as cadeias finitas sobre _sigma_ menos a cadeia vazia.
- Linguagem
    - Subconjunto de _sigma^*_
- Linguagem livre de contexto:
  - Linguagens descritas por uma gramática livre de contexto.
  - Úteis para especificar linguagens de programação. 
  - Vamos estudar com mais detalhes a seguir.
- Linguagens regulares:
  - Caso particular de linguagens livres de contexto.
  - Linguagens que podem ser descritas através de expressões regulares reconhecidas por autômatos finitos.

### Analisador Léxico
- Recebe uma sequência de caracteres e produz uma sequência

### Símbolos Léxicos

### Não símbolos

### Exemplo

```
float match0(char *s) {
    /* find a zero */
        if (!strncmp(s, "0.0", 3))
    return .0;
}
```

---