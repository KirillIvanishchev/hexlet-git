# GIT COMMANDS
## созадние ключей и проверка версии
- `git --version`						# Проверка версии
- `git config --global user.name` **__имя фамилия__**		# Создание имени учётной записи
- `git config --global user.email` **__ваш емейл__**		# Создание учётной записи
- `ssh-keygen -t ed25519  -C` **__ваш емейл__**			# Создание ssh-ключей
- `eval "$(ssh-agent -s)"`					# Запуск агента ssh, который следит за ключами
- `ssh-add ~/.ssh/id_ed25519`					# Добавления нового ssh-ключа в агент
- `cat ~/.ssh/id_ed25519.pub`					# Содержимое файла ключа (добавить на GitHub)
## соединение с GitHub
- `git remote add origin git@github.com:USERNAME/REPOSITORY.git`		#создает соединение через SSH ключи
- `git remote set-url origin https://github.com/USERNAME/REPOSITORY.git`        #создает соединение через http протоколы
- `git branch -M` **__main__**							#создаёт и переименовывает текущую ветку на main
- `git push -u origin` **__main__**						#отправляет изменения в ветку (в данном случае main)
- `remote -v`									#просмотр всех ссылок на GitHub репозитории
- `remote add upstream` **__repo link__**					#добавление потока на GitHub репозиторий поверх основного для обновления
## работа с рабочей директорией
- `git init`						#Инициализирует рабочий репозиторий в текущей директории
- `pwd`							#Показывает текущий путь к директории
- `cd	/ cd ..`					#Переход к директории (через .. вернуться в предыдущую директорию)
- `ls -a`						#Показывает все файлы в текущей директории
- `mkdir`						#Создает пустую директорию
- `git clean -fd`					#Удаляет все пустые файлы и директории
- `rm -r` **__directory name__**			#Удаляет директорию в репозитории, а также все файлы внутри
- `git mv` **__old name__** **__new name__**		#Переименовывает файл в рабочей директории
## добавление в индекс
- `git add` **__filename__** 				#добавляет в индекс файл
- `git add -i` 						#добавляет в индекс файлы на выбор (через консоль)
- `git add .`						#добавляет в индекс абсолютно все файлы
## коммит
- `git commit -m 'message'` **__filename__** / `-a`	#коммитит файл/ все изменения в индексе с сообщением
- `git commit` **__filename__** / `-a`			#коммитит файл/ все изменения в индексе без сообщения
- `git commit --amend (--no-edit)`			#отменяет последний коммит и перекоммичивает все изменения в индексе (без изм. сообщения)
- `git comit --allow-empty`				#пустой коммит без изменений для сборки
##
- `git restore` **__filename__** / `git restore .`	#отменяет изменения в файлах /во всех файлах
- `git restore --staged` **__filename__** / `.`		#отменяет изменения в индексе /всех файлов в индексе
- `git revert` **__7 digits of hash__**			#отменяет коммит по Хэшу
- `git reset --hard HEAD~`**__numbers of commits__**	#отменяет и удаляет все коммиты по <количеству коммитов>
- `git reset --mixed HEAD~`**__numbers of commits__**	#отменяет и отправляет в рабочую директорию по <количеству коммитов>
## просмотр изменений
- `git status`                                          #Показывает статус файлов в директории
- `git diff` / `git diff --staged`                      #показывает разницу изменений / изменений в индексе (зелен)
- `git log`  / `git log -p`                             #показывает все коммиты с сообщ / с изменениями и сообщ
- `git log --oneline`/ `--graph`			#показывает логи в одну линию / граф с ветками
- `git checkout` **__hash__**				#переключение на коммит
- `git show` **__7 digits of hash__**                   #показывает изменения в коммите
- `git blame` **__filename__**                          #поиск последних изменений в файле
- `git grep` **__anything__**				#поиск совпадения со строкой
## работа с ветками
- `git branch` **__branchName__**			#создание новой ветки
- `git checkout` **__branchName__**			#переход на ветку
- `git checkout -b` **__branchName__**			#создание и переход на ветку
- `git checkout` **__branchName__**				#переход на предыдущий узел / пред пред идущий
- `git checkout HEAD^` / `HEAD^^` / `HEAD~`**__num of iterations__**	# переход на предыдущую ветку РОДИТЕЛЯ
- `git rebase` **__branchName__**					# переключить базу (все ответвления) на узел (коммит)  
- `git branch -f` **__chosenBranch__** **__toBranch(~num of iterations)__**	# принудительно перенести один (несколько) узел (коммит) на другой
