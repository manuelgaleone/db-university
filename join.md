## QUERY TO DO:

## 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT *
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

## 2. Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze

```sql
SELECT *
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze'
AND `degrees.level` = `magistrale`;
```

## 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT *
FROM `course_teacher`
WHERE `teacher_id` = 44;
```

## 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT `students`.*, `degrees`.*, `departments`.*
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees.id`
JOIN `departments` ON `degrees.department_id` = `departments.id`
ORDER BY `students.name`, `students.surname`;
```

## 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT `degrees.name`, `courses.name`, `courses.period`, `courses.year`, `courses.cfu`, `teachers.name`, `teachers.surname`
FROM `degrees`
JOIN `course_teacher` ON `course_teacher.course_id` = `courses.id`
JOIN `teachers` ON `course_teacher`.`course_id` = `teachers.id`;
```

## 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
SELECT `teachers`.*
FROM `course_teacher` ON `course_teacher`.`teacher_id` = `teacher.id`
JOIN `courses` on `course_teacher`.`course_id` = `courses.id`
JOIN `degrees` ON `courses.degree_id` = `degrees.id`
JOIN `departments` ON `degrees.department_id` = `departments.id`
WHERE `departments.name` = 'Dipartimento di Matematica';
```
