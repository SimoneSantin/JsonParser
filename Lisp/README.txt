Santin Simone 886116
Colombo Lorenzo 885895

Descrizione funzioni Lisp:

-jsonparse: controlla che jsonstring sia una stringa, poi passa la stringa al
metodo splitList, dopo aver rimosso gli eventuali spazi con il metodo removespaces
e dopo aver trasformato la stringa in lista con il metodo string_list

-splitList: analizza se i caratteri esterni di JSONList sono parentesi quadre o 
graffe, le rimuove poi grazie al metodo removeExtern, in base a questo richiamerà
la funzione splitMembers o splitArray

-splitArray: divide i valori dell'array in base alla virgola e li passa a
scanValue che li analizzerà

-splitMembers: divide le coppie dell'oggetto basandosi sulla virgola e passa 
ogni coppia al metodo splitPair

-splitPair: divide i pair basandosi sui due punti e passa i value alla funzione
scanValue, inolte controlla che i doppi apici siano inseriti correttamente

-scanValue: analizza se il valore è accettato da JSON e in caso il value sia 
un oggetto o un array, richiama il metodo splitList

-jsonaccess: riceve una stringa JSON e dei parametri opzionali per recuperare
l'elemento corrispondente, cioè un nome nel caso volessimo recuperare un oggetto
e una serie di numeri nel caso volessimo recuperare un campo in un array

-find-obj: cerca attraverso attribute, l'attributo corrispondente nell'oggetto
e restituisce il suo value in caso lo trovi

-find-array:cerca in base all'index, l'elemento corrispondente nell'array 

-jsonread: legge una stringa json dal file e la passa al jsonparse, la stringa
viene letta carattere per carattere e poi viene creata

-jsondump: prende in input una lista contenente un oggetto json in formato
lisp e un filename, restituisce filename e in oltre converte l'oggetto in formato
json, appoggiandosi ad altre funzioni, scrivendolo in un file di nome filename. 
Se il file non esiste lo crea se esiste utilizza quello già esistente.  
