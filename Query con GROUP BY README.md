es 1 - Contare quanti iscritti ci sono stati ogni anno
procedura:
SELECT COUNT(*), YEAR(`enrolment_date`)
FROM `students`
GROUP BY YEAR(`enrolment_date`)  
ORDER BY `YEAR(``enrolment_date``)` ASC

es 2 - Contare gli insegnanti che hanno l'ufficio nello stesso edificio
procedura:
SELECT COUNT(*), `office_address`
FROM `teachers`
GROUP BY `office_address`

es 3 - Calcolare la media dei voti di ogni appello d'esame
SELECT `exam_id`, AVG(`vote`)
FROM `exam_student`
GROUP BY `exam_id`