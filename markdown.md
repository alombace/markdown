# Конспект: основы Markdown. Создание репозитория Git. 
Markdown — это облегчённый язык разметки, который используется для форматирования текста с помощью простых символов. Он часто применяется для написания документации, README-файлов, заметок и статей, особенно в среде разработчиков. 
## Основные элементы Markdown
### Заголовки
Они обозначаются с помощью символа #, если решетка одна (#), то это заголовок первого уровня. Если решетки две (##), то это заголовок второго уровня, и так далее. Всего уровней шесть. 
### Выделение текста
Текст может выделяться _курсивом_, __жирным__ или ~~перечеркнутым~~. Рассмотрим каждый тип по отдельности. 

| Формат | Символ |
|-|-|
| Курсив | Есть два варианта выделения курсивом: использовать символ "_" или "*" в начале и конце фразы. |
| Жирный | Аналогично, есть два варианта выделения жирным: использовать символы "__" или "**" в начале и конце фразы. |
| Перечеркнутый | Тут только один вариант использования: нужно добавить "~~" в начале и конце фразы. |

---

## Создание репозитория Git
Git — один из видов систем контроля версий (или СКВ). Такие системы записывают изменения в набор файлов, а позже позволяют вернуться к определенной версии.

Для выполнения домашнего задания я выполнила следующие шаги: 
1. Установила Git 
```
polinavasileva@MacBook-Air-Polina ~ % git --version
git version 2.39.5 (Apple Git-154)
```
2. Создала папку на рабочем столе и создала репозеторий с помощью команды `git init`
```
polinavasileva@MacBook-Air-Polina ~ % cd desktop/markdown_doc
polinavasileva@MacBook-Air-Polina markdown_doc % git init
Initialized empty Git repository in /Users/polinavasileva/Desktop/markdown_doc/.git/
```
3. Поместила в созданный репозиторий данный файл и с помощью команды `git status` убедилась, что файл добавлен
```
polinavasileva@MacBook-Air-Polina markdown_doc % git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	markdown.md

nothing added to commit but untracked files present (use "git add" to track)
```
4.Выполнила команды:
```
git add .
git commit -m "Added the markdown.md file"
```
```
polinavasileva@MacBook-Air-Polina markdown_doc % git status
On branch main
nothing to commit, working tree clean
```
5. Далее создала на GitHub новый репозиторий (см. 5.1 и 5.2 - скриншоты)
6. При попытке отправить изменения в удаленный репозиторий столкнулась с ошибкой 
```
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/alombace/markdown.git/'
```
7. После долгой гуглежки создала personal access tokens и поборола ошибку (см. 7.1 скриншот)
8. Отправила изменения на удалённый репозиторий командами:
```
git remote add origin https://github.com/alombace/markdown.git
git branch -M main
git push -u origin main
```