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

es 3 - Seleziona tutti gli studenti che hanno più di 30 anni
procedura:
SELECT *
FROM `students`
WHERE TIMESTAMPDIFF(YEAR,`date_of_birth`,CURDATE())>30;

es 4 - Seleziona tutti i corsi del primo semestre del primo anno di un qualiasi corso di laurea
prodecura:
SELECT COUNT(*)
FROM `courses`
WHERE `period`LIKE 'I semestre'
AND `year` LIKE 1;

es 5 - Seleziona tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020
procedura:
SELECT COUNT(*) 
FROM `exams` 
WHERE `date` = '2020-06-20'
AND HOUR(`hour`)>=14;

es 6 - Selezionare tutti i corsi di laurea magistrale
procedura:
SELECT COUNT(*) 
FROM `degrees`
WHERE `level` LIKE 'Magistrale';

es 7 - Da quanti dipartimenti è composta l'università?
procedura:
SELECT COUNT(*) 
FROM `departments`;

es 8 - Quanti sono gli insegnanti che non hanno un numero di telefono?
procedura:
SELECT COUNT(*)
FROM `teachers`
WHERE `phone` IS NULL;
