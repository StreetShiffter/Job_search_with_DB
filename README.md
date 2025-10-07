 
<h3 style="background: linear-gradient(257deg, Gold, green); -webkit-background-clip: text; color: transparent;">
  Проект "Парсер вакансий hh.ru через SQL"
</h3> 

# 🔖 Описание проекта:

Данный проект является парсером по сайту HH.ru. Всю полученную информацию заносит в структурированную таблицу базы данных.


# 🔧 Установка компонентов:


1. Создайте проект и установите poetry:


```pip install --user poetry```

2. Клонируйте репозиторий:


```git clone https://github.com/StreetShiffter/PythonOOPHW.git```

3. Установите инструменты для обработки кода


![Black](https://img.shields.io/badge/black-000000?style=flat&logo=python&logoColor=white)

![Mypy](https://img.shields.io/badge/mypy-checked-blue.svg?logo=python&logoColor=green)

![Flake8](https://img.shields.io/badge/flake8-checked-blue.svg?logo=python&logoColor=blue)

![JSON](https://img.shields.io/badge/json-5E5C5C?logo=json&logoColor=red)

КОМАНДЫ ДЛЯ УСТАНОВКИ ЗАВИСИМОСТЕЙ
```
poetry add --dev flake8 mypy isort black
pip install types-requests
```

# ✒️ Использование
Основное использование приложения запускается из файла *main.py*

⚠️ ВАЖНО ⚠️
*Для проверки работы программы воспользуйтесь pgAdmin.* 

Для работы с таблицами установите библиотеку *psycopg2* 
```
 poetry add psycopg2 
```

### 🗂 Структура таблиц:

#### Таблица `employers`:
| Поле         | Тип           | Описание              |
|--------------|----------------|------------------------|
| id_company   | VARCHAR(20)    | ID работодателя       |
| name         | VARCHAR(255)   | Название компании     |
| alternate_url| TEXT           | Ссылка               |
| area         | VARCHAR(100)   | Регион                |

#### Таблица `vacancies`:
| Поле         | Тип           | Описание              |
|--------------|----------------|------------------------|
| id           | VARCHAR(20)    | ID вакансии            |
| employer_id  | VARCHAR(20)    | Ссылка на компанию     |
| name         | VARCHAR(255)   | Название вакансии      |
| salary_from  | INTEGER        | Зарплата от            |
| salary_to    | INTEGER        | Зарплата до            |
| currency     | VARCHAR(10)    | Валюта                 |
| url          | TEXT           | Ссылка на вакансию     |



# Структура проекта
```
Kurse_2_class_OOP/
├── 📁 data/ # Директория для хранения данных
├── 📁 src/ # Основной код приложения
│ ├── 📄init .py # Инициализация пакета
│ ├── 📄api_class_.py # Класс парсер по API
│ ├── 📄database.py # Модуль создания БД и таблиц
│ ├── 📄db_manager.py # Класс для работы с БД через SQL запросы
│ └── 📄utils.py # Вспомогательные утилиты
├── 📄.flake8 # Настройки flake8
├── 📄.gitignore # Исключения для Git
├── 📄config.py # Конфигурационный файл
├── 📄database.ini # Конфигурационный файл БД
├── 📄main.py # Главный скрипт
├── 📄poetry.lock # Зависимости Poetry
├── 📄pyproject.toml # Конфигурация Poetry
└── 📄README.md # Этот файл
```

# 📝 Документация 

Для получения дополнительной информации обратитесь к [документации](https://api.hh.ru/openapi/redoc#section)
