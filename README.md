# Git_How_To
___
## 1. Фінальні приготування

### 1. Встановлюємо ім'я та адресу електронної пошти
- git config --global user.name "Your Name"
- git config --global user.email "your_email@whatever.com"

### 2. Назва гілки за замовчуванням
- git config --global init.defaultBranch main

### 3. Коректна обробка закінчень рядків
- git config --global core.autocrlf input
- git config --global core.safecrlf warn

## Результат:
![lesson_1.1](/screenshots/photo_1.jpg)

## 2. Створення проєкту

### 1. Створіть сторінку «Hello, World»
- mkdir work
- cd work
- touch hello.html

### 2. Створіть репозиторій
- git init

### 3. Додайте сторінку у репозиторій
- git add hello.html
- git commit -m "Initial Commit"

## Результат:
![lesson_1.2](/screenshots/photo_2.jpg)
![lesson_1.2-bonus](/screenshots/photo_3.jpg)

## 3. Перевірка стану

### 1. Перевірте стан репозиторія
- git status

## 4. Внесення змін

### 1. Змініть сторінку «Hello, World»
- <h1>Hello, World!</h1>

### 2. Перевірте стан
- git status

## Результат:
![lesson_1.4](/screenshots/photo_4.jpg)

## 5. Індексація змін

### 1. Додайте зміни
- git add hello.html
- git status

## Результат:
![lesson_1.5](/screenshots/photo_5.jpg)

## 7. Коміт змін

### 1. Закомітьте зміни
- git commit

### 2. Перевірте стан
- git status

## 8. Зміни, а не файли

### 1. Перша зміна: Додайте стандартні теги сторінок
 html
<html>
  <body>
    <h1>Hello, World!</h1>``````
  </body>
</html>

### 2. Додайте ці зміни
- git add hello.html

### 3. Друга зміна: Додайте заголовок HTML
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
![lesson_8.3](/screenshots/photo_8.jpg)

### 4. Перевірте поточний статус
- git status

![lesson_1.7.2-4](/screenshots/photo_7.jpg)
![lesson_8.3-4](/screenshots/photo_9.jpg)

### 5. Коміт
- git commit -m "Added standard HTML page tags"
- git status

### 6. Додайте другу зміну
- git add .
- git status

### 7. Зробіть коміт другої зміни
- git commit -m "Added HTML header"

![lesson_7.1](/screenshots/photo_11.jpg)

## 9. Історія проєкту

### 1. Отримання списку зроблених змін
- git log

![lesson_9.1](/screenshots/photo_12.jpg)

### 2. Однорядкова історія
- git log --pretty=oneline

![lesson_9.2](/screenshots/photo_13.jpg)

### 3. Контроль відображення записів
- git log --oneline --max-count=2
- git log --oneline --since="5 minutes ago"
- git log --oneline --until="5 minutes ago"
- git log --oneline --author="Your Name"
- git log --oneline --all

![lesson_9.3](/screenshots/photo_14.jpg)

### 4. Ухитряємося
- git log --all --pretty=format:"%h %cd %s (%an)" --since="7 days ago"

![lesson_9.4](/screenshots/photo_15.jpg)

### 5. Кінцевий формат історії
- git log --pretty=format:"%h %ad | %s%d [%an]" --date=short
- git config --global format.pretty '%h %ad | %s%d [%an]'
- git config --global log.date short

![lesson_9.5](/screenshots/photo_16.jpg)
![lesson_9.5](/screenshots/photo_17.jpg)

## 10. Отримання старих версій

### 1. Отримайте хеші попередніх комітів
- git log
- git checkout <hash>
- cat hello.html

![lesson_10.1](/screenshots/photo_18.jpg)
### 2. Поверніться до останньої версії в гілці main
- git switch main
- cat hello.html

![lesson_10.2](/screenshots/photo_19.jpg)

## 11. Створення тегів версій

### 1. Створіть тег першої версії
- git tag v1
- git log

![lesson_11.1](/screenshots/photo_20.jpg)

### 2. Теги для попередніх версій
- git checkout v1^
- cat hello.html
- git tag v1-beta
- git log

