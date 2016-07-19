# NPM (основы работы)


### Основные команды

* `node -v`   ~   Показать текущую версию node.js
* `which node`   ~   Показать где установлен node.js
* `node`   ~   Открывает интерактивную среду и можно выполнять JavaScript команды непосредственно в командной строке, чтобы выйте необходимо нажать 2 раза `Cntr + C`
* `node script.js`   ~  Выполняет и выводит результат скрипта прямо в командной строке 
* `npm -v`   ~   Показать текущую версию npm
* `npm init`   ~   Создать и настроить package.json из командной строки
* `npm config list`   ~   Выводит список уже установленных значений настроек
* `npm config ls -l`   ~   Весь список и установленных и возможных значений настроек
* `npm install`   ~   Устанавливает все пакеты, перечисленные в package.json
* `npm uninstall pack`   ~   Удаляет выбранный пакет
* `npm uninstall pack -g`   ~   Удаляет выбранный пакет, установленный глобально
* `npm i --save-dev https://github.com/substack/node-browserify.git`   ~   Установить пакет из удаленного репозитория
* `npm install express`   ~   Устанавливает пакет express
* `npm install express --save`   ~   Устанавливает express и вносит запись о нем в package.json в секцию dependencies
* `npm install grunt --save-dev`   ~   Устанавливает grunt и вносит запись о нем в package.json в секцию devDependencies
* `npm install pack@0.3.0`   ~   Устанавливает определенную версию пакета
* `npm install PACKAGE --save --save-exact`   ~   Устанавливает определенную версию пакета и не обновляет ее
* `npm search pack`   ~   Выполнить поиск пакоетов по названию
* `npm list`   ~   Показать все установленные пакеты со всеми зависимостями
* `npm list --depth=0`   ~   Показать все установленные пакеты в коротком виде с версиями (без зависимостей)
* `npm view pack`   ~   Показать описание пакета
* `npm outdated`   ~   Проверяет и показывает устаревшие пакеты в package.json
* `npm update`   ~   Обновление всех пакетов проекта
* `npm update pack`   ~   Обновление выбранного пакета
* `npm update --save`   ~   Кроме обновления, в зависимостях заменятся все указания версии виду “*” на текущие актуальные в npm
* `npm update npm -g`   ~   Обновить сам npm
* `npm shrinkwrap`   ~   Зафиксирует точные версии пакетов и создаст свой файл shrinkwrap.json
* `npm cache clean`   ~   Очистить локальный кэш


### Сокращения

Ключ  | Сокращение
----------------|----------------------
install      | i
uninstall      | r
config   | c
update       | up
list    | ls
--save | -S
--save-dev     | -D