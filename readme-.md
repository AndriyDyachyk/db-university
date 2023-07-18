es 1 - Selezionare tutti gli studenti nati nel 1990
procedura:
SELECT COUNT(*) 
FROM `students`
WHERE `date_of_birth` LIKE '1990%';

