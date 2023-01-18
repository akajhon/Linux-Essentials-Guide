## 1) LFS - Linux File System

		![[Pasted image 20221208203052.png]]

`#` = Comentário. Vale para não executar comandos na CLI.

`ALT + F1 ` = Primeiro Terminal

`ALT + F2 ` = Segundo Terminal

## 2) Desligando e Reiniciando Linux

- ```sudo shutdown now```
- ```sudo shutdown -r```
- ```sudo halt```
- Desligar: ```init 0```
- Reiniciar: ```init 6```

## 3) Manipulação de Diretórios

 - ### Comando ```ls``` 
	Descrição: Utilizado para listar o conteúdos de diretórios. A data do arquivo é sempre a data da última alteração no arquivo  (Criação é uma alteração).
	Parâmetros do Comando ```ls ```:
	 - ```-a ```: Lista os arquivos e diretórios ocultos.
	 - ```-A ```: Lista os arquivos ocultos e os normais. Porém exclui o ```. ```e o ```.. ```da listagem.
	 - ```-B ```: Não lista os arquivos que terminal com ```~```. Os arquivos que terminam com ``` ~``` indicam arquivos de backup no linux.
	 - ```-r``` : Reverte a listagem.
	 - ```-G ```: Oculta a coluna do Dono do arquivo.
	 - ```-o ```: Exibe apenas o Dono do arquivo.
	 - ```-n ```: Converte o nome do Dono e do grupo em UID e GUID. Converte para o formato numérico.
	 - ```-d ```: Lista apenas o nome da Pasta. E o detalhamento apenas da pasta especificada.
	 - ```-l ```: Traz o detalhamento dos arquivos, contendo: Permissões, Dono e grupo.
	 - ```-L ```: Oculta os links simbólicos e mostra apenas os links alvos.
	 - ``-p ``: Listagem Simples. Semelhante ao `-F .`
	 - ```-F ```: Coloca um separador para identificar os arquivos.
	 - ```-t ```: Ordena os arquivos por data.
	 - ```-f ```: Não classifica a listagem em ordem alfabética.
	 - ```--color=auto ```: Atribui cores para o arquivo, diretório e outros.
	 Exemplos:
	 - ```ls pasta1 pasta2 ```: Lista os conteúdos da "pasta1" e da "pasta2".
	 - ```ls -l pasta1 -d ```: Lista o detalhamento da "pasta1", como Permissões, Dono e Grupo.

 - ### Comando ```cd``` 
	Descrição: Utilizado para navegar entre diretórios. CD = Change Directory.
	Exemplos:
	 - ```cd \ ```: Vai para o diretório Raiz do Sistema.
	 - ```cd ~ ```: Vai para o diretório Home do Usuário.
	 - ```cd - ```: Vai para o diretório anterior.
	 - ```cd ..``` : Vai para o diretório anterio ao atual. Volta pastas na hierarquia de diretório. 

 - ### Comando ```pwd```
	Descrição: Utilizado para mostrar o diretório atual em que estamos. Bem utilizado em Shell Scripts.

- ### Comando ```mkdir``` 
	Descrição: Utilizado para criar diretórios.
	Exemplos:
	 - ```mkdir Diretorio1```: Cria um diretório com o nome "Diretorio1"
	 - ```mkdir Diretorio1 Diretorio2```: Cria 2 diretórios, o "Diretorio1" e o "Diretorio2".
	 - ```mkdir -p Diretorio1/Diretorio2/Diretorio3 ```: O parametro ```-p``` permite a criação de uma hierarquia de diretórios. No exemplo, o "Diretorio3" será criado dentro do "Diretorio2", que será criado dentro do "Diretorio1".

- ### Comando ```tree``` 
	Descrição: Utilizado para mostrar a hierarquia de diretorios e arquivos de forma mais amigável.
	Parâmetros do Comando ```tree ```:
	- ```-A ```: Melhora a resolução e os caracteres.

- ### Comando ```rmdir``` 
	Descrição: Utilizado para  remover diretórios. Remove apenas os diretórios vazios. Se houver algum arquivo dentro do diretório, o ```rmdir``` não funcionará.
	Parâmetros do Comando ```rmdir ```:
	 - ```-p ```: Apagua todos os diretórios de acordo com a estrutura hierarquica.


## 4) Manipulação de Arquivos

 - ### Comando ```cat``` 
	Descrição: Utilizado para vizualizar o conteúdo de arquivos.
	Parâmetros do Comando ```cat ```:
	 - ```-n ```: Numera todas as linhas do arquivo.
	 - ```-s ```: Oculta linhas em branco repetidas.
	 - ```-b ```: Numera apenas as linhas que possuem algum conteúdo dentro do arquivo.
	 - ```-E ``` : Adiciona um ```$ ``` ao fim de cada linha.
	 - ```-T ```: Exibe o TAB como um CRTL+I (^I).
	 Exemplos:
	 - ```zcat teste.gz```: Lista o conteúdo de arquivos compactados.
	 - ```bzcat teste.bz2 ```: Lista o conteúdo de arquivos bz2.
	 - ```xzcat texte.xz ```: Lista o conteúdo de arquivos xz.
	 - ``tac teste ``: Inverte a apresentação do arquivo.

 - ### Comando ```rm``` 
	Descrição: Utilizado para deletar arquivos.
	Parâmetros do Comando ```rm ```:
	 - ```-r ```: Deleta os arquivos de forma recursiva, removendo subdiretórios e seus arquivos.
	 - ```-f ```: Força a remoção, sem confirmação de remoção.
	 - ```-i ```: Sempre solicita a confirmação.
	 - ```-- ``` : Para deletar arquivos que contenham caracteres especiais no nome.
	 Exemplos:
	 - ```rm teste.gz```: Solicita confirmação e apaga.
	 - ```rm -rf teste.bz2 ```: Deleta o arquivo sem perguntar e recursivamente.
	 - ```rm -f teste1 teste2 teste12 ```: Deleta todos os arquivos passados como parametro.
	 - ``rm -rf * ``: Deleta todos os arquivos que não estão ocultos no diretório.
	 -  ``rm -rf a* ``: Deleta todos os arquivos que começam com a letra ``a`` no diretório.
	 - `rm -- - `: Deleta o `-` .

 - ### Comando ```cp``` 
	Descrição: Utilizado para copiar arquivos.  `cp [origem] [destino]`.
	Parâmetros do Comando ```cp ```:
	- ```-r ```: Copia todos os arquivos de forma recursiva para o destino.
	- `-f` : Copia de forma forçada.
	- `-v `: Ativa o modo Verbose.
	- `-R `: Recursivo. Porém copia dispositivos especiais e FIFOS, como Sockets, Links, Dispositivos e etc.
	- `-VS `: Cria um link Simbólico para os arquivos.
	- `-u `: Somente copia os arquivos se o arquivo origem estiver atualizado, ou seja, se a data de alteração do arquivo de destino for mais antiga que a do arquivo de origem.
	- `-x `: Não copia arquivos que estejam em outra estrutura, como em dispositivos externos. 
	- `-p `: Preserva atributos do arquivo.
	- `-a `: Combina os parametros `-d, -p & -R`.
	Exemplos:
	- ```cp teste teste_copia```: Copia o arquivo "teste" para o arquivo "teste_copia".
	- ```cp teste diretorio/```: Copia o arquivo "teste" para dentro do diretório "diretorio". Se o diretório não existir, um arquivo com o nome "diretorio" será criado no lugar.

 - ### Comando ```mv``` 
	Descrição: Utilizado para mover arquivos de uma determinada origem para um determinado destino. A origem é apagada após a execução. Também serve para renomear arquivos.
	Parâmetros do Comando ```mv ```:
	- ```-i ```: Modo interativo.
	- `-f` : Move de forma forçada.
	- `-v `: Ativa o modo Verbose.
	- `-u `: Somente  move arquivos que são mais novos ou possuem a mesma data de alteração do destino.
	Exemplos:
	- ```mv destino destino_renomeado```: Renomea o arquivo "destino" para "destino_renomeado".

