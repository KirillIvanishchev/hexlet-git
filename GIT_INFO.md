git commnds:
#
git --version						# Проверка версии

git config --global user.name "имя фамилия"		# Создание имени учётной записи

git config --global user.email "ваш емейл"		# Создание учётной записи

ssh-keygen -t ed25519  -C "ваш емейл"			# Создание ssh-ключей

eval "$(ssh-agent -s)"					# Запуск агента ssh, который следит за ключами

ssh-add ~/.ssh/id_ed25519				# Добавления нового ssh-ключа в агент

cat ~/.ssh/id_ed25519.pub				# Содержимое файла ключа (добавить на GitHub)

#
git remote add origin git@github.com:USERNAME/REPOSITORY.git			#создает соединение через SSH ключи

git remote set-url origin https://github.com/USERNAME/REPOSITORY.git            #создает соединение через http протоколы

git branch -M main								#создаёт и переименовывает текущую ветку на main

git push -u origin main								#отправляет изменения в ветку (в данном случае main)

#
pwd							#Показывает текущий путь к директории

cd	/ cd ..						#Переход к директории (через .. вернуться в предыдущую директорию)

ls -a							#Показывает все файлы в текущей директории

mkdir							#Создает пустую директорию

git clean -fd						#Удаляет все пустые файлы и директории

#
git status						#Показывает статус файлов в директории

git diff / git diff --staged				#показывает разницу изменений / изменений в индексе (зелен)

git log  / git log -p					#показывает все коммиты с сообщ / с изменениями и сообщ	

git show <7 digits of hash>				#показывает изменения в коммите

git blame <FILENAME>					#поиск последних изменений в файле

#
git add <FILENAME> 					#добавляет в индекс файл

git add -i 						#добавляет в индекс файлы на выбор (через консоль)

git add .						#добавляет в индекс абсолютно все файлы

#
git commit -m 'message' <FILENAME> / -a			#коммитит файл/ все изменения в индексе с сообщением

git commit <FILENAME> / -a				#коммитит файл/ все изменения в индексе без сообщения

git commit --amend (--no-edit)				#отменяет последний коммит и перекоммичивает все изменения в индексе (без изм. сообщения)

git comit --allow-empty					#пустой коммит без изменений для сборки

#
git restore <FILENAME> /git restore .			#отменяет изменения в файлах /во всех файлах

git restore --staged (<FILENAME> /.)			#отменяет изменения в индексе /всех файлов в индексе

git revert <7 digits of hash>				#отменяет коммит по Хэшу

git reset --hard HEAD~<numbers of commits>		#отменяет и удаляет все коммиты по <количеству коммитов>

git reset --mixed HEAD~<numbers of commits>		#отменяет и отправляет в рабочую директорию по <количеству коммитов>

#
git grep <anything>					#поиск совпадения со строкой

#
