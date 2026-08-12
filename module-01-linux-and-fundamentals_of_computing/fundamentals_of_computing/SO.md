# SISTEMA OPERACIONAL
    É o responsável por receber as solicitações dos programas e gerenciar os recursos do computador para que as instruções sejam executadas (É uma espécie de intermediário entre o hardware e o programa).
- Sem o SO (Sistema operacional) cada programa precisaria saber operar o hardware. 
    - Isso não seria seguro e mal gerenciado, já que um programa poderia modificar ou acessar dados de outros programas.
****
## kernel
    O sistema operacional é composto por vários componentes e o principal deles é o kernel, o qual é o responsável por gerenciar o hardware em si para que as solicitações dos programas sejam realizadas.
- O kernel é o responsável por definir:
    - Quanto de memória é dedicada a determinada atividade.
    - Quem tem permissão de acesso a determinado dado.
- Programas não conversam com o hardware, eles conversam com o kernel e este conversa com o hardware.
### USER SPACE x KERNEL SPACE
USER SPACE
        
    O espaço do usuário é o local onde os programas são executados com restrições e controle (privilégios limitados).
KERNEL SPACE

    O espaço kernel é o local onde o kernel é executado, nele é possível ter total acesso a tudo (memória, controle da CPU, dispositivos, etc) sem restrição.
- Quando um programa precisa de algo ele não consegue fazer diretamente pois não tem acesso, logo é preciso pedir para o kernel autorizar e fazer (System call).

### System Call
       O System Call é a interface padronizada de comunicação entre os programas (User Space) e o kernel (Kernel Space). Pelo qual os programas solicitam serviços ao kernel.
       Ele dita o que pode ser pedido e como deve ser pedido ao kernel, assim evitando que os programas baguncem o funcionamento do mesmo.

### Scheduler
       É um componente do kernel responsável por decidir qual processo ou thread utilizará a CPU, em qual núcleo e por quanto tempo.
- **Time Slice**: É o pequeno intervalo de tempo que o Scheduler concede a um processo ou thread para utilizar a CPU antes de passar a vez para outro. 