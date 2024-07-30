# Anotações do Curso de Git e GitHub

Este arquivo tem formato Markdown, as sintaxe basicas estão no link a seguir: [Clique aqui para acessar o o guia de sintaxe básica](https://www.markdownguide.org/basic-syntax/)

## Introdução
Esta é a primeira versão das anotações realizadas durante o curso Git e GitHub, atualizações serão realizadas ao decorrer do tempo.

## Comandos GIT Bash
**openssl sha1 texto.txt** - utilizado para gerar hash do um arquivo, informação e no caso objeto internos do git.

**ssh-keygen -t ed25519 -C <email-github-user>** - utilizado para gera um par de chaves para acessar um github específico, caminho padrão onde a chave é gerada /c/Users/<USER>/.ssh/.

**eval $(ssh-agent -s)** - comando utilizado para iniciar o ssh agent.

**ssh-add <priv-key-name>** - utilizado para passar a chave privada a ser usada na comunicação ssh.

**git init** - para iniciar o repositório do git, ou seja, ao iniciar um diretório que enviaremos os dados para o github, damos o comando git init para iniciá-lo no Git.
Para os primeiros usos, precisamos colocar um e-mail e apelido, pois os commit necessitam de um autor, para isso usamos dois comandos:
- **git config --global user.email "<EMAIL-GITHUB>"**
- **git config --global user.name "<NOME-USER-GITHUB>"**

**git add** - para mover arquivos e dar início ao versionamento, informa que os arquivos, ou arquivo único será enviado para o Github (tira a snapshot do projeto).

**git commit** - para dar os commits, nomeia os envios ao github, o que ajuda na controle de versionamento. O editor padrão abrirá e deve esperar pela edição da mensagem do commit.
Obs. Após modificar o projeto, sempre usar git add e git commit para atualizar os metadados.

**git commit -m "<MENSAGEM>"** - inclui as alterações realizadas dentro da estrutura de arquivos criadas, que recebe uma mensagem (descrição do commit) para dar sentido ao que foi comitado. 

**git status** - ajuda a entender qual status o arquivo ou projeto está.

**git config --list** - Para apresentar as configurações atuais do Git, é recomendado que o comando seja utilizado sempre que um novo computador já com git for utilizado.

**git config --global --unset user.email** - Utilizado para retirar o email que está configurado.

**git config --global --unset user.name** - Utilizado para retirar o nome que está configurado.

**git remote add origin <link do repositório>** - Comando utilizado para adicionar um repositório remoto. ex GitHub. O origin representa apenas um alias (Apelido) para no futuro não utilizar o link do repositório no GitHub sim o alias.

**git remote -v** - lista os diretórios remotos cadastrados no diretório que for rodado o comando.

**git remote set-url origin <LINK-REPOSITORIO>** - Cadastra o link do diretório remoto.

**git push -u <ALIAS-LINK-REMOTE-REPOSITORY> <BRANCH>** - comando utilizado para enviar projeto para o diretório remoto.

**git push -u origin --all** -  para subir todas as branches para o repositório remoto.

**git pull <ALIAS-LINK-REMOTE-REPOSITORY> <BRANCH>** - utilizado para puxar o repositório que apresentou conflito, será baixado com informações para entender o que está de diferente no código.

**git branch** -  utilizado para apresentar as branches disponíveis e atual, o * indica a branch atual.

**git checkout <BRANCHE-NAME>** - checkout se move entre branches.

**git checkout -b <NEW-BRANCHE-NAME>** - checkout se move entre branches e ao colocar o parâmetro -b criamos uma branche e nos movemos imediatamente para ela.

**git merge <SECUNDARY-BRANCHE-NAME>** - Comando realizado a partir da branche principal, para unir o commit que já foi validado na branche principal.

**git branch -m <NEW-NAME-FOR-BRANCH>** - Para renomear uma branch existente, para isso precisamos acessá-la e realizar o comando.

**git branch -m <BRANCH-NAME> <NEW-NAME-FOR-BRANCH>** - para renomear uma branch a partir da branch principal do projeto.

**git branch -d <BRANCH-NAME>** - para deletar uma branch.

**git switch -c feature2** - switch se move entre branches e ao colocar o parâmetro -c criamos uma branche e nos movemos imediatamente para ela.

**git stash save "ADICIONAR-CONTEXTO"** - Utilizado para não carregar sujeira de uma branch para outra, se realizarmos atenas o git stash o git criara uma sigla WIP (Work in Progress), nome da branch e um valor de hash.

**git stash list** - para listar as stash disponíveis na branch.

**git stash apply** - Aplicar o último stash.

**git stash pop** - Aplicar e remover o último stash.

**git stash apply stash@{1}** - Aplicar um stash específico.

**git stash drop stash@{1}** - Remover um stash específico.

**git stash clear** - Limpar todos os stashs.

**git log** - para listar o histórico de commits, podemos direcionar a leitura ao apontar para diretórios ou arquivos específicos. ex **git log <DIR/FILE>**

**git log --oneline** - Traz as informações de forma resumida.

**git log --graph** - traz o retorno um pouco mais ilustrado.

**gitk** - abre uma ferramenta gráfica no windows.

**git reset <COMMIT-HASH>** - utilizado para reverter o commit até o commit que teve o hash declarado.

**git reset HEAD~<NUMBER-COMMITS-RETURN>** - Comando utilizado para voltar a quantidade de commits declarando um numeral em **<NUMBER-COMMITS-RETURN>**

**git reset --soft HEAD~1** - Reverte o commit e trás os arquivos para o ponto onde após dar o comando git add.

**git reset --mixed HEAD~1** - Reverte o commit e coloca os arquivos no status de untracked.

**git reset --hard HEAD~1** - Reverte o commit e deletando os arquivos que foram commitados.

**git revert HEAD~1** - Em poucas palavras o revert gera um commit revertendo para um commit anterior declarado.

**git config --global core.editor "code --wait"** - para definir o VS Code como editor padrão.

**git config --global --unset core.editor** - para limpar o editor utilizado.

**vim .gitignore** - este arquivo armazena informações no formato de expressões regulares, do que deve ser ignorado pelo git, quais padrões de arquivos que serão ignorados.