![lesson_11.2](/screenshots/photo_21.jpg)

### 3. Перемикання за ім'ям тегу
- git checkout v1
- git checkout v1-beta

![lesson_11.3](/screenshots/photo_22.jpg)

### 4. Перегляд тегів за допомогою команди tag
- git tag

![lesson_11.4](/screenshots/photo_23.jpg)

### 5. Перегляд тегів у логах
- git log main --all

![lesson_11.5](/screenshots/photo_24.jpg)
## 12.Скасування локальних змін (до індексації)

### 1. Перейдіть на гілку main
- git switch main

![lesson_12.1](/screenshots/photo_25.jpg)

### 2. Змініть hello.html
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <!-- This is a bad comment. We want to revert it. -->
  </body>
</html>
### 3. Перевірте стан
- git status

![lesson_12.3](/screenshots/photo_26.jpg)

## 4. Скасування змін в робочій директорії
- git restore hello.html
- git status
- cat hello.html

## Результат:
![lesson_12.4](/screenshots/photo_27.jpg)

## 13. Скасування проіндексованих змін (перед комітом)

### 1. Внесіть зміни у файл і проіндексуйте їх
<html>
<head>
    <!-- This is an unwanted but staged comment -->
</head>
<body>
<h1>Hello, World!</h1>
</body>
</html> 

- git add hello.html

### 2. Перевірте стан
- git status

![lesson_13.1-2](/screenshots/photo_28.jpg)

### 3. Відновлення індексу
- git restore --staged hello.html

## 4. Відновлення файлу
- git restore hello.html
- git status

![lesson_13.3-4](/screenshots/photo_29.jpg)

## 14. Скасування комітів

### 1. Змініть файл і зробіть коміт
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <!-- This is an unwanted but committed change -->
  </body>
</html>
- git add hello.html
- `git commit -m "Oops, we didn't want this commit"

### 2. Зробіть коміт з новими змінами, що скасовують попередні
- `git revert HEAD`

### 3. Перевірте лог
- git log

![lesson_14.1-3](/screenshots/photo_30.jpg)

![lesson_14.1-3](/screenshots/photo_31.jpg)

## 15. Видалення комітів з гілки (revert)

### 1. Перевірте нашу історію
- git log

### 2. Для початку позначте цю гілку
- git tag oops

### 3. Відкіт до коміту, що передує до oops
- git reset --hard oops^
- git log

## 4. Нічого ніколи не губиться
- git log --all

![lesson_15.1-4](/screenshots/photo_32.jpg)
![lesson_15.1-4](/screenshots/photo_33.jpg)

## 16. Видалення тегу oops
- git tag -d oops
- git log --all

![lesson_16.1-4](/screenshots/photo_34.jpg)

## 17. Внесення змін до комітів

### 1. Змініть сторінку, а потім зробіть коміт
<!-- Author: Alexander Shvets -->
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>

- git add hello.html
- git commit -m "Added copyright statement"
- git log

![lesson_15.1-4](/screenshots/photo_35.jpg)

### 2. Ой... необхідний email
<!-- Author: Alexander Shvets (alex@githowto.com) -->
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>

### 3. Змініть попередній коміт
- git add hello.html
- git commit --amend -m "Added copyright statement with email"

## 4. Перегляд історії
- git log

![lesson_17.1-4](/screenshots/photo_36.jpg)
![lesson_17.1-4](/screenshots/photo_37.jpg)

## 18. Створення гілки

### 1. Створіть гілку
- git switch -c style
- git status

![lesson_18.1](/screenshots/photo_38.jpg)

### 2. Додайте файл стилів style.css
- touch style.css
h1 {
  color: red;
}
- git add style.css
- git commit -m "Added css stylesheet"

![lesson_18.1-2](/screenshots/photo_40.jpg)

### 3. Змініть hello.html для того, щоб використовувати style.css
<!-- Author: Alexander Shvets (alex@githowto.com) -->
<html>
  <head>
    <link type="text/css" rel="stylesheet" media="all" href="style.css" />
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
- git add hello.html
- git commit -m "Included stylesheet into hello.html"

![lesson_18.3](/screenshots/photo_41.jpg)

## 19. Перемикання гілок
- git log --all

## 1. Перемкніться на гілку main
- git switch main
- cat hello.html

## 2. Повернемося до гілки style
- git switch style
- cat hello.html

![lesson_19.1-2](/screenshots/photo_43.jpg)
![lesson_19.1-2](/screenshots/photo_44.jpg)

## 20. Переміщення файлів

### 1. Перегляд історії змін конкретного файлу
- git log -- hello.html
- git log -- style.css

![lesson_19.1-2](/screenshots/photo_45.jpg)

### 2. Перегляд різниці між версіями певного файлу
- git show v1

![lesson_20.1-2](/screenshots/photo_46.jpg)

### 3. Перейменуйте hello.html.
- git mv hello.html index.html
- git status
- git add .
- git status

![lesson_20.3](/screenshots/photo_47.jpg)

## 4. Безпечне переміщення файлу style.css\- `mkdir css
- mkdir css
- git mv style.css css/style.css
- git status
- git commit -m "Renamed hello.html; moved style.css"
- git log css/style.css
- git log --follow css/style.css

