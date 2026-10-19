## Modulo Spring

**Che cos'è Spring?**

Il framework Spring è un framework open source per lo sviluppo di applicazioni java enterprise, in particolare applicazioni web.

**Che cos'è Spring boot e la differenza con Spring?**

Spring Boot invece è una evoluzione di Spring, progettata per rendere lo sviluppo ancora più rapido e produttivo.
Elimina gran parte della configurazione manuale tipica di Spring grazie all’auto-configurazione, integrando un server embedded come Tomcat.

**Inversion of Control**

L’**Inversion of Control (IoC)** è un principio secondo cui il flusso di controllo di un’applicazione non è gestito direttamente dal codice dell’applicazione stessa, ma viene “invertito” e gestito da un **contenitore**. In Spring, questo contenitore è lo **IoC Container** (o ApplicationContext), che si occupa di **creare, configurare e gestire il ciclo di vita** degli oggetti.

**Dependency injection**

**La Dependency Injection** (DI) è un modo concreto con cui Spring realizza l’IoC.
Invece di creare manualmente le dipendenze all’interno delle classi (usando ad esempio `new`), queste vengono iniettate automaticamente dal contenitore di Spring.
Le iniezioni possono avvenire tramite:

- **Costruttore** (injection via constructor)
- **Setter** (injection via setter)
- **Field** (injection diretta con `@Autowired`)

**@Component**

Annotazione generica che indica una classe gestita dal container IoC di Spring.
Serve per marcare una classe come bean, cioè un oggetto che viene creato, iniettato e gestito da Spring.

**Specializzazioni di Component sono:**

**@Service**

Usata per definire un bean che contiene la logica di business. Viene utilizzato nel Service Layer , il layer dell'applicazione che elabora i dati del controller e li passa al repository.

**@Repository**

Usata per definire le classi e le interfacce che interagiscono con il database.

**@Controller**

Usata per definire un **controller MVC** che gestisce le richieste HTTP e restituisce generalmente delle viste come pagine html.

**@RestController**

Usata per le API REST, dove il controller restituisce dati in formato JSON all'interno del corpo delle risposte HTTP.

**Flusso richiesta Http**

- Il Controller intercetta la richiesta all'endpoint mappato ( che può essere di tipo GET, POST, PUT, ecc), insieme ad eventuali dati di ingresso e delega al service le operazioni da effettuare.
- Il Service riceve la richiesta del Controller ed applica la logica di business.
- Il Service chiama il repository, il layer di accesso ai dati, per leggere o salvare dati dal database
- I dati dal repository risalgono al service, che li elabora se necessario, e poi passano al controller, il quale li restituisce al client in formato JSON

**Gestione delle eccezioni in Spring**

In Spring le eccezioni possono essere gestite in modo centralizzato mediante una classe annotata con @ControllerAdvice o @RestControllerAdvice, e funge da intercettatore globale per le eccezioni lanciate dai controller.

All'interno di queste classi, si definiscono dei metodi annotati con @ExceptionHandler, che specificano quale tipo di eccezione devono catturare.

Quando l'eccezione verrà lanciata, Spring individua il metodo @ExceptionHandler corrispondente e lo esegue restituendo una risposta personalizzata.

Nel caso di un'applicazione REST, con @RestControllerAdvice, viene restituita direttamente la risposta in formato JSON.

**Che cos'è JPA?**

JPA sta per Java Persistence API ed è una specifica di java che definisce uno standard per la gestione e la persistenza dei dati nell'applicazione java. In pratica, JPA, stabilisce come mappare le classi Java alle tabelle di un database relazionale attraverso un insieme di interfacce e annotazioni, come @Entity, @Id.

L'implementazione più diffusa di JPA prende il nome di Hibernate, che si occupa di tradurre le operazioni fatte sugli oggetti java in operazioni SQL sul database.

**@Entity**

Indica che una classe Java rappresenta una **tabella del database**.
Ogni istanza della classe corrisponde a una **riga** della tabella.

**@Id**

Indica il **campo chiave primaria** (Primary Key) della tabella.
Ogni entità deve avere un campo con questa annotazione.

**@GeneratedValue**

Specifica la **strategia di generazione automatica dell’ID**.

**@OneToMany**

Definisce una **relazione uno-a-molti** tra due entità.
È spesso accompagnata da `mappedBy`, che indica il campo che possiede la relazione.

**@ManyToOne**

Definisce una **relazione molti-a-uno**.
Si mette sempre nella **classe che contiene la chiave esterna (FK)**.

**@ManyToMany**

Definisce una **relazione molti-a-molti**.
Serve quando più entità A possono essere collegate a più entità B.
Si usa spesso con una **tabella di join** (`@JoinTable`).

**@JoinColumn**

Serve a **specificare il nome della colonna di join** in una relazione, di solito quando c’è una foreign key.

**Fetching**

Il fetching indica come devono essere caricati i dati relazionati, cioè i dati di un record in relazione con la tabella principale.
Esistono due politiche di fetching: il Lazy fetching dove i dati relazionati non vengono caricati subito ma solo quando servono, rischiando però la LazyInitializationException, mentre con Eager, i dati vengono caricati subito insieme all'entità principale, consumando più risorse.

**Cosa sono i Repository in spring data JPA?**

In Spring Data JPA, i Repository sono interfacce che gestiscono le operazioni CRUD sul database in modo automatico, senza bisogno di scrivere query SQL a mano.

**Transazioni**

Una transazione rappresenta un'unità logica composta da una o più operazioni sul database che devono essere eseguite tutte o nessuna. Se una di queste operazioni fallisce, Spring fa un rollback, cioè annulla tutte le modifiche effettuate fino a quel momento. Per abilitare una transazione in Spring, bisogna mettere l'annotation @Transactional sopra la firma del metodo o a tutta la classe, solitamente di un service.

**Cos'è un'API e un'API REST?**

Si definisce come API il mezzo per la quale due sistemi diversi, scritti anche con linguaggi diversi di comunicare.
In particolar modo le API REST sono un modello di API che utilizzano il protocollo HTTP per la comunicazione e utilizzano formati leggeri come JSON e XML per lo scambio di dati.

**State**: significa che un sistema mantiene delle informazioni sullo stato dell'utente o della sessione tra una richiesta e l'altra.

**Stateless**: significa che ogni richiesta che il client invia al server è autonoma e indipendente. Il server non conserva alcuno stato tra le richieste, quindi ogni volta che il client fa una richiesta, deve fornire tutte le informazioni necessarie.
Le API REST sono stateless.

**Cos'è Maven?**

Maven è uno strumento per la gestione dei progetti java, ci permette di compilare, pacchettizzare in formato jar le applicazioni e gestire le dipendenze delle librerie esterne in modo automatico. Le dipendenze vengono scaricate da un suo repository centrale, o locale se presenti. La configurazione delle dipendenze viene fatta nel pom.xml
