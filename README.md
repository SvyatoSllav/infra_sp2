# Infra_sp2

### Описание
Проект infra собирает отзывы (Review) пользователей на произведения (Titles).
Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором.
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
Произведению может быть присвоен жанр (Genre) из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор.
Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). 
На одно произведение пользователь может оставить только один отзыв.

### **Стек**
![python version](https://img.shields.io/badge/Python-3.7-green)
![django version](https://img.shields.io/badge/Django-2.2-green)
![pillow version](https://img.shields.io/badge/Pillow-8.3-green)
![pytest version](https://img.shields.io/badge/pytest-6.2-green)
![sorl-thumbnail version](https://img.shields.io/badge/thumbnail-12.7-green)
![sorl-thumbnail version](https://img.shields.io/badge/Django%20REST%20Framework-%203.12.4-green)
![python version](https://img.shields.io/badge/Docker-3.3-green)
![python version](https://img.shields.io/badge/Nginx-%201.18-green)
![python version](https://img.shields.io/badge/Docker-3.3-green)
![python version](https://img.shields.io/badge/Docker-3.3-green)

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/evencatt/infra_sp2.git
```

```
cd infra
```

Развернуть докер контэйнеры:
```
sudo docker-compose up
```

Выполнить миграции и собрать статику
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```

### Примеры использования api:
Получение произведений:
```
GET /api/v1/titles/
```
Добавление произведения (только администратор):
```
POST /api/v1/titles/
```
В параметрах передавать json
```
{
    "name": "Название произведения",
    "year": 1990,
    "description": "Описание произведения",
    "genre": [
    "fantasy"
    ],
    "category": "films"
}
```
