# Краткая инструкция по работе с Git

__1.__ Устанавливаем Git и VisualStudio Code

__2.__ На жестком диске создаем папку, в которой далее будет настроен контроль версий, то есть репозитарий.

__3.__ При первом запуске VisualStudio Code необходимо представиться системе контроля версий. Это нужно сделать один раз. Для этого в терминале вводим следующие команды:
* `git config --global user_name` - где *user_name* - ваше имя на английском
* `git config --global user_emale` - где *user_emale* - ваш emale

__4.__ `git --version` - проверяем версию git.

__5.__ `git init` - вводим команду, инициализирующую репозиторий в текущей директории.
> Указываем папку, в которой git начнет отслеживать изменения.
![Пример](pic1.jpg)

__6.__ `git add ` - добавить текущее сохранение/изменение в файл.
> **TAB** помогает выбрать файл. Например: *git add HomeWork1.md*
![Пример](pic2.jpg)

__7.__ `git commit -m "..."` - зафиксировать/сохранить изменения.
> Например: *git commit -m "Необходимый комментарий"*
![Пример](pic3.jpg)

__8.__ `git log` - показывает журнал сохранений.
> Перед тем как переключаться между версиями, необходимо выполнить команду **git log**, чтобы увидеть все версии и выбрать нужную.
![Пример](pic5.jpg)

__9.__ `git checkout` - переключается между версиями/коммитами.
> Для перехода к нужному коммиту необходимо указать первые 4-5 символов его индекса. Например: *git checkout 58e7c*

__10.__ `git diff` - показывает разницу между текущим состоянием и записанной версией файла.
![Пример](pic4.jpg)

__11.__ `clear` - очищает видимую часть терминала.

## Продолжение инструкции

__12.__ `git branch` - выводит на экран список веток, которые у нас есть.

![Пример](pic6.jpg)

`git branch new_branch_name` - создание новой ветки

![Пример](pic7.jpg)

`git branch -d branch_name` - удаление ветки
> Удалять вспомогательную ветку можно только после того, как ее информация слита в основную и ее удаление ничего не повредит.

![Пример](pic9.jpg)

__13.__ `git merge branch_name` - слияние веток
> Вызывается в основной ветке (master), т.е. там куда мы из вспомогательной ветки хотим переместить информацию.

![Пример](pic12.jpg)

__14.__ `git log --graph` - отображает все комиты графически, по веткам с ответвлениями.

![Пример](pic11.jpg)

## Варианты слияния веток

__1.__ `fast_forward` - подразумевает, что основная ветка просто отстала от вспомогательной. При слиянии основная догоняет вспомогательную. Конфликт невозможен.

__2.__ `ort strategy` - в основной и во вспомогательной ветках произведены изменения разных участков, которые не затрагивают друг друга. При слиянии конфликта также не возникнет.

__3.__ `conflict` - возникает, когда в основной и во вспомогательной ветках произведены разные изменения на одних и тех же участках.

## Варианты решения конфликта при слиянии веток

`accept current change` - применить текущую версию.

`accept incoming change` - применить входящую версию.

`accept both change` - оставить оба варианта.
> Рекомендуется выбирать именно данный вариант разрешения конфликта.

`compare change` - сравнить версии.
> Данный пункт не решает конфликт!

## Продолжение Инструкции (Лекция/Семинар 3)

`GitHub` - онлайн сервис для работы с удаленными репозиториями.

>`Git` и `GitHub` - разные вещи!

### Краткий чек-лист по работе с удаленным репозиторием

1. Делаем `fork` интересующего нас репозитория;
2. Создаем пустую папку на компьютере для дальнейшей работы с удаленным репозиторием;
3. Заходим в `VS code`, открываем только что созданную папку и делаем `git clone` для нашей версии этого репозитория;
4. `Обязательно` создаем новую ветку, где будем проводить все предполагаемые изменения;
5. Производим все изменения `только` в этой ветке;
6. Отправляем эти изменения на свой аккаунт - `git push --set -upstream origin description`;
7. В окне на `GitHub` появляется зеленая кнопка `Pull request` - нажимаем, чтобы отправить свой запрос на внесение изменений.

### Основные команды

__1.__ `fork` - сделать полную копию чьего-то репозитория на своем аккаунте в `GitHub`.
> Делается это не в терминале `VS code`, а в онлайн сервисе `GitHub` в своем личном аккаунте.

__2.__ `git clone https_адрес` - закачивает полную копию удаленного репозитария на локальный компьютер.
> Внутри нашей папки на компьютере `нет репозитария`! Он есть внутри той папки, которую скачали. Поэтому, чтобы работать с gitом, необходимо переместиться внутрь скачанной папки:
`cd имя_папки`

__3.__ `git push` - загружаем изменения в нашу копию удаленного репозитория.
> При первой загрузке необходимо будет ввести: <br>
`git push --set -upstream origin description` - так удаленный репозиторий понимает, что мы создали вспомогательную ветвь, которой до этого не было.

__4.__ `git pull` - загрузить с удаленного репозитория все изменения.
> Является составной командой - подгружает изменения и пытается их слить `(merge)` - далее один из `вариантов слияния`.

__5.__ `pull request` - запрос на вливание каких-либо изменений в удаленный репозиторий другого пользователя.