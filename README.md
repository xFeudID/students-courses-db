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
