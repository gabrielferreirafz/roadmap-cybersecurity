# Comandos do Linux
## Comando e Parâmetro (flag)
- Comando = programa que o kernel vai executar
- Paramêtro(flag) = altera a comportamento do comando

        Quando você digita o comando:
        ls -l

        ls -> programa
        -l -> Parâmetro
## Navegação no Terminal
- **Diretório:** são as pastas
    - **Diretório Home (~):** volta diretamente para o seu diretório pessoal.
    - **Diretório Pai (..):** volta para o diretório pai do local atual em que o terminal estiver
    - **Diretório Atual (.):** diretório atual

Comandos: 
    
    cd -> Change Directory
    pwd -> Print Working Directory
    ls -> List
## Manipulação de Arquivos
    mkdir -> Make a directory (criação)
    rmdir -> Remove a directory (remove o diretório desde que ele esteja vazio)
    rm -> Remove (remove arquivos)
    touch -> Tocar (Cria um arquivo vazio)
    cat -> Concatenate (exibe o conteúdo do arquivo e junta conteúdos de arquivos)
    
    cp -> Copy (Copiar arquivo ou diretório)
    mv -> Move (Move arquivos e renomeia)
    wc -> word count (conta palavras, linhas e caracteres(bytes))
## Localização de Arquivos
    file -> Arquivo (identifica o tipo do arquivo)

    find -> Procurar (procura uma arquivo/diretório específico a percorrendo toda a arvóre a partir de um ponto estabelecido e baseado em um parâmetro) ex:. find . -name "nome-arquivo" (find (ponto de partida) (paramêtro))

    locate -> Localizar (guarda em um banco de dados todos os caminhos de cada arquivo e diretório, assim localiza nesse banco e entrega o caminho da procura) +rápido
    
    grep -> global regular expression print (procura textos/padrões dentro de arquivos, muito usado para localizar dentro de arquivos as mesmas palavras)