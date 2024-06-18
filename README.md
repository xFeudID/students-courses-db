

## Ф.И.О, № группы
Почкалов Ростислав, группа ИС22-9/1

## Описание Базы Данных
База данных создана для хранения информации о студентах и курсах. Основные таблицы: `students`, `courses`, `student_courses`.

### Таблицы и их атрибуты

#### Таблица `students`
| Поле         | Тип         | Описание                        |
|--------------|-------------|---------------------------------|
| `student_id` | SERIAL      | Уникальный идентификатор студента |
| `first_name` | VARCHAR(50) | Имя студента                    |
| `last_name`  | VARCHAR(50) | Фамилия студента                |
| `group_number`| VARCHAR(10)| Номер группы студента           |

![](/image/students.png)


#### Таблица `courses`
| Поле         | Тип         | Описание                        |
|--------------|-------------|---------------------------------|
| `course_id`  | SERIAL      | Уникальный идентификатор курса  |
| `course_name`| VARCHAR(100)| Название курса                  |
| `description`| TEXT        | Описание курса                  |

![](/image/courses.png)

#### Таблица `student_courses`
| Поле         | Тип         | Описание                        |
|--------------|-------------|---------------------------------|
| `student_id` | INT         | Идентификатор студента (внешний ключ к `students.student_id`) |
| `course_id`  | INT         | Идентификатор курса (внешний ключ к `courses.course_id`)    |
| PRIMARY KEY (`student_id`, `course_id`) | - | Первичный ключ, комбинирующий `student_id` и `course_id` |
| FOREIGN KEY (`student_id`) REFERENCES `students`(`student_id`) | - | Внешний ключ на таблицу `students` |
| FOREIGN KEY (`course_id`) REFERENCES `courses`(`course_id`)    | - | Внешний ключ на таблицу `courses`  |

![](/image/students_courses.png)

### Схема
![](/image/image.png)

### Демонстрация запросов

#### 1. UNION
![](/image/1.jpg)
Описание: Результирующая таблица включает имена студентов и названия курсов.

#### 2. ORDER BY
![](/image/2.jpg)
Описание: Таблица отсортирована по фамилии студентов.

#### 3. HAVING
![](/image/3.jpg)
Описание: Таблица групп с количеством студентов более одного.

#### 4. Вложенный запрос
### 4.1. SELECT
![](/image/4.jpg)
Описание: Результат запроса включает имена студентов и названия их курсов.

### 4.2. WHERE
![](/image/5.jpg)
Описание: Таблица студентов, которые зарегистрированы на курс с ID 1.

#### 5. Оконные функции
### 5.1. Агрегатные функции
![](/image/6.jpg)
Описание: Количество студентов в каждой группе.

### 5.2. Ранжирующие функции
![](/image/7.jpg)
Описание: Ранжирование студентов по фамилии.

### 5.3. Функции смещения
![](/image/8.jpg)
Описание: Предыдущий студент в отсортированном списке по фамилии.

#### 6. Работа join'ов
### INNER JOIN
![](/image/9.jpg)
### LEFT JOIN
![](/image/10.jpg)
### RIGHT JOIN
![](/image/11.jpg)
### FULL OUTER JOIN
![](/image/12.jpg)
Описание: Информация о студентах и их курсах.

#### 7. CASE
![](/image/13.jpg)
Описание: Присвоение меток группам студентов.

#### 8. WITH
![](/image/14.jpg)
Описание: Использование временной таблицы для подсчета количества студентов в группах.
