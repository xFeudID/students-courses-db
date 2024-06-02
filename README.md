# Проект базы данных: Студенты и Курсы

## Ф.И.О, № группы
Почкалов Ростислав, группа ИС22-9/1

## Описание Базы Данных
База данных создана для хранения информации о студентах и курсах. Основные таблицы: `students`, `courses`, `student_courses`.

### Таблицы и их атрибуты

#### Таблица `students`
- `student_id`: SERIAL, PRIMARY KEY
- `first_name`: VARCHAR(50), NOT NULL
- `last_name`: VARCHAR(50), NOT NULL
- `group_number`: VARCHAR(10), NOT NULL

#### Таблица `courses`
- `course_id`: SERIAL, PRIMARY KEY
- `course_name`: VARCHAR(100), NOT NULL
- `description`: TEXT

#### Таблица `student_courses`
- `student_id`: INT, NOT NULL
- `course_id`: INT, NOT NULL
- PRIMARY KEY (student_id, course_id)
- FOREIGN KEY (student_id) REFERENCES `students`(student_id)
- FOREIGN KEY (course_id) REFERENCES `courses`(course_id)

### Демонстрация запросов

#### 1. UNION
![](/scrinshots/UNION.jpg)
Описание: Результирующая таблица включает имена студентов и названия курсов.

#### 2. ORDER BY
![](/scrinshots/ORDER_BY.jpg)
Описание: Таблица отсортирована по фамилии студентов.

#### 3. HAVING
![](/scrinshots/HAVING.jpg)
Описание: Таблица групп с количеством студентов более одного.

#### 4. Вложенный запрос
### 4.1. SELECT
![](/scrinshots/SELECT.jpg)
Описание: Результат запроса включает имена студентов и названия их курсов.

### 4.2. WHERE
![](/scrinshots/WHERE.jpg)
Описание: Таблица студентов, которые зарегистрированы на курс с ID 1.

#### 5. Оконные функции
### 5.1.
![](/scrinshots/Агрегатные_функции.jpg)
Описание: Количество студентов в каждой группе.

### 5.2.
![](/scrinshots/Ранжирующие_функции.jpg)
Описание: Ранжирование студентов по фамилии.

### 5.3.
![](/scrinshots/Функции_смешения.jpg)
Описание: Предыдущий студент в отсортированном списке по фамилии.

#### 6. Работа join'ов
![](/scrinshots/join.jpg)
Описание: Информация о студентах и их курсах.

#### 7. CASE
![](/scrinshots/case.jpg)
Описание: Присвоение меток группам студентов.

#### 8. WITH
![](/scrinshots/with.jpg)
Описание: Использование временной таблицы для подсчета количества студентов в группах.
