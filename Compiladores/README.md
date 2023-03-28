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
## Aula 03 - Análise Léxica -  21.03.2023

### Analisador léxico

- Alguns símbolos têm um valor semântico associados a eles.
  - IDs e NUMs.
- Como são descritas as regras lexicográficas?
- Um identificador é uma sequência de letras e dígitos.
  - O primeiro caractere deve ser uma letra.
  - O underscore "_" conta como uma letra.  
  - Letras maiúsculas e minúsculas são diferentes.
  - Se o fluxo de entrada resultar em um símbolo até um dado caractere, o próximo caractere é lido visando encontrar a maior string de caracteres possível que constitua um símbolo.  
  - Espaços, tabs, novas linhas e comentários são ignorados exceto quando eles servem de separadores de símbolos.  
  - Um espaço em branco é usado para separar identificadores adjacentes, palavras chaves e constantes.
- Como os tokens são especificados?

### Expressões Regulares

- Uma linguagem é um conjunto de strings.
- Uma string é uma sequência de símbolos.
- Estes símbolos estão definidos em um alfabeto finito.  
  - Ex.: Linguagem C ou Pascal, linguagem dos primos, etc.
- Queremos poder dizer se uma string está ou não em uma linguagem.  
- **Símbolos**:  Para cada símbolo _a_ no alfabeto da linguagem, a expressão regular _a_ representa a linguagem contendo somente a string _a_.  
- **Alternação**: Dadas duas expressões regulares M e N, o operador de alternação (|) gera uma nova expressão M|N. Uma string está na linguagem de M|N se ela está na linguagem de M ou na linguagem de N.
  - Ex.: A linguagem de _a_|_b_ contém as duas strings _a_ e _b_.
- **Concatenação**: Dadas duas expressões M e N, o operador de concatenação (.) gera uma nova expressão M . N. Uma string está na linguagem de M . N se ela é a concatenação de quaisquer duas strings α e β tal que α está na linguagem de M e β está na linguagem de N.
  - Ex.: (a|b) . a contém as strings aa e ba.  
- **Epsilon**: A expressão regular  ε representa a linguagem cuja única string é a vazia.
  - Ex.: (a . b)|ε representa a linguagem {" ", "ab"}
- **Repetição**: Dada uma expressão regular M, seu Kleene closure é M*. Uma string está em M* se ela é a concatenação de zero ou mais strings todas em M.  
  - Ex.: ((a|b) . a)* representa {" ", "aa", "ba", "aaaa", "baaa", "aaba", "baba", "aaaaa", ...}
- Exemplos:  
  - (0|1)* . 0
    - Números binários múltiplos de 2.
  - b*(abb*)*(a|ε)
    - Strings de a's e b's sem a's consecutivos.
  - (a|b)*aa(a|b)\*
    - Strings de a's e b's com a's consecutivos.

<div>
  <img src="./imgs/A03-img01.png" alt="A03-img01"/>
</div>

- Como seriam as expressões regulares para os seguintes tokens?  
  - IF
    - if
  - ID
    - [a-z][a-z0-9]
  - NUM
    - [0-9]+

- Quais símbolos representam as seguintes expressões regulares?  
  - ([0-9]+"."[0-9]*)|([0-9]\*"."[0-9]+)
    - R -> REAL.
  - ("- -"[a-z]*"\n")|(""|"\n"|"\t")+
    - Nenhum token, somente comentário, brancos, nova, linha e tab.

### Analisador Léxico

- Ambiguidade:
  - if8 é um ID ou dois tokens IF e NUM(8)?
  - if 89 começa com um ID ou uma palavra-reservada?
- Duas regras:
  - Maior casamento: o próximo símbolo sempre é a substring mais longa possível de ser casada.  
  - Prioridade: Para uma dada substring mais longa, a primeira regra a ser casada produzirá o token.
- A especificação deve ser completa, sempre reconhece uma substring da entrada.
  - Mas quando estiver errada? Use uma regra com o "."
  - Em que lugar da sua especificação deve estar esta regra?
- Esta regra deve ser a última! (por quê?)

---
## Aula 04 - Análise Léxica -  22.03.2023

### Autômatos Finitos

- Expressões regulares são convenientes para especificar os símbolos.
- Precisamos de um formalismo que possa ser convertido em um programa de computador.
- Este formalismo são os autômatos finitos.  
- Um autômato finito possui:  
  - Um conjunto finito de estados.
  - Arestas levando de um estado a outro, anotada com um símbolo.
  - Um estado inicial.
  - Um ou mais estados finais.
  - Normalmente os estados são numerados ou nomeados para facilitar a manipulação e discussão.

<div>
  <img src="./imgs/A04-img01.png" alt="A04-img01"/>
</div>

### Autômato Finito Determinístico

