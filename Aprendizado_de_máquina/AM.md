# Aprendizado de Máquina - 2023.1

![AM meme](https://i.imgflip.com/3w8557.jpg)

## Repositório

[GitHub - AM](https://github.com/liviaalmada/ml20230)

---
## Aula 01 - 14.03.2023

### Ciência de dados

- É a transformação de dados usando matemática e estatística em insights, decisões e produtos valiosos.  
- Exemplos de tomada de decisões a partir da analise dos dados:  
  - Estratégias de logística
  - Melhoria no transito urbano
  - Controle de estoque de produtos.  
  - Alocação de tarefas e colaboradores.  

### Motivações

- Barateamento e popularização dos dispositivos móveis e dos mais diversos tipos de sensores para coleta de dados.  
- Aumento do poder de processamento e armazenamento dos computadores.  
- Otimização de recursos.  

### Passos importantes no aprendizado de máquina

1. Definir problema.
1. Análise exploratória de dados.
   - Uso de estatística descritiva e visualização.
1. Preparar os dados.
1. Avaliar Algoritmos.
1. Melhorar os resultados.
1. Apresentar os resultados.

### Materiais extras

- [Data Science Academy - Introdução à Ciência de Dados](https://www.datascienceacademy.com.br/cursosgratuitos?msg=not-logged-in)
- [Data Science Academy - Python Fundamentos para Análise de Dados](https://www.datascienceacademy.com.br/cursosgratuitos?msg=not-logged-in)

---

## Aula 02 - 20.03.2023

### Big Data

- Habilidade dos computadores de aprenderem a partir dos dados.

### Aprendizado de máquina

- Humanos derivam regras manualmente e constroem modelos de analisar grandes quantidades de dados.
- Algoritmos de auto aprendizagem que derivam do conhecimento dos dados para fazer previsões.

### Tipos de aprendizado de máquina

|Supervised Learning|Unsupervised Learning|Reinforcement Learning|  
|-------------------|---------------------|----------------------|  
|Base de dados rotulada (categorias)|Sem rótulos|Processo de decisão|
|Feedback direto|Sem feedback|Sistema de recompensas|
|Previsão dos resultados/futuro|Encontrar a estrutura escondida nos dados|Aprender séries de aões|  

### Aprendizado supervisionado

- 1° Etapa - treino
  - Dados de treino: Quais são os dados mais interessantes para treinar o meu algoritmo para o fim específico?  
```
Rótulos/dados de treino -> Algorítmo de aprendizado de máquina -> Modelo preditivo
```  
- 2° Etapa
```
Novos dados -> Modelo preditivo -> Predição
```

- É importante separar o nosso dataset em duas categorias: dados de treino e dados de teste.
  - Os dados de teste serão utilizados para validar a eficácia do nosso algoritmo.
  - Os dados de treino são utilizados na etapa de treino.

<div>
    <img src="./imgs/Aula02-img01.png" alt="Aula02-img01"/>
</div>
<div>
    <img src="./imgs/Aula02-img02.png" alt="Aula02-img02"/>
</div>
<div>
    <img src="./imgs/Aula02-img03.png" alt="Aula02-img03"/>
</div>
<div>
    <img src="./imgs/Aula02-img04.png" alt="Aula02-img04"/>
</div>

&nbsp;
### Aprendizado por reforço

- Interações com o ambiente
- Informação do estado atual.
- Maximizar um sinal de recompensa.
  - Medida da ação do agente.

<div>
    <img src="./imgs/Aula02-img05.png" alt="Aula02-img05"/>
</div>


### Aprendizado não-supervisionado

- Objetivo: explorar a estrutura dos dados para extrair informações significativas.  
- Não há variável de sapida conhecida.
  - Dados não rotulados.  
- Não há função de recompensa.
- Estrutura dos dados pode ser desconhecida.

#### Clusterização

- Grupos baseados na similaridade dos atributos x1 e x2.
- Ex. de agrupamento de imagens por similiaridade:
  <div>
      <img src="./imgs/Aula02-img06.png" alt="Aula02-img06"/>
  </div>  

- Ex. de segmentação de imagens por agrupamento de pixels de acordo com a similaridade:
  <div>
    <img src="./imgs/Aula02-img07.png" alt="Aula02-img07"/>
  </div>

&nbsp;
#### Redução de dimensionalidade

- Limitações de dados de alta dimensionalidade: espaço de armazenamento e desempenho dos algoritmos.  

<div>
    <img src="./imgs/Aula02-img08.png" alt="Aula02-img08"/>
</div>

&nbsp;
### Terminologia e notação

<div>
    <img src="./imgs/Aula02-img09.png" alt="Aula02-img09"/>
</div>

&nbsp;
### Representação dos dados (Ex. Iris Dataset)

<div>
    <img src="./imgs/Aula02-img10.png" alt="Aula02-img10"/>
</div>

&nbsp;
### Criação de um modelo de aprendizado de máquina

<div>
    <img src="./imgs/Aula02-img11.png" alt="Aula02-img11"/>
</div>

---