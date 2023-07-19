es 1 - Selezionare tutti gli studenti al corso di laurea di Economia
procedura:
SELECT `students`.`name`,`students`.`surname`,`students`.`registration_number`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'