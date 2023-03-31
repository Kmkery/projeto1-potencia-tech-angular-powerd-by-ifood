## Como o GIT funciona

O **GIT** é um CLI (command line interface) o que significa que funciona por linhas de comandos. Devido à forma como ele foi projetado, o sistema é capaz de distribuir de forma fiel e segura o conteúdo existente, sendo muitíssimo difícil alguém conseguir realizar uma alteração de forma indevida, pois cada altaração gera um registro único.

O que permite que o GIT execute o versionamento de código de forma segura é o **SHA1**, conjunto de funções criptográficas que foi desenvolvida pela NSA (Agência de Segurança Nacional dos EUA). O SHA1 toma um arquivo e "embaralha" de forma específica, gerando neste processo um conjunto de caracteres (identificador) de 40 dígitos, único. Se o arquivo for alterado e o algorítmo for novamente executado nele, o conjunto de caracteres será diferente, em outras palavras, é possível gerenciar as alterações realizadas nele.

### Objetos internos do GIT

O GIT possui objetos internos. 

**Blobs** são objetos que são blocos básicos de composição, onde os arquivos ficam guardados juntamente com seus metadados. 

**Trees** (árvores) são objetos que armazenam blobs e apontam para eles ou para outras _trees_, além de armazenar o nome dos arquivos. São responsáveis por montar toda a estrutura de localização dos arquivos. 

**Commits** são objetos cuja função é unir tudo o que há na árvore. Uma mudança no blob irá refletir em toda a cadeia e o SHA1 de um _commit_ é o identificador de toda esta informação.
    
