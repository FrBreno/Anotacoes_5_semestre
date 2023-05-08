# Matemática Computacional - 2023.1

<div>
    <img height="440em" src="https://pbs.twimg.com/media/FsOIgv-WAAA0kED.jpg" />
</div>

## Por que fazer Matemática Computacional?  

- Desenvolvimento de modelos matemáticos e métodos numéricos para obtenção de soluções para problemas complexos.

## Aula 01 - Ferramentas básicas - 23.03.2023

- A seguir temos algumas ferramentas básicas que podem ser necessárias para essa disciplina.

### Sequência

- É uma coleção possivelmente infinita de números alinhados em alguma ordem (X1, X2, X3, ...).

- Uma sequência {Xn}n → ∞ tem um limite A se existe um N >= 0 tal que para todo n >= , para ε >= 0:  
|Xn - A| <= ε

- Podemos ecpressar o fato acima na notação de limite:  
lim n→∞ xn = A

- Uma sequência é **convergente** se ela tem um limite quando _n_ tende a infinito, e **divergente** caso contrário.

- Uma sequência {Xn} é **limitada** se existe algum número M >= 0 tal que |Xn| < M para todo 1, 2, ... e ilimitada se tal número não existir.
- Exemplos:
  - Xn = 1/n é limitada, uma vez que |Xn| < 1.
  - Xn = n é ilimitada.

- Uma sequência {Xn} é crescente se Cn < Xn+1, para todo n. E decrescente se Xn > Xn+1 para todo n.  

### Série Infinita

- Dado uma sequência {Xn} a expressão somatório de Xn de n = 1 até o infinito = X1 + X2 + ..., é chamada de série infinita.   
- Se uma série infinita é convergente com um limite s. Dizemos que essa série converge para a soma s.

<div>
    <img src="./imgs/A01-img01.png" alt="A01-img01" />
</div>
<div>
    <img src="./imgs/A01-img02.png" alt="A01-img02" />
</div>

### Derivada e taxa de variação

#### Velocidade média

- Seja s(t) uma função que determina a distância de uma partícuça. A velocidade média da partícula no intervalo de tempo de t até delta t pode ser calculado pela seguinte fórmula:

<div>
    <img src="./imgs/A01-img03.png" alt="A01-img03" />
</div>  

&nbsp;
### Velocidade Instantânea

- A velocidade instantânea de uma partícula no momento _t_ pode ser cakculada calculando o limite da velocidade média quando delta tende a zero.

<div>
    <img src="./imgs/A01-img04.png" alt="A01-img04" />
</div>  
<div>
    <img src="./imgs/A01-img05.png" alt="A01-img05" />
</div>  

- Note que a velocidade instantânea começa com o valor -5. Quando chega no ponto 5/2 torna-se zero.  

### Teorema do valor médio

- Seja _f_ uma função contínua no intervalo fechado [a, b] e diferenciável no intervalo aberto (a, b). Então existe um ponto ξ ∈ [a, b] tal que: `f'(ξ) = (f(b) - f(a))/(b - a)`.
- Essa equação estabelece que a inclinação da reta tangente ao ponto ξ é igual a inclinação média da curva no intervalo [a, b].
- Podemos reescrever o teorema do valor médio da seguinte maneira: `f(x1) - f(x2) = f'(ξ)(x1 - x2)`.
- Com essa equação, podemos substituir a diferença dos valores da função pela diferença entre dos valores dos argumentos da função.  

### Teorema do Valor Intermediário

- Seja _f_ uma função contínua no intervalo [a, b]. Seja _W_ um valor tal que `f(a) <= W <= f(b)` ou `f(b) <= W <= f(a)`. Então existe um ponto _c_ ∈ [a, b] tal que `f(c) = W`.  
- Consequência: Se você encontrar um intervalo [a, b] tal que `f(a) < 0 < f(b)` ou `f(b) < 0 < f(a)`. Então existe um ponto c ∈ [a, b] tal que `f(c) = 0`.
  - Este teorema pode ser usado para encontrar o zero de uma função.  

### Teorema de Taylor  

- É um resultado matemático que nos ajuda a entender melhor o comportamento de uma função em torno de um ponto específico.  
  - Diz que, se uma função é suficientemente suave em um intervalo ao redor desse ponto, podemos aproximar a função por um polinômio.  
  - Por que um polinômio? -> polinômios são expressões matemáticas mais simples e fáceis de trabalhar.  
- Exemplo: Imagine que você queira aproximar a função cos(x) em torno do ponto x = 0. 
  - O teorema de Taylor nos permite escrever uma expressão para essa função que é um polinômio de grau cada vez mais alto, e quanto mais termos adicionamos, melhor será a nossa aproximação. 
  - Assim, podemos usar essa expressão para fazer cálculos mais facilmente e entender melhor o comportamento da função.
- Esse teorema é importante, pois nos permite aproximar uma função por meio de uma série de polinômios.  
  - Esses polinômios são os chamados polinômios de Taylor -> usados para encontrar uma boa aproximação da função em torno de um ponto específico.  