![lesson_20.4](/screenshots/photo_49.jpg)
![lesson_20.4](/screenshots/photo_50.jpg)

## 21. Зміни в гілці main

### 1. Створіть файл README
This is the Hello World example from the GitHowTo tutorial.
### 2. Закомітьте файл README у гілку main
- git switch main
- git add README.md
- git commit -m "Added README"

![lesson_21.1-2](/screenshots/photo_51.jpg)
![lesson_21.1-2](/screenshots/photo_52.jpg)

## 22. Перегляд розбіжних гілок

### Перегляньте поточні гілки
git log --all --graph

![lesson_22](/screenshots/photo_53.jpg)

## 23. Злиття

### Злиття гілок
- git switch style
- git merge main
- git log --all --graph

![lesson_23](/screenshots/photo_54.jpg)

## 24. Створення конфлікту

### 1. Поверніться у main і створіть конфлікт
- git switch main
<!-- Author: Alexander Shvets (alex@githowto.com) -->
<html>
  <head>
    <title>Hello World Page</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <p>Let's learn Git together.</p>
  </body>
</html>
- git add hello.html
- git commit -m "Added meta title"

### 2. Перегляд гілок
- git log --all --graph

![lesson_24.1-2](/screenshots/photo_55.jpg)

## 25. Вирішення конфліктів

### 1. Злиття main до гілки style
- git switch style
- git merge main
- git status

![lesson_25.1](/screenshots/photo_56.jpg)
![lesson_25.1](/screenshots/photo_57.jpg)

## 2. Скасування злиття
- git merge --abort
- git status

![lesson_25.2](/screenshots/photo_58.jpg)

### 3. Рішення конфлікту
- git merge main
- відредагувати файл до стану, що нас влаштовує
### 4. Зробіть коміт з розв'язаним конфліктом
- git add index.html
- git commit -m "Resolved merge conflict"
- git status
- git log --all --graph

![lesson_25.3-4](/screenshots/photo_59.jpg)

## 26. rebase проти merge

## 27. Відкочування гілки style

### 1.  Відкотіть гілку style
- git switch style
- git log --graph
- git reset --hard HEAD~2

![lesson_27](/screenshots/photo_60.jpg)
![lesson_25.3-4](/screenshots/photo_61.jpg)

### 2. Перевірте гілку
- git log --graph

![lesson_25.3-4](/screenshots/photo_62.jpg)

## 28. Перебазування

### 1. Перебазуйте гілку style на main.
- git switch style
- git rebase main
- git status

![lesson_28.1](/screenshots/photo_63.jpg)

### 2 . Розв'яжіть конфлікт
- git add .
- git rebase --continue
- git status
- git log --all --graph

![lesson_28.2](/screenshots/photo_64.jpg)

## 29. Злиття в гілку main

### 1. Злиття style в main
- git switch main
- git merge style

### 2. Перегляньте логи
- git log --all --graph

![lesson_29.1-2](/screenshots/photo_65.jpg)
![lesson_29.1-2](/screenshots/photo_66.jpg)
