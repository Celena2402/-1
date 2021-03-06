# Инструкция по работе с  GIT

Git - система контроля версий (файлов).

## Для чего нужен GIT

1. Возможность хранить различные версии проекта.
2. Возможность в возвращаться к различным версиям проекта.

Работать с Git можно двумя способами:
* Через командную строку (терминал).
* Через IDE.

## **Порядок действий по работе с Git**

1. *Установка* . 
Установить программу git на свою машину.

2. *Настройка*.
После установки git нужно добавить немного настроек. Ввести в терминале - наше имя пользователя и адрес электронной почты. 

3. *Создание нового репозитория*.
Чтобы создать новый репозиторий, нам нужно открыть терминал, зайти в папку нашего проекта и выполнить команду **git init**. Это включит приложение в этой конкретной папке и создаст скрытую директорию .git, где будет храниться история репозитория и настройки.

4. *Определение состояния*.
**Git Status** — это еще одна важнейшая команда, которая показывает информацию о текущем состоянии репозитория: актуальна ли информация на нём, нет ли чего-то нового, что поменялось, и так далее. 

5. *Подготовка файлов*.
Команда **git add** добавляет содержимое рабочего каталога в индекс (staging area) для последующего коммита. По умолчанию **git commit** использует лишь этот индекс, так что вы можете использовать git add для сборки слепка вашего следующего коммита.
Это одна из ключевых команд Git.

6. *Далее можно работать с файлом*.

**Основные команды**

* **git commit** Команда git commit берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.
 
 * **git log** Для просмотра всех выполненных фиксаций можно воспользоваться историей коммитов. Она содержит сведения о каждом проведенном коммите проекта. В ней содержиться вся информация о каждом отдельном коммите, с указанием его хэша, автора, списка изменений и даты, когда они были сделаны. Также эта команда используется перед переключением версий.

 * **git checkout** Переключение между версиями.
Для работы нужно указать не только интересующий вас коммит, но и вернуться в тот, где работаем, при помощи команды
**git checkout master**.

* **git diff** Показывает разницу между текущим файлом
и сохранённым. Перед переключением версии файла в Git
используйте команду git log, чтобы увидеть количество сохранений.

## **Ветвление**

**Зачем нужны ветви.**

Ветки позволяют легко управлять
черновиками и чистовиками в Git.

Во время разработки новой функциональности считается хорошей практикой работать с копией оригинального проекта, которую называют веткой. Ветви имеют свою собственную историю и изолированные друг от друга изменения до тех пор, пока вы не решаете слить изменения вместе.

### *Команды*

1. *Создание новой ветки*

**git branch <название новой ветки>** создание новой ветки.
Делать это надо в папке с репозиторием. Можно посмотреть список веток в репозитории.
Если у нас несколько версий черновика, мы можем вывести на экран ветку, где находимся,
командой **git branch**.

2. *Переключение между ветками.* 

Если потребуется переключиться с одной ветки на другую, вызовем команду **git checkout <имя
ветки>**.
Git checkout позволяет нам переключаться как между удаленными, так и меду локальными ветками. Это один из способов получить доступ к работе коллеги или соавтора, обеспечивающий более высокую продуктивность совместной работы.

3. *Слияние веток*.

Команда **git merge** используется для слияния одной или нескольких веток в текущую. Затем она устанавливает указатель текущей ветки на результирующий коммит.
 Чтобы слить любую ветку с текущей, вызываем **git merge <имя ветки для слияния с текущей>**
Перед слянием обязательно проверить, в какой ветке вы находитесь.

4. *Удаление веток*

Команда **git branch -d <имя ветки>**
где флажок -d являющийся опцией команды git branch - это сокращенная версия ключевого слова --delete, предназначенного для удаления ветки.

5. *Конфликт изменений*.

При работе в двух ветках одновременно может возникнуть ситуация, когда в одной и другой
ветке мы по-разному изменили блок текста. Если затем мы попробуем слить эти ветки, Git сообщит о конфликте и предложит выбрать,
какие же изменения записать.

! Поэтому у проекта в репозитории должен быть один
ответственный пользователь, наделённый правом проводить
слияния и разрешать конфликты.

