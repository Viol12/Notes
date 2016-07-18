
# Git команды

### Настройки

* `git config --global user.email "John@gmail.com"`   //   установить ваш email в git гловально
* **git config --global user.name "John Doe"**   //   установить ваше имя в git гловально 
* git config user.email   //   проверить ваш email в git
* git config user.name   //   проверить ваше имя в git
* git config --global core.editor emacs     //   устанавлявает редактор для записей в консоле, например (emacs)
* git config --list   //   показывает все настройки которые установдлены в git, в том числе и алисы
* -- global   //   исполняет команду глобально, тоесть во всей системе

### Работа с ветками

* git branch   //   показать все существующие ветки в директории
* git branch -a   //   показать все существующие ветки, даже те которые только в репозитории на github-е
* git merge origin/ticket_1001_branch   //   слияние веток 
* git pull origin ticket_1001_branch   //   забирает изменения из ветки на удаленном сервере и проводит слияние с активной * веткой
* git merge <name branch>
* git branch -d <name branch>
* git checkout -b <name branch>
* git branch -r
* git branch cat
* git checkout <name branch>
* git checkout <name branch>
* git init   //   создает репозиторий в нынешней директории
* git add *.c   //   добавить все файли, которые заканчиваются на .c для индексации и отслеживанию в репозитории
* git add <file1> <file2>   //   добавить file1 и file2 для индексации и отслеживанию в репозитории
* git rm <file1> <file2>   //   удалить file1 и file2
* git add .   //   добавить все файлы из данной дериктории в репозиторий
* git commit -m '...'   //   создать комментарий для последних изменений
* git clone https://github.com/libgit2/libgit2   //   склонировать репозиторий к себе на компьютер
* git clone https://github.com/libgit2/libgit2 Hohoho   //   склонировать репозиторий и назвать каталог Hohoho
* git status   //   узнать какие файлы в каком состоянии находятся.
* git checkout php   //   подтягивает ветку php из удаленного репазитория на локальную директорию
* git checkout -b dev   //   создать новую папку в локальном репозитории и перейти в неё
* git push origin dev   //   залить на github изменения сделаные локально (запушить, сделать пуш)
* git pull orogin dev   //   влить изменения в ветку dev
* git reset --hard 9a452d955bdb57e7e4f2b09f8ce2fbb6cd56377a   //   сделать откат до нужного коммита (номер коммита узнаем из * git log)
* git log   //   выводит все сделанные коммиты в репозитории в обратном к хронологическому порядке
* git log -p -2   //   -p выводит только разницу внесенную в каждый коппит, -2 устанавливает лимит на вывод количества коммитов
* git log --stat   //   показывает сокращенную статистику для каждого коммита
* mkdir project_dir   //   создание нового локального репазитория (после нужно выполнить cd project_dir и git init)
* git cherry-pick eb042098a5   //   применить один коммит из одной ветку в другую
* git grep   //   поиск подстроки в проэкте
* 
* git help 
* mkdir 
* cd
* git diff
* git diff —staged
* git reset HEAD "…"
* git checkout —"…"
* git commit -a -m "…"
* git reset —soft HEAD^
* git commit —amend -m "…"
* git remote add origin "…"
* git remote -v
* git remote rm <name>
* git clone "…"
* git clone «…» <name>
* ls
* git remote show origin
* git tag
* git checkout v0.0.1
* git tag -a v0.0.1 -m "…"
* git push —tags
* git fetch
* git rebase
* git rebase <name branch>
* git diff HEAD
* git blame <name file>
* git stash
* git stash list
* git stash apply
* git stash applt stash@{0}
* git stash apply --index
* git stash drop stash@{0}
* git stash pop stash@{0}
* git stash branch <name branch>
