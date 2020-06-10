Лабораторная работа №2 по ТиМП

Работу выполнил: Сакулин Даниил

1. Создаю пустой репозиторий на сервисе GitHub: https://github.com/DaniilSakulin/lab02

2. Выполняю инструкцию по созданию первого коммита на странице репозитория, созданного на предыдущем шаге:

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

3. Создаю файл hello_world.cpp в локальной копии репозитория:

```
$ nano hello_world.cpp
```

Реализую программу Hello world на языке C++ используя плохой стиль кода:

```
#include <iostream>
using namespace std;
int main(){
cout<<"Hello world"<<endl;
return 0;
}
```

4. Добавляю файл в локальную копию репозитория:

```
$ git add hello_world.cpp
```

5. Коммичу изменения с осмысленным сообщением:

```
$ git commit -m 'HELLO_WORLD commit'
[master b0c8b3c] HELLO_WORLD commit
1 file changed, 6 insertions(+)
create mode 100644 hello_world.cpp
```

6. Изменяю исходный код так, чтобы программа через стандартный поток ввода запрашивала имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя:

```
$ nano hello_world.cpp
```

```
#include <iostream>
using namespace std;
int main(){
string name;
cin>>name;
cout<<"Hello world from "<<name<<endl;
return 0;
}
```

7. Коммичу новую версию программы:

```
$ git add hello_world.cpp
$ git commit -m 'Read user name commit'
[master cbe2632] Read user name commit
1 file changed, 3 insertions(+), 1 deletion(-)
```

8. Отправляю изменения в удалённый репозиторий:

```
$ git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 2.01 KiB | 2.01 MiB/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To github.com:DaniilSakulin/lab-02.git
a81f784..cbe2632  master -> master
```
