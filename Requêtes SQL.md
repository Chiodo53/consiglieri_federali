# Requêtes SQL

### Classer les conseillers fédéraux par date de décès:

SELECT p.name 
From person p 
Order by p.date_of_death  

### Classer les conseillers fédéraux par date de naissance:

SELECT p.name 
From person p 
Order by p.date_of_birth

### Afficher les personnes et leurs lieux:
SELECT p.name AS persona, gp.name AS luogo, l.begin_date, l.end_date
FROM localisation l
JOIN person p ON l.fk_person = p.pk_person
JOIN geographical_place gp ON l.fk_geographical_place = gp.pk_geographical_place;

### Afficher toutes les localisations historiques d’une personne spécifique:
SELECT p.name AS persona, gp.name AS luogo, l.begin_date, l.end_date
FROM localisation l
JOIN person p ON l.fk_person = p.pk_person
JOIN geographical_place gp ON l.fk_geographical_place = gp.pk_geographical_place
WHERE p.name = 'Stefano Franscini'
ORDER BY l.begin_date

### Compter combien de personnes ont vécu dans chaque lieu:

SELECT gp.name AS luogo, COUNT(DISTINCT l.fk_person) AS numero_persone
FROM localisation l
JOIN geographical_place gp ON l.fk_geographical_place = gp.pk_geographical_place
GROUP BY gp.name
ORDER BY numero_persone DESC;

### Afficher les personnes et les organisations auxquelles elles appartiennent:

SELECT p.name AS persona, o.name AS organizzazione, om.begin_date, om.end_date
FROM organisation_membership om
JOIN person p ON om.fk_person = p.pk_person
JOIN organisation o ON om.fk_organisation = o.pk_organisation

### Afficher les rôles occupés par les personnes au sein des organisations:

SELECT p.name AS persona, o.name AS organizzazione, r.role_type, r.begin_date, r.end_date
FROM role r
JOIN person p ON r.fk_person = p.pk_person
JOIN organisation o ON r.fk_organisation = o.pk_organisation

### Cette requête affiche pour chaque personne toutes les informations principales, les lieux où elle a vécu, les organisations dont elle a été membre et les rôles qu’elle a occupés, en incluant également les dates de début et de fin de chaque association ou rôle:

SELECT 
    p.name AS persona,
    p.date_of_birth,
    p.date_of_death,
    p.gender,
    p.religion,
    p.langue,
    gp.name AS luogo,
    l.begin_date AS localizzazione_inizio,
    l.end_date AS localizzazione_fine,
    o.name AS organizzazione,
    om.begin_date AS membership_inizio,
    om.end_date AS membership_fine,
    r.role_type AS ruolo,
    r.begin_date AS ruolo_inizio,
    r.end_date AS ruolo_fine
FROM person p

-- Localizzazione geografica
LEFT JOIN localisation l ON p.pk_person = l.fk_person
LEFT JOIN geographical_place gp ON l.fk_geographical_place = gp.pk_geographical_place

-- Appartenenza a organizzazioni
LEFT JOIN organisation_membership om ON p.pk_person = om.fk_person
LEFT JOIN organisation o ON om.fk_organisation = o.pk_organisation

-- Ruoli ricoperti
LEFT JOIN role r ON p.pk_person = r.fk_person AND r.fk_organisation = om.fk_organisation

ORDER BY p.name, l.begin_date, om.begin_date, r.begin_date
