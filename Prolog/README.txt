Santin Simone 886116
Colombo Lorenzo 885895
 
Descrizione funzioni prolog:

-jsonparse: restituisce true se JSONString/JSONAtom, può venire scorporato come
come stringa, numero o nei termini composti e passa poi la stringa al jsonobj

-jsonobj: rimuove le parentesi graffe esterne grazie al metodo removebrackets e 
passa poi il risultato al metodo parse member

-jsonarray: passa ogni elemento al parse value, il quale controllerà i valori, 
e richiama se stesso ricorsivamente

-parsemember: splitta la stringa in base alla virgola e passa le coppie al 
metodo parsepair

-parsepair: riceve le coppie di elementi e divide l'attributo dal value 
basandosi sui due punti e passa il value al metodo parsevalue, inoltre controlla
che attribute sia effettivamente una stringa

-parsevalue: analizza il value e restituisce true se value è un valore accettato
da json, inoltre nel caso sia termine composto, richiama il jsonparse 

-jsonaccess: che risulta vero quando Result è recuperabile seguendo i campi 
presenti in Attribute a partire da ParsedObject. Un campo rappresentato da N 
(con N un numero maggiore o uguale a 0) corrisponde a un indice di un array JSON

-searchField: cerca nell'oggetto json il valore corrispondente al attributo

-searchValue:cerca nell'array il valore corrispondente al counter

-jsondump: scrive l’oggetto ParsedJSON sul file FileName in sintassi JSON. 
Se FileName non esiste, viene creato e se esiste viene sovrascritto, inoltre 
passa l'oggetto ParsedJson alla funzione parsedjson per convertire l'oggetto in 
sintassi json

-parsedjson: trasforma il ParsedObject o il ParsedArray in una stringa grazie ai
corrispettivi metodi memberJson o arrayJson

-arrayJson: trasforma l'array in una stringa che contiene l'array versione json

-memberJson: trasforma l'oggetto in una stringa che contiene l'oggetto versione 
json

-valueJson: converte dal valore al corrispettivo valore json, in particolare se
trova un altro oggetto lo ripassa al parsedjson

-tostring: viene usato per concatenare tutti i campi separandoli con una virgola

-jsonread: prende il nome del file Filename, legge il contenuto e lo passa al 
jsonparse per verificare che sia scritto correttamente in formato json



