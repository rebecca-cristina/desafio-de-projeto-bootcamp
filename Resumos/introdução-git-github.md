## Introdução ao Git e GitHub



### Definições básicas:

#### GIT 

O GIT é um sistema de versionamento de arquivos.

Em outras palavras, um sistema que salva todas as versões decorrentes das alterações já realizadas naquele arquivo.

Nos permite ter o controle de tudo aquilo que já foi escrito, apagado, etc. Inclusive, permite a modificação feita por outros colaboradores, sem dar problema e sem que se perca a origem.

[Download Git](https://git-scm.com/downloads)

#### GitHub

É uma plataforma para você poder hospedar esses arquivos que você está utilizando no GIT.

Nessa plataforma você pode trabalhar em grupo, clonar um repositório, colaborar trabalhando em cima de um projeto em andamento ou finalizado, etc.

[Sign Up GitHub](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home)

### Funcionamento do GIT

#### SHA1 - Secure Hash Algorithm

Projetado pela NSA - _Agência de Segurança Nacional dos EUA_, ele é um conjunto de funções hash criptográficas. Basicamente um algoritmo que vai pegar meu arquivo, seja foto, imagem, frase e vai embaralhar ele de uma forma muito específica.

A encriptação realizada gera um conjunto de 40 caracteres identificador e único. Caso o arquivo seja alterado, o SHA1 passa a ser outro, porém, caso haja uma nova alteração retornando ao primeiro modelo, o SHA1 volta a ser a mesma chave da primeira vez.

Exemplo: O SHA1 do nome **Brian** seria: 75c450c3f963befb912ee79f0b63e563652780f0;

Já o SHA1 de **Brain** seria: 8b9248a4e0b64bbccf82e7723a3734279bf9bbc4. Como vocês podem ver, essas duas saídas são bastante diferentes, apesar do fato de que a diferença entre o nome Brian e Brain são apenas a ordem das vogais.

Se inserimos cada palavra deste artigo no gerador, vamos ter este hash: db8471259c92193d6072c51ce61dacfdda0ac3d7. Isso é cerca de 1621 caracteres (com espaços incluídos) condensados em uma produção de 40 caracteres, o mesmo comprimento que tivemos com o nome de 5 letras.

#### Objetos internos do Git

1. Blobs

2. Tree

3. Commits

   

   1. **Blobs**

   Blobs contém metadados, que por sua vez, fornece o tipo de objeto e tamanho da string. 

   São arquivos em texto, binário, fotos, etc, onde, em cada arquivo é gerado um SHA1 com as informações de objeto e tamanho.  

   2. **Tree**

   Tree é um objeto que também contém metadados e que encapsula esse comportamento de diretórios, usado para apontar para diretórios que contém arquivos e por consequência, apontam para arquivos também. Melhor dizendo, as trees armazenam blobs. 

   Elas apontam para o blob (que contém o SHA1) e também para outras trees e guardam o nome do arquivo. Uma vez que os diretórios, dentro de um sistema operacional, podem conter outros diretórios, faz sentido que o GIT use um tipo de objeto abrangente como as trees.

   As trees tem um SHA1 desse metadado. Se houver qualquer alteração nas blobs, estaremos mudando toda a encriptação dessa estrutura, então a alteração do SHA1 da blob, altera, por consequência, o SHA1 das trees. 

   3. **Commit**
   
   Commit é um objeto que vai fazer a junção de tudo, vai dar sentido para a alteração sendo realizada. 
   
   O SHA1 desse commit é o hash de toda essa informação. Melhor dizendo, o SHA1 desse commit é a compactação de todas essas informações.
   
    Hash é uma função de hash criptográfico, muitas vezes é conhecida simplesmente como hash – é um algoritmo matemático que transforma qualquer bloco de dados em uma série de caracteres de comprimento fixo. Independentemente do comprimento dos dados de entrada, o mesmo tipo de hash de saída será sempre um valor hash do mesmo comprimento, ou seja, independentemente da quantidade de caracteres desse dado, ele sempre vai gerar uma chave de 40 dígitos, nunca vamos ter 2 hash iguais.
   
   Os commits carregam as informações das trees, do parente, do autor, da data e também possui uma mensagem que serve para especificar os arquivos que estão dentro.
   
   [Como escrever boas mensagens de commit](https://gist.github.com/lucasmezencio/3835117)
   
   
   
   
   
   ![a presentation about git, the stupid content tracker, for the novice and  the semi-experienced git user : r/git](https://external-preview.redd.it/3Yr6x4IsjvrMzkoX-iFkfROiU-jm7F6ycMvXmabnKT8.jpg?auto=webp&s=e40d18e3f6437bd0e8aab95376ed02c6f2486eb8)
   
   
   
   #### Tracked and Untracked
   
   **Untracked** são arquivos não rastreáveis pelo GIT
   
   Dentro de **Tracked** (arquivos que são rastreáveis pelo GIT), ele pode se subdivir em 3 estágios diferentes: Unmodified, Modified e Staged.
   
   **Unmodified** são arquivos que não sofreram modificação.
   
   **Modified** é o oposto, que foi submetido à alguma alteração.
   
   **Staged** é quando um arquivo está pronto para ser commitado. Ele está preparado para fazer parte de outro tipo de agrupamento.
   
   
   
   Considere cada setinha da imagem abaixo como fases. Em seguida tem as explicações:
   
   
   
   ![Git - Recording Changes to the Repository](https://git-scm.com/book/en/v2/images/lifecycle.png)
   
   
   
   1ª fase - Quando criamos um arquivo recetemente, ele está Untracked (O GIT não sabe da existência). Assim que rodamos o segundo comando (git add), ele moveu de um arquivo desconhecido para Staged (rastreável e pronto para ser commitado);
   
   2ª fase - Os arquivos Unmodified ainda não sofreu modificação, quando ele é alterado, muda automaticamente de Unmodified para Modified (compara o SHA1 dos arquivos e percebe que houve modificação);
   
   3ª fase - Quando rodamos novamente o comando git add, ele vai para a área de Staged (preparado para fazer parte de um outro grupo).
   
   4ª fase - Se um arquivo Unmodified for excluído, ele volta ao estágio Untracked.
   
   5ª fase - Para os arquivos que estão em Stage, damos um Commit. 
   
   Envelopamos todas essas informações, dando significância. Ele retorna esses arquivos para a fase de Unmodified para começar o ciclo novamente.
   
   #### Repositório
   
   O GIT é um sistema distribuído, então, temos o ambiente do servidor (GitHub) e o ambiente de desenvolvimento (local).
   
   As alterações que são feitas na máquina, não repercurte imediatamente para o repositório remoto, a não ser que a gente execute um conjunto de códigos específicos, ai empurramos a alteração do repositório local, para o servidor.
   
   Os arquivos vão estar se alterando entre o repositório de trabalho e a área Staged, a medida que você vai alterando, adicionando novos arquivos, etc.
   
   Quando fazemos um Commit, ele passa a integrar o repositório local, que por sua vez, pode ser empurrado para um repositório remoto.
   
   
   
   ![Git Essentials - CodeNewbie Community](https://community.codenewbie.org/images/lURlZgymWj62CHhOEy5ZjkHt8c1lv4WGQDpXSSseMZA/w:880/mb:500000/aHR0cHM6Ly9kZXYt/dG8tdXBsb2Fkcy5z/My5hbWF6b25hd3Mu/Y29tL3VwbG9hZHMv/YXJ0aWNsZXMvY3Jq/Z2JvcGJ2bmNlbTFy/YW9qeTQuanBn)
   
   

#### README

Um arquivo nomeado, por convenção, como README, contém informação sobre os arquivos num diretório e é comummente distribuído com softwares de computador.

Literalmente "leia-me" antes de abrir o repositório. Os README contam a hitória daquele repositório e expõe para aquela pessoa o que ela encontrará ao abrir a pasta.

Quando o GitHub encontra um arquivo com extensão Markdown - _.md_ (uma linguagem de marcação utilizada para converter o texto em um HTML válido, forma mais humana de se escrever), ele formata aquele arquivo e expõe para pessoa que estiver acessando aquela pasta em específico em uma forma mais arranjada.

##### Remote

É você fazer com que o repositório da máquina, também vá para a plataforma GitHub

##### Push

"Empurrar" um Commit para o servidor

##### Pull

"Puxar" - o contrário de push. Puxa o que está no repositório do GitHub para sua máquina.

##### Main ou Master

Linha cronológica principal (antigamente mais conhecida como Master, atualmente está sendo utilizado a expressão Main)

##### Branch 

"Ramo"

Temos a linha cronológica principal, e quando vamos criar alguma funcionalidade (um botão, calendário, etc), nós damos o nome de branch (ramo-ramificações)

##### Merge

"Mesclar" - Junção da branch que você tava criando alternativamente, com um branch principal.

### Primeiros comandos com o GIT

- Iniciar o GIT
- Iniciar o versionamento
- Criar commit

1. git init (inicializa o repositório)
2. git add (move o arquivo para a área de staged, marcando-o para inclusão no próximo commit)
3. git commit

#### Chave SSH e Tokens

A chave SSH é a forma de estabeler uma conexão segura e encripitada entre duas máquinas, os tokens são os acessos com usuário e senha.

##### --> Criando uma chave SSH

Comandos:

- **ssh-keygen -t ed25519 - C <seu email>**

A chave pública e privada será gerada dentro da pasta oculta .ssh que por padrão, estará alocada dentro da sua pasta pessoal, no diretório home (Linux) ou Users (Windows). 

-digitar sua senha

**--> Buscar as chaves**

Comandos:

- **cd /c/Users/<usuário>/ .ssh/**

-  *ls** (id_ed25519 - _pessoal_ / id_ed25519.pub - _pública_)

-  **cat id_ed25519.pub** (chave pública que iremos expor no GitHub)

##### --> Inicializando o SSH agent

Comandos:

- **eval $(ssh-agent -s)**

O agente foi criado, agora é necessário atribuir a chave ao agente.

##### --> Entregar a chave para agent

Comandos:

- **ssh-add id_ed25519** (chave privada para que, toda vez que chegar uma criptografia com a chave pública, ele vai usar nossa chave privada para descriotigrafar essa chave)

  -digitar senha

__________________________________________________________________________________________________________________

###### Comandos anotados durante a aula:

**cd <nome da pasta>** - entra na pasta

**cd ..** - retrocede para a base anterior

**dir** ou **ls** (no Git) - lista os arquivos contidos naquele local

**ls -a** - lista os arquivos ocultos

**cls** ou **ctrl+L** (no GIT) - limpa o terminal de trabalho

**echo <nome arquivo> > <nome arquivo>.<tipo do arquivo.txt.md.etc> **- cria um arquivo

**del <nome da pasta>** (S) - deleta um arquivo

**mkdir <nome da pasta>** - cria pasta

**rmdir <nome da pasta>** - remove uma  pasta com todos os arquivos que estão lá dentro

**mv <nome arquivo> > <nome pasta>** ou **mv <nome arquivo> ./ <nome pasta>** - mover arquivo para dentro de uma pasta 

**pwd** - mostra o caminho completo

**cat id_ed25519.pub** - mostra sua chave publica

**git status** - vai dizer se aquele arquivo está Stage, Modified, etc.

**git init** - inicializa um repositório

**git restore --staged <nome arquivo>** - para retornar para unstaged

**git commit -m "string (mensagem)"** - cria pasta receitas, move arquivo para receitas

**git add <nome do arquivo>** - adiciona esse arquivo em específico na área de Staged

**git add *** , **git add .** ou **git add +** - pega tudo que foi modificado, tudo que está no diretório de trabalho e adiciona para o Staged

**git remote -v** - vai listar as listas de repositórios remotos que tenho cadastrado

**git push origin master** - empurrar commits para o servidor

**git pull** - puxar um arquivo do servidor

**git remote add origin <URL do GitHub>** - aponta para o repositório remoto que iremos enviar os arquivos

**git remote rm origin <URL do GitHub>**  - estorna processo da inserção da URL informada

**git clone <URL>** - clonar um repositório do servidor para o ambiente de desenvolvimento

**git branch -M <main> **- renomear de Master para Main

**git branch -M <master>** - renomear de Main para Master

**git config --global -- unset <algo a ser modificado>** - para alterar algum dado configurado

**git config --global user.email <seu email>**- para configurar o seu e-mail

**git config --global user.name <seu nome>** - para configurar seu nome

**git config --list** - traz a lista de todas as configurações que estão no seu GIT

###### Atalhos teclado

TAB - tem a função de autocompletar a palavra

Seta para cima - navega no histórico de comandos que ja foram executados nesse terminal

Ctrl+Shift+V - colar algo no terminal

[Comandos básicos do Git](https://gist.github.com/rebecca-cristina/1a1700c47e34751245f6ff19035a7477)