- Para uma função `f(x)` que é contínua e diferenciável `n` vezes em um intervalo fechado [a, b], existe um polinômio de grau `n`, chamado de polinômio de Taylor.
  - Esse polinômio pode ser escrito como uma soma de termos da forma `(x-a)^k/k!`.
  - Onde `k` é um número inteiro não negativo, tal que:  
  ```
  f(x) = f(a) + f'(a)(x-a) + f''(a)(x-a)^2/2! + ... + f^n(a)(x-a)^n/n! + R_n(x)
  ```
  - `R_n(x)` é o chamado termo de resto, que mede o erro na aproximação da função `f(x)` pelo polinômio de Taylor.

---  
- A seguir temos uma segunda versão dessa explicação (extraido do material da disciplina):  

<div>
    <img src="./imgs/A01-img06.png" alt="A01-img06" />
</div>
<div>
    <img src="./imgs/A01-img07.png" alt="A01-img07" />
</div>
&nbsp;

### Métodos interativos 

- Hierão desenvolveu um algoritmo para o cálculo da raiz quadrada que pode ser interpretado geometricamente da seguinte maneira:
  - Imagine que você queira calcular _√d_. Geometricamente, você quer encontrar o lado quadrado tal que a área do quadrado é _d_, ou seja, _l_ * _l_ = _d_ (_l_ = _√d_).
  - Podemos começar com uma aproximação inicial considerando _l_ = _a_:  

    <div>
        <img src="./imgs/A01-img08.png" alt="A01-img08" />
    </div>
    <div>
        <img src="./imgs/A01-img09.png" alt="A01-img09" />
    </div>

---

## Aula 02 - Erros - 24.03.2023

- O processo de resolução computacional de um problema pode ser estrturado em várias fases:
  - Levantamento dos dados.
  - Construção de um modelo matemático.  
  - Escolha de um método numérico adequado.  
  - Implementação computacional do modelo.  
  - Análise dos resultados obtidos.

### Problema: Calculando a altura de um prédio

- Supondo que estamos em cima de um prédio com uma bola de metal e um cronômetro. Vamos usar isso para medir a altura do edifício.
  - Para isso, podemos usar como auxílio a seguinte equação:  
  `s = s0 + v0t + (1/2)gt^2`  
- A bolinha foi solta do topo do edifício e o cronômetro marcou que ela levou 2s para atingir o solo. Logo, `s = (1/2)*9.8 * 4 = 19,6`.  
- Essa resposta é confiável? Quais são os possíveis erros da modelagem?  
  - Erros de modelagem
    - Resistência do ar
    - Velocidade do vento
    - Forma do objeto.  
  - Erros de resolução  
    - Precisão dos dados
    - Representação dos dados
    - Operações numéricas realizadas.  
    - Erros de truncamento.

### Erro de precisão  

- A maioria das linguagens de programação utiliza uma quantidade fixa de bytes para a representação númerica para números reais -> Impossibilita a representação exata de todos os números reais.  
- Esses erros de precisão podem se acumularem dependendo do número de operações realizadas.  
- Durante a etapa de escolha do método numérico adequado, temos que considerar os possíveis erros que podem ser acumulados durante a resolução do problema.  
- A seguir, vamos ver como podemos representar um número de uma maneira simplificada.  

### Notação científica  

- Permite representar números muito grandes ou muito pequeno de uma maneira simplificada.  
- Um número N na notação científica tem a forma geral `N = m * 10^e`, onde:  
  - `m` é um valor entre 1 e 10
  - `e` é o expoente.

### Ponto Flutuante Normalizada

- A notação em ponto flutuante na forma normalizada é parecida como a notação científica com as seguintes diferenças:  
  - A parte inteira é sempre zero
  - O primeiro dígito após a vírgula é sempre diferente de zero.  
- Um número _x_ pode ser expresso da seguinte maneira:  

<div>
    <img src="./imgs/A02-img01.png" alt="A01-img01" />
</div>  

- Exemplos:  
1. 2345.89 = 0.23589 * 10^4
1. 0.0000586 = 0.586×10^(−4)
1. −12000 = -0.12 * 10^5

### Conversão da parte fracionária de um número decimal para base 2  

- Para converter a parte fracionária na base 10 para a base 2, começamos com a parte fracinária e multiplicanos por 2, separando a parte inteira da parte fracionária.  
- Continue esse processo de multiplicação até obter uma parte fracionária resultante igual a zero.  
- Em seguida, basta escrever as partes inteiras dos resultados de cada multiplicação.  
- Exemplos:  
  <div>
    <img src="./imgs/A02-img02.png" alt="A01-img02" />
  </div>  

### Erro Absoluto e Erro Relativo  

- Seja x o valor de um número e x¯¯ um valor aproximado de x. O erro absoluto é a diferênça entre o valor exato e o valor aproximado de x.  
- Dado pela fórmula:  `EAx = x - x¯¯`.   
- Seja  x  o valor exato de um número e x¯¯ um valor aproximado de  x . O erro realativo é a razão entre o erro absoluto e o valor aproximado de x, dado pela fórmula  `ERx = EAx / x¯¯`.

