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
essa esprime il fatto che una persona appartiene a un certo luogo in un determinato lasso di tempo. Entrambe sono relazioni n a 1
pertanto la localizzazione ha come oggetto localizzante un luogo 
mentre una persona è localizzata tramite una localizzazione 

### appartenenza a una localizzazione 


