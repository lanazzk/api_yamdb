# API к сервису YaMDb

---

### Описание сервиса

---

Сервис **YaMDb** собирает **отзывы (Review)** пользователей на **произведения (Titles)**. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список **категорий (Category)** может быть расширен администратором (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
Произведению может быть присвоен жанр (Genre) из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор.

Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

### Документация к сервису находится по адресу (после установки и запуска):
`http://127.0.0.1:8000/redoc/`

## Установка и запуск

Склонировать репозиторий

    git clone git@github.com:Alfaram/api_yamdb.git

Создать и активировать виртуальное окружение
    
    python -m venv venv
    
    source venv\bin\activate

Создать и активировать виртуальное окружение
    
    python -m venv venv
    
    source venv\bin\activate

Обновить pip
    
    python -m pip install --upgrade pip

Установить зависимости из файла requirements.txt

    pip install -r requirements.txt

Выполнить миграции

    python manage.py migrate

Запустить сервер

    python manage.py runserver

### Примеры запросов/ответов:

#### Запрос на получение токена авторизации:

```json
{
  "username": "Ваш логин",
  "confirmation_code": "Код подтверждения"
}
```
#### Ответ:

```json
{
  "token": "Токен для авторизации на сервисе"
}
```

#### Contributors:

[Виталий](https://github.com/vkoolko) - система аутентификации, авторизации, управление доступом пользователей. 

[Максим](https://github.com/Alfaram) - отзывы (Review) и комментарии (Comments):  модели, представления, настраивает эндпойнты, определяет права доступа для запросов. рейтинги произведений

[Светлана](https://github.com/lanazzk) - категории (Categories), жанры (Genres) и произведения (Titles): модели, представления и эндпойнты для них

### Лицензия [MIT](https://opensource.org/licenses/MIT)

