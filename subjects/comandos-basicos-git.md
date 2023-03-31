## Comandos básicos no GIT

Alguns comandos básicos diferem de acordo com o sistema operacional usado.

 - Windows:
    - cd (change directory) - entrar em um diretório. Sintaxe: ``cd nome-do-diretorio``;
    - cd / - leva para a base do diretório;
    - cd .. - retorna um nível hierárquico de diretório, isto é, se estivermos em um subdiretório, retornaremos ao diretório pai deste;
    - dir (directory) ou ls - exibe uma lista do conteúdo do diretório corrente;
    - mkdir (make directory) - cria um novo diretório. Sintaxe: ``mkdir nome-do-diretorio``;
    -del (delete) - del apaga o conteúdo de um diretório. Sintaxe: ``del nome-do-diretorio``;
    - rmdir (remove directory) - apaga o diretório e seu conteúdo. Sintaxe: ``rmdir nome-do-diretorio /S /Q``. As flags indicam uma remoção sem confirmação (/S) e exclusão de toda a árvore do diretório (/Q);
    - cls (clear screen) - limpa a tela do terminal;
    - rm (remove) - remove um arquivo. Sintaxe: ``rm nomedoarquivo``.
    
 - Unix/ Linux:
    - ls - exibe uma lista do conteúdo do diretório corrente;
    - rm –rf (remove) – _r_ significa _recursive_. Se existirem subdiretórios dentro do diretório especificado, serão todos deletados juntamente com seus conteúdos. Já o _f_ significa _force_ e serve para forçar a exclusão sem aparecer nenhum tipo de confirmação. Sintaxe: ``rm -rf nome-do-diretorio``
    - clear - limpa a tela do terminal. Possui um atalho, que é apertar crtl+l;

 - Outros úteis:

    - Para autocompletar, digitamos a primeira letra do nome que queremos e apertamos tab
    - Se digitarmos ``echo hello``, o terminal irá exibir _"hello"_. Se digitarmos ``echo hello > hello.txt``, ela vai pegar a saída (_"hello"_) e, com o redirecionador de fluxo (``>``) irá criar o arquivo _hello.txt_ e armazená-lo dentro deste.   


### Usando o GIT e criando um commit

 - Criar uma pasta para o projeto;
 - Com o GIT acessando esta pasta, inserir o comando ``git init`` para iniciar o projeto. Este comando irá criar uma pasta oculta (_.git_) que é uma pasta gerencial do GIT. Para conseguir ver esta pasta, usamos ``ls -a``; 
 - Sendo o primeiro uso do GIT no projeto, precisamos configurar o email e nome do usuário que está criando:
   - ``git config --global user.email endereço-email`` (podemos setar apenas para o repositório ou global);
   - ``git config --global user.name nome-usuário`` (inserimos o nome do user);
   
   O nome e endereço de email não precisa necessariamente ser os da conta do GitHub, porém, uma vez que criarmos os arquivos com as informações setadas, mas é interessante que sejam os mesmos, pois mesmo que posteriormente email e user sejam alterados nas configurações, o trabalho continuará creditado ao user e email creditado inicialmente.
   Mesmo assim, caso desejemos alterar estas configurações, devemos inserir ``git config –global –unset user.email`` e ``git config –global –unset user.name`` para resetar e depois reinserir os novos email/user com o mesmo procedimento realizado na primeira configuração destes. Para conferir quais configurações foram feitas no GIT, digitar ``git config --list``;

 - Criar um arquivo com o nome de _README.md_, nele inserir as informações pertinentes ao projeto. Este arquivo deve ficar do lado de fora da pasta do projeto. A extensão ``.md`` refere-se ao tipo _Markdown_, que é uma forma "mais humana" de se escrever HTML. Além de tipografia básica, o arquivo também suporta emojis. Mais informações sobre o tipo de formatação usado podem ser encontradas no [GitHub Docs](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax); 

  - Criar os demais documentos (arquivos, diretórios) que fazem parte do projeto;

 - Após todas as etapas acima, é preciso fazer com que o GIT "conheça" o projeto. Pode-se fazer um a um, indicando o nome de cada arquivo sequencialmente (por exemplo, ``git add README.md pastaprojeto/`` está commitando o arquivo README e a pasta do projeto), ou inserindo o comando ``git add *`` (o asterisco significa que deve pegar tudo o que existe dentro do projeto e adicionar para futuro commit);
 - Adicionar uma descrição ao commit usando ``git commit -m "descrição do commit"``. Esta etapa irá gerar informações importantes sobre o commit.
  
   Em cada alteração ou criação dos arquivos/pastas, é necessário aplicar o comando ``add`` e depois o ``commit``.


