## Instalação do GIT

Precisamos ir até o [site oficial do GIT](https://www.git-scm.com), clicar em download e escolher a versão apropriada para o sistema operacional utilizado. Dependendo do sistema operacional, o processo de instalação muda um pouco. 


### Sistema Windows

Após baixar o software e iniciar a instalação, **atentar-se para os campos que devem ser alterados**:

 1. Observar se as opções _"Git Bash Here"_ e _"Git GUI Here"_ estão marcadas (se não estiverem, devem ser marcadas);
 2. Escolher _"Git default editor"_ (por vezes, poderá haver a necessidade de uso de um editor de texo);
 3. É interessante deixar _"override the default branch name for new repositories"_ marcado, o termo faz referência ao branch principal de repositório, antes nomeado como _master_ e agora é chamado de _main_;
 4. Em _"Configuring the line ending conversions"_, atentar para a escolha de acordo com o sistema operacional usado, no caso _"checkout windows"_.


### Sistemas Linux

A instalação é feita via linha de comando indicado na página do site do GIT, devendo apenas acrescentar _``sudo``_ no começo e _``-y``_ no fim da linha ( o _y_ confirma todas as etapas).
Depois do término da instalação, isnerir o comando _``sudo apt update``_ para atualizar informações de pacotes e, após finalizar este, inserir o comando de instalar _``sudo apt install git``_. 

### Sistemas MacOS

Para instalar o GIT, recomenda-se optar por gerenciador de pacotes, sendo sugerido o _Homebrew_. Neste caso, inserir no terminal _``brew install git``_ para instalar o 
GIT. 
