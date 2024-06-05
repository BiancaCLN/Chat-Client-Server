INTRODUCERE

  Proiectul consta intr-o aplicatie de mesaje intre 2 persoane (stil mesaje pe telefon) in care exista un server la care se conecteaza 2 clienti (pentru o singura conversatie). 
	Acest proiect este scris in Java si foloseste biblioteca Swing pentru a crea o interfata grafica si intuitiva pentru aplicatie. Scopul este de a crea o aplicatie de chat simpla, unde s-au folosit socket-uri, fire de executie, fluxuri, fire de executie, interfata grafica, resurse commune pe server accesate simultan de client.
 
1. Client-Server 
Codul include un server (ChatServer.java) care gestionează conexiunile multiple ale clienților și clienți (ChatClient1.java și ChatClient2.java) care se conectează la server.

3. Fluxuri, Serializare
⦁	Fluxuri: Sunt utilizate PrintWriter și BufferedReader pentru a trimite și primi mesaje între client și server.
⦁	Serializare: Mesajele sunt trimise și primite ca șiruri de caractere (String), care este o formă simplă de serializare.

4. Fire de execuție
Serverul creează un nou fir de execuție (thread) pentru fiecare client conectat, gestionat de clasa ClientHandler.java.

5. Interfețe grafice, evenimente
⦁	Interfață grafică: Clienții utilizează biblioteca Swing pentru a crea o interfață grafică care afișează mesajele într-o listă și permite trimiterea de mesaje.
⦁	Evenimente: Se utilizează ActionListener pentru a detecta și a răspunde la evenimentele de trimitere a mesajelor (când utilizatorul apasă Enter sau butonul "Send").

6. Resurse comune pe server accesate simultan de client
Serverul gestionează o listă comună de ClientHandler pentru toți clienții conectați. Această resursă comună este accesată simultan de mai multe fire de execuție.

8. Metode de rezolvare a problemelor de concurență: monitoare, semafoare
Resursele comune, cum ar fi lista de clienți conectați (clientHandlers), trebuie protejate pentru a preveni conflictele care pot apărea atunci când mai multe fire de execuție încearcă să modifice aceleași date simultan. În acest proiect, folosim blocuri sincronizate (synchronized) pentru a asigura accesul exclusiv la resursa comună.
O alternativă la blocurile sincronizate este sincronizarea la nivel de metodă. Acest lucru poate fi realizat prin adăugarea cuvântului cheie synchronized la semnătura metodei. În acest proiect, am folosit blocuri sincronizate pentru flexibilitate, dar sincronizarea la nivel de metodă este o opțiune viabilă pentru metodele mici și atomice.
Java oferă o alternativă mai flexibilă la sincronizare prin utilizarea obiectelor de blocare (Lock). Biblioteca java.util.concurrent.locks include implementări precum ReentrantLock care oferă funcționalități avansate de blocare.

 ![image](https://github.com/BiancaCLN/Chat-Client-Server/assets/132608029/98216995-1c87-42ff-9699-8aad640b67ab)
 ![image](https://github.com/BiancaCLN/Chat-Client-Server/assets/132608029/9af0ec5f-e0a2-458c-b0ab-c6594afe94b5)![image](https://github.com/BiancaCLN/Chat-Client-Server/assets/132608029/78efd456-9bbf-4aa8-9bae-737eb8bb287f)