## 5) Editores de Texto

 - ### Editor ```nano``` 
	Descrição: É o editor de texto mais simples.
	Comandos:
	 - `CTRL + X `: Sair.
	 - `CTRL + O `: Gravar o Arquivo.

 - ### Editor ```mcedit``` 
	Descrição: Editor poderoso que não acompanha a maioria das distros por padrão. Para utilizado deve-se instalar o pacote `mc` através do comando `sudo apt install mc`.
	Comandos:
	 - `F2 `: Salvar.
	 - `F8 `: Deleta a linha toda
	 - `F10 `: Sair do arquivo.
	 - `ESC 2x `: Sair do arquivo;
	 - `F7 `: Buscar dentro do arquivo.

 - ### Editor ```vi``` 
	Descrição: É o editor de texto famoso e modal. Um dos mais utilizados.
	Comandos:
	 - ``:q ``: Sai do editor
	 - `:q `: Sair do editor de forma forçada.
	 - `:i `: Entra no modo de edição.
	 - `ESC`: Sai de um modo.
	 - `:x `: Salva e sai do arquivo.
	 - `:w `: Apenas salva o arquivo.

## 6) Caracteres Coringas

 - ### Caracter ```*``` 
	Descrição: Nenhum, 1 ou mais de um.
	Exemplos:
	 - `ls a*` = Todos os arquivos que começem com a letra "a".
	 - `ls *path` = Todos os arquivos que terminam com "path".

 - ### Caracter ```?``` 
	Descrição: 1 caracter naquela posição.
	Exemplos:
	 - `ls m?` = Todos os arquivos que posuem 2 caracteres.

 - ### Caracter ```[a-z]``` 
	Descrição: Intervalo de caracteres.
	Exemplos:
	 - `ls m[a-z]` = Todos os arquivos que possuem um caracter entre a e z após o m.
	 - `ls m[^a-c] `= Todos os arquvios que comecem com M e não contenham nenhum caracter de a até c depois do m

 - ### Caracter ```{sa}``` 
	Descrição: Padrão para strings.
	Exemplos:
	 - `ls *{list}* `= Todos os arquivos que contenham "list" em seu nome.

