## Modulo Java Base

**Cos'è un programma ?**
Per programma, in generale, si intende come la traduzione di un algoritmo in un linguaggio comprensibile alla macchina, cioè il computer, e si intende per algoritmo, un elenco di passo ordinati per arrivare a un risultato.


**Cos'è Java ?**
Java è un **linguaggio di programmazione orientato agli oggetti**, multipiattaforma, **fortemente tipizzato** e progettato per essere **portabile e sicuro**.


**Componenti fondamentali di java**
Uno dei componenti fondamentali di java è il JDK.
Il **JDK** (java development kit) include tutto ciò che serve per **scrivere**, **compilare** ed **eseguire** programmi Java.
Il compilatore del JDK è chiamato **javac** e si occupa di compilare il file sorgente java (.java) in  bytecode (.class). 
Per eseguire il codice compilato, il JDK mette a disposizione il **JRE** (Java runtime environment) che include le librerie di base e la **JVM** (java virtual machine), che è la macchina virtuale che si occupa di interpretare il bytecode ed eseguirlo sulla macchina reale.


**Stack, Heap e Garbage Collector**
In Java la memoria è gestita principalmente attraverso due aree: lo **stack** e l’**heap**. Lo stack è utilizzato per memorizzare variabili locali e riferimenti agli oggetti; ogni thread ha il proprio stack e funziona con una logica LIFO, quindi quando un metodo termina lo spazio occupato viene automaticamente liberato. L’heap invece è l’area di memoria condivisa tra tutti i thread dove vengono creati gli oggetti e le istanze delle classi; è più grande dello stack, ma meno veloce, e gli oggetti restano in memoria finché esistono riferimenti attivi ad essi. La gestione della memoria nello heap è affidata al **Garbage Collector**, un meccanismo automatico che libera lo spazio eliminando gli oggetti non più raggiungibili.


**Perché java rispetto ad altri linguaggi di programmazione?**
Usiamo Java rispetto ad altri linguaggi principalmente per questi motivi:

1. **Portabilità**: grazie alla JVM, lo stesso programma può essere eseguito su piattaforme diverse.

2. **Gestione della memoria**: il Garbage Collector riduce gli errori legati alla memoria e rende lo sviluppo più sicuro, rispetto ad altri linguaggi come il C o C++.

3. **Robustezza e stabilità**: è un linguaggio maturo, utilizzato da anni in applicazioni enterprise.

4. **Ecosistema ricco**: dispone di tantissime librerie e framework, come Spring, che accelerano lo sviluppo.


**Quale è lo scopo della keyword static in java?**
La keyword **static** in Java viene utilizzata per dichiarare membri (variabili, metodi, classi annidate) che appartengono alla **classe stessa** piuttosto che alle istanze della classe. Dichiarare membri statici permette di condividere i dati tra tutte le istanze di una classe, di creare metodi di utilità che non richiedono l’istanziazione di un oggetto oppure di definire vincoli specifici.


**Come le gestisci le eccezioni in java?**
Le eccezioni in java possono essere gestite usando i blocchi `try-cathc`. 
Nel blocco del try scriviamo il codice che potrebbe lanciare un eccezione e nel blocco del catch specifichiamo le operazioni da effettuare se l'eccezione avviene.
Un blocco finally può essere usato per eseguire delle operazioni indipendentemente dall'esito del blocco `try-catch.`


**Differenza tra eccezioni controllate e eccezioni non controllate**
Le eccezioni controllate sono eccezioni che il compilatore di Java **richiede** di gestire esplicitamente.  Se un blocco può generare un eccezione controllata, bisogna gestirla adeguatamente con un blocco `try-catch`.
Le eccezioni non controllate, invece, non sono controllate dal compilatore. Derivano da `RuntimeException` o `Error` e sono solitamente causate da **errori di programmazione** che dovrebbero essere corretti.
Gestire queste eccezioni con `try-catch` è possibile, ma non è considerato una buona pratica


