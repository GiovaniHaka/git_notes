#Guia de Git

Configurações:
    git config --global user.name "Giovani Haka"
    git config --global user.email "haka.giovani@gmail.com"
    git config user.name
    git config --list

Inicializar um Repositório:
    //inicializa o rep e observa as mudanças
        git init 
    // printa o que tem dentro
        ls -la

Visualizar Logs
    git log
    // Mostra infos a mais
    git log --decorate
    // filtrar por autor
    git log --author="Giovani"
    git shortlog
    // Mostra a árvore
    git log --graph

Diferença entre versões
    git diff
    // Apenas os arquivos que foram modificados
    git diff --name-only

Desfazendo com reset 
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

Branchs
    git checkout -b <nome-branch>
    git branch
    git checkout <nome-branch>
    git branch -D <nome-branch>

.gitignore
    // Extensão
    *.dart
    // Arquivo
    index.js

Stash
    // Ele tira todas as modificações e coloca em uma "pasta"
    git stash
    // Coloca as modificações que estão "guardadas"
    git stash apply
    git stash list
    git stash clear

Tags
    // Pelo que eu entendi é criar uma versão do produto/"release"
    git tag -a 1.0.0 -m "anotação"
    // Lista as Tags
    git tag
    git tag -d <nome-tag>

Revert
    // Reverte o commit (apaga tudo o que foi feito mas não delta o commit da árvore)(ajuda caso quebre)
    git revert <nome-do-commit>

Apagar tags e branchs REMOTOS
    git push origin :<nome-tag>
    git push origin :<nome-branch>