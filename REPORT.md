Лабораторная работа №2 по ТиМП

Работу выполнил: Сакулин Даниил

Часть 1.

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
Counting objects: 11, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (9/9), done.
Writing objects: 100% (11/11), 1.20 KiB | 1.20 MiB/s, done.
Total 11 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To http://github.com/DaniilSakulin/lab02.git
aaa222e..3523362  master -> master
```

9. Проверяю историю коммитов на GitHub'е: https://github.com/DaniilSakulin/lab02/commits/master

Часть 2.

1. В локальной копии репозитория создаю локальную ветку patch1:

```
$ git checkout -b patch1
Switched to a new branch 'patch1'
```

2. Вношу изменения в ветке patch1 по исправлению кода и избавления от using namespace std:

```
$ nano hello_world.cpp
```

```
#include <iostream>
int main(){
std::string name;
std::cin>>name;
std::cout<<"Hello world from "<<name<<std::endl;
return 0;
}
```

3. Коммичу и пушу локальную ветку в удалённый репозиторий:

```
$ git add hello_world.cpp
$ git commit -m "Right version of program"
[patch1 7bc5b2a] Right version of program
 1 file changed, 3 insertions(+), 4 deletions(-)
$ git push --set-upstream origin patch1
Counting objects: 64, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (53/53), done.
Writing objects: 100% (64/64), 13.17 KiB | 1.88 MiB/s, done.
Total 64 (delta 15), reused 0 (delta 0)
remote: Resolving deltas: 100% (15/15), done.
remote:
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/DaniilSakulin/lab02/pull/new/patch1
remote:
To http://github.com/DaniilSakulin/lab02.git
 * [new branch]      patch1 -> patch1
Branch 'patch1' set up to track remote branch 'patch1' from 'origin'.
```

4. Проверяю, что ветка patch1 доступна в удалённом репозитории: https://github.com/DaniilSakulin/lab02/tree/patch1

5. Создаю pull-request из patch1 в master: https://github.com/DaniilSakulin/lab02/pull/1

6. В локальной копии в ветке patch1 добавляю в исходный код комментарии:

```
$ nano hello_world.cpp
```

```
#include <iostream>
/* 
* Main function.
*/
int main(){
// reas user input
std::string name;
std::cin>>name;
// write to console
std::cout<<"Hello world from "<<name<<std::endl;
return 0;
}
```

7. Коммичу и пушу локальную ветку в удалённый репозиторий:

```
$ git push
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 403 bytes | 403.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To http://github.com/DaniilSakulin/lab02.git
   7bc5b2a..284a47b  patch1 -> patch1
```

8. Проверяю, что новые изменения есть в созданном на шаге 5 pull-request: https://github.com/DaniilSakulin/lab02/pull/1

9. В удалённом репозитории выполняю слияние PR patch1 -> master и удаляю ветку patch1 в удаленном репозитории: https://github.com/DaniilSakulin/lab02/commit/00b6740d8de6b233776f2552cbe1527261f17405

10. Локально выполняю pull:

```
$ git pull
remote: Enumerating objects: 32, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (25/25), done.
remote: Total 26 (delta 8), reused 1 (delta 0), pack-reused 0
Unpacking objects: 100% (26/26), done.
From http://github.com/DaniilSakulin/lab02
   3523362..5a0a645  master     -> origin/master
Your configuration specifies to merge with the ref 'refs/heads/patch1'
from the remote, but no such ref was fetched.
```

11. С помощью команды git log просмотриваю историю в локальной версии ветки master:

```
$ git log
commit 284a47be00126333d57ddfe27c8c04ad48134a9a (HEAD -> patch1, origin/patch1)
Author: DaniilSakulin <sakulin_daniil@mail.ru>
Date:   Wed Jun 10 17:59:12 2020 +0300
    Program with comments
commit 7bc5b2ae7e4e2b815f40f8753e519cf397aba3a5
Author: DaniilSakulin <sakulin_daniil@mail.ru>
Date:   Wed Jun 10 17:35:50 2020 +0300
    Right version of program
commit cbe26324663f527406b372cf55627d68d54a5643
Author: DaniilSakulin <sakulin_daniil@mail.ru>
Date:   Wed Jun 10 15:26:22 2020 +0300
    Read user name commit
commit b0c8b3cc45a7ff568601368acdc1f17f02e58399
Author: DaniilSakulin <sakulin_daniil@mail.ru>
Date:   Wed Jun 10 15:14:26 2020 +0300
    HELLO_WORLD commit
commit cf6d372ca6a49e3dc34707053adfab65d4792c1c
Author: DaniilSakulin <57504464+DaniilSakulin@users.noreply.github.com>
Date:   Wed Jun 10 15:03:02 2020 +0300
    Create README.md
commit b7dabcc5d3500d7e682a36510dc66cb3a0ff8280
Author: DaniilSakulin <sakulin_daniil@mail.ru>
Date:   Wed Jun 10 15:00:38 2020 +0300
    first commit
```

12. Удаляю локальную ветку patch1:

```
$ git checkout master
Switched to branch 'master'
Your branch is behind 'origin/master' by 11 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
$ git branch -d patch1
warning: deleting branch 'patch1' that has been merged to
         'refs/remotes/origin/patch1', but not yet merged to HEAD.
Deleted branch patch1 (was 284a47b).
```

Часть 3.

1. Создаю новую локальную ветку patch2

```
$ git checkout -b patch2
Switched to a new branch 'patch2'
$ git push --set-upstream origin patch2
Total 0 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/DaniilSakulin/lab02/pull/new/patch2
remote:
To http://github.com/DaniilSakulin/lab02.git
 * [new branch]      patch2 -> patch2
Branch 'patch2' set up to track remote branch 'patch2' from 'origin'.
```

2. Изменяю code style с помощью утилиты clang-format.

```
$ clang-format -i -style=Mozilla hello_world.cpp
```

3. Коммичу, пушу и создаю pull-request patch2 -> master

```
$ git add hello_world.cpp
$ git commit -m "New style"
[patch2 27bdc57] New style
 1 file changed, 3 insertions(+), 4 deletions(-)
$ git push
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 352 bytes | 352.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To http://github.com/DaniilSakulin/lab02.git
   3523362..27bdc57  patch2 -> patch2
```

