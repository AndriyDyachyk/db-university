es 1 - Selezionare tutti gli studenti al corso di laurea di Economia
procedura:
SELECT `students`.`name`,`students`.`surname`,`students`.`registration_number`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'

es 2 - Seleziona tutti i corsi di laurea magistrale del dipartimento di neuroscienze
procedura:
SELECT `degrees`.*
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`level` = 'magistrale'
AND `departments`.`id` = 7;

es 3 - Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
procedura:
SELECT `courses`.* 
FROM `courses`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`id` = 44;