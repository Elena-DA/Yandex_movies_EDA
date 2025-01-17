# Исследование рынка российского кинопроката

Заказчик этого исследования — Министерство культуры Российской Федерации.

Нужно изучить рынок российского кинопроката и выявить текущие тренды. Уделить внимание фильмам, которые получили государственную поддержку и выяснить, насколько такие фильмы интересны зрителю.

Вы будете работать с данными, опубликованными на [портале открытых данных Министерства культуры](http://opendata.mkrf.ru/). Набор данных содержит информацию о прокатных удостоверениях, сборах и государственной поддержке фильмов, а также информацию с сайта КиноПоиск.

---
    
**Описание данных**

Таблица `mkrf_movies` содержит информацию из реестра прокатных удостоверений. У одного фильма может быть несколько прокатных удостоверений.

- `title` — название фильма;
- `puNumber` — номер прокатного удостоверения;
- `show_start_date` — дата премьеры фильма;
- `type` — тип фильма;
- `film_studio` — студия-производитель;
- `production_country` — страна-производитель;
- `director` — режиссёр;
- `producer` — продюсер;
- `age_restriction` — возрастная категория;
- `refundable_support` _—_ объём возвратных средств государственной поддержки;
- `nonrefundable_support` _—_ объём невозвратных средств государственной поддержки;
- `financing_source` _—_ источник государственного финансирования;
- `budget` _—_ общий бюджет фильма;
- `ratings` _—_ рейтинг фильма на КиноПоиске;
- `genres` _—_ жанр фильма.

Обратите внимание, что столбец `budget` уже включает в себя полный объём государственной поддержки. Данные в этом столбце указаны только для тех фильмов, которые получили государственную поддержку.

Таблица `mkrf_shows` содержит сведения о показах фильмов в российских кинотеатрах.

- `puNumber` — номер прокатного удостоверения;
- `box_office` — сборы в рублях.
---
    
**Цель исследования**

1. Изучить рынок российского кинопроката и выявить текущие тренды
2. Исследовать фильмы, которые получили государственную поддержку
3. Выявить, насколько фильмы с господдержкой интересны зрителю
---
    
***Ход исследования***
    
Данные о прокатных удостоверениях получим из файла `/datasets/mkrf_movies.csv`, а также есть данные о прокате в российских кинотеатрах, их получим из файла `/datasets/mkrf_shows.csv`. О качестве датасетов информации нет. Перед тем как приступать к цели исследования, необходимо объединить эти два файла и изучить данные.
    
Проверим данные на предмет ошибок и оценим их влияние на результаты исследования. В процессе преодобработки данных попробуем исправить все ошибки, которые могут привести к искажению конечного результата. Далее мы создадим необходимые столбцы и приступим к исследовательскому анализу данных.
    
Таким образом, мое исследование пройдет в пять этапов:
- изучение предоставленных данных и объединение их в один датафрейм
- предобработка данных
- расчеты и добавление результатов в таблицу
- изучение закономерностей в данных
- написание общего вывода

**Используемые языки и библиотеки**

**Python**, *pandas*, *matplotlib*, *numpy*, *seaborn*
