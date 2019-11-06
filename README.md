# dvmn_e-diary_utils
Утилита для исправления успеваимости [электронного дневника сайта школы](https://github.com/Zed-chi/e-diary). Можно исправить оценки, убрать замечания, добавить похвальные записи.

## Запуск скриптов по успеваемости

Скрипт должен лежать в корне сайта рядом с `manage.py`
Проще всего запустить сам файл utils.py или функцию main оттуда
1) `python utils.py`
2) `from utils import main`

Либо запускать функции fix_marks/remove_chastisements/create_commendation по отдельности.
 
## Функции в файле:

`get_kid(kid_name)` : Принимает имя ребенка, которого нужно найти, возвращает обьект модели Schoolkid из базы Если учеников с таким именем не найдено или найдено несколько учеников, то происходит вызов исключения.

`get_marks(kid)` : Принимает обьект модели Schoolkid возвращает все найденные оценки связанные с ним.

`get_bad_marks(kid)` : Аналогично get_marks(kid), только возвращает оценки 2 и 3.

`fix_marks(marks)` : Принимает набор обьектов Mark и исправляет в каждом значение points на 4 или 5.

`get_chastisements(kid)` : Принимает обьект модели Schoolkid и возвращает найденные обьекты модели замечаний.

`remove_chastisements(chastisements)` : Принимает набор обьектов модели замечаний и удаляет их из базы данных.

`get_lessons(title, year=6, letter="А")` : Принимает название предмета, год и букву класса ученика, возвращает набор найденных обьектов модели Lesson.

`create_commendation(kid_name, lesson_title)` : Принимает имя ученика, название предмета урока и создает обьект модели Сommendation с текстом похвалы в случайный день проводившихся уроков.

`main()` :
Запрашивает имя ученика и название предмета в терминале, исправляет плохие оценки, удаляет замечания, создает похвальную запись.

## Цели проекта

Код написан в учебных целях — это урок в курсе по Python и веб-разработке на сайте [Devman](https://dvmn.org).
