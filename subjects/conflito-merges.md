## Conflito de merges

Um possível caso de conflito acontece quando duas pessoas estão trabalhando com o mesmo arquivo do projeto, cada uma com uma cópia dele. Supondo que ambos farão uma alteração nos mesmos trechos de código e um deles "empurra" a atualização que fez em sua cópia, neste momento, as duas cópias não estarão mais sincronizadas. Se em seguida a outra pessoa tentar "empurrar" a sua cópia com suas atualizações para o repositório, o GitHub verificará a data/horário de ambos os commits, comparará e apontará que este último commit não possui a versão mais recente, que é a da pessoa que commitou primeiro.

Para que o GitHub aceite o commit da segunda pessoa, esta será obrigada a pegar o commit considerado recente, realizar as alterações pretendidas em cima deste e só aí então commitar novamente. 

Este problema descrito chama-se conflito de merge.
Por exemplo, GtHub contém algum arquivo que o repositório local não tem, ao criarmos um no repositório local e tentar empurrar este para o GitHub, o GIT irá avisar para resolver o conflito.

Para resolver estes tipos de problemas, fazemos antes de qualquer coisa o _**pull**_, digitando ``git pull origin master``.

Havendo conflito, o GIT irá apontar e tentar integrar os dois repositórios, indicando o que há de divergente. Os arquivos indicados devem ser abertos e corrigidos (marcações devem ser vistas no conteúdo dos arquivos que ele indicar) para então commitar e empurrar para o GitHub.