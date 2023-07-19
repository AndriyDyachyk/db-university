es 1 - Contare quanti iscritti ci sono stati ogni anno
procedura:
SELECT YEAR(`enrolment_date`) as `anno`,COUNT(*) as `numero_iscritti`
FROM `students`
GROUP BY `anno`  
ORDER BY `anno`

es 2 - Contare gli insegnanti che hanno l'ufficio nello stesso edificio
procedura:
SELECT `office_address`, COUNT(*) as `numero_insegnanti`
FROM `teachers`
GROUP BY `office_address`

es 3 - Calcolare la media dei voti di ogni appello d'esame
SELECT `exam_id`, AVG(`vote`) as `voto_medio`
FROM `exam_student`
GROUP BY `exam_id`

es4 - Contare quanti corsi di laurea ci sono per ogni dipartimento
procedura:
SELECT `department_id`, COUNT(*) as `corsi`
FROM `degrees`
GROUP BY `department_id`;