6. *Визуализация всех веток* 

Отображает ASCII граф с ветвлениями и историей слияний.

**git log --graph**
Ключ -graf в связке с командой log позволяет отобразить коммиты в виде дерева.

## **Добавление изображения**

Добавим изображение в файл-инструкцию.
В Git не принято добавлять файлы
изображений, их хранят на сторонних
носителях. Чтобы исключить ненужные файлы
из загрузки, есть команда git ignore.

![Добавление изображения](image.jpg)

## **Работа с удаленным репозиторием**

Удаленный (иногда говорят "внешний") репозиторий – это версии вашего проекта, сохраненные на удаленном сервере. Доступ к репозиторию на таком сервере может осуществляться по интернету или по локальной сети.

Удаленный репозиторий – полноценный репозиторий, ничем не отличающийся от локального. У удаленного репозитория есть собственные ветки, собственный указатель HEAD, своя история коммитов и так далее.

### *Команды*

#### **Подключение удаленного репозитория git remote**

* **git remote add** - добавляет удаленный репозиторий к существующему локальному.

* **git remote remove** - отключение удаленного репозитория от локального

* **git remote rename** - меняет имя переданного удаленного репозитория

* **git remote show** - выводит список всех подключенных удаленных репозиториев. Если передано имя репозитория, то выводит информацию об этом репозитории.

#### **Клонирование удаленного репозитория git clone**

Необходимость клонировать существующий удаленный репозиторий возникает в ситуациях, когда вы решаете поработать над уже существующим кодом. Для выполнения этой операции в Git предусмотрена команда git clone.

* **git clone** - клонирует переданный репозиторий на ваш компьютер. 

#### **Получение изменений из удаленного репозитория git fetch**

* **git fetch** - получает изменения из переданного удаленного репозитория. Если не было передано ни одного удаленного репозитория, ни ключа --all, команда пытается получить изменения из репозитория с именем origin.

#### **Получение изменений из удаленного репозитория git pull**

* **git pull [ключи] [имя удаленного репозитория]** - получает изменения из переданного удаленного репозитория и обновляет рабочую копию в соответствии с удаленным репозиторием. Эта команда позволяет скачать все
из текущего репозитория и автоматически
сделать merge с нашей версией.пше

#### **Отправка изменений в удаленный репозиторий git push**

* **git push [ключи] [имя удаленного репозитория] [имя ветки]** - загружает изменения в удаленный репозиторий. Эта команда позволяет отправить нашу
версию репозитория на внешний
репозиторий. ТРЕБУЕТ АВТОРИЗАЦИИ
на внешнем репозитории.

#### **Как настроить совместную работу**

1. Создать аккаунт на GitHub.com
2. Создать локальный репозиторий
3. “Подружить” ваш локальный и удалённый репозитории.
GitHub при создании нового репозитория подскажет, как это можно сделать
4. Отправить (push) ваш локальный репозиторий в удалённый (на GitHub), при этом, возможно,
вам нужно будет авторизоваться на удалённом репозитории
5. Провести изменения “с другого компьютера”
6. Выкачать (pull) актуальное состояние из удалённого репозитория

#### **pull request** — предложение изменения кода в чужом репозитории

➜ команда для предложения изменений
➜ запрос на вливание изменений в репозиторий
В больших компаниях один ответственный за проект создает аккаунт. Другие пользователи дают
команду pull request. Предлагать изменения на GitHub нужно в отдельной ветке. Сначала
пользователь копирует репозиторий на свой компьютер, делает fork репозитория, затем
клонирует версию на своём ПК, создаёт ветку с предлагаемыми изменениями, отправляет
изменения командой push в свой аккаунт на GitHub и даёт команду pull request.

*Как сделать pull request*
* Делаем (ответвление) репозиторияfork
* Делаем git clone версии репозиторияСВОЕЙ
* Создаем новую ветку и в НЕЕ вносим свои изменения
* Фиксируем изменения (делаем коммиты)
* Отправляем свою версию в свой GitHub
* На сайте GitHub нажимаем кнопку pull request
