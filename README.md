#План автоматизации тестирования

##Автоматизируемые сценарии
Необходимо автоматизировать тестирование записи на курс “Тестировщик ПО”

###Сценарии отправки формы:

- Главная страница→Каталог курсов→Программирование→Тестировщик ПО→Записаться (в описании курса)→Записаться (отправка формы)

- Главная страница→Каталог курсов→Программирование→Тестировщик ПО→Условия акции→Купить курс→Записаться (отправка формы)

- Главная страница→Каталог курсов→Программирование→Тестировщик ПО→Записаться (отправка формы внизу страницы)

- Главная страница→(Направления обучения) Программирование→Тестировщик ПО→Записаться (в описании курса)→Записаться (отправка формы)

- Главная страница→(Направления обучения) Программирование→Тестировщик ПО→Условия акции→Купить курс→Записаться (отправка формы)

- Главная страница→(Направления обучения) Программирование→Тестировщик ПО→Записаться (отправка формы внизу страницы)

- Главная страница→Выбрать курс→Тестировщик ПО→Записаться (в описании курса)→Записаться (отправка формы)

- Главная страница→Выбрать курс→Тестировщик ПО→Условия акции→Купить курс→Записаться (отправка формы)

- Главная страница→Выбрать курс→Тестировщик ПО→Записаться (отправка формы внизу страницы)

####Ожидаемый результат: отправляется заявка на обучение

###Сценарии заполнения формы:

####Заполнение поля ввода имени валидными значениями и отправка формы:
- Имя кириллицей с заглавной буквы (Иван)
- Имя кириллицей с маленькой буквы (иван)
- Имя латиницей с заглавной буквы (Petr)
- Имя латиницей с маленькой буквы (petr)
- Имя с ё (Пётр)
- Имя кириллицей через дефис (Аль-Кадир)
- Имя кириллицей с пробелом (Аль Кадир)
- Имя латиницей через дефис (Al-Kadyr)
- Имя латиницей с пробелом (Al Kadyr)

####Ожидаемый результат: форма заполняется корректно, отправляется заявка на обучение

####Заполнение поля ввода имени невалидными значениями и отправка формы:
оставить поле пустым

####Ожидаемый результат: появляется сообщение “Обязательное поле”, заявка на обучение не отправляется
заполнить поле цифрами (1234)

####Ожидаемый результат: появляется сообщение “Должно состоять из букв”, заявка на обучение не отправляется
заполнить поле знаками препинания (!!!)

####Ожидаемый результат: появляется сообщение “Должно состоять из букв”, заявка на обучение не отправляется
заполнить поле одной буквой (А)

####Ожидаемый результат: появляется сообщение “Должно быть не короче 2 символов”, заявка на обучение не отправляется

####Заполнение поля ввода телефона валидными значениями и отправка формы:

- заполнить поле форматом +7 и 10-ти значный номер (+7 9999999999)
- заполнить поле форматом 8 и 10-ти значный номер (8 9999999999)
- заполнить поле 9-ти значным номером (123456789)
- заполнить поле 14-ти значным номером (12345678901234)

####Ожидаемый результат: форма заполняется корректно, отправляется заявка на обучение

####Заполнение поля ввода телефона невалидными значениями и отправка формы:
оставить поле пустым

####Ожидаемый результат: появляется сообщение “Обязательное поле”, заявка на обучение не отправляется
заполнить поле буквами (ааа)

####Ожидаемый результат: появляется сообщение “Номер в формате +9 (999) 999-99-99”, заявка на обучение не отправляется
заполнить поле знаками препинания (!!!)

####Ожидаемый результат: появляется сообщение “Номер в формате +9 (999) 999-99-99”, заявка на обучение не отправляется
заполнить поле 8-ми значным номером (12345678)

####Ожидаемый результат: появляется сообщение “Номер в формате +9 (999) 999-99-99”, заявка на обучение не отправляется
заполнить поле 15-ти значным номером (123456789012345)

####Ожидаемый результат: появляется сообщение “Номер в формате +9 (999) 999-99-99”, заявка на обучение не отправляется

####Отправка формы через кнопку “Записаться”

####Ожидаемый результат: отправляется заявка на обучение


#Используемые инструменты
- Java Преимущества: наличие готовых фреймворков для автоматизированного тестирования web-приложений 
- Selenide (фреймворк для автоматизированного тестирования) Преимущества: поддерживает кросс-браузерную автоматизацию, лаконичная документация, более простой поиск локаторов. Для тестирования web-интерфейса
- RestAssured (библиотека для тестирования API) Преимущества:подходит для проверки небольшого количества http-запросов. Для тестирования запросов к серверу
- Junit5 (библиотека для тестирования) Преимущества: содержит методы и аннотации, упрощающие написание тестовых методов
- Allure (фремйворк для составления отчетности по результатам тестирования) Преимущества: результаты тестирования понятным не только автоматизаторам, но и другим участникам команды


#Необходимые разрешения/данные/доступы
- разрешение на проведение автоматизированного тестирования
- SUT, в которой заявки на обучение не будут уходить в отдел продаж
- доступ к базе данных и API сайта


#Возможные риски для автоматизации
- Изменения в структуре html-страницы в отношении элементов с акциями (Пример: Условия акции→Купить курс→Записаться (отправка формы))
- Высокие временные и финансовые затраты при небольшом покрытии тестированием функциональности сайта
- сложность с поиском локаторов в разметке сайта
#Необходимые специалисты для автоматизации
инженер по автоматизации

#Интервальная оценка с учетом рисков (в часах)


Задача        | Время
------------- | -------------
Разработка тестовых сценариев  | 8 часов
Написание автотестов  | 40 часов
Работа с результатами и документацией | 8 часов
Риски | 16 часов
Итого | 72 часа
