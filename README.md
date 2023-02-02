# Git Cookbook
Un semplice esercizio per fare pratica con i comandi di Git.  

## Scenario
Siamo un gruppo di persone esperte di programmazione e arte culinaria.  
Un famoso editore ci ha commissionato un libro di ricette per programmatrici e programmatori, 
dal titolo _"Le migliori ricette per developers"_. 

L'editore vuole avere delle versioni intermedie del libro, 
in modo che i revisori di bozze possano leggerle e correggerle.  

Inoltre, vuole sperimentare una nuova modalità di pubblicazione, 
che prevede un rilascio di una nuova versione del libro ogni 2 settimane. 


## Modalità di lavoro
Per la stesura del libro usiamo Git e dei semplici file di testo in formato Markdown.  
Ogni persona può aggiungere ricette al libro.  
Ci sono 4 categorie:
- _antipasti_
- _primi_
- _secondi_
- _dessert_

Ogni persona deve tracciare il proprio lavoro seguendo uno schema preciso.

## Organizzazione del repository
Nel repository ci sono 4 sotto-cartelle, una per ogni gruppo di ricette:
- antipasti
- primi
- secondi
- dessert

Le ricette vanno create al loro interno.
Nel nome della ricetta non devono esserci spazi; al loro posto si usano i trattini (ad es. `pasta-e-fagioli.md`).  

Nel repository ci sono anche dei file comuni che vanno aggiornati 
ogni volta che viene aggiunta o rimossa una ricetta.

Ci sono 4 file con la lista dei piatti, uno per ogni tipo di piatto:
- `antipasti.md`
- `primi.md`
- `secondi.md`
- `dessert.md`

I file hanno un template predefinito; questo ad esempio quello per gli antipasti:

~~~markdown
# Antipasti

## Antipasti di terra
- [Torta rustica salata](antipasti/torta-rustica-salata.md)
- ...

## Antipasti di mare
- ...

~~~

### Creazione delle ricette
Ogni persona deve aggiungere delle ricette (basta un compia-incolla da internet).  
Negli step descritti sotto verranno assegnati dei compiti, che ci permetteranno di 
sfruttare le funzionalità di Git al fine di rendere ordinato e "sempre rilasciabile" 
il nostro libro di ricette :)


## Setup
Ogni persona deve seguire questi passi per predisporre l'esercizio.   

1) Clona sul tuo PC questo repository:
~~~shell
git clone https://github.com/jesuswasrasta/GitCookbook-workshop
~~~

2) Imposta il tuo nome utente e la tua mail:

~~~shell
git config user.name "Nome Cognome"
git config user.email "nome.cognome@email.it"
~~~

## Obiettivo
...


---
## Esercizio 1: aggiungi la tua prima ricetta
- Cerca in rete una ricetta che ti piace.  
- Crea un nuovo file Markdown nella sotto-cartella adatta.  
- Copia incolla la ricetta nel file Markdown (non badare troppo alla formattazione: lo scopo è sperimentare i comandi di Git,
più che creare un libro di ricette ben impaginato :)
- Aggiorna il relativo file con la lista dei piatti (ad es. `secondi.md` se hai aggiunto la ricetta di un secondo piatto)
- Esegui il commit:

~~~shell
git add <file-ricetta>
git commit --m "Aggiunta ricetta <nome-ricetta>"
~~~

### Domande, spunti
1. Meglio creare un branch per ogni ricetta? Uno per tipo di ricetta (primi, secondi, etc.)?
2. C'è un errore nel commit appena fatto 😭. Come si può rimediare? (scopriamo `git amend`)

### Cosa abbiamo imparato
In locale possiamo muoverci liberamente, facendo tutti i commit che vogliamo. 

---
## Esercizio 2: condividi i tuoi aggiornamenti 
- Condividi le tue modifiche eseguendo un `push` sul repository remoto:
~~~shell
git push origin main
~~~

### Domande, spunti
1. Si sono verificati dei conflitti 😏?
2. Chi non ha avuto conflitti?
3. Come sistemiamo?
4. pull con merge o pull con rebase?
5. NUOVA REGOLA: ordiniamo in ordine alfabetico le ricette aggiunte ai file con la lista

Prima di proseguire:
- Uno di noi sistema i file delle liste e fa un nuovo `commit` seguito da `push`:
~~~shell
git add <file-lista>
git commit -m "Le liste delle ricette sono in ordine alfabetico"
git push origin main
~~~
- Tutti gli altri fanno `pull`:
~~~shell
git pull
~~~

---
## Esercizio 3: primo rilascio in bozze
Dobbiamo ora confezionare la prima bozza del libro: come procediamo? 

### Domande, spunti
1. Facciamo un branch per le bozze? Chi lo fa?
2. Che succede se ci fanno cambiare qualcosa? Come e dove eseguiamo le modifiche?

- Uno di noi:
~~~shell
git branch bozze
git push --all
~~~

- Tutti:
~~~shell
git pull
~~~

### Cosa abbiamo imparato
Serve una strategia di branching nota e condivisa all'interno del team. 

---
## Esercizio 4: correzione della bozza
Le ricette contengono dei refusi.  
Per semplicità, procediamo come segue: 
ognuno fa una piccola modifica al suo file della ricetta ed esegue un nuovo commit.
 
Ora però ognuno fa una `pull` prima di effettuare la sua `push`:
~~~shell
git pull --rebase
~~~

### Domande, spunti
1. Ci sono dei nuovi conflitti?
2. Qual è un modo per risolverli?

### Cosa abbiamo imparato
Prima di pushare, meglio pullare 😄.


---
## Esercizio 5: primo rilascio pubblico