## 7) Comandos Diversos

 - ### Comando ```clear``` 
	Descrição: Limpa a tela colocando o cursor no canto superior esquerdo.

 - ### Comando ```date``` 
	Descrição: Exibe a data/horário do sistema. Converte entre diversos formatos.
	Parâmetros do Comando ```date ```:
	 - ```-u ```: Horário no formato UTC
	 - ```-s ```: Configurar o horário
	 - ```hwclock --systohc ```: Joga o horário definido com "date -s" para o hardware.
	 Exemplos:
	 - ```date +%d ```: Mostra somente o dia.
	 - ```date +%d-%y```: Mostra Dia e Ano.
	 - `date +"%d-%m-%Y %T"` : Mostra Dia, Mes, Ano e Hora.
	 - ``date -u --date='@1'``: Primeiro segundo do Unix time.

 - ### Comando ```df``` 
	Descrição: Serve para mostrar o espaço livre em cada partição montada no sistema.
	Parâmetros  e exemplos do Comando ```df ```:
	 - `df -h` = Human Readable
        - `df -H` = Human Readable mostrando o espaço comercial
        - `df -l` = Lista somente o sistema de arquivos locais
	 - `df -m` = Exibe a saida em Megabytes, diretamente.
	 - `df -a` = Inclui pseudofilesystems
	 - `df -i` = Exibe os INODES
	 - `df -T` = Qual o sistema de arquivos está em qual partição
	 - `df -t` = Exibe a listagem do DF apenas ccom o sistema de arquivos especificado.
	 - `df -P` = Traz a saída em formato POSIX

 - ### Comando ```ln``` 
	Descrição: Serve para criar Links entre arquivos e diretórios.
	 - Hard Links - Links que são criados dentro do mesmo sistema de arquivos.Representa o arquivo real e precisam de root.
	 - Link Simbólico - Link criado em outro sistema de arquivos. Representa um atalho.
	Parâmetros  e exemplos do Comando ```ln ```:
	 - `ln -s` = Cria um link simbólico.
	 - `ln ` = Cria um Hard Link. 

 - ### Comando ```du``` 
	Descrição: Exibe a ocupação de cada arquivo dentro da partição 
	Parâmetros  e exemplos do Comando ```du ```:
	 - `du -h `= Human readable
	 - `du -hs ` = Conta o total
	 - `du --inodes ` = Mostra os dados dos Inodes

 - ### Comando ```find``` 
	Descrição: Permite localizar arquivos e diretórios no sistema linux
	Parâmetros do Comando ```find ```:
	- `type d/ f/ b/ p/ c/ s/ l `= Especifíca o tipo de arquivo. 
		- `d` = Diretório
		- `a` = Arquivo
		- `b `= Blocos 
		- `p `= Pipes 
		- `c `= Dispositivos de caracter 
		- `s `= Sockets
		- `l `= Links
	- `maxdepth 2 ` = Mostra apenas 2 diretórios de hierarquiva na estrutura.
	- `mindepth 2 ` = No mínimo 2 diretórios na hierarquia
	- `mtime -1 `= Arquivos que foram modificados a um dia atrás.
	- `ctime +-1 = Arquivos ou pastas que foram criados a mais/menos de 1 dia
	- `cmin -1 ` = Arquivos ou pastas criados no ultimo minuto
	- `mount ` = Apenas faz a pesquisa dentro da estrutura de arquivos montados
	- `gid ` = Pesquisa por grupo
	- `uid ` = Pesquisa por usuário
	- `user ` = pesquisa pelo user, porem em extenso
	- `group ` = pesqusia pelo grupo, porem em extenso
	- `links ` = Pesquisa arquivos ou diretórios que tem links como referencia
	- `size ` = pesquisa pelo tamanho do arquivo
	Exemplo:
	 - `find . -name ls ` = Busca na pasta atual arquivos contendo "ls" no nome.

 - ### Comando ```free``` 
	Descrição: Exibe a Memória RAM fífica e SWAP disponíveis na máquina. Utiliza o /proc/meminfo.
	Parâmetros do Comando ```free ```:
	- `-h ` = Human Readable Format
	- `--kilo ` = Saída em Kilobytes
	- `--mega ` = Saída em Megabytes
	- `--kibi ` = Saída em Kibibytes. Em blocos de 1024
	- `--mebi ` = Saída em Megabytes.
	- `-s ` = Traz a memória a cada 1 segundo - Em tempo real

 - ### Comando ```grep``` 
	Descrição: Pesquisa por expressões em arquivos.
	Parâmetros do Comando ```free ```:
	 - `-v ` = Inverte a busca. O que não tem a expressão passada.
	 - `-f ` = Arquivo de entrada para a busca. O arquivo contém a expressão.
	 - `-i ` = Ignora Maiusculos e Minusculos
	 - `-E ` = Pesquisa por expressões regulares
	 - `-F ` = Pesquisa por caracteres especiais dentro de uma expressão.
	 - `-r ` = Pesquisa de forma recursiva
	 - `-l ` = Lista apenas o nome dos arquivos em que a expressão é encontrada.
	 - `-n ` = Numero da linha em que as expressão se encontra dentro do arquivo.

 - ### Comando ```head``` 
	Descrição: Mostra as primeiras linhas de um arquivo. Por padrão, ele mostra as 10 primeiras linhas de um arquivo.
	Parâmetros do Comando ```head ```:
	 - `-c ` = Especifica a Quantidade de bytes qe será exibida.
	 - `-n ` = Especifica a quantidade de linhas que deseja ver.

 - ### Comando ```nl``` 
	Descrição: Numera as linhas de um determinado arquivo.
	Parâmetros do Comando ```nl ```:
	 - `-f ` = Filtros
	 - `-i ` = Determinar o incremento.
	 - `-v ` = especificar a linha inicial.

 - ### Comando ```more``` 
	Descrição: Serve para visualizar arquivos grandes, pausa página à pagina.

 - ### Comando ```less``` 
	Descrição: Aprimoramento do more. É possível rolar para cima e para baixo no arquivo; É Possivel pesquisar usando o less.

 - ### Comando ```time``` 
	Descrição: Visualiza o tempo de execução de um comando.Visualiza o tempo de execução de um comando.

 - ### Comando ```uptime``` 
	Descrição: Mostra o tempo de atividade da máquina desde o último boot.

 - ### Comando ```mesg``` 
	Descrição: Ativa o comando talk.

 - ### Comando ```sync``` 
	Descrição: Permite gravar os buffers do kernel/ memória de sistema no disco.

 - ### Comando ```patch``` 
	Descrição: Aplica mudanças em arquivos

 - ### Comando ```whereis``` 
	Descrição: Permite localizar um arquivo de manual no sistema.

 - ### Comando ```which``` 
	Descrição: Permite localizar onde o binário se encontra no sistema.


 - ### Comando ```sort``` 
	Descrição: Ordena os conteúdos de um arquivo de forma alfabética.
	Parâmetros do Comando ```sort ```:
	 - `-r `= Inverte a classificação da listagem.
	 - `-n `= Classificar de forma numérica.
	 - `-c `= Reotorna se a lista já está ordenada ou não.
	 - `+1 `= Ordena pela Segunda coluna. Inicia em 0
	 - `-k `= Ordena por colunas também, porém, de forma extensa.
	 - `-t `= Escolhe o delimitador

 - ### Comando ```tail``` 
	Descrição: Permite visualizar o final de um arquivo.  Por padrão, as últimas 10 linhas são exibidas.
	Parâmetros do Comando ```tail ```:
	 - `-n `= Especifica o número de linhas a ser visualizado.
	 - `-f `= Observa modificações no arquivo em tempo real.

 - ### Comando ```touch``` 
	Descrição: Permite a criação de arquivos vazios.
	Parâmetros do Comando ```touch ```:
	 - `-t `= Modifica a Timestamp do arquivo.
	 - `-a `= Modifica o Timestamp de acesso do arquivo.

 - ### Comando ```dmesg``` 
	Descrição: Exibe as mensagens do ringbuffer do Kernel. Exibe as últimas mensagens do Kernel.
	Parâmetros do Comando ```dmesg ```:
	 - `-t ` = Retira os números da primeira coluna.
	 - `--color `= Exibe cores
	 - `-w ` = Observa mensagens do kernel em tempo real.
	 - `-x ` = Decodifica algumas mensagens em texto legivel, colocando categoria das mensagens.
	 - `-T `= Coloca a timestamp do boot e transforma em data e hora legível.
	 - `-c `= Limpa as mensagens do kernel.

 - ### Comando ```uname``` 
	Descrição: Retorna o nome do sistema.
	Parâmetros do Comando ```uname ```:
	 - `-a `= Retorna varios dados do Kernel
	 - `-s `= Exibe o nome do Kernel
	 - `-n `= Exibe o nome da máquina
	 - `-r `= Retorna a versão atual do kernel
	 - `-v `= Mostra a data de compilação do kernel
	 - `-m `= Mostra a arquitetura do sistema

 - ### Comando ```chattr``` 
	Descrição: Alterar atributos de arquivos no sistema. Atributos são diferentes de permissões.
	Parâmetros do Comando ```chattr ```:
	 - `+` = adiciona atributo
	 - `- `= Remove atributo
	 - -R = Recursivamente
	 - `chattr +i ` = Imutavel = Não permite Alterações ou deleções no arquivo.
	 - `chattr +a `= Append = Coloca o arquivo ou diretório em modo Append. Em pastas o "-a" impede a remoção de pastas.
	 - `chattr +c `= Compactação= Permite a compactação.
	 - `chattr +s `= Security = Permite a deleção do arquivo.
	 - `chattr +S `= Sync = Permite a sincronização imediata do arquivo.
	 - `chattr +D `= Directory = Grava de forma síncrona.
	 - `chattr +d `= Arquivos e pastas com o atributo D são excluídos do backup .do DUMP.
	 - `chattr =aie * `= Atribui os atributos a e i à todos os arquivos do diretório.

 - ### Comando ```lsattr``` 
	Descrição: Lista atributos de arquivos.


 - ### Comando ```cut``` 
	Descrição: Corta um pedaço do arquivo, exibindo apenas o que deseja.
	Parâmetros do Comando ```uname ```:
	 - `-d `= Define um delimitador para o corte.
	 - `-f `= Define qual campo iremos pegar no arquivo.
	 - `-b `= Sintaxe de bytes. Permite cortar utilizando bytes.
	 - `-c `= Apenas caracteres válidos

 - ### Comando ```wc``` 
	Descrição: Conta o número de palavras, bytes e linhas da entrada padrão ou de um arquivo.
	Parâmetros do Comando ```wc ```:
	 - `-l `= Exibe somento o numero de linhas
	 - `-c `= Apenas o numero de bytes
	 - `-w `= Exibe apenas o numero de palavras

 - ### Comando ```diff``` 
	Descrição: Mostra as diferenças entre os arquivos. Mostrando as linhas.
	Parâmetros do Comando ```diff ```:
	 - `-u `= Formato legível
	 - `-r `= Recursivo

 - ### Comando ```echo``` 
	Descrição: Exibe uma mensagem na tela
	Parâmetros do Comando ```echo ```:
	 - `-n `= Não faz a quebra de linha no final da mensagem.
	 - `-e `= Habilita a interpretação de caracteres especiais.

 - ### Comando ```seq``` 
	Descrição: Imprime uma sequência de números.
	Parâmetros do Comando ```seq ```:
	 - `-w `= Ordena utilizando o 0.

 - ### Comando ```cmp``` 
	Descrição: Serve para comparar arquivos.
	Parâmetros do Comando ```cmp ```:
	 - `-s `= Sem saída. Retorna apenas o código de saída -> 1 ou 0.

 - ### Comando ```su``` 
	Descrição: Permite elevar os privilégios do usuário para usuário root. `su` pede senha do próprio root enquanto `sudo `pede a senha do próprio usuário.
	Parâmetros do Comando ```su ```:
	 - `- `ou `-l ` = Faz o login e inicia um ambiente novo, sem variaveis de ambiente.
	 - `-s `= Permite especificar o shell.

 - ### Comando ```sudo``` 
	Descrição: Permite elevar os privilégios, permitindo especificar quais usuários podem escalar o privilégio para root.
	 - `adduser xxxxx sudo `= adiciona permissão de elevação de privilegios à um user.
	 - `deluser xxxxx sudo `= remove permissão de elevação de privilegios de um user.


## 8) Comandos para Desligamento/Restart

 - ### Comando  para ```DESLIGAMENTO``` 
	 - `halt`
	 - `systemctl halt`
	 - `shutdown -h now`
	 - `echo o > /proc/sysrg-trigger` = Última opção.
	 - `shutdown -h 09:40` = Agenda o desligamento para as 09:40
	 - `shutdown -c` = Cancela os agendamentos


 - ### Comando  para `RESTART` 
	 - `reboot `= Reinicia a máquina. Permitido apenas para o root.
		 - `-f `= Força o reboot. Interessante rodar o sync antes desta opção.
	 - `systemctl reboot`
	 - `shutdown -r now `= Reinicia a máquina no momento.
	 - `echo b > /proc/sysrq-trigger `= Última opção.


## 9) Discos e Partições

 - `MS-DOS `: Partição Legada. Possui apenas 4 partições primárias. Partição máxima de 2Tb
 - `GPT`: Partição máxima de 1 Zb
 - Partição Estendida: Partição primária utilizada para estender as limitações da partição `MS-DOS`
 - `mkfs `: Formata partições no formato desejado.
 - `mkswap `: Formata partições SWAP
 - `wipefs `: Destrui dados de partições.
 - `UEFI` : Evolução do BIOS. Instalado diretamente na EEPROM na máquina. GPT Obrigatório. A partição BIOS deve ter 1 Mb
 
 - ### Comando ```fdisk``` 
	Descrição: Particionador de discos do Linux.
	Parâmetros do Comando ```fdisk ```:
	 - ```-l ```: Lista os discos do sistema
	 - ``` m ```: Chama a ajuda

 - ### Comando ```gdisk``` 
	Descrição: Particionador de discos GPT.
	Parâmetros do Comando ```gdisk ```:
	 - ```? ``` :  Ajuda
	 - ```n ```: Nova Partição
	 - `b` : Backup do layout de particionamento.
	 - `v `: Verificação do particionamento.

 - ### Comando ```parted``` 
	Descrição: Particionador de discos. Alterações em tempo real.
	Parâmetros do Comando ```parted ```:
	 - ```print ``` :  Exibe as partições do HD.
	 - ```help ```: Ajuda
	 - `mkpart` : Cria partições.

 - ### Comando ```cfdisk``` 
	Descrição: Particionador de discos de linha de comando gráfico. UFI ou DOS

 - ### Planejamento de particionamento: 
	 - Planejar antecipadamente as partições garante maior segurança e resiliência ao sistema. Além de evitar que o servidor seja parado para realizar manutenções.

		 - Disco de 1 Tb:
			 - / = 20 Gb
			 - /usr = 15 Gb
			 - /var = 60 Gb
			 - /home = 500 Gb
			 - swap = 8 Gb
				ou
			 - / = 50 Gb
			 - /home = 930 Gb
			 - swap = 8 Gb

		-   Servidor de E-mails:
			 - / = 20 Gb
			 - /var = 500 Gb -> Isolado em uma partição
			 - /home = 5 Gb
			 - swap = 16 Gb


		-   Servidor de Arquivos:
			 - / = 20 Gb
			 - /data = 900 Gb -> Isolado em uma partição
			 - /home = 5 Gb

		-    Servidor Web:
			 - / = 20 Gb
			 - /var = 950 Gb -> Isolado em uma partição
			 - /home = 5 Gb
			 -  swap = 8 Gb

 - ### /etc/fstab
	 - Arquivo responsável por realizar a montagem de dispositivos no sistema linux.


## 10) Hardware e dispositivos de expansão

 - `/proc/interrupts` : Arquivo que gerencia as interrupções do sistema linux. 
 - `IRQ` : Interrupção de requisição
 - `IO Ports` : Portas utilizadas pelo SO para se comunicar com o Hardware. 

 - `Firmware `: Código que vem junto ao hardware e que não vem junto ao linux.
 - `/lib/firmware `: Diretório que contém os firmwares intalados junto ao SO.
 - `apt-get install firmware-linux-nonfree `: Instalar Firmwares proprietários. 

 - ### Comando ```lspci``` 
	Descrição: Lista todas as placas físicas conectadas ao sistema.
	Parâmetros do Comando ```lspci ```:
	 - ```-vv ```: Mais detalhes acerca de cada placa conectada ao sistema.

 - ### Comando ```lsusb``` 
	Descrição: Lista os dispositivos USB conectados ao sistema

 - ### Comando ```lshw``` 
	Descrição: Lista todos os hardwares conectados ao SO com muitos detalhes.

## 11) Administração de Usuários

 - `UID `: User Identification. UID root = 0.
 - `GID` : Group Identification. Sempre que um novo usuário é criado, um grupo com o mesmo nome do usuário é criado e o usuário é adicionado ao mesmo por Default.
 - `id `: Mostra as informações de GID e UID do usuário em questão.
 - ``skel ``: Local onde estão todos os arquivos de criação dos usuários. Quando um novo usuário é criado, todos os arquivos do ``/etc/skel`` são copiados para o ``/home``do usuário.

 - ``/etc/passwd ``: Arquivo de configuração dos usuários.
	 - Coluna 1: Nome do usuário
	 - Coluna 2: Senha do usuário - A senha real está em ``/etc/shadow``.
	 - Coluna 3: UID
	 - Coluna 4: GID
	 - Coluna 5: Comentários
	 - Coluna 6: Diretório Home
	 - Coluna 7: Shell Padrão do Usuário

 - ``/etc/group ``: Arquivo de configuração dos grupos.
	 - Coluna 1: Nome do grupo
	 - Coluna 2: Senha do Grupo - A senha real está em ``/etc/gshadow``.
	 - Coluna 3: GID
	 - Coluna 4: Usuários que fazem parte do grupo.

 - ``lastlog ou last``: Histórico de logins do Sistema.

 - ### Comando ```adduser``` 
	Descrição: Utilizado para adicionar usuários ao sistema. O Arquivo `/etc/adduser.conf` carrega as informações padrões de criação. Muito mais completo que o `useradd`.
	 Exemplos:
	 - ```adduser joao ```: Adiciona o user João.
	 - ```adduser --group teste ```: Cria o grupo teste

 - ### Comando ```useradd``` 
	Descrição: Utilizado para adicionar usuários ao sistema. Não cria Diretório Home para o usuário.
	
 - ### Comando ```userdel``` 
	Descrição: Utilizado para remover usuários do sistema.
	Exemplos:
	 - ```userdel joao ```: Remove o user João.
	 - ```userdel -r joao ```: Remove o user João e apaga sua pasta ``/home``.

 - ### Comando ```deluser``` 
	Descrição: Utilizado para remover usuários do sistema.
	 Exemplos:
	 - ```deluser joao ```: Remove o user João.
	 - ```deluser --remove-home joao ```: Remove o user João e apaga sua pasta ``/home``.

 - ### Comando ```groupadd``` 
	Descrição: Utilizado para adicionar grupos ao sistema. Pega o último GID criado e adiciona o proximo ao grupo recém-criado.
	 Exemplos:
	 - ```groupadd users ```: Adiciona o grupo users.

 - ### Comando ```addgroup``` 
	Descrição: Utilizado para adicionar grupos ao sistema. O Arquivo `/etc/adduser.conf` carrega as informações padrões de criação.
	 Exemplos:
	 - ```addgroup users ```: Adiciona o grupo users.
	 - ```addgroup --system users ```: Cria o grupo de sistemas users.

 - ### Comando ```newgrp``` 
	Descrição: Utilizado para adicionar grupos ao sistema.  `newgrp` Serve para entrar em grupos durante o período da sessão.
	 Exemplos:
	 - ```newgrp - users```: Adiciona o grupo users ao usuário logado pelo período da sessão.

 - ### Comando ```delgroup``` 
	Descrição: Utilizado para remover grupos do sistema.
	 Exemplos:
	 - ```delgroup joao ```: Remove o grupo joao

 - ### Comando ```groupdel``` 
	Descrição: Utilizado para remover grupos do sistema.
	Exemplos:
	 - ```groupdel joao ```: Remove o grupo João.

 - ### Comando ```passwd``` 
	Descrição: Utilizado para Alterar senhas de usuários. 
	Parâmetros:
	 - `-e `: Expira a senha
	 - `-l `: Lockout
	 - `-d `: Deleta a senha
	Exemplos:
	 - ```passwd joao ```: Altera a senha do user joao.

 - ### Comando ```gpasswd``` 
	Descrição: Utilizado para definir senhas em grupos. Também pode ser utilizado para adicionar usuários em grupos.
	Parâmetros:
	 - `-a `: Adiciona um usuário à algum grupo.
	 - `-A `: Adiciona um usuário Administrador ao grupo.
	 - `-d `: Remover usuário do grupo.
	 - `-M `: Adiciona um usuário como membro e Admin do grupo.
	Exemplos:
	 - ```gpasswd joao ```: Altera a senha do grupo joao

 - ### Comando ```usermod``` 
	Descrição: Utilizado para modificar um usuário.
	Parâmetros:
	 - `-u `: Modifica o UID
	 - `-g `: Modifica o GID
	 - `-c `: Modifica os comentários do Usuário.
	 - `-d `: Modifica o /home de um usuário.
	 - `-s `: Modifica o Shell do usuário.
	 - `-l `: Modifica o Nome de login do usuário.
	 - `-m `: Move os arquivos do /home antigo do user para o novo especificado.

 - ### Comando ```groupmod``` 
	Descrição: Utilizado para modificar um grupo.

## 12) Gerenciamento de Processos 

 - `PID` = Process Identification
 - Os binários de root sempre são pesquisados primeiramente, depois os do usuário padrão.
 
 - ```& ```: Joga a saída do comando para segundo plano e exibe mensagem após concluído.
 - ```Jobs ```: Lista os comandos rodando em todos os planos.
 - ```Fg 1 ```: Traz o comando para primeiro plano.
 - ```Bg 1 ``` : Joga o comando para o segundo plano.
 - ```CTRL + Z ```: Pausa o programa

 - ### Comando ```ps``` 
	Descrição: Lista processos em execução no sistema.
	Parâmetros do Comando ```ps ```:
	 - ```-a ```: Lista os processos rodando em todos os terminais.
	 - ```-ax ```: Lista todos os processos que possuem um terminal ou não associados à todos os usuários do sistema.
	 - ```-u ```: Lista os usuários à que os processos estão relacionados.
	 - ```-m ```: Detalhes relacionados à uso de memória.
	 - ```-f ```: Traz a listagem em modo de árvore.
	 - ```-e ```: Mostra as variaveis de ambiente utilizadas no comando.
	 - ```-w ```: Exibe a linha completa.
	 - ```-s ```: Sort : Classifica a listagem do PS utilizando um delimitador.

 - ### Comando ```pidof``` 
	Descrição: Retorna o número do PID do comando.
	Parâmetros do Comando ```pidof ```:
	 - ```-s ```: Retorna apenas o PID do primeiro processo.

 - ### Comando ```pstree``` 
	Descrição: Exibe a árvore de processos em execução no sistema.
	Parâmetros do Comando ```pstree ```:
	 - ```-A ```: Usa caracteres ASCII.
	 - ```-c ```: Inclui todas as estruturas.
	 - ```-h ```: Destaca o processo pai do processo atual.
	 - ```-p ```: Exibe o PID junto.
	 - ```-H ```: Pesquisa por PID.
	 - ```-u ```: Mostra o ID do processo.
	 - ```-g ```: Mostra o grupo de execução.

 - ### Comando ```kill``` 
	Descrição: Mata a execução de algum programa.
	Parâmetros Importantes para o comando ```kill ```:
	 - ```%3 ```: Mata o processo rodando no terceiro plano.
	 -  ```%2 ```: Mata o processo rodando no segundo plano.
	 -  ```%1 ```: Mata o processo rodando no primeiro plano.
	 - ```-15 ```: Sinal Terminate: Fecha de forma amigável.
	 - ```-9 ``` :  Sinal Terminate Forçado: Fecha Imediatamente.
	 - ```-HUP ```: Forma de o processo reler os arquivos de configuração, sem reiniciá-lo.

 - ### Comando ```psgrep``` 
	Descrição: Realiza um grep de processos.
	Parâmetros Importantes para o comando ```psgrep ```:
	 - ```-u ```: Especifica o usuário.

 - ### Comando ```pskill``` 
	Descrição: Permite manipular processos através do nome.
	Parâmetros Importantes para o comando ```pskill ```:
	 - ```%3 ```: Mata o processo rodando no terceiro plano.

 - ### Comando ```killall``` 
	Descrição: Mata o processo de acordo com o nome.
	Parâmetros Importantes para o comando ```killall ```:
	 -  ```-u ```: Especifica o usuário.

 - ### Comando ```killall5``` 
	Descrição: Mata todos os processos do sistema.
	Parâmetros Importantes para o comando ```killall5 ```:
	 - ```-9 ```: Mata todos os processos como root.

 - ### Comando ```nohup``` 
	Descrição: Protege um processo em execução contra sinais de execução, como o -9, -15 e etc.


 - ### Comando ```top``` 
	Descrição: Traz o status da execução dos processos de 2 em 2 seg..
	Parâmetros do Comando ```top ```:
	 - ```Letra m ```: Altera a forma como a memória é exibida.
	 - ``1 ``: Altera a forma como os dados de CPU são mostrados.
	 - ``SHIFT + M ``: Classifica por uso de memória.
	 - ```K ```: Para matar processos.
	 - ```D ```: Muda o delay de atualização.
	 - ```SHIFT + W ```: Salva as personalizações.
	 - ```-i ```: Ignora os processos zumbis.
	 - ``-c ``: Mostra a linha de comando do programa.

 - ### Comando ```nice``` 
	Descrição: Determina a prioridade de execução do programa.
	Parâmetros do Comando ```nice ```:
	 - ```-20 ```: Prioridade de execução mais alta.
	 - ``19 ``: Prioridade de execução mais baixa.
	 - ```-n ```: Especifica a prioridade.

 - ### Comando ```renice``` 
	Descrição: Reajusta a Prioridade de execução de algum programa.
	Parâmetros do Comando ```renice ```:
	 - ```-n ```: Numero da prioridade.
	 - ``-g ``: Especifica o Grupo.

 - ### Comando ```Tload``` 
	Descrição: Monitora os processos de uma forma mais gráfica.

 - ### Comando ```Vmstat``` 
	Descrição: Permite visualizar o tempo de execução dos parametros do sistema


## 13) Multiplexadores 

 - ### Multiplexador ```screen``` 
	Descrição: sudo apt install screen.
	Parâmetros do  ```screen ```:
	 - ```-ls ```: Lista todas as screens.
	 - ```-x ```: Reconecta à screen.
	Navegação no  ```screen ```:
	 - ```CTRL + A ```: Atalhos internos:  Pressionar em todos os comandos.
	 - ```W ```: Numero da screen.
	 - ```C ```: Nova Screen.
	 - ```A ```: Alterna entre as screens criadas.
	 - ```0, 1, 3 ```: Vai para a screen definida pelo número passado.
	 - ```D ```: Desconectar da screen.

 - ### Multiplexador ```tmux``` 
	Descrição: sudo apt install tmux.
	Parâmetros do  ```TMUX ```:
	 - ```new ```: Nova Sessão.
	 - ```attach ```: Reconecta à Sessão.
	Navegação no  ```TMUX ```:
	 - ```CTRL + B ```: Tecla de atalho : Pressionar em todos os comandos.
	 - ```C ```: Cria novas telas
	 - ```D ```: Desconecta : Dettach
	 - ```SHIFT + " ```: Divide a tela de forma horizontal.
	 - ```0, 1, 3 ```: Vai para a sessão definida pelo número passado.
	 - ```SHIFT + % ```: Divide a tela de forma vertical.
	 - ```Seta para cima ```: Alterna entre os painéis.

