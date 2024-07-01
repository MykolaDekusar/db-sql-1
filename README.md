# Usare il database per eseguire le query del file

1. Selezionare tutti gli studenti nati nel 1990 (160)

   - SELECT \* FROM `students` WHERE YEAR(`date_of_birth`) = 1990;

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

   - SELECT \* FROM `courses` WHERE `cfu` > 10;

3. Selezionare tutti gli studenti che hanno più di 30 anni

   - SELECT \* FROM `students` WHERE 2024 - YEAR(`date_of_birth`) > 30

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)

   - SELECT \* FROM `courses` WHERE `year` = 1 AND `period` = 'I semestre';

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
   20/06/2020 (21)

   - SELECT \* FROM `exams` WHERE HOUR(`hour`) >= 14 AND `date` = '2020/06/20';

6. Selezionare tutti i corsi di laurea magistrale (38)

   - SELECT \* FROM `degrees` WHERE `level` = 'magistrale';

7. Da quanti dipartimenti è composta l'università? (12)

   - SELECT COUNT(\*) AS `total_departments` FROM departments;

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

   - SELECT \* FROM `teachers` WHERE `phone` IS NULL;

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
   degree_id, inserire un valore casuale)

   - INSERT INTO `students` VALUES(NULL, 45, 'Mykola', 'Dekusar', '1997-05-22','DKDMKW12URCIS', '2024-03-16', 485923, 'ciao@gmail.com');

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

    -UPDATE `teachers` SET `office_number` = 126 WHERE `name` = 'Pietro' AND `surname` = 'Rizzo';

11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

- DELETE FROM `students` WHERE `name` = 'Mykola' AND `surname` = 'Dekusar';
