## QUERY TO DO:

## 1. Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT COUNT(`id`) AS 'tot_subscribers'
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

## 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT COUNT(`id`) AS 'same_office_num', `office_address`
FROM `teachers`
GROUP BY `office_address`;
```

## 3. Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT AVG(`vote`), `exam_id`
FROM `exam_student`
GROUP BY `exam_id`;
```

## 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT COUNT(`id`), `department_id`
FROM `degrees`
GROUP BY `department_id`;
```