## 14) Permissionamento 

                                                            -rw-rw-r--

||         -                     ||          rw-                       ||          rw-                        ||    r--       ||
||  Tipo do Arquivo   ||  Permissões do Dono  ||  Permissões do Grupo  ||  Outros  ||

### TIPO DE ARQUIVO
	`-` => Arquivo de Texto
	l => Link Simbólico
	d => Diretório
	b => Dispositivo de bloco
	c => Dispositivo de caractere
	s => Socket

### PERMISSÕES - LETRA
	`-` => Ausência da Permissão
	r => Permissão de leitura
	w => Permissão de escrita
	x => Permissão de execução
	t => Stick Bit
	S => SGID/SUID

### PERMISSÕES - USERS
	u => Dono do Arquivo
	g => Grupo Dono do arquivo
	o => Outros
	a => Todos

### PERMISSÕES - OCTAL
	0 => Ausência da Permissão
	4 => Permissão de leitura
	4 => SGID
	2 => Permissão de escrita
	2 => SUID
	1 => Permissão de execução
	1 => Ativar Stick Bit

 - ### Comando ```CHMOD``` 
	Descrição: Modifica as Permissões.
	Parâmetros do  ```CHMOD ```:
	 - ``-R`` = Modo Recursivo

 - ### Comando ```CHOWN``` 
	Descrição: Modifica o Dono/Grupo do arquivo/Diretório.
	Parâmetros do  ```CHOWN ```:
	 - ``-R`` = Modo Recursivo

 - ### Comando ```CHGRP``` 
	Descrição: Modifica o Grupo do arquivo/diretório.
	Parâmetros do  ```CHGRP ```:
	 - ``-R`` = Modo Recursivo

 - ### Comando ```UMASK``` 
	Descrição: Define a permissão padrão de arquivos/diretórios. Através da subtração entre a Permissão padrão e a UMASK, podemos encontrar a permissão padrão do arquivo em questão naquele momento.
	Permissões padrão do  ```UMASK```:
	 - ``666`` = Arquivo
	 - ``777`` = Diretório 

 - ### Bit ```STICKBIT``` 
	Descrição: Quando este Bit está ativo, Apenas o dono do arquivo consegue alterar o arquivo/diretório.

 - ### Bit ```SUID/ SGID``` 
	Descrição: O bit SUID/ SGID é definido para dar permissões temporárias para um usuário executar um programa ou arquivo com as permissões do proprietário do arquivo (geralmente o root).

