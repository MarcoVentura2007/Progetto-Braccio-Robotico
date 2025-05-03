# Progetto-Braccio-Robotico

Documentazione del Progetto Arduino - Braccio Robotico con Controllo Bluetooth

<h3> 1. Descrizione Generale </h3>
Il progetto consiste nello sviluppo e miglioramento di un braccio robotico controllato tramite servomotori, con un'integrazione avanzata che permette il controllo via Bluetooth. Nasce come evoluzione di un progetto scolastico, con l’obiettivo di aumentarne le possibilità applicative.



<h3> 2. Obiettivi del Progetto </h3>
Controllabilità Bluetooth: permettere il controllo del braccio robotico da qualunque dispositivo compatibile Bluetooth (es. joystick della PlayStation, smartphone, Raspberry Pi, ecc.).

Interfaccia Web: aggiunta di un’interfaccia HTML per il controllo remoto da pagina web.
Modularità: progettazione flessibile per sostituire il braccio o integrarlo con altri attuatori o motori.




<h3> 3. Componenti principali utilizzati </h3>
Arduino uno r3: riceve comandi via seriale da Flask e controlla i servomotori.

Raspberry Pi p5: esegue un server Flask e gestisce l'interfaccia web.

Servomotori MG996R: movimentano le parti del braccio robotico.




<h3> 4. Funzionamento Tecnico </h3>
L'interfaccia HTML permette all'utente di controllare i movimenti del braccio inserendo valori per i servomotori.

Il server Flask scritto in python riceve i comandi dall'interfaccia sotto forma di valore e li converte in string.
Arduino riceve i comandi via seriale e li converte in intero per i servomotori, dividendoli usando una funzione molto simile all’strtok.

I servomotori eseguono il movimento richiesto con un semplice codice sviluppato nell’arduino idee.



 
<h3> 5. Possibili Sviluppi Futuri </h3>
Aggiunta di ruote e motori per trasformare il sistema in una macchinina robotica con braccio.

Estensione della struttura per usare altri attuatori, aumentando la flessibilità e adattabilità.

Miglioramento dell'interfaccia utente(pagina html ad esempio) e della reattività del sistema.

Integrazione con sistemi di visione artificiale o comandi vocali.

Implementando sistemi appositi di intelligenza artificiale potremmo arrivare a far fare certi movimenti al braccio semplicemente facendo un gesto con la mano(questa idea ci è venuta ispirandoci a un progetto di una ex quinta)

<h2> Approfondimento: funzionamento </h2>


Il progetto nasce come estensione di un lavoro scolastico già esistente, con l’intento di migliorare la funzionalità, interattività e modularità.
Interfaccia Utente (Web):
- L’utente imposta i valori desiderati per ogni angolazione dei servomotori attraverso dei slider o input numerici.
- I comandi vengono inviati in tempo reale tramite HTTP request al server Flask.

Server Flask (Raspberry Pi):
- Il server riceve i valori, li converte in stringhe formattate, e li invia via seriale USB all’Arduino.

Arduino:
- Riceve la stringa, divisa con una funzione simile a strtok(), e la converte in valori numerici interi.
- I servomotori vengono poi controllati tramite la funzione servo.write() con il valore ricevuto.

Movimento del Braccio:
-I servomotori eseguono il movimento richiesto con precisione grazie alla modulazione del segnale PWM.
- Il sistema è reattivo e preciso, con feedback visivo immediato.



<h3> 6. Autori del Progetto </h3>
Candeloro Simone


Fontana Andrea

Uboldi Luca

Ventura Marco

Provenza Tiziana

