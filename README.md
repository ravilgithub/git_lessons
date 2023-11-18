# git_lessons
Уроки Git + Github

Учебно-тестовый репоситорий.


Команды:

- Клонирование репозитория
git clone <Repository URL>

- Состояние локального репозитория
git status

- Разница между состоянием локального и удалённого репозитория
git fetch [<origin>]

- Слить удалённую ветку с текущей локальной
git merge

- Вывод коммитов
  всех веток
  каждый в одну строку
  с графическим представлением ветвлений
  с отображение изменённых файлов для каждого коммита
  и указанием количества начиная с последнего
git log --oneline --graph --all --name-only -10

- Вывод коммитов с отображение изменений в файлах
git log --patch

- Показать только коммиты слияния на текущей ветке
  git log --merges

- Показать все коммиты, кроме коммитов слияния на текущей ветке
  git log --no-merges

- Показать коммиты которые есть на удалённой ветке, но которых нет в локальной ветке
  git log <local_branch>..<origin>/<remote_branch>

- Показать только коммиты слияния которые есть на удалённой ветке, но нет в локальной ветке
  git log --merges <local_branch>..<origin>/<remote_branch>

- Показать все коммиты, кроме коммитов слияния которые есть на удалённой ветке, но нет в локальной ветке
  git log --no-merges <local_branch>..<origin>/<remote_branch>

- Отправить изменения на удалённую ветку с именем отличным от имени локальной ветки
  git push --set-upstream <origin> <local_branch>:<remote_branch>

- Показ локальных и удалённых веток
git branch --all

- Переключение на ветку
git switch <branch-name>
git checkout <branch-name>

- Создать ветку и переключиться на неё
git switch -c <branch-name>
git checkout -b <branch-name>

- Индексировать файл
git add <file>

- Показ изменения в не индексированных файлах
git diff

- Показ в индексированных изменённых файлах
git diff --staged

- Показ строк с не нужными пробельными символами
git diff --check

- Посмотреть разницу состояний локальной и удалённой веток
git diff origin/HEAD

- Фиксация изменений
git commit -m "Message"

- Индексирование и фиксация изменений
git commit -am "Message"

- Редактирование последнего коммита
git commit --amend

- Отмена индексации файла
git restore --staged <file>

- Откат изменённого файла
git restore <file>

- Перемещение/переименование файла
git mv <file-from> <file-to>

- Удаление файла
git rm <file>

- Влить ветку в текущюю
git merge [<origin>/]<branch-name>

- Принудительное трёхстороннее слияние даже если возможно слияние методом fast-forward.
  Находясь на ветке в которую нужно влить изменения с сохранение истории ( параметр --no-ff ).
git merge <branch-name> --no-ff

- Слияние удалённой/удалённых веток
git fetch --all
git checkout <branch_to>
git pull [<origin> <branch_to>]
git merge [<origin>] <branch_from>
git push [<origin> <branch_to>]

- Добавление ветки в удалённый репозиторий
git push --set-upstream <origin> <branch-name>

- Удаление ветки из удалённого репозитория
git push <origin> --delete <branch-name>

- Переименование локальной ветки
git branch --move <branch-name-from> <branch-name-to>

- Удаление локальной ветки
git branch -d <branch-name> [<branch-name>]

- Принудительное удаление локальной ветки даже если она не слита с другой веткой
git branch -D <branch-name> [<branch-name>]

- Показать ветки слитые с текущей веткой
- Слитые ветки можно удалить
git branch --merged [--all]

- Показать ветки не слитые с текущей веткой
git branch --no-merged [--all]

- Удаление веток слежения которые ссылаются на несуществующие/удалённые в удалённом репозитории
- http://microsin.net/programming/pc/git-prune.html
git fetch --prune

- Извлечь удалённую ветку которой не в локальном репозитории и переключиться на неё
- Создать ветку слежения
git checkout <branch-name>

- Настроить текущую ветку на слежение за удалённой веткой
git branch --set-upstream-to <origin>/<branch-name>

- Посмотреть как у вас настроены ветки слежения
git branch -vv

- Перебазирование <branch-from> поверх <branch-to>
git switch <branch-from>
git rebase <branch-to>
git switch <branch-to>
git merge <branch-from>
- или
git rebase <branch-to> <branch-from>
git switch <branch-to>
git merge <branch-from>

- История коммитов
- https://jeka.by/ask/254/cancel-git-commit-amend/
git reflog
- Отмена редактирования последнего коммита с помощью параметра --amend,  без изменения файлов.
- Где n - номер коммита в истории на который нужно откатиться
- 0 - последний
- 1 - до --amend, если коммитов больше не было
git reset --soft HEAD@{n}


------------------------------------------------

Попрактиковать и описать

- Перебазирование глава 3.6
git rebase [--onto] <branch-to> <branch-from>
git switch <branch-to>
git merge <branch-from>

------------------------------------------------

Не выполнять на удалённых репозиториях!

Редактирование коммита
- git commit --amend 

- Перебазирование ветки
git rebase <origin> <branch-name>