## 15) Editor VIM

 - `ESC ` : Retorna ao modo de comando.

 - ### Modos de  ```Inserção``` 
	 - `i ` : Inserir na posição do cursor
	 - `I ` : Inserir no inicio da linha
	 - `o ` : Inserir texto na linha abaixo
	 - `O `: Inserir texto na linha acima
	 - `a ` : Inserir um caractere a frente
	 - `A ` : Inserir no final da linha

 - ### Salvando e Saindo
	 - `:w ` : Salvar.
	 - `:q ` : Sair.
	 - `:qa ` : Sair de todos os arquivos abertos.
	 - `:q! `: Sair forçando
	 - `:wq ` : Sair e Salvar
	 - `:x ` : Sair e Salvar
	 - `ZZ ` : Sair e Salvar ( Zair e Zalvar)
	 - `ZQ ` : Sair Sem Salvar (Zair sem Salvar)

 - ### Copiando, Colando e Recortando
	 - `yy ` : Copia.
	 - `p ` : Cola na linha abaixo.
	 - `P ` : Cola na linha acima.
	 - `y8y `: Copiar 8 linhas (yNy - copiar N linhas) 
	 - `dd ` : apaga / recorta a linha inteira
	 - `d8d ` : apaga / recorta 8 linhas inteiras
	 - `dw `: Apaga uma palavra.
	 - `dG ` : Apaga da posiçao atual ate o final do arquivo.
	 - `dgg ` : Apaga da posiçao atual ate o inicio do arquivo.
	 - `cw ` : Recorta uma palavra.
	 - `yw ` : copiar uma palavra.
	 - `x ` : Apaga um caractere (igual ao Delete).
	 - `X ` : Apaga um caractere antes do cursor (igual ao backspace).
	 - `r + N ` : replace: substituir o caractere atual pelo N.

 - ### Modo Visual
	 - `v ` : Visual : Selecionar um pedaço do texto.
	 - `V ` : Visual Line : Selecionar Linhas do texto.
	 - `CTRL + V ` : Visual Block : Selecionar um bloco de texto.

 - ### Voltando e Refazendo
	 - `u ` : Voltar.
	 - `CTRL + Z ` : Refazer

 - ### Buscas e localização
	 - `/STRIGUS ` : Buscar a palavra STRIGUS descendo arquivo
	 - `?STRIGUS ` : Buscar a palavra STRIGUS subindo o arquivo.
	 - `n ` : Continua com a busca.
	 - `N `: Continua com a busca ao contrario.
	 - `gg ` : Vai para a primeira linha.
	 - `G ` : Vai para a última linha.
	 - `M `: Meio da tela.
	 - `H ` : No alto da tela.
	 - `L` : Parte da tela

 - ### Comando ```set```
	 - `:set nlsearch ` : Highlight para as buscas.
	 - `:set number ` : Numera as linhas.
	 - `:set tabstop `: Tamanho do TAB.
	 - `:set expandtab `: Converte o TAB em espaços.
	 - `:set bg=light `: Muda o esquema de cor.
	 - `:e nome_do_arquivo `: Abre outro arquivo.
	 - `:r nome_do_arquivo `: Copia o conteudo do arquivo especificado para o arquivo atual.
	 - `:split nome_do_arquivo ` : Divide a tela com o arquivo especificado.
	 - `:vsplit nome_do_arquivo `: Divide a tela com o arquivo especificado.
	 - `:! comando `: Executa o comando no shell e retorna para o vim.
	 - `!! comando `: Executa e copia/cola o comando para dentro do arquivo.

 - ### Substituindo
	 - `:40s/palavra_antiga/palavra_novo/ `: Substitui na linha 40 a palavra_antiga.
        - `:40,50s/palavra_antiga/palavra_novo/ ` : Substitui entre a linha 40 e a linha 50 a palavra_antiga.
        - `:%s/palavra_antiga/palavra_novo/ ` :  Substitui a palavra_antiga em todo o arquivo - uma palavra por linha.
        - `:%s/palavra_antiga/palavra_novo/g ` : Substitui a palavra_antiga em todo o arquivo.

