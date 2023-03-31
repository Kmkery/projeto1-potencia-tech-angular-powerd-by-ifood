## Status de um arquivo no GIT

Quando um arquivo é criado, é necessário fazer com que o GIT o reconheça como parte do projeto. Da mesma forma, quando alterado, o GIT precisa saber se as alterações realizadas devem ser consideradas.

Podemos verificar o que o GIT "enxerga" com o comando ``git status``, de acordo com o status, ele irá sugerir adicionar ou desfazer mudanças.

Para adicionar mudanças no projeto (criação do arquivo ou alterações), usamos o comando ``add nomedoarquivo`` e, para rejeitar, usamos o comando ``restore nomedoarquivo``. 

Estas ações compreendem o ciclo de vida dos arquivos no GIT, onde temos basicamente dois estados: _**Untracked**_ e _**Tracked**_. O primeiro refere-se ao estado no qual o GIT ainda não tem conhecimento do arquivo (ele está lá, mas ainda não faz parte do projeto), enquanto o segundo abrange 3 estados: _unmodified_, _modified_ e _staged_.
 - Unmodified -  são os arquivos que não sofreram alteração;
 - Modified - são os arquivos que foram alterados;
 - Staged - são os arquivos que estão se preparando para fazer parte de algum tipo de agrupamento.

O esquema do ciclo basicamente é:

Untracked ==> adicionar arquivo ==> arquivo vai para staged

Tracked ==> editar arquivo ==> arquivo vai para modified ==> logo após arquivo vai para staged

Tracked ==> arquivo unmodified ==> remover arquivo ==> arquivo volta para untracked

Tracked ==> arquivo staged ==> dar commit ==> arquivo vai para unmodified

