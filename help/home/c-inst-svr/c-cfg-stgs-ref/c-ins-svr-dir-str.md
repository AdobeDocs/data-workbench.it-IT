---
description: Elenco dei file installati con Insight Server e i file presenti dopo che è stato registrato ed eseguito per la prima volta.
solution: Insight
title: Struttura directory server Insight
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Struttura directory server Insight{#insight-server-directory-structure}

Elenco dei file installati con Insight Server e i file presenti dopo che è stato registrato ed eseguito per la prima volta.

## File inclusi nel pacchetto di installazione {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Le seguenti directory sono incluse nel pacchetto di [!DNL Insight Server] installazione:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Descrizione del contenuto della directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Controllo degli accessi </td> 
   <td colname="col2"> <span class="keyword"> File di configurazione di Insight Server </span> che specifica un elenco di gruppi di accesso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzi </td> 
   <td colname="col2"> Indirizzi utilizzati per la comunicazione con <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audit </td> 
   <td colname="col2"> Registri di accesso giornalieri contenenti informazioni su tutti i tentativi di connessione a <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> File </span> di programma eseguibili di Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificati </td> 
   <td colname="col2"> Certificati digitali SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componenti </td> 
   <td colname="col2"> <span class="keyword"> File di configurazione dei </span> componenti di Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componenti per i server di elaborazione </td> 
   <td colname="col2"> <span class="keyword"> File di configurazione dei </span> componenti di Insight Server per l’elaborazione dei server <span class="keyword"> Insight </span> in un cluster <span class="keyword"> Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventi </td> 
   <td colname="col2"> Registri di eventi giornalieri contenenti messaggi di stato dell’evento dettagliati, compresi i messaggi di errore. Gli eventi acquisiti e registrati da <span class="keyword"> Insight Server </span> vengono visualizzati anche nel visualizzatore eventi di Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registri </td> 
   <td colname="col2"> <p>File di registro prodotti da <span class="wintitle"> Sensor </span>(s). </p> <p>"Logs" è la directory di registrazione predefinita, ma una directory alternativa potrebbe essere stata specificata nel file <span class="filepath"> communication.cfg </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerche </td> 
   <td colname="col2"> File di ricerca, ad esempio elenchi di robot e motori di ricerca. <span class="keyword"> Insight Server </span> deve caricare tutti i file di ricerca in memoria. La dimensione totale di tutti i file di ricerca a cui si fa riferimento nei file di configurazione dei componenti, più il sovraccarico (ad esempio, 12 byte per riga per i file <span class="filepath"> FlatFileLookup </span> ), non deve superare la memoria fisica o virtuale disponibile dopo il caricamento di tutte le altre applicazioni software. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profili </td> 
   <td colname="col2"> <p>File relativi a ciascun profilo (file di configurazione, area di lavoro e visualizzazione). I profili sono compilati dai dati provenienti da un dataset. I set di dati includono i dati evento ("Dati di registro"); tali dati possono essere catturati da <span class="wintitle"> </span>Sensori installati, trasmessi da Web beacon o tag di pagina, o immessi da data warehouse. <span class="keyword"> Gli </span> utenti con accesso a un determinato profilo possono utilizzare il set di dati elaborati per tale profilo, nonché le aree di lavoro e le visualizzazioni definite all'interno di tale profilo. </p> <p>Le aree di lavoro sono aree di lavoro per l'amministrazione o l'analisi del sistema. Un'area di lavoro può contenere più interfacce che mostrano diversi dettagli sulle prestazioni del sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Aggiornamenti </span> del software. Gli aggiornamenti del software di report sono anche memorizzati qui. </td> 
  </tr> 
 </tbody> 
</table>

## Directory e file creati dopo l’avvio {#section-ef7408e8fae64454b326ec07453d4628}

Le directory elencate di seguito vengono create dopo che [!DNL Insight Server] sono state registrate ed eseguite per la prima volta:

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Stato </td> 
   <td colname="col2"> Informazioni di elaborazione generate da <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Posizione dei file temporanei utilizzati da <span class="keyword"> Insight Server </span> durante la rielaborazione e il funzionamento. In genere esiste un file (denominato <span class="filepath"> </span> temp.db per impostazione predefinita) per unità fisica. </p> <p> <span class="keyword"> È </span> necessario configurare Insight Server per scrivere in questa directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> Log and event data about <span class="keyword"> Insight Server </span>. Utile per la risoluzione dei problemi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utenti </td> 
   <td colname="col2"> Utenti denominati ( <span class="keyword"> Insight </span>) con accesso ai profili sul server. All'interno della directory Users viene creata una directory per ciascun utente denominato autorizzato quando l'utente accede per la prima volta a <span class="keyword"> Insight Server </span> tramite <span class="keyword"> Insight </span>. La directory di ciascun utente denominato contiene le directory corrispondenti a tutti i profili a cui l'utente ha accesso in tale server <span class="keyword"> Insight </span> e ai relativi file di indirizzo locali. </td> 
  </tr> 
 </tbody> 
</table>

