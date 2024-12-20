### 1 - Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```SQL
SELECT `s`.*
FROM `students` AS `s`
JOIN `degrees` AS `d`
ON `s`.`degree_id` = `d`.`id`
WHERE `d`.`name` = 'Corso di Laurea in Economia';
```

### 2 - Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```SQL
SELECT `deg`.*
FROM `degrees` AS `deg`
JOIN `departments` AS `dep`
ON `deg`.`department_id` = `dep`.`id`
WHERE `deg`.`level` = 'magistrale'
AND `dep`.`name` = 'Dipartimento di Neuroscienze';
```

### 3 - Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL
SELECT `c`.*
FROM `courses` AS `c`
JOIN `course_teacher` AS `c_t`
ON `c`.`id` = `c_t`.`course_id`
JOIN `teachers` AS `t`
ON `c_t`.`teacher_id` = `t`.`id`
WHERE `t`.`id` = 44;
```

### 4 - Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```SQL
SELECT  `s`.`surname`, `s`.`name`, `deg`.`name` AS 'degree', `dep`.`name` AS 'department'
FROM `students` AS `s`
JOIN `degrees` AS `deg`
ON `s`.`degree_id` = `deg`.`id`
JOIN `departments` AS `dep`
ON `deg`.`department_id` = `dep`.`id`
ORDER BY `s`.`surname`, `s`.`name`;
```

### 5 - Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```SQL
SELECT `deg`.`name` AS 'degree', `c`.`name` AS 'course',  `t`.`surname`, `t`.`name`
FROM `degrees` AS `deg`
JOIN `courses` AS `c`
ON `deg`.`id` = `c`.`degree_id`
JOIN `course_teacher` AS `c_t`
ON `c`.`id` = `c_t`.`course_id`
JOIN `teachers` AS `t`
ON `c_t`.`teacher_id` = `t`.`id`
ORDER BY `deg`.`name`, `c`.`name`
```

### 6 - Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```SQL
SELECT DISTINCT `t`.`surname`, `t`.`name`
FROM `teachers` AS `t`
JOIN `course_teacher` AS `c_t`
ON `t`.`id` = `c_t`.`teacher_id`
JOIN `courses` AS `c`
ON `c_t`.`course_id` = `c`.`id`
JOIN `degrees` as `deg`
ON `c`.`degree_id` = `deg`.`id`
JOIN `departments` as `dep`
ON `deg`.`department_id` = `dep`.`id`
WHERE `dep`.`name` = 'Dipartimento di Matematica'
```

### 7 - BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```SQL

```
