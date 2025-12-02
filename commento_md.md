# Commento al modello concettuale

## person
Ogni essere umano che è stato o è consigliere federale
Le proprietà associate a questa classe sono:
nome; data di nascita, data di morte, sesso e religione
Queste proprietà sono ritenute essenziali per la persona e non variano nel corso del tempo 
(per semplificare si ritengono la religione e il sesso proprietà essenziali sebbene in realtà sono contingenti)

## Relazioni
Ogni persona possiede diverse relazioni: con il luogo da cui proviene, con l'organizzazione lavorativa e con l'organizzazione politica

queste relazioni sono *fatti sociali* 

### Provenienza geografica
Per esprimere la relazione di appartenenza a un luogo geografico si è proceduto nel modo seguente:
i luoghi sono stati raggruppati in una classe di tipi: cantoni, comuni e attinenza
nella classe dei luoghi sono inseriti le istanze
si ha quindi una relazione n a 1 tra la classe luogo e tipo di luogo
questa relazione esprime il fatto che un certo luogo geografico appartiene a un determinato tipo di luogo geografico

La localizzazione va così interpretata:
essa esprime esplicitamente il fatto che una persona appartiene a un certo luogo in un determinato lasso di tempo. Entrambe sono relazioni n a 1
pertanto la localizzazione ha come oggetto localizzante un luogo 
mentre una persona è localizzata tramite una localizzazione 

### Appartenenza a un'organizzazione
L'appartenenza a un'organizzazione è espressa in modo esplicito con la tavola dell'organisation membership (relazioni n a 1)
questa idenfica la persona coinvolta nell'apparteneza e la lega con l'organizzazione coivolta nell'appartenenza

Le organizzazioni appartengono a dei tipi, per esempio: partiti, settore pubblico, settore privato, ONG, consiglio federale,... (relazione n a 1) 
a ogni tipo di organizzazione corrispondono delle proprietà, come fatturato, destra / sinistra, prodotti,... (relazione n a 1)
queste proprieté possono essere raggruppate per classi e questo è espresso nella tavola "class of organisation properties" 

Quindi un'organizzazione appartiene a un tipo, ogni tipo ha le sue proprietà e le proprietà possono essere raggruppate in classi

### Ruolo all'interno di un'organizzazione

Si vuole rendere esplicito il ruolo ricoperto da una persona all'interno di un organizzazione
per farlo si è creata la classe "ruolo" in cui è espresso il fatto che la persona toccata da questa appartenenza ricopre un determinato ruolo all'interno dell'organizzazione coinvolta in questa appartenenza


