# HARDWARE
## Conceitos Gerais
### O que é um computador?
    Uma máquina capaz de receber entradas, processar dados, armazenar e entregar saídas.
- Um computador é composto por:
    - CPU (executa as instruções)
    - Dispositivos de entrada e saída 
    - Dispositivos de armazenamento (RAM,SSD,cache e registradores)

Fluxo de funcionamento:

        Entrada -> Processamento -> Armazenamento -> Saída
### Modelo de Von Neumann
        Antes os programas não ficavam armazenados na memória do computador, logo sempre era necessário que fosse configurado toda vez para que um programa fosse iniciado. 
        Entretanto, Von Neumann teve a ideia de passar a deixar os programas armazenados dentro dos computadores, facilitando o acesso e uso.
### Ciclo de execução de uma instrução
- As instruções são executadas em 3 passos pela CPU (componente responsável por executa-lás):
    - **Fetch** (Busca): buscar a próxima instrução na memória.
    - **Decode** (Interpretar/decodificar): Interpretar o que uma instrução pede para ser feito.
    - **Execute** (Execução): Realizar a instrução.
- Esse ciclo acontece bilhões de vezes por segundo dentro de um processador.
****
## Componentes do computador
### CPU 
    Responsável por executar as instruções no computador.

- **RIP/PC (Program Counter)**: Mecanismo criado para responder a pergunta "Qual a próxima instrução que a CPU deve buscar?" 
            
        O PC/RIP é o "marcador de posição" da CPU, indicando continuamente qual instrução será buscada no próximo ciclo.
- **ALU (Arithmetic Logic Unit)**: unidade dentro da CPU responsável por executar operações aritméticas e lógicas (instruções de soma, subtração, AND, OR, XOR, etc).
- **Clock da CPU**: são sinais que sincronizam e mantém o funcionamento/execução das tarefas de forma organizada pela CPU.
    - Medido em GHz (ex:. 3,5 GHz = 3,5 bilhões de ciclos por segundo)
    - Clock (ciclos) ≠ quantidade de instruções executadas
        - Algumas instruções levam mais de um ciclo para serem executadas.
- **Núcleos**: são como várias mini CPU´s dentro da CPU.
    - Cada núcleo tem seus próprios componentes internos (cache, ALU, Registradores, etc).
    - Cada núcleo fica executando uma atividade, assim uma CPU com vários núcleos consegue executar mais atividades de forma simultanea com mais facilidade.
- **Processos**: São programas em execução
    - **Threads**: São uma linha de execução dentro de um processo
    
    Os processos e Threads são controlados para serem executados pelo SO (Sistema Operacional) para serem executados pelo núcleos. 
- **Interrupções**: É um sinal enviado a CPU que interrompe as execuções e avisa que algo de importante aconteceu.
        Exemplo de um interrupção:

        CPU executando programa -> Teclado gera interrupção(tecla é pressionada) -> CPU pausa execuções -> Executa tarefa do teclado -> CPU volta a executar as instruções de onde parou anteriormente
    - As interrupções existem, para que execuções importantes sejam executadas de imediato e não precisem entrar na fila de instruções que serão executadas. 
    - PC/RIP: são muito usados aqui para salvar a instrução que a CPU parou antes de resolver a interrupção
****
### SSD/HD
- Dispositivos de memória permanente, logo mesmo com o computador desligado os dados permanecem gravados
### Memória RAM
- Dispositivos de memória não permanente
- Armazenam dados apenas durante o uso da CPU
- +rápidos que os SSD´s/HD´s porém com menor capacidade de armazenamento
### Registradores
- São as memórias mais rápidas do computador
- Ficam localizadas dentro de cada núcleo da CPU
- Armazenamento de dados temporário (apenas durante o uso)
### Cache
- Memória rápida que fica localizada dentro da CPU
- Existem 3 tipos:
    - **L1**: menor, mais rápida e cada núcleo tem uma exclusiva
    - **L2**: intermediária
    - **L3**: mais lenta comparada aos demais tipos e é compartilhada entre os núcleos
### Hierarquia da memória
        Os tipos de memória seguem uma hierarquia que varia as seguintes variáveis (capacidade, velocidade e proximidade da CPU).
        - Quanto mais próximo da CPU = menor a capacidade de armazenamento e maior a velocidade
        - Quanto mais longe da CPU = maior a capacidade de armazenamento e menor a velocidade
- Hierarquia:

(+capacidade/-velocidade) SSD/HD -> RAM -> Cache -> Registradores (-capacidade/+velocidade)
****
### Barramentos
    São os responsáveis por ligar todos os componentes do computador entre si.
- Existem 3 tipos: 
    - **Barramentos de Dados**: Transportam dados.
    - **Barramentos de Endereço**: Transportam a localização das instruções/dados.
    - **Barramentos de Controle**: Transportam os comandos que serão feitos na memória.
****
## Comandos de checagem do Sistema
    São comandos que informam algumas informações importantes a respeito do hardware (esses comandos são específicos do Linux, mas todo SO tem seus próprios comandos de checagem).
### lscpu
    Comando que exibe todas as informações do hardware do sistema.
Algumas informações importantes para um **Cyber Security**:
    Vulnerabilities -> informa as vulnerabilidades da CPU (not affected, vulnerable and mitigation)
    Architecture -> informa a quantidade de bits que o SO processa por vez
    Virtualization -> informa se CPU suporta virtualização e detectar se você está dentro de um VM
### free -h
    Comando que exibe todas as informações de memória RAM
### df -h
    Comando que exibe todas as informações a respeito da memória em disco (HD/SSD)