- Exemplo:  
  <div>
    <img src="./imgs/A02-img03.png" alt="A01-img03" />
  </div>  

- Em muitos casos, o valor exato do número não é conhecido.
- Contudo, conhecendo o valor de aproximações sucessivas.
  - Seja x^i e x^(i + 1) valores de duas aproximações para um número exato x. O erro de aproximação é dado por `Erro_aprox = x^(i+1) − x^i`.

### Sistemas de numeração em ponto flutuante  

- Sistemas computacionais representam os números reais por meio de um sistema de numerção em ponto flutuante.
  - Forma geral: `F(β,p,m,M)`
    - 
    - `β` repersenta a base.  
    - `p` representa a precisão.  
    - `m` e `M` representam os valores mínimo e máximo que o expoente pode assumir.  
  - Exemplos:
  <div>
    <img src="./imgs/A02-img07.png" alt="A01-img07" />
  </div>  
  <div>
    <img src="./imgs/A02-img08.png" alt="A01-img08" />
  </div>  


### Epsilon da Máquina  

- É definido de forma que 1 + ε seja o menor número representável maior que 1.  
  - Represintável, mas não existe números representáveis em (1, 1 + ε).  

  ```Python
  import sys
  t = 0
  eps = 1
  while 1 + eps > 1:
    eps = eps /2.0
    t += 1
  eps = eps*2.0

  print(sys.float_info.epsilon )
  print(eps)
  print(t)
  ```
  ```
  2.220446049250313e-16
  2.220446049250313e-16
  53
  ```

### Aritmética de Ponto Flutuante  

#### Soma de dois números ponto flutuante

- Passo para realizar a soma de dois números ponto flutuante:  
  1. Represente os números a ser somado.  
  1. Iguale o menor expoente ao maior.
  1. Some as mantissas.
  1. Calcule o resultado.  
  1. Normalize o resultado.  
  1. Ajuste a precisão do resultado.  
  1. Realize o arrendodamento se necessário.
  1. Mostre o resultado final.

  <div>
    <img src="./imgs/A02-img04.png" alt="A01-img04" />
  </div>  

### Operações Críticas da soma

- Soma dois números com grandezas muito diferentes.  
- Geralmente o menor número perde muita precisão pois, nesta situação seus dígitos menos podem ser descartados durante a operação.

<div>
  <img src="./imgs/A02-img05.png" alt="A02-img05" />
</div>  
<div>
  <img src="./imgs/A02-img06.png" alt="A02-img06" />
</div>  

---

## Aula 03 - Raízes de Equações - 31.03.2023

- Considere o seguinte problema:  
<div>
  <img src="./imgs/A03-img01.png" alt="A03-img01" />
</div>  

### Fase de Refinamento

- Dependendo do tipo da função _f_, os métodos que veremos aqui obtém apenas uma aproximação.  
- Nesta fase, considera uma aproximação para a raiz e melhorá-la sucessivamente até se obter uma aproximação com a precisão requerida.  

#### Critério de Parada

- Dizemos que Xk é uma boa "aproximação" para a raiz de β de uma equação _f(x) = 0_ se os critéios abaixo forem satisfeitos:
  - | _f_ (Xk) | < ε
  - | Xk - β | < ε
- Onde ε é a precisão (tolerância) admitida.  

### Método da Bisseção  

- A ideia do método da Bisseção é reduzir o intervalo [a, b] que contém a raiz β dividindo-o ao meio a cada interação.  
<div>
  <img src="./imgs/A03-img05.png" alt="A03-img05" />
</div>
&nbsp;

### Método da posição falsa  

- No método da posição falsa, a função _f(x)_ é aproximada por uma função linear _g(x)_.
<div>
  <img src="./imgs/A03-img02.png" alt="A03-img02" />
</div> 
<div>
  <img src="./imgs/A03-img03.png" alt="A03-img03" />
</div> 
<div>
  <img src="./imgs/A03-img04.png" alt="A03-img04" />
</div>
&nbsp;

- Podemos encontrar algumas alterações do método da posição falsa para ter uma convegência mais rápida.  
  - O método de Pégaso é uma dessas adaptações.
  - Durante o método de Pégaso, os pesos atribuídos aos pontos [$a_k$, $b_k$] são modificados apropriadamente.  

### Método de Pégasos

- A ideia do método é partir dos valores ($a_0, F(a_0), b_0, F(b_0)$) com $F(a_0) = f(a_0)$, $F(b_0) = f(b_0)$ e $F(a_0)F(b_0) < 0$:
  -   encontrar novos valores ($a_k, F(a_k), b_k, F(b_k)$) com $F(a_k)F(b_k) < 0$ em cada passo do método.
<div>
  <img src="./imgs/A03-img06.png" alt="A03-img06" />
</div>

---