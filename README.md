# Тестовое задание

## Брифинг
В файле **data/stream.json** находятся данные из ленты событий пользователя.
Необходимо вывести список событий в виде вертикальной ленты событий с кратким превью каждого события.
При клике по событию в ленте, открывается подробная информацией о событии.
Есть возможность "лайкать" события.

## Задача
Реализовать ленту событий на основе входных данных, с возможностью просмотра подробной информации по каждому событию;
Необходима возможность "лайкать" события. Если событие уже было "полайкано", то при нажатии на кнопку "лайка" необходимо снимать "лайк".
Постарайтесь не использовать сторонние библиотеки, но jQuery можно.

Необходимо максимально оптимизировать скорость загрузки страницы, за исключением минификации и обфускации файлов.

Страница должна хорошо выглядеть на современных мобильных устройствах.

Мобильные браузеры: Safari, Chrome, FireFox, UC Browser(желательно). 

### Лента (Список событий)
В ленте каждое событие представлено в виде блока с минимальным набором информации:

- аватар пользователя + имя (или ник, если нет имени)
- дата события
- весь заголовок(поле **title**) или максимум 100 первых символов текста события (поле **user_text**)
- максимум 1 фотография
- количество "лайков" (если доступно)
- количество "комментариев" (если доступно)

### Подробно о событии
В блоке подробной информации о событии необходимо вывести

- аватар пользователя + имя (или ник, если нет имени)
- дата события
- весь текст с ссылками и тегами (из **text_media**)
- заголовок + описание, если есть(**title** и **description**)
- все фотографии
- все видео
- количество "лайков" (если доступно)
- количество "комментариев" (если доступно)

### Описание полей
- **author** - информация об авторе события
- **is_commentable** - флаг о доступности комментирования
- **is_likeable** - флаг о доступности "лайка"
- **is_liked_by_me** - флаг, "лайкал" ли пользователь событие
- **text_media** - массив, содержащий в себе результат разбиения текста поста на куски по типу данных. Каждый элемент массива может быть текстом(text), ссылкой (link), тэгом(tag).
- **time** - дата события
- **type_name** - название события
- **attachments** - массив приложений к событию. Может содержать картинки(image) и ссылки(link) 

## Дизайн

Интерфейс должен быть максимально похожим на то, что на макетах. Если придётся отступиться от дизайна по каким-то причинам - напишите пояснения(например, что-то не нарисовано на макетах).

Макет резиновый до 600px, далее он просто центрируется в окне.

Оригиналы в масштабе x2. 

### Лента

Второе событие на макете - это оформление для событий с **type_name** в значениях **share**, **app_add** и **user_community_actions_enter**.  

<img src="https://github.com/Belyash/mailru-test/raw/master/screens/feed.jpg?raw=true" alt="Лента событий" width="360"/>

### Страница события

 В шапке появляется кнопка "Назад", при нажатии на которую нас возвращает в ленту.
 Блоки "Нравится" и "Комментарии" - полностью статические без динамики (голый HTML). 
 Поле ввода комментария всегда прибито к низу экрана.

<img src="https://github.com/Belyash/mailru-test/raw/master/screens/feed-post.png?raw=true" alt="Страница события" width="360"/>
 
 
## P.S.
 
Если во входном JSON есть ошибки, то допускается их исправление.