**Qual è lo scopo della keyword final in Java?**  
La keyword **final** in Java viene utilizzata per dichiarare **variabili, metodi o classi** che non possono essere modificati.
- **Variabili final**: il loro valore **non può essere cambiato** dopo l’inizializzazione.
- **Metodi final**: **non possono essere sovrascritti** nelle classi figlie.
- **Classi final**: **non possono essere estese**, quindi nessuna sottoclasse può essere creata.


**Qual è lo scopo dei modificatori di visibilità in Java?**  
I modificatori di visibilità determinano chi può accedere a variabili, metodi e classi. I principali sono:
- **public**: il membro è accessibile **da qualsiasi classe**.
- **private**: il membro è accessibile **solo all’interno della stessa classe**.
- **protected**: il membro è accessibile **all’interno della stessa classe, delle classi dello stesso package e delle sottoclassi**.
- **default** (nessun modificatore scritto): il membro è accessibile **solo all’interno dello stesso package**.


**Cos'è una variabile?**
Le variabili sono **contenitori per dati**. In Java vanno dichiarate con **tipo e nome**.

Tipi di variabili:
- **Locali**: dichiarate dentro un metodo, vive solo all’interno del metodo.
- **Di istanza**: dichiarate dentro la classe, ma fuori dai metodi, legate all’oggetto.
- **Statiche**: dichiarate con `static`, legate alla classe invece che all’oggetto.


**Quali sono i tipi di variabili primitivi in java?**
I tipi primitivi sono **predefiniti dal linguaggio** e memorizzano direttamente il valore nella memoria stack.
- **`byte`** – Numero intero da -128 a 127, occupa 1 byte.
- **`short`** – Numero intero da -32.768 a 32.767, occupa 2 byte.
- **`int`** – Numero intero standard da -2^31 a 2^31-1, occupa 4 byte. 
- **`long`** – Numero intero grande da -2^63 a 2^63-1, occupa 8 byte. 
- **`float`** – Numero decimale a precisione singola (~7 cifre), occupa 4 byte. Richiede `f` alla fine del valore.
- **`double`** – Numero decimale a precisione doppia (~15 cifre), occupa 8 byte. Standard per valori decimali.
- **`char`** – Singolo carattere Unicode, occupa 2 byte.
- **`boolean`** – Valore logico `true` o `false`, occupa 1 bit.


**E i tipi reference?**
I tipi reference **non contengono direttamente il valore**, ma un **riferimento all’oggetto** memorizzato nello heap. Gli esempi sono gli oggetti di classe e gli array.


**Cos'è un array?**
Un **array** è una struttura dati che permette di memorizzare più valori dello stesso tipo sotto un unico nome e ogni elemento dell’array è accessibile tramite un **indice**
**Caratteristiche principali:**
- Dimensione **fissa**: una volta creato, non può essere ridimensionato.
- Tipo **omogeneo**: tutti gli elementi devono essere dello stesso tipo.


**E un array multidimensionale?**
Un **array multidimensionale** è un array di array, utile per rappresentare matrici di dati.


**Differenze tra `==` e `.equals()`**
L’operatore `==` confronta **i riferimenti** degli oggetti, cioè verifica se due variabili puntano **allo stesso oggetto in memoria**.  
Per i tipi primitivi, invece, confronta i **valori**.
Il metodo `.equals()` confronta il **contenuto** degli oggetti, non i riferimenti.
Per le classi definite dall’utente, il metodo `.equals()` di default (ereditato da `Object`) confronta i riferimenti degli oggetti. Per confrontare i valori degli attributi invece dei riferimenti, è necessario **overridare** il metodo `.equals()` nella classe.


**Cos'è una classe Wrapper in Java?**  
Le **classi wrapper** sono classi che permettono di trattare un **tipo primitivo come un oggetto**.
Esse sono necessarie quando si usano **collezioni**, perché non accettano tipi primitivi.
Forniscono **metodi utili** per manipolare i dati, e permettono di avere un **valore nullo**, cosa impossibile con i tipi primitivi.


**Cos'è l’autoboxing e l’unboxing in Java?**
Autoboxing: è la conversione automatica da un tipo primitivo nel suo corrispettivo wrapper.
Unboxing: è la conversione automatica inversa da wrapper a tipo primitivo.


