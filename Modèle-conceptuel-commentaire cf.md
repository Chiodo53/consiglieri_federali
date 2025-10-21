Ce document contient le commentaire, avec exemples, du modèle conceptuel

## Person

Tout être humain qui a été conséiller fédéral. 

### Propriétés
Nom standard, notice, le genre, la date de naissance, la date de mort, la religion, le canton .
Il s'agit d'une classe objet (persistent item)


## Occupation

Un métier ou tout autre type d'occupation
Il s'agit d'une classe objet (persistent item)

## parti politique

un parti politique et son orientation (dx ou sx) 
Il s'agit d'une classe objet (persistent item)

### Propriétés
Nom standard, notice

### Relations
Une relation réfléxive de spécialisation, termes plus génériques associés à des termes plus précis.
Par exemple 'épicier' spécialise le terme de 'négociant'.


## Pursuit

Le fait d'avoir telle occupation ou activité durant telle période 
Il s'agit d'une classe temporalité (temporal entity)

Exemple: " Alain Berser a été un conseiller fédéral " (Wikipedia)

### Relations

Une _Pursuit_ peut comprend une et une seule personne, une et une seule occupation (ces deux relations sont nécessaires) et éventuellement on peut associer une (et une seule) organisation auprès de laquelle l'activité est exercée.

Si plusieurs organisation sont concernées par une activité, plusieurs individus de la classe _Pursuit_ seront créées.



## Tag

Un mot clé qui introduit un classement de recherche, généralement lié au questionnement.

### Relations

Relation reflexive (d'un classe vers elle même) qui créer une taxonomie (i.e. une hiérarchie) de mots clés, les plus généraux étant les parents ou ancêtres des plus spécifiques