## 16) Gerenciamento de Pacotes 

 - `DEBIAN `: DPKG & APT
 - `RedHat `: RPM & YUM & DNF

 - ### Comando ```APT ``` 
	Descrição: Realizar a instalação de novos pacotes a partir de um repositório. Instala dependências.
	Parâmetros do Comando ```APT ```:
	 - ```apt install nome_do_pacote ```: Instalar pacotes.
	 - ```apt remove nome_do_pacote ```: Remoção de pacotes.
	 - ```apt purge nome_do_pacote ```: Purge.
	 - ```apt update ```: Buscar pacotes mais recentes.
	 - ```/etc/apt/sources.list e /etc/apt/sources.list.d ```: Localização dos repositorios.
	 - `-f `: Resolve dependências.
	 - `-y `: Aceita opções.

 - ### Comando ```DPKG ``` 
	Descrição: Realizar instalação de pacotes que já estão na máquina(.deb). Não resolve dependências.
	Parâmetros do Comando ```DPKG ```:
	 - ```dpkg -i nome_do_pacote ```: Instalar pacotes.
	 - ```dpkg -I nome_do_pacote ```: Informações do pacote.
	 - `dpkg -l ` : Listar pacotes Instalados.
	 - `dpkg -r nome_do_pacote `: Remover Pacotes.
	 - `dpkg -P nome_do_pacote `: Purge.
	 - `dpkg -S /caminho `: Lista os pacotes relacionados ao caminho.
	 - `dpkg -L nome_do_pacote` : Lista de arquivos relacionados ao Pacote.
	 - `dpkg -s nome_do_pacote` : Status do pacote no sistema.
	 - `dpkg -C nome_do_pacote` : Busca pacotes corrompidos.
	 - ``dpkg --configure nome_do_pacote`` : Reconfigurar pacotes.

 - ### Comando ```RPM ``` 
	Descrição: Gerenciador de pacotes dos sistemas RedHat.
	Parâmetros do Comando ```RPM ```:
	 - ```rpm -ivh nome_do_pacote ```: Instalar pacotes.
	 - ```rpm -Uvh nome_do_pacote ```: Atualização.
	 - `rpm -ev nome_do_pacote ` : Remoção de pacotes.
	 - `rpm -qa nome_do_pacote `: Informações dos pacotes.
	 - `rpm -qi nome_do_pacote `: Informações de um pacote específico.
	 - `rpm -qf /arquivo` : Informações de um pacote a partir de um arquivo.
	 - `rpm -qc nome_do_pacote` : Arquivos de configuração de um serviço.

 - ### Comando ```YUM/DNF ``` 
	Descrição: Realizar a instalação de novos pacotes a partir de um repositório, em sistemas RedHat.
	Parâmetros do Comando ```YUM/DNF ```:
	 - ```yum/dnf install nome_do_pacote ```: Instalar pacotes.
	 - ```yum/dnf update nome_do_pacote```: Atualização.
	 - `yum/dnf remove nome_do_pacote ` : Remoção de pacotes.
	 - `yum/dnf list installed `: Informações dos pacotes.
	 - `yum/dnf info nome_do_pacote` : Informações de um pacote específico.
	 - `yum/dnf provides /arquivo` : Informações de um pacote a partir de um arquivo.
	 - `yum/dnf grouplist` : Lista grupo de aplicativos disponíveis.
	 - `yum/dnf groupinstall nome_do_grupo` : Instalar um grupo de aplicativos.
	 - ``yum/dnf groupremove nome_do_grupo`` : Remover um grupo de aplicativos.
	 - ``yum/dnf repolist `` : Listar repositórios.
	- 
