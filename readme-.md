es 1 - Selezionare tutti gli studenti nati nel 1990
procedura:
SELECT COUNT(*) 
FROM `students`
WHERE `date_of_birth` LIKE '1990%';

es 2 - Selezionare tutti i corsi che valgono più di 10 crediti
procedura:
SELECT COUNT(*) 
FROM `courses`
WHERE `cfu` > 10;