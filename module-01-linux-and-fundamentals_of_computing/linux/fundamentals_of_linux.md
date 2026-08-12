# Linux
    Linux é o kernel do SO, responsável por fazer a intermediação entre o software e o hardware.
## Distribuição (distro)
    É um sistema operacional construído em torno de um kernel, cada distribuição escolhe o que instalar (programas, pacotes, interface gráfica, etc) mas o kernel continua sendo o mesmo.
## Unix
    O Linux foi influenciado pelo Unix. A filosofia Unix tem alguns princípios e o linux segue eles:
    - Faça uma coisa e faça bem (cada programa tem uma responsabilidade específica)
    - Tudo é arquivo (quase tudo é representado como arquivo)
    - Automatize tudo (se uma tarefa pode ser repetida ela pode ser automatizada)
## Estrutura do Sistema de Arquivos 
O **Linux** possui uma única árvore de diretórios (raiz do sistema), cuja raiz é representada por:

    /
#### Segue alguns dos diretórios mais:
    - /home → arquivos dos usuários.
    - /etc → configurações do sistema.
    - /usr → programas e bibliotecas.
    - /var → logs e dados que mudam com frequência (importante para cybersecurity)
    - /tmp → arquivos temporários.
    - /boot → inicialização do sistema.
    - /dev → dispositivos.
    - /proc → informações do kernel e processos.
## Terminal
    Programa que permite enviar comandos ao sistema operacional
Existem uma diferença entre Terminal e Shell importante de se saber:
- **Terminal:** é o programa onde você digita os comandos para o SO.
- **Shell:** é o programa que interpreta os comandos digitados no terminal. 
#### Caminho
    É o endereço de um arquivo/diretório dentro do sistema.
- **Caminho absoluto:** é o endereço que aponta sempre para o mesmo local (endereço exato).
- **Caminho relativo:** É um caminho calculado a partir do diretório onde você está atualmente.