**Che cos'è il casting?**
Il casting è il processo di conversione di un tipo di dato in un altro. Un esempio è quando vogliamo convertire un numero intero in un numero in virgola mobile o viceversa

Il casting implicito avviene automaticamente quando si converte un tipo di dato più piccolo in un tipo di dato più grande. 

Il casting esplicito richiede una conversione manuale e può comportare la perdita di dati o la precisione. Questo tipo di casting è necessario quando si converte un tipo di dato più grande in un tipo di dato più piccolo. (forzato dal programmatore)

**Che cos'è una classe?**
La classe rappresenta il modello che definisce tutte le caratteristiche (dette attributi) e le funzionalità (dette metodi) di un insieme di oggetti.


**Che cos'è un oggetto?**
Un oggetto rappresenta l'istanza della classe, che una volta istanziato occupa memoria nello heap.


**Che cos'è il costruttore?**
Un **costruttore** è un **metodo speciale** di una classe utilizzato per **inizializzare gli oggetti** quando vengono creati.
- Ha lo **stesso nome della classe**.
- **Non ha un tipo di ritorno**.
- Può avere **parametri** per inizializzare gli attributi con valori specifici.
- Se non viene definito, Java fornisce automaticamente un **costruttore di default** senza parametri.


**Programmazione ad oggetti e pilastri**
La programmazione orientata agli oggetti è un paradigma in cui il software viene strutturato attorno a oggetti, che combinano dati (attributi) e comportamenti (metodi).


**Ereditarietà**
L’ereditarietà consente a una classe di ereditare i membri (attributi e metodi) da un’altra classe. La classe che eredita è chiamata sottoclasse o classe derivata, mentre la classe dalla quale eredita è chiamata superclasse o classe base. L’ereditarietà promuove la riutilizzabilità del codice e consente di estendere e specializzare le funzionalità esistenti.


**Incapsulamento**
Consiste nel nascondere i dettagli interni di un oggetto e proteggere i dati tramite modificatori di visibilità rendendoli accessibili tramite metodi pubblici, i getter e i setter.


**Astrazione**
L’astrazione è il principio secondo cui si mostrano **solo le caratteristiche essenziali** di un oggetto, nascondendo i dettagli di implementazione.  
In Java si realizza principalmente con:
- **Classi astratte**: possono avere sia metodi astratti (senza corpo) che concreti (con implementazione). Non possono essere istanziate.
- **Interfacce**: definiscono un contratto che le classi devono rispettare, dichiarando solo metodi astratti (nelle versioni moderne di Java possono avere anche metodi di default e statici).


**Polimorfismo**
l polimorfismo si riferisce alla capacità di oggetti di classi diverse di rispondere allo stesso messaggio o chiamata di metodo, favorendo il riuso del codice e la creazione di strutture più flessibili.
Esso può essere realizzato attraverso l’ereditarietà e la sovrascrittura dei metodi. Un metodo definito in una classe base può essere sovrascritto dalle classi derivate, consentendo a ogni classe di implementare il proprio comportamento per quel metodo.


**Overloading**
Si definisce con overloading la pratica di definite più metodi con lo stesso nome all'interno della stessa classe, tuttavia questi metodi devono avere firme diverse, ovvero devono avere diversi tipi o numeri di parametri.


Overriding
Si definisce con overriding la pratica di redifinizione di un metodo di una sottoclasse ereditato da una superclasse.


**Cosa sono le collections?**
Le collections rappresentano un insieme di interfacce e classi per gestire gruppi di oggetti.

Le strutture principali sono:

**List**
Collezione ordinata che mantiene l'ordine di inserimento, può contenere elementi duplicati e si può accedere ai singoli elementi tramite l'indice.
Le implementazioni più comuni sono quelle dell'ArrayList e della LinkedList.


**Differenza tra un array e un ArrayList**
L'array ha dimensione fissa, può contenere sia oggetti e tipi primitivi.
L'arraylist è costituito da un array di dimensione dinamica, la cui capacità cresce o diminuisce in modo automatico e può contenere solo oggetti.
L'array non ha metodi mentre L'ArrayList mette a disposizione diversi metodi.


