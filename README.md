# Документирование приложения интернет-магазина ювелирных изделий

## 1. Структура функциональных возможностей (Mind Map)

```mermaid
mindmap
  root((Веб-приложение Ювелирный магазин))
    Пользователи
      Регистрация
      Профиль
    Товары
      Каталог ювелирных изделий
      Фильтры по характеристикам изделий
      Отзывы
    Корзина
      Общая сумма
      Добавленные товары
      История транзакций
    Безопасность
      Аутентификация
      Защита данных

```

### Описание:

Эта диаграмма иллюстрирует структуру функциональных возможностей для интернет-магазина ювелирных изделий.

### Основные узлы и их значение:

* <u>Пользователи:</u> функционал, связанный с управлением учетными записями.

* <u>Товары:</u> доступные для покупки изделия.

* <u>Корзина:</u> добавленные для покупки изделия

* <u>Безопасность:</u> безопасная передача данных пользователей


## 2. Диаграмма путешествия пользователя (User Journey Diagram)

```mermaid
journey
  title Путь пользователя: Первая покупка
  section Регистрация
    Переход на сайт: 5: Новый пользователь
    Заполнение формы: 4: Новый пользователь
    Подтверждение доступности логина: 3: Система
  section Каталог ювелирных изделий
    Просмотр ювелирных изделий: 4: Клиент
    Фильтрация по предпочтениям: 3: Клиент
    Добавление товара в корзину: 2: Клиент
  section Оформление покупки
    Переход в корзину: 5: Клиент
    Подтверждение покупки: 4: Клиент
  section Написание отзыва
    Переход на страницу ювелирного изделия: 5: Клиент
    Написание отзыва: 4: Клиент
    Отправка отзыва: 3: Клиент

```

### Описание:

Диаграмма описывает ключевые этапы взаимодействия пользователя с системой:

* Регистрация: пользователь создает учетную запись.

* Каталог ювелирных изделий: пользователь просматривает доступные товары и добавляет в корзину.

* Оформление покупки: пользователь совершает заказ

* Написание отзыва: пользователь описывает свои впечатления от заказа


## 3. Квадрант-граф (Prioritization Quadrant)

```mermaid
quadrantChart

    title Priorities of Functionality Development
    x-axis Easy --> Hard
    y-axis Low Priority --> High Priority

    "Регистрация": [0.28, 0.9]
    "Список товаров": [0.4, 0.95]
    "Фильтрация товаров": [0.7, 0.6]
    "Корзина": [0.6, 0.8]
    "Система отзывов": [0.55, 0.45]
    "Редактирование профиля": [0.3, 0.3]
    "Аутентификация": [0.1, 0.9]
    "Защита данных": [0.9, 0.9]

```

### Описание:

Квадрант-граф помогает приоритизировать разработку функций системы. Каждая точка соответствует функционалу:

* Ось X: сложность реализации (от простого к сложному).

* Ось Y: приоритет для пользователей (от низкого к высокому).

## 4. Гит граф (Gitgraph)

```mermaid
gitGraph
    commit id: "v0.1.0: Project initialization"
    commit id: "v0.2.0: Basic market layout"
    commit id: "v0.3.0: Basic navigation"

    branch feature-auth
    checkout feature-auth
    commit id: "Add user registration"
    commit id: "Add user authentication"

    checkout main
    merge feature-auth id: "Merge auth features into main"
    commit id: "v0.4.0: Authentication and registration features"

    branch feature-jewelry
    checkout feature-jewelry
    commit id: "Add jewelry list"
    commit id: "Implement jewelry filters"
    commit id: "Add putIntoBasket button"

    checkout main
    merge feature-jewelry id: "Merge jewelry features into main"
    commit id: "v0.5.0: Jewelry list features"

    branch feature-basket
    checkout feature-basket
    commit id: "Add jewelry list on basket page"
    commit id: "Add total cost on basket page"
    commit id: "Add orderJewelry feature"

    checkout main
    merge feature-basket id: "Merge basket features into main"
    commit id: "v0.6.0: Basket features"

    branch feature-review
    checkout feature-review
    commit id: "Add review functionality"
    commit id: "Implement checks for review permission"

    checkout main
    merge feature-review id: "Merge review features into main"
    commit id: "v0.7.0: Reviews release"

    branch feature-security
    checkout feature-security
    commit id: "Improve data protection"
    commit id: "Implement review checks"
    commit id: "Advanced logging security updates"

    checkout main
    merge feature-security id: "Merge security features into main"
    commit id: "v0.8.0: Security enhancements"

    commit id: "v1.0.0: First stable release"


```

### Описание:

 Гит-граф показывает процесс разработки системы через версии:

1. Основная ветка (main): стабильные версии системы.

2. Функциональные ветки: каждая ветка посвящена отдельной функциональности (список изделий, корзина и т.д.).

3. Слияния: после завершения работы над веткой, изменения интегрируются в main.
