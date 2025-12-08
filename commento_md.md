# Commentaire sur le modèle conceptuel

## Personne

Tout être humain qui a été ou est conseiller fédéral.
Les propriétés associées à cette classe sont : nom, date de naissance, date de décès, sexe et religion.
Ces propriétés sont considérées comme essentielles pour la personne et ne varient pas au cours du temps (pour simplifier, on considère la religion et le sexe comme des propriétés essentielles, bien qu’en réalité elles soient contingentes).

### Relations

Chaque personne possède plusieurs relations : avec le lieu d’origine, avec l’organisation professionnelle et avec l’organisation politique.
Ces relations sont des faits sociaux.

## Provenance géographique

Pour exprimer la relation d’appartenance à un lieu géographique, la démarche suivante a été adoptée :
les lieux ont été regroupés dans une classe de types : cantons, communes et villes.
La classe des lieux contient les instances.
Il existe donc une relation n à 1 entre la classe « lieu » et « type de lieu ».
Cette relation exprime le fait qu’un certain lieu géographique appartient à un type déterminé de lieu géographique.

La localisation doit être interprétée de la manière suivante :
elle exprime explicitement le fait qu’une personne appartient à un certain lieu durant une période déterminée. Il s’agit, dans les deux cas, de relations n à 1.
Ainsi, la localisation a pour objet localisant un lieu, tandis qu’une personne est localisée à travers une localisation.

## Appartenance à une organisation

L’appartenance à une organisation est exprimée explicitement par la table « organisation membership » (relations n à 1).
Elle identifie la personne concernée par cette appartenance et la relie à l’organisation impliquée dans cette appartenance.

Les organisations appartiennent à des types, par exemple : partis politiques, secteur public, secteur privé, ONG, Conseil fédéral, etc. (relation n à 1).
À chaque type d’organisation correspondent des propriétés, telles que chiffre d’affaires, orientation gauche/droite, produits, etc. (relation n à 1).
Ces propriétés peuvent être regroupées par classes, ce qui est exprimé dans la table « type of organisation properties ». Par exemple, les propriétés « gauche » et « droite » appartiennent au type de propriété que l’on nomme « orientation politique ».

Ainsi, une organisation appartient à un type, chaque type possède ses propriétés et ces propriétés peuvent être regroupées en classes.

## Rôle au sein d’une organisation

On souhaite rendre explicite le rôle occupé par une personne au sein d’une organisation.
Pour ce faire, la classe « rôle » a été créée, dans laquelle est exprimé le fait que la personne concernée par cette appartenance occupe un rôle déterminé au sein de l’organisation impliquée, et ce, durant une période donnée.
Il est donc possible, par exemple, d’exprimer qu’une personne est président de la Confédération pendant une année.