## 17) Gerenciamento de Variáveis de Ambiente 

 - Variaveis de Ambiente são sempre Maiusculas.
 
  - ### O que é?
		 - É um método simples e prático que permite a especificação de opções de configuração de programas sem precisar mexer com arquivos no disco ou opções. Algumas variáveis do GNU/Linux afetam o comportamento de todo o Sistema Operacional, como o idioma utilizado e o path (veja ???) . Variáveis de ambientes são nomes que contém algum valor e tem a forma Nome=Valor. As variáveis de ambiente são individuais para cada usuário do sistema ou consoles virtuais e permanecem residentes na memória RAM até que o usuário saia do sistema (logo-off) ou até que o sistema seja desligado.

 - ### Comando ```echo ``` 
	Descrição: Exibe o conteúdo da variável de ambiente passada.
	Uso: ``echo $NOME_DA_VARIAVEL``
	
 - ### Comando ```set ``` 
	Descrição: Visualiza o conteúdo de todas as variáveis de ambiente..
	Uso: ``set $NOME_DA_VARIAVEL`` ou `set`

 - ### Comando ```printenv ``` 
	Descrição: Visualiza o conteúdo de todas as variáveis de ambiente.
	Uso: ``printenv | grep -i NOME_DA_VARIAVEL`` ou `printenv`

 - ### Comando ```env ``` 
	Descrição: Visualiza o conteúdo de todas as variáveis de ambiente.
	Uso: ``env | grep -i NOME_DA_VARIAVEL`` ou ``env``

 - ### Comando ```export ``` 
	Descrição: Define variáveis de ambiente no formato `NOME=VALOR`. Se a variável possuir espaços, utilizar aspas.
	Uso: 
		``export NOME_DA_VARIAVEL=valor``
		``export NOME_DA_VARIAVEL=valor01:valor02``
		`export NOME_DA_VARIAVEL=" valor01 "`

 - ### Comando ```unset ``` 
	Descrição: Remove a variavel de ambiente.
	Uso: ``unset NOME_DA_VARIAVEL`` 

 - ### Comando ```ALIAS ``` 
	Descrição: Cria apelidos para outros comandos.
	Uso: ``alias nome_desejado="comando"`` 

