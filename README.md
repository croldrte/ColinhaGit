## Tipos de commits

- `feat`- Indica que seu trecho de código está incluindo um **novo recurso** (se relaciona com o minor do versionamento semântico).

- `fix` - Indica que seu trecho de código commitado está **solucionando um problema** (bug fix), (se relaciona com o patch do versionamento semântico).

- `docs` - Indica que houve **mudanças na documentação**, como por exemplo no README do seu repositório (não inclui alterações em código).

- `test` - Utilizado quando são realizadas **alterações em testes**, seja criando, alterando ou excluindo testes unitários (não inclui alterações em código).

- `build` - Utilizado quando são realizadas modificações em **arquivos de build e dependências**.

- `perf` - Serve para identificar quaisquer alterações de código que estejam relacionadas a **performance**.

- `style` - Indica que houve alterações referentes a **formatações de código**, semicolons, trailing spaces, lint... (não inclui alterações em código).

- `refactor` - Refere-se a mudanças devido a **refatorações que não alterem sua funcionalidade**, como por exemplo, uma alteração no formato como é processada determinada parte da tela, mas que manteve a mesma funcionalidade, ou melhorias de performance devido a um code review.

- `chore` - Indica **atualizações de tarefas** de build, configurações de administrador, pacotes... como por exemplo adicionar um pacote no gitignore (não inclui alterações em código).

- `ci` - Indica mudanças relacionadas a **integração contínua** (_continuous integration_).

- `raw` - Indica mudanças relacionadas a arquivos de configurações, dados, features, parâmetros.

- `cleanup` - Utilizado para remover código comentado, trechos desnecessários ou qualquer outra forma de limpeza do código-fonte, visando aprimorar sua legibilidade e manutenibilidade.

- `remove` - Indica a exclusão de arquivos, diretórios ou funcionalidades obsoletas ou não utilizadas, reduzindo o tamanho e a complexidade do projeto e mantendo-o mais organizado.

## Principais comandos

- `cmdkey /delete:LegacyGeneric:target=git:https://github.com` - Exclui todas as credenciais armazenadas anteriormente no computador.

- `git config --global user.name "<nome>"` - Configura o nome de usuário para todos os repositórios Git no computador.

- `git config --global user.email "<e-mail>"` - Configura o e-mail do usuário para todos os repositórios Git no computador.

- `git clone <url do repositório>` - Clona um repositório remoto existente no GitHub para o seu ambiente local.

- `git init` - Inicializa um novo repositório Git no diretório atual.

- `git add .` - Adiciona todos os arquivos e alterações no diretório atual para a área de stage (preparando-os para o commit).

- `git commit -m "<mensagem do commit>"` - Registra as alterações adicionadas na área de stage com uma mensagem descritiva sobre o que foi modificado.

- `git branch -M main` - Renomeia a branch atual (master) para main. O -M é usado para forçar a renomeação, movendo a branch se necessário.

- `git remote add origin <url do repositório>` - Conecta seu repositório local a um repositório remoto.

- `git push -u origin <branch>` - Envia os commits da branch atual do repositório local para o repositório remoto e define a branch como padrão para futuros pushes e pulls.

- `git diff` - Mostra as modificações que você fez localmente, mas ainda não comitou.

- `git fetch` - Busca todas as atualizações do repositório remoto sem integrá-las à branch atual. Isso atualiza as referências remotas.

- `git pull` - Atualiza o repositório local com as mudanças do repositório remoto.

- `git push --force-with-lease` - Forma mais segura de forçar o envio de alterações locais para o repositório remoto. Verifica se não houve alterações feitas por outros colaboradores desde sua última atualização local, evitando sobrescrever acidentalmente o trabalho de outros.

- `git revert <id do commit>` - Cria um novo commit que desfaz as alterações feitas pelo commit especificado, preservando o histórico. Útil para desfazer mudanças de forma segura sem reescrever o histórico.

- `git reset --hard <id do commit>` - Redefine o repositório para o estado do commit especificado, apagando todas as mudanças feitas após esse commit. Ideal para uso local. Para sincronizar remotamente, use `git push --force-with-lease` posteriormente.

- `git commit --amend -m "<mensagem reescrita>"` - Altera a mensagem do último commit. Após usar este comando, sincronize remotamente com `git push --force-with-lease`.

- `git cherry-pick <hash do commit>` - Utilizado para obter um commit específico. Exemplo de uso: Imagine que você tenha duas branchs (main) e (develop) e na segunda você tem 3 commits mas deseja apenas pegar o primeiro commit dela, com o uso de cherry-pick você pode.

- `git rebase -i HEAD~<N>` - Permite modificar os últimos "N" commits. No editor, substitua `pick` por:

  - `reword` - Edita a mensagem do commit.
  - `edit` - Faz alterações no commit.
  - `squash (s)` - Mescla o commit com o anterior.
  - `drop` - Remove o commit.
  - `fixup (f)` - Mescla o commit ao anterior, descartando sua mensagem.

Caso haja conflitos, resolva-os e continue com `git rebase --continue`.
