Лабораторная работа №2 по ТиМП

Работу выполнил: Сакулин Даниил

1. Создаю пустой репозиторий на сервисе GitHub: https://github.com/DaniilSakulin/lab02

2. Выполняю инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге:

```
$ git init
Reinitialized existing Git repository in /home/yrojiobwuha/workspace/projects/projects/lab02/.git/
$ echo "#lab02" >> README.md
$ git add README.md
$ git commit -m "first commit"
[master (root-commit) a81f784] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git
$ git push -u origin master
warning: redirecting to https://github.com/DaniilSakulin/lab02.git/
Counting objects: 3, done.
Writing objects: 100% (3/3), 223 bytes | 223.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To http://github.com/DaniilSakulin/lab02.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```
