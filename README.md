### 1 - Selezionare tutti gli studenti nati nel 1990

```SQL

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990
```

### 2 - Selezionare tutti i corsi che valgono più di 10 crediti

```SQL

SELECT *
FROM `courses`
WHERE `cfu` > 10;
```

### 3 - Selezionare tutti gli studenti che hanno più di 30 anni

```SQL

SELECT *
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) > 30;

```

### 4 - Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea

```SQL

SELECT *
FROM `courses`
WHERE period = "I semestre" AND year = 1;
```

### 5 - Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020

```SQL

SELECT *
FROM `exams`
WHERE `date` = "2020-06-20" AND `hour` > "14:00:00";
```

### 6 - Selezionare tutti i corsi di laurea magistrale

```SQL

SELECT *
FROM degrees
WHERE level = "magistrale"

```

### 7 - Da quanti dipartimenti è composta l'università?

```SQL

SELECT COUNT(*) AS department_count
FROM `departments`;
```

### 8 - Quanti sono gli insegnanti che non hanno un numero di telefono?

```SQL

SELECT COUNT(*) AS teacher_without_phone
FROM `teachers`
WHERE `phone` IS NULL;
```

### 9 - Inserire nella tabella degli studenti un nuovo record con i propri dati

```SQL

INSERT INTO `students` (name, surname, date_of_birth, degree_id, email, fiscal_code, enrolment_date, registration_number)
VALUES ('Francesco', 'Cifaldi', '1996-03-26', 29, 'francesco.cifaldi@hotmail.it', 'CFLFNC96C26L049X','2024-09-11',888888);

```

### 10 - Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```SQL

UPDATE `teachers`
SET `office_number` = 126
WHERE `name` = 'Pietro' AND `surname` = 'Rizzo'
```

### 11 - Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```SQL

DELETE FROM `students`
WHERE email =  'francesco.cifaldi@hotmail.it';
```