## 18) Customização de Ambiente 

 - `source /arquivo `: Re-lê o arquivo, dispensando o reboot.
 - `~/.bash_logout `: Arquivo executado pelo bash quando acontece o logout.
 - `~/.bashrc `: Os comandos deste arquivo são executados no momento que o usuário inicia um shell com as características acima. 
 - `~/.bash_profile `: Os comandos deste arquivo são executados no momento que o usuário inicia um shell com as características acima. Os comandos deste arquivo são executados no momento que o usuário inicia um shell com as características acima. Os comandos deste arquivo são executados no momento que o usuário inicia um shell com as características acima. 
 - `/etc/profile `: Este arquivo contém comandos que são executados para todos os usuários do sistema no momento do login. Somente o usuário root pode ter permissão para modificar este arquivo.
 - `/etc/environment `: Armazena as variáveis de ambiente que são exportadas para todo o sistema. Apenas o ROOT pode editá-lo. As variáveis colocadas aqui persistem para todos os usuários após reboot.
 - `~/.hushlogin `: Deve ser colocado no diretório pessoal do usuário. Este arquivo faz o bash pular as mensagens do /etc/motd, número de e-mails, etc. Exibindo imediatamente o aviso de comando após a digitação da senha.
 - `variável $PS1 `: Primeiro texto que aparece na linha de comando.

 - ### Ordem de Carregamento dos arquivos
	Quando é carregado através de um shell que requer login (nome e senha), o bash procura estes arquivos em seqüência e executa os comandos contidos, caso existam:

  	/etc/profile`
	 - `~/.bash_profile`
		 - `~/.bash_login`
			 - `~/.profile`

	Ele interrompe a pesquisa assim que localiza o primeiro arquivo no diretório do usuário (usando a sequência acima). Por exemplo, se você tem o arquivo ~/.bash_login e ~/.bash_profile em seu diretório de usuário, ele processará o /etc/profile e após isto o ~/.bash_profile, mas nunca processará o ~/.bash_login (a menos que o ~/.bash_profile seja apagado ou renomeado).

## 19) Network

 - `DNS `: Configurado em `/etc/resolv.conf` .

- ### Comando ```ip addr show ``` 
	Descrição: Mostra As interfaces e os IPS dentro do sistema.

- ### Comando ```ip addr show dev nome_da_interface``` 
	Descrição: Lista os detalhes da interface especificada.

- ### Comando ```ip addr show lo ``` 
	Descrição: Lista a interface de loopback.

- ### Comando ```ip -6 addr show dev nome_da Interfaceip addr show ``` 
	Descrição: Lista os detalhes IPV6 da interface especificada.

- ### Comando ```ip -4 addr show dev nome_da Interface ``` 
	Descrição: Lista os detalhes IPV4 da interface especificada.

- ### Comando ```ip addr add 192.168.0.215/24 dev enp0s3 ``` 
	Descrição: Atribui o endereço 192.168.0.215 à interface enp0s3.

- ### Comando ```traceroute``` e ```traceroute6``` 
	Descrição: Mostra o caminho até o endereço em IPV4 e IPV6.
	
- ### Comando ```mtr e mtr -6 ``` 
	Descrição: Mesma função do traceroute, porém com mais informações.

- ### Comando ```host ``` 
	Descrição: Traz informações sobre a resolução de DNS - igual ao nslookup. 
	Install: apt install bind9-host
	Exemplos:
	- `host nome_do_endereco`
	- `host -t` : Especifica o tipo do registro(A,AAAA, MX)



## 20) Shell Script

 - Utilizados para automação.
 - Aspas simples não exibem conteúdos de variáveis.
 - `&& ` : Apenas executa o próximo comando se a saída do anterior for 0.
 - `|| `: Apenas executa o próximo comando se a saida do anterior for 1.
 - Para executar comandos externos podemos usar `$(comando_externo)` ou \`comando_externo\` 