- DFAs não podem apresentar duas arestas que deixam o mesmo estado, anotadas com o mesmo símbolo.  
- Saindo do estado inicial o autômato segue extamente uma aresta para cada caractere da entrada.  
- O DFA aceita a string se, após percorrer todos os caracteres, ele estiver em um estado final.  
- Se em algum momento não houver uma aresta a ser pecorrida para um determinado caractere ou ele terminar em um estado não-final, a string é rejeitada.  
- A linguagem reconhecida pelo autômato é o conjuto de todas as strings que ele aceita.
- Consigo combinar os autômatos definidos para cada símbolo de maneira a ter um único autômato que possa ser usado como analisador léxico?
  - Sim.
  - Veremos um exemplo ad-hoc e mais adiante mecanismos formais para esta tarefa.

### Autômato Finitos

<div>
  <img src="./imgs/A04-img02.png" alt="A04-img02"/>
</div>

&nbsp;
### Autômato Combinado

- Estados finais nomeados com o respectivo símbolo.  
- Alguns estados apresentam caracterísitcas de mais de um autômato anterior.   
  - Ex.: 2.
- Como ocorre a quebra de ambiguidade entre ID e IF?

<div>
  <img src="./imgs/A04-img03.png" alt="A04-img03"/>
</div>

&nbsp;
### Maior Substring

- A tabela anterior é usada para aceitar ou recusar uma string.  
- Porém, precisamos garantir que a maior string seja reconhecida.  
- Necessitamos de duas informações.  
  - Último estado final.
  - Posição da entrada no último estado final.

&nbsp;
<div>
  <img src="./imgs/A04-img04.png" alt="A04-img04"/>
</div>

### Autômato finito Não-Dterminístico

- Pode ter mais de uma aresta saindo do mesmo estado com o mesmo símbolo.  
- Pode ter aresta anotadas com o símbolo ε.  
  - Essa aresta pode ser precorrida sem consumir nenhum caractere caractere de entrada.

<div>
  <img src="./imgs/A04-img05.png" alt="A04-img05"/>
</div>

<div>
  <img src="./imgs/A04-img06.png" alt="A04-img06"/>
</div>

- Este autômato reconhece a mesma linguagem do autômato acima.


- Não são apropriados para transformar em programas de computador.  
  - "Adivinha" qual caminho deve ser seguido não é uma tarefa faacilmente executada pelo hardware dos computadores.  
- NFAs se tornam úteis porque é fácil converter expressões regulares (ER) para NFA.

---
## Aula 05 - Análise Léxica -  28.03.2023

### Convertendo ER's para NFA's
- De maniera geral, toda ER terá um NFA com uma cauda (aresta de entrada) e uma cabeça (estado final).
- Podemos definir essa conversão de maneira indutiva pois:
  - Uma ER é primitiva (único símbolo ou vazio) ou é uma combinação de outras ERs.
  - O mesmo vale para NFAs.  

<div>
  <img src="./imgs/A05-img01.png" alt="A05-img01" />
</div>

- Exemplo: ERs para IF, ID, NUM e ERROR

<div>
  <img src="./imgs/A05-img02.png" alt="A05-img02" />
</div>

### NFA vs DFA

- DFAs são facilmente simuláveis por programas de computador.  
- NFAs são mais complexos, pois o programa teria que "adivinhar" o melhor caminho em alguns momentos.  
- Outra alternativa seria tentar todas as possibilidaeds.

<div>
  <img src="./imgs/A05-img03.png" alt="A05-img03" />
</div>

### ε-Closure

- Edge(s,c): todos os estados alcançáveis a partir de s, consumindo c.  
- Closure(S): todos os estados alcançáveis a partir do conjunto S, sem consumir caractere de entrada.  
- Closure(S) é o menor conjunto T, tal que:  

<div>
  <img src="./imgs/A05-img04.png" alt="A05-img04" />
</div>
&nbsp;

### Algoritmo

<div>
  <img src="./imgs/A05-img05.png" alt="A05-img05" />
</div>

<div>
  <img src="./imgs/A05-img06.png" alt="A05-img06" />
</div>
&nbsp;

### Convertendo NFA em DFA

- Manipular esses conjuntos de estados é muito caro durante a simulação.  
- Solução:
  - Calcular todos eles antecipadamente.  
- Isso converte um NFA em um DFA!
  - Cada conjunto de estados no NFA se torna um estado no DFA. 

#### Algoritmo

<div>
  <img src="./imgs/A05-img07.png" alt="A05-img07" />
</div>

- O estado _d_ é final se qualquer um dos estados de `states[d]` for final.
- Pode haver vários estados finais em `states[d]`.  
  - `d` será anotado com o token que ocorrer primeiro na especificação léxica (ERs) => Regra de prioridade.
- Ao final
  - Descartar `states[]` e usar `trans[]` para análise léxica.

<div>
  <img src="./imgs/A05-img08.png" alt="A05-img08" />
</div>

- Esse é o menor autômato possível para essa linguagem?  
  - Não.
  - Existem estados que são equivalentes.  
- Quais estados são equivalentes no autômato acima?
- Como encontrar estados equivalentes?  
  - `trans[s1,c] = trans[s2,c]` para todo `c`. -> Isso não é suficiente!
  - _S1_ e _S2_ são equivalentes quando o autômato aceita σ começando em _S1_ sse ele também aceita σ começando em _S2_.

---