**Differenza tra un ArrayList e una LinkedList**
L'ArrayList utilizza un array dinamico per memorizzare i suoi elementi.
La LinkedList è costituita da nodi, dove ogni nodo è costituito dall'elemento memorizzato è un riferimento che punta all'elemento successivo (e al precedete se si tratta di una double linked list).
La differenza sostanziale tra queste due strutture sta nelle performance per determinate operazioni:
L'ArrayList risulta più veloce per l'accesso casuale degli elementi perché avviene tramite indice, rispetto alla LinkedList che deve scorrere gli elementi per trovare quello desiderato.
Gli inserimenti e le cancellazioni invece risultano più lenti, se avvengono nel mezzo, in un ArrayList, perché ad ogni elemento inserito/rimosso, gli elmenti dell'ArrayList vengono spostati, mentre nella LinkedList risulta più efficiente inserire/rimuovere elementi perché basta aggiornare i riferimenti dei nodi.



**Set**
Collezione non ordinata di oggetti che non permette duplicati dei suoi elementi, non presenta indici, utilizzando stesso gli elementi come iteratori. Le implementazioni più comuni sono HashSet, LinkedHashSet e TreeSet.


HashSet
Questo set ha la caratteristica che non memorizza l'ordine degli elementi consente di memorizzare solo un elemento di valore null.

LinkedHashSet
Questo set ha la caratteristica di memorizzare i dati nell'ordine di inserimento e consente solo un elemento di valore null.

TreeSet
Mantiene gli elementi **ordinati** (per ordinamento naturale o tramite Comparator) e non accetta elementi di valore null.


Map
Collezione che memorizza dati in **coppie chiave - valore**, le **chiavi** sono **uniche** non possono esserci duplicati mentre i **valori** possono essere duplicati. L’accesso agli elementi avviene tramite la chiave. Le principali implementazioni sono HashMap, LinkedHashMap e TreeMap.


Hashmap
Non garantisce nessun ordine sugli elmenti e accetta chiavi e valori null.

LinkedHashMap
Mantiene l'ordine di inserimento delle coppie e accetta chiavi e valori null.

TreeMap
Mantiene l'ordine delle chiavi in ordine crescente, o di un ordine specificato tramite Comparator.
Non accetta chiavi null ma il valore può essere null.


**Cosa sono i design pattern?**
I design pattern sono delle soluzioni riutilizzabili a problemi che sono ricorrenti nello sviluppo software. In pratica sono dei modelli di progttazione che aiutano a scrivere codice.

Tipi di pattern sono 
**Creazionali**: gestiscono **come vengono creati gli oggetti**.
**Strutturali**: gestiscono **come le classi e gli oggetti vengono collegati tra loro**.
**Comportamentali**: gestiscono **come gli oggetti comunicano e interagiscono**.

**Singleton**
Il Singleton è un pattern creazionale che garantisce che di una classe si abbia una e una sola istanza in tutto il programma e un punto di accesso globale a quell'istanza. Un esempio è quando si vuole una risorsa condivisa in comune con tutto il programma, come può essere la connessione con il database.

il singleton puo essere definito in due modi, con inizializzazione eager e inizializzazione lazy.
Con la eager, l'instanza del singleton viene creata non appena viene caricata la classe mentre con l'inizializzazione lazy, l'istanza viene creata solo quando serve, quando viene richamato il suo getter.


Factory Method
Il factory pattern è un pattern creazionale, che ha il compito di delegare la creazione degli oggetti ad altre sottoclassi.


**MVC**
Il pattern MVC, detto model-view-controller, è un tipo di pattern che separa la struttura di un applicazione in 3 parti distinte:
- Model: Rappresenta la struttura dei dati e la logica di business dell'applicazione., 
- View: è quella parte dell'applicazione che rappresenta la presentazione dei dati, mostrando ciò che il model fornisce.
- Controller: Gestisce le richieste dell'utente e gestisce l'interazione tra la view e il model.