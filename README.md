##### DAY 1: Настройка GIT  [10.02.2022]

Для установки Git на Windows, переходим на сайт https://git-scm.com/ и скачиваем нужную нам версию программы.

Затем устанавливаем ее и производим настройку.
Запускаем GitBash и выполняем команды:
``` bash
git config --global user.name "ВАШЕ ИМЯ"
git config --global user.email "ВАШ_E-MAIL"
```
Генерируем ключи SSH:
```bash
ssh-keygen -t rsa -b 4096 -C "ВАШ_E-MAIL"
```
На вопрос «Enter file in which to save the key (/Users/you/.ssh/id_rsa):» просто нажмитеEnter
На вопрос «Enter passphrase (empty for no passphrase):» введите контрольную фразу (пароль, который нужно запомнить)
Затем повторите пароль.
Вводим в консоли: 

``` bash
ls -al ~/.ssh 
```
Он покажет наши ключи
Добавляем их в GitBash:
```bash
ssh-agent -s
eval "$(ssh-agent)"
ssh-add ~/.ssh/id_rsa
```
Копируем ключ в буфер:
```bash
clip < ~/.ssh/id_rsa.pub
```
На сайте Github добавляем ключ: https://github.com/settings/keys
В консоли вводим для проверки соединения:
```bash
ssh -T git@github.com
```
В ответ должны увидеть:
```
Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
```
Переходим на ПК в каталог где будет наш репозиторий, запускаем в нем GitBash (Важно что-бы текущий путь в gitbash был в текущий каталог)
Затем выполняем команды:
```bash
git init
git remote add origin git@github.com:tanderbull/frontend.learning.git
git remote -v
```
Вывод должен быть вида (Это SSH-url):
```bash
origin  git@github.com:USERNAME/OTHERREPOSITORY.git (fetch) 
origin  git@github.com:USERNAME/OTHERREPOSITORY.git (push)
```
Создаем на сайте Git репозиторий и после создания он выдаст нам инструкцию, копируем ссылку и вставляем ее в GitBash:
```bash
git remote set-url origin git@github.com:tanderbull/frontend.learning.git 
```

В дальнейшем для работы с Github планирую придерживаться следующей схемы работы:

1. `git pull` - Обновляем данные с репозитория
1. `git status -s` - Смотрим статус
1. Работаем над проектом
1. `git diff` - Смотрим изменения
1. `git add -A` - Добавляем файлы в коммит
1. `git commit -m "Text"` - Коммитим
1. `git push origin` - Пушим на Github (В конце рабочего дня)

----

##### DAY 0: Стартовая точка  [07.02.2022]

Уже несколько раз пытался освоить FrontEnd и перейти в данную сферу, но в связи с различными ситуациями которые настигали меня в жизни приходилось приостанавливать обучение. Последняя попытка у меня была в 2019 году. Сейчас буду освежать все в памяти и надеюсь что силы воли и мотивации у меня хватит в этот раз дойти этот путь до конца. 

Моей текущей промежуточно-финальной точкой будет освоение профессии до хороших знаний Junior разработчика и трудоустройство по специальности. Сейчас совмещаю все это с работой которая не связана с IT.
Для себя решил начать все с чистого листа. Создал новый профиль на github и все прошлое, остается в прошлом.

Так же планирую создать телеграмм канал где буду описывать свои достижения или временные неудачи.