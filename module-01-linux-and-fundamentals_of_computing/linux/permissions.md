# Permissões do Linux
## Conceitos
    Todo arquivo/diretório tem membros e cada membro tem suas devidas permissões.

    Os membros podem ser:
    - owner(u) = quem criou o arquivo
    - group(g) = grupos
    - others(o) = todo o restante do sistema

    As permissões podem ser:
    - read(r) = apenas de leitura
    - write(w) = modificar o arquivo(escrever/apagar)
    - execute(x) = executar o programa
****
    whoami -> comando usado para saber que usuário você é.

    id -> mostra uid (ID do usuário), gid (grupo principal) e groups (todos os grupos que o usuário pertence).
## Leitura/Alteração
    ls -la -> mostra informações a respeito do arquivo ou diretório, entre essas informações estão: tipo do arquivo, permissões de cada membro, owner do arquivo e group do arquivo.
    exemplo de saída: 
        drwxr-xr-x 2 gabriel_ferreira gabriel_ferreira 4096 Aug  9 15:28 documentos
        └───┬────┘└┬┘└──────┬───────┘ └──────┬───────┘ └┬─┘ └────┬────┘  └────┬───┘
            │      │        │                │          │        │            │
        permissões │       dono            grupo     tamanho    data     nome do arquivo
            │    links                    (bytes)            modificação   
            │
            ├─ d       → tipo (d=diretório, -=arquivo, l=link)
            ├─ rwx     → permissões do DONO
            ├─ r-x     → permissões do GRUPO
            └─ r-x     → permissões de OUTROS
****
    chmod -> change mode (usado para alterar as permissões dos membros)

    - existem 2 formas de usar chmod (númerica e simbólica).

    - NÚMERICA:
        - relacionada com o número octal
        chmod (número octal) (nome do arquivo)
        ex:. chmod 755 arquivo_teste.txt
        Isso deixaria as permissões dos usúarios da seguinte forma: -rwxr-xr-x

    - SIMBÓLICA:
        chmod  u  -  r   arquivo_teste.txt
               |  |  |          |
               |  |  |          └── nome do arquivo
               |  |  └── permissão (r-leitura; w-escrever; x-executar)
               |  └── operação (-;+;=)
               └── quem (dono(o)/grupo(g)/outros(o)/todos(a))
****
    chown -> change owner (usado para alterar o dono/grupo dono do arquivo/diretório)
    chown (nome do novo dono/grupo) (nome do arquivo)
    ex:. chown  gabriel  :  users   arquivo_teste.txt
                  |      |    |            |
                  |      |    |            └── nome do arquivo
                  |      |    └── novo grupo dono
                  |      └── separador entre usuário e grupo
                  └── novo usuário dono
****
    umask -> número usado como padrão para subtrair do número octal máximo de novos arquivos/diretórios e assim iniciarem com um padrão de permissões pre-estabelecidos ao serem criados.
    - número máximo para arquivos= 666 (arquivos por segurança nunca iniciam com a função(w-write) ativa de início); diretórios = 777
    - Desse número máximo é subtraído o umask (ex:. novo arquivo = 666 - umask(022) = permissão final (644))
    - Para altera o número umask basta usar o comando:
        umask (novo número)
## Permissões especiais
    SUID (relacionado ao owner)
    É um mecanismo que permite que um programa seja executado com as permissões do owner ao invés de quem está executando.

    Como saber se o SUID está ativado em um arquivo:
    drwxr-xr-x 2 gabriel_ferreira gabriel_ferreira 4096 Aug  9 15:28
       |      
       └── quando no lugar da letra "x" (permissão de execução do owner) estiver "s" significa que o SUID está ativado nesse arquivo.
****
    SGID (relacionado ao group)
    Mesma função do SUID porém relacionado ao group, onde o programa é executado com as permissões do group dono do arquivo.
    - relacionado a diretórios, todos os arquivos criados dentro de um diretório compartilhado com SGID ativado herdarão as permissões do grupo dono do diretório e não da pessoa que criou o novo arquivo.

    Para saber se o SGID está ativado em um arquivo:
    drwxr-xr-x 2 gabriel_ferreira gabriel_ferreira 4096 Aug  9 15:28
          |      
          └── quando no lugar da letra "x" (permissão de execução do group) estiver "s" significa que o SGID está ativado nesse arquivo.
****
    Sticky Bit
    Mecanismo que evita que um usuário apague arquivos criados por outros usuários.

    Para saber se o Sticky Bit está ativado em um arquivo:
    drwxr-xr-x 2 gabriel_ferreira gabriel_ferreira 4096 Aug  9 15:28
             |      
             └── quando no lugar da letra "x" (permissão de execução do others) estiver "t" significa que o Sticky Bit está ativado nesse arquivo.
### Ativação/Desativação de permissões especiais
    Para ativar ou desativar alguma permissão especial dentro de um arquivo/diretório usa-se o comando:
    chmod (número referente a permissão especial (4=SUID;2=SGID;1=Sticky Bit;0/none=desativar)+número octal) (nome do arquivo)
    exemplo:
        NÚMERICO
        chmod  4 7 5 5  nome_arquivo
               │ └─┬─┘
               │   └──── permissão normal (owner/group/others) — não muda
               └──────── dígito especial (representante da permissão especial)
                               4 = SUID  2 = SGID  1 = Sticky Bit  0 = nenhuma (desativa todas)
        SIMBÓLICO
        chmod  u + s  arquivo
               │ │ │
               │ │ └── s = SUID (quando "quem" = u) ou SGID (quando "quem" = g)
               │ └──── operação
               └────── u = owner    |   g = group
        - relacionado ao Sticky Bit usa-se a letra "t"
