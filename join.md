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
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze';
```

## 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT *
FROM `course_teacher`
WHERE `teacher_id` = 44;
```
