### Contare quanti iscritti ci sono stati ogni anno

```SQL
SELECT YEAR(`enrolment_date`) AS year, COUNT(*) AS `total_students`
FROM `students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY year DESC
```

### 1 -Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```SQL
SELECT `office_address`, COUNT(*) AS `teacher_count`
FROM `teachers`
GROUP BY `office_address`
```

### 3 - Calcolare la media dei voti di ogni appello d'esame

```SQL
SELECT `exam_id`, AVG(`vote`) AS `average_vote`
FROM `exam_student`
GROUP BY `exam_id`
```

### 4 - Contare quanti corsi di laurea ci sono per ogni dipartimento

```SQL
SELECT `department_id`, COUNT(*) AS `total_courses`
FROM `degrees `
GROUP BY `department_id`
```
