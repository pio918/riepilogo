## Modulo JDBC

**Che cos'è JDBC?**
JDBC sta per Java Database Connectivity, è un'API fornita da Java per consentire l'interazione tra un'applicazione java e un database relazionale.
Gli elementi principali del JDBC sono: 
- **Connection**, oggetto attivo che permette di aprire una connessione con il database.
- **PreparedStatement**, oggetto che prepara la query con parametri mediante l'utilizzo di parametri placeholder (?), e la esegue.
- **ResultSet**, oggetto che viene utilizzato per memorizzare tutte le query di tipo SELECT.

**Differenza tra Statement e PreparedStatement**
Usando statement, le query vengono scritte come stringhe e inviate al database, con il rischio di SQL injection.
Con PreparedStatement la query viene costruita dinamicamente, grazie all'utilizzo di placeholder (?) che vengono sostituiti in modo sicuro, prevenendo SQL injection.

**Che cos'è una servlet?**
In Java una servlet è una classe Java che viene eseguita all'interno di un Web Server, ad esempio Tomcat, e servono per gestire le richieste e le risposte http. Estendono la classe HttpServlet e fanno un override dei metodi doGet, doPost, ecc..., che corrispondono ai vari metodi http ai quali al loro interno si possono gestire le operazioni CRUD.