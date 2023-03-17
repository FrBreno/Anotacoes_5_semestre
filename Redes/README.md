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
1. Borda da rede
1. Núcleo da rede
1. Atraso, perdas e vazão nas redes comutadas por pacotes.
1. Camadas de protocolo, modelos de serviço
1. Segurança da rede
1. História.

#### Visão básica
- Milhões de dispositivos de computação conectados:
  - Hospedeiros (Hosts) = sistemas finais.
     - Rodando aplicações de rede.

- Enlaces de comunicação
  - Fibra, cobre, satélite, rádio.
  - Taxa de transmissão.

- Roteadores -> Encaminham pacotes (pedaços de dados).

- Alguns conceitos:
  - Largura de banda -> Faixa de frequência medida em Hz.
  - Dados -> Medido em Bits ou Byts.
  - Transmissão de dados -> bps (bits por segundo) ou Bps (bytes por segundo).
  - Velocidade -> (distância/tempo) -> M/s ou KM/h.

#### Visão dos elementos básicos

- **Protocolos**: controle de envio e recepção de mensagens.  
  - Ex.: TCP, IP, HTTP, Skype, Ethernet.
- **Internet: "rede de redes"**
  - Vagamente hierárquica.
  - Internet pública _versus_ intranet privada.  
- Padrões da Internet
  - RFC: Request For Comments
  - IETF: Internet Engineering Task Force.

#### Uma visão de serviço

- **Infraestrutura de comunicação**
  - Possibilita aplicações distribuídas:
    - Web, VolP, e-mail, jogos, e-commerce, compartilhamento de arquivos.
- **Serviços de comunicação fornecidos às aplicações**
  - Entrega de dados confiável da origem ao destino.  
  - Entrga de dados pelo "melhor esforço" (não confiável).

### O que é um protocolo?

- Protocolos humanos:
  - Que horas são?
  - tenho uma pergunta
  - introduções

- Protocolos de rede:
  - máquinas em vez de humanos.
  - toda atividade de comunicação na internet controlada por protocolos.

- Protocolos definem formato, ordem de msgs enviadas e recebidas entre entidades de rede e ações tomadas sobre transmissão e recepção de msgs.

### Visão mais de perto da estrutura de rede:  

- Borda da rede 
  - Aplicações e hospedeiros.  
- Redes de acesso, meios físicos: enlaces de comunicação com e sem fio.
- Núcleo da rede.
  - Roteadoes interconectados.
  - Rede de redes.

### A borda da rede
- Sistemas finais (hospedeiros)
  - Executar programas de aplicação.
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
  - Redes de acesso institucional (escola, empresa)
  - Redes de acesso móvel

- Lembre-se:
  - Taxa de transmissão (bits por segundo) da rede de acesso?
  - Compartilhado ou dedicado> 