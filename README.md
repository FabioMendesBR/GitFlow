# GitFlow


Git flow
fluxo de trabalho organizado através de implementação de regras de "conduta" a serem seguidas no decorrer das alterações no projeto.

Git é um sistema de controle de versão distribuído, (VCS - Version Control System).
https://git-scm.com/

<h2>qualidades:</h2>


-Centralizar Armazenamento (repositorio em rede);
-clone do projeto local (repositorio local);
-Trabalhar simultaneamente;
-Versionar
-Contar a historia do projeto;

<img src="estrutura.jpg">



cria um repositorio vazio.
>git init

mostra a arvore (pacote deve ser instalado)
>tree .git/


<img src="areas.jpg">

working directory

staging area

repository

>git status

>git add

adiciona todos os aquivos pendentes para a area "staging area".(-a = all)
>git add -A
 

adiciona somente o aquivo mencionado para a "staging area".
>git add "nomedoarquivo"

>git commit

>git commit -m "descricao da mudanca"
(-m = message)


lista dos commits realizados
>git log

lista dos commits realizados em ordem.
>git log --oneline

lista dos commits realizados em ordem do branch ativo
>git log --oneline --decorate

lista dos commits realizados em ordem de todos os branch
>git log --oneline --decorate --all

lista dos commits realizados em ordem de todos os branch mostrando a separação dos arquivos por branchs
>git log --oneline --decorate --all --graph


Branch é uma linha de desenvolvimento, permite  trabalhar em paralelo para posterior união (merge).

lista os branchs existentes.
>git branch

por padrao é criado apenas o master.

cria um novo branch
>git branch "nome do novo branch"

Cria a estrutura basica de branch para implementação do conceito "git flow".
>git flow init


<pre>
$ git flow init
Which branch should be used for bringing forth production releases?
   - master
Branch name for production releases: [master]
Branch name for "next release" development: [develop]

How to name your supporting branch prefixes?
Feature branches? [feature/]
Bugfix branches? [bugfix/]
Release branches? [release/]
Hotfix branches? [hotfix/]
Support branches? [support/]
Version tag prefix? []
Hooks and filters directory? [C:/#git/GitFlow/.git/hooks]
</pre>


Branch basicos:
-master
-develop
-feature
-release
-bugfix
-hotfix


move o "Head" (branch ativo) para o branch mencionado.
>git chechout "branch"


cria o branch e direciona o "head" para ele.
>git checkout - b "branch"

MERGE:

>git merge "branch"


apaga (deleta) o branch mencionado. (-d = delete)
>git branch -d "branch"




Stash (esconderijo)
é uma area para armazenar codigo sem a necessidade de realizar um commit.
permitido mudar de branch ou realizar outras operações de forma organizada.


>git stash list

isola o arquivo do projeto
>git stash save "nome do arquivo"

trás de volta para o projeto o arquvo
>git stash apply stash@{x}

exclui o arquivo do stash e do projeto.
>git stash drop stash@{x}

desempilha o arquivo sem necessidade de drop.
>git stash pop

cria uma branch para armazenar os arquivos "slashs"
>git stash branch 'nome da branch"



 Açoes Remotas: Pull e Push

PUSH

>git push


PULL
o “git pull” carrega as mudanças do repositório remoto na branch que você se encontra para o local. Durante o “git pull” você vai ser alertado se existem conflitos entre os seus commits locais e os remotos e pedir para que eles sejam solucionados por merge manual ou automático.

>git push origin master





>ls
lista arquivos e diretorio corrente (do branchatual)
>ls -la

>cat .arquivo

De forma resumida: “git fetch” atualiza o seu repositório local em relação a todas mudanças no repositório remoto sem baixa-las. Ou seja, ao dar o “git fetch” você consegue saber se existem mudanças e como elas afetam as suas mudanças locais.

Git - git-fetch Documentation

Já o “git pull” carrega as mudanças do repositório remoto na branch que você se encontra para o local. Durante o “git pull” você vai ser alertado se existem conflitos entre os seus commits locais e os remotos e pedir para que eles sejam solucionados por merge manual ou automático (dependendo da sua ferramenta de versionamento).

Git - git-pull Documentation



referencias:
https://www.youtube.com/playlist?list=PLQCmSnNFVYnRdgxOC_ufH58NxlmM6VYd1
https://www.youtube.com/watch?v=YnVnFanIAzU&list=PLucm8g_ezqNq0dOgug6paAkH0AQSJPlIe


