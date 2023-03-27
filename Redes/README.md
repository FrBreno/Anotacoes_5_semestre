# Redes de Computadores - 2023.1

## Aula 01 - 16.03.2023

### Bibliografia

- KUROSE J. ROSS K. W. Redes de Computadores e internet uma abordagem top-down (IDEAL).
- ANDREW S. TANENBAUM. Redes de Computadores 4° edição, editora Campus (PARA UM MAIOR APROFUNDAMENTO). 

### Avaliações

- 3 avaliações escritas.
- Trabalho final substituí a última avaliação (AP3).
- Segunda chamada e avaliação final cobrem todo o assunto da matéria.

### Sistemas

- Frquência e arquivos - SIPPA.
- Resultados e avaliações - SIGAA.

---
### Capítulo 01

### O que é a Internet?
- Aspectos principais da internet:
  - Componentes de software e hardware báscios que a formam.
- Podemos descrever a Internet em termos de uma infraestrutura de redes que fornece serviços para aplicações distribuídas.

1. Borda da rede
1. Núcleo da rede
1. Atraso, perdas e vazão nas redes comutadas por pacotes.
1. Camadas de protocolo, modelos de serviço
1. Segurança da rede
1. História.

- Alguns conceitos da internet

  <div>
    <img src="./img/A02-img07.png" alt="A02-img07" />
  </div>

#### Visão básica
- A internet é uma rede de conhecimento que interconecta centenas de milhões de dispositivos de computação ao redor do mundo.
  - Hospedeiros (Hosts) = sistemas finais.
     - Rodando aplicações de rede.
  - Sistemas finais são conectados entre si por **enlaces (links) de comunicação** e **comutadores (switches) de pacotes**.
  - Quando um sistema final possui dados para enviar a outro sistema final, o sistema emissor segmenta esses dados e adicona bytes de cabeçalho a cada segmento.
  - Os **pacotes** são enviados através da rede ao sistema final de destino, onde são remontados para os dados originais.

- Enlaces de comunicação
  - Fibra, cobre, satélite, rádio.
  - Taxa de transmissão.

- Roteadores -> Encaminham pacotes (pedaços de dados).

- Alguns conceitos:
  - Largura de banda -> Faixa de frequência medida em Hz.
  - Dados -> Medido em Bits ou Byts.
  - Transmissão de dados -> bps (bits por segundo) ou Bps (bytes por segundo).
  - Velocidade -> (distância/tempo) -> M/s ou KM/h.

- Um comutador de pacotes encaminha o pacote que está chegando em um de seus enlaces de comunicação de entrada para um de seus enlaces de comunicação de saída (os mais predominantes são roteadores e comutadores de chamada de enlace).
  - Comutadores de chamada de enlace são geralmente utilizados em redes de acesso.
  - Roteadores são principalmente utilizados no núcleo da rede.
- **rota**/**caminho**: sequência de enlaces de comunicação e comutadores de pacotes que um pacotes percorre.
- Sistemas finais (Hosts) acessam a internet por meio de **Provedores de Serviços de Internet (ISPs)**
  - Cada ISP é uma rede de comutadores de pacotes e enlaces de comunicação.
  - Um ISP de nível mais alto consiste em roteadores de alta velocidade interconectados com enlaces de fibra ótica de alta velocidade.

#### Visão dos elementos básicos
- Sistemas finais, comutadores de pacotes e outras peças da internet executam protocolos.
- **Protocolos**: controle de envio e recepção de mensagens.  
  - Ex.: TCP, IP, HTTP, Skype, Ethernet.
- **Internet: "rede de redes"**
  - Vagamente hierárquica.
  - Internet pública _versus_ intranet privada.  
- Padrões da Internet
  - RFC: Request For Comments
  - IETF: Internet Engineering Task Force.  
- O protocolo IP especifica o formato dos pacotes que são enviados e recebidos entre roteadores e sistemas finais.
  - Os principais protocolos da internet são conhecidos como **TCP/IP**.
- Dada a importância de protocolos para a internet, é adequado que todos concordem sobre o que cada um deles faz.
  - Aqui entram em ação **Padrões de Internet** que são desenvolvidos pela IETF.
  - Os documentos padronizados da IETF são denominados **RFCs** (**Request For Comments** - pedido de comentários).

#### Uma visão de serviço

- **Infraestrutura de comunicação**
  - Possibilita aplicações distribuídas:
    - Web, VolP, e-mail, jogos, e-commerce, compartilhamento de arquivos.
- **Serviços de comunicação fornecidos às aplicações**
  - Entrega de dados confiável da origem ao destino.  
  - Entrga de dados pelo "melhor esforço" (não confiável).
- Os sistemas finais ligados à internet oferecem uma **Interface de Programa de Aplicação** (API).

### O que é um protocolo?

- Protocolos humanos:
  - Que horas são?
  - tenho uma pergunta
  - introduções

- Protocolos de rede:
  - máquinas em vez de humanos.
  - toda atividade de comunicação na internet controlada por protocolos.

<div>
  <img src="./img/A02-img08.png" alt="A02-img08" />
</div>

- Um protocolo define o formato e a ordem das mensagens trocadas entre duas ou mais entidades comunicantes, bem como as ações realizadas na transmissão e/ou no recebimento de uma mensagem ou outro evento.
- Um protocolo de rede é semelhante a um protocolo humano; a única diferêncça é que as entidades que trocam mensagens e realizam ações são componentes de hardware ou software de algum dispositivo.

### Visão mais de perto da estrutura de rede:  

- Borda da rede 
  - Aplicações e hospedeiros.  
- Redes de acesso, meios físicos: enlaces de comunicação com e sem fio.
- Núcleo da rede.
  - Roteadoes interconectados.
  - Rede de redes.

### A borda da rede
- Sistemas finais (hospedeiros)
  - São hospedeiros porque executam programas de aplicação.
  - Ex.: Web, e-mail.
  - na "borda da rede".

- Modelo cliente/servidor
  - Hospedeiro cliente solicita e recebe serviços de servidor sempre ativo.
  - Ex.: navegador/servidor Web, cliente/servidor de e-mail.

- modelo peer-peer:  
  - Usa mínimo (ou nenhum) de servidores dedicados.
  - Ex.: Skype

### Redes de acesso e meios físicos

- Como conectar sistemas finais ao roteador da borda?
  - Rede de acesso residencial.
    - Os dois tipos de acesso residencial banda larga predominantes são a **linha digital de assinante (DSL)** ou a cabo.
    - Normalmente, uma residência obtém acesso DSL à Internet da mesma empresa que fornece acesso telefônico local com fio.
    - A linha telefônica conduz, simultaneamente, dados e sianis telefônicos tradicionais, que são codificados em frequências diferentes:
      - Um canal _downstream_ de alta velocidade, com banda de 50KHz a 1MHZ.
      - Um canal _upstream_ de velocidade média, com uma banda de 4 KHz a 50 KHz.
      - Um canal de telefone bidirecional comum, com uma banda de 0 a 4 KHz. 
  - Redes de acesso institucional (escola, empresa)  
    - Uma rede local (LAN) costuma ser usada para conectar sistemas finais ao roteador da periferia (isso também ocorre nas residencias, com mais frequêcnia atualmente).
    - A **Ethernet** é uma tecnologia LAN que é utilizada predominantemente.  
    - Em uma LAN sem fio, os usuários transmitem/recebem pacotes para/de um ponto de acesso que está conectado à rede da empresa (quase sempre incluindo Ethernet com fio) que, por sua vez, é conectada à Internet com fio.
    - Um usuário de LAN sem fio deve estar no espaço de alguns metros do ponto de acesso.  
    - O acesso à LAN sem fio é baseado na tecnologia IEEE 802.11m ou seja, Wi-Fi, está presente em todo lugar.
  - Redes de acesso móvel
    - Dispositivos com acesso móvel empregam a mesma infraestrutura sem fios usada para a telefonia celular para enviar/receber pacotes por uma estação-base que é controlada pela operadora de rede celular.  
    - Diferente do Wi-Fi, um usuário só precisa estar dentro de algumas dezenas de quilômetros da estação-base.

- Lembre-se:
  - Taxa de transmissão (bits por segundo) da rede de acesso?
  - Compartilhado ou dedicado? 

---
## Aula 02 - 17.03.2023

### Modem discado

<div>
  <img src="./img/A02-img01.png" alt="A02-img01">
</div>

- Usa infrasestrutura de telefonia existente.
  - Casa conectada ao **escritório central**.
- Até 56 kbps de acesso direto ao roteador (geralmente menos).
- Não pode navegar e telefonar ao mesmo tempo: não está "sempre ligado".

### Digital Subscriber Line (DSL)

<div>
  <img src="./img/A02-img02.png" alt="A02-img02">
</div>

- Também usa infraestrutura de telefone existente.
- Até 1 Mbps upstram (hoje, normalmente < 256 kbps).
- Até 8 Mbps downstram (hoje, normalmente < 1 Mbps>).
- Linha física dedicada à central telefônica.

### Acesso residencial: modems a cabo

- Não usa infraestrutura de telefone.
  - Usa infraestrutura de TV a cabo.
- **HFC: Hybrid Fiber Coax**
  - assimétrico: até 30 Mbps downstream, 2 Mbps upstream.
- **Rede** de cabo e fibra conecta casas ao roteador ISP.
  - Casas **compartilham acesso** ao roteador.
  - Diferente de DSL, que tem **acesso dedicado**.

### Fibra nas residências

<div>
  <img src="./img/A02-img03.png" alt="A02-img03">
</div>

- Enlace ótico da central à residência.
- Duas tecnologias óticas concorrentes:  
  - Passive Optical Network (PON).
  - Active Optical Network (PAN).
- Velocidades de internet muito mais altas;
- Fibra também transporta serviços de tv e telefone.

### Acesso à Internet por Ethernet

<div>
  <img src="./img/A02-img04.png" alt="A02-img04">
</div>

- Normalmente usado em empresas, universidade, etc.
- Ethernet a 10 Mbs, 100 Mbps, 1 Gbps, 10 Gbps.
- Hoje, os sistemas finais normalmente se conectam ao comutador Ethernet.

### Redes de acesso sem fio

<div>
  <img src="./img/A02-img05.png" alt="A02-img05">
</div>

- Rede de acesso sem fio compartilhado conecta sistema final ao roteador.
  - Via estação base, também conhecida como "ponto de acesso".
- **LANs sem fio:**
  - 802.11b/g (wifi): 11 ou 54 Mbps
- **Acesso sem fio de área mais remota**
  - Fornecido pelo operador de telecomunicação.  
  - ~1 Mbps por sistema celular (EVDO, HSDPA)
  - Próximo (?): WiMAX (101s Mbps) por área remota. 

### Redes residenciais

- **Componentes típicos da rede residencial:**
- modem DSL ou a cabo.
- roteador/firewall/nat
- Ethernet
- Ponto de acesso sem fio

<div>
  <img src="./img/A02-img06.png" alt="A02-img06">
</div>

### Meios físicos

- **bit**: propaga entre pares de transmissor/receptor.
- **enlace físico**: o que fica entre o transmissor e receptor.
- **Meio guiado**:
  - Sinais se propagam em meio sólido: cobre, fibra, coaxial.  
- **Meio não guiado**:
  - Sinais se propagam livrimente, Ex.: rádio.
- **Par Trançado (TP)**
  - Dois fios de cobre isolados (é o tradicional cabo Ethernet).  
    - Categoria 3: fios de telefone tradicionais, Ethernet a 10 Mbps.
    - Categoria 5: Ethernet a 100 Mbps.
### Meio físico: cabo coaxial, fibra

- **Cabo coaxial**:
  - Dois condutores de cobre concêntricos
  - Bidirecional
  - Banda base:
    - Único canal no cabo.
    - Ethernet legado.
  - Banda larga:
    - Múltiplos canais no cabo
    - HFC
- **Cabo de fibra ótica**:
  - Fibra de vidro conduzindo pulsos de luz. Cada pulso é um bit.
  - Operação em alta velocidade:
    - Transmissão em alta velocidade ponto a ponto (Ex.: 10-100 Gps).

### Meio físico: rádio

- Sinal transportado no espectro eletromagnético.
- Nenhum "fio" físico.
- Bidirecional.
- Efeitos no ambiente de propagação:
  - Reflexão
  - Obstrução por objetos
  - Interferência
- **Rasdo link types:**
  - micro-ondas terrestre
    - Ex.: até canais de 45 Mbps
  - LAN (Ex.: Wifi)
    - 11 Mbps, 54 Mbps
  - àrea ampla (Ex.: celular)
    - celular 36: ~1 Mbps
  - satélite
    - Canal de Kbps a 45 Mbps (ou múltiplos canais menores)
    - Atraso fim a fim de 270 msec.
    - Geoestacionário VS baixa altitude.

### O núcleo da rede

- Malha de roteadores interconectados.
- A questão fundamental:
  - Como os dados são transferidos?

### Núcleo da rede: comutação de circuitos

- **Recursos fim a fim reservados para "chamada"**
- Largura de banda do enlace, capacidade de comutação.
- Recursos dedicados: sem compartilhamento.  
- Desempenho tipo circuito (garantido).
- Exige preparação de chamada.
- Recursos de rede (Ex.: largura de banda) divididos em "pedaços".
  - Pedaços alocados a chamadas.
  - Pedaço de recurso **ocioso** se não usado por chamada particular (sem compartilhamento).
- Dividindo largura de banda do enlace em "pedaços".  
  - Divisão de frequência
  - Divisão de tempo

<div>
  <img src="./img/A02-img09.png" alt="A02-img09">
</div>

<div>
  <img src="./img/A02-img10.png" alt="A02-img10">
</div>

Resolução:

- 1536/24 = 64 Mbps = 64.000.000 bps
- 640.000/64.000.000 = 0,01 segundos = 10 ms
- 500 ms + 10 ms = **510 ms**

### Núcleo da rede: comutação de pacotes

- **Cada fluxo de dados fim a fim dividido em pacotes**
- Usuário A, pacotes de B compartilham recursos da rede.
- Cada pacote usa largura de banda total do enlace.
- Recrusos usados quando necessário.
- **Disputa por recursos**:
  - Demanda de recurso agregado pode exceder quantidade disponível.
  - Congestionamento: fila de pacotes, espera por uso do enlace.
  - store and forward: pacotes se movem um salto de cada vez.  
    - Nó recebe pacote completo antes de encaminhar.
### Comutação de pacotes: multiplexação estatística

<div>
  <img src="./img/A02-img11.png" alt="A02-img11">
</div>

### Comutação de pacotes: store-and-forward

<div>
  <img src="./img/A02-img12.png" alt="A02-img12">
</div>

### Comutação de pacotes VS comutação de circuitos

- A comutação de pacotes permite que mais usuários usem a rede.  

<div>
  <img src="./img/A02-img13.png" alt="A02-img13">
</div>
<div>
  <img src="./img/A02-img14.png" alt="A02-img14">
</div>

---
## Aula 03 - 23.03.2023

---