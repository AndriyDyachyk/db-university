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

es 4 - Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
procedura:
SELECT `students`.`registration_number` as `N.Matricola`,`students`.`surname` as `Cognome`,`students`.`name` as `Nome`,`degrees`.`name` as `Laurea`,`degrees`.`level` as `Tipo`,`departments`.`name` as `Dipartimento`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `Cognome`,`Nome`;

es 5 - Selezionare tutti i corsi di laurea con i relativi corsi ed insegnanti
SELECT `degrees`.`name` as `Laurea`, `degrees`.`level` as `Tipo`,`courses`.`name` as `Corso`, `courses`.`year` as `Anno`, `courses`.`cfu` as `CFU`,`teachers`.`name` as `Nome_docente`,`teachers`.`surname` as `Cognome_docente`
FROM `degrees`
JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`
ORDER BY `Laurea`