# Guia de Git

<h4>Configurações</h4>
    git config --global user.name <"nome">
    git config --global user.email <"email">
    git config user.name
    git config --list

<h4>Inicializar um Repositório<h4>
    //inicializa o rep e observa as mudanças
        git init 
    // printa o que tem dentro
        ls -la

<h4>Visualizar Logs<h4>
    git log
    // Mostra infos a mais
    git log --decorate
    // filtrar por autor
    git log --author="Giovani"
    git shortlog
    // Mostra a árvore
    git log --graph

<h4>Diferença entre versões<h4>
    git diff
    // Apenas os arquivos que foram modificados
    git diff --name-only

<h4>Desfazendo com reset<h4>
    // Cancela tudo o que eu fiz, (somente se eu fzier antes de dar "git add")
    git checkout <nome-do-arquivo>
    // Remove do stage (tira da lista do add, antes de commitar) mas não apaga as mudanças que eu fiz
    git reset HEAD <nome-do-arquivo>
    // "descommit" (volta o commit mas mantem os arquivos em add, prontos para commitar)(necessário passar o hash do commit anterior)
    git reset --soft <hash-do-commit>
    // "descommit" (volta os arquivos antes de add, então será necessário add e commit)(necessário passar o hash do commit anterior)
    git reset --mixed
    // "descommit" (volta tudo para o commit anterior, apagando tudo o que você fez)(necessário passar o hash do commit anterior)(Deve ser usado com muito cuidado, de preferência somente se os commits estiverem local)
    git reset --hard

<h4>Branchs<h4>
    git checkout -b <nome-branch>
    git branch
    git checkout <nome-branch>
    git branch -D <nome-branch>

<h4>.gitignore<h4>
    // Extensão
    *.dart
    // Arquivo
    index.js

<h4>Stash<h4>
    // Ele tira todas as modificações e coloca em uma "pasta"
    git stash
    // Coloca as modificações que estão "guardadas"
    git stash apply
    git stash list
    git stash clear

<h4>Tags<h4>
    // Pelo que eu entendi é criar uma versão do produto/"release"
    git tag -a 1.0.0 -m "anotação"
    // Lista as Tags
    git tag
    git tag -d <nome-tag>

<h4>Revert<h4>
    // Reverte o commit (apaga tudo o que foi feito mas não delta o commit da árvore)(ajuda caso quebre)
    git revert <nome-do-commit>

<h4>Apagar tags e branchs REMOTOS<h4>
    git push origin :<nome-tag>
    git push origin :<nome-branch>