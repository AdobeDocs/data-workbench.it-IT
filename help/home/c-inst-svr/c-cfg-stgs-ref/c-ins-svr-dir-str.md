---
description: Elenco dei file installati con Insight Server e dei file presenti dopo la sua registrazione ed esecuzione per la prima volta.
title: Struttura directory di Insight Server
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Struttura directory di Insight Server{#insight-server-directory-structure}

Elenco dei file installati con Insight Server e dei file presenti dopo la sua registrazione ed esecuzione per la prima volta.

## File inclusi nel pacchetto di installazione {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Le seguenti directory sono incluse nel pacchetto di installazione [!DNL Insight Server]:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Descrizione del contenuto della directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Controllo di accesso </td> 
   <td colname="col2"> <span class="keyword"> File di  </span> configurazione di Insight Server che specifica un elenco di gruppi di accesso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzi </td> 
   <td colname="col2"> Indirizzi utilizzati per la comunicazione con <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audit </td> 
   <td colname="col2"> Log di accesso giornalieri contenenti i dettagli relativi a tutte le connessioni tentate a <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bidone </td> 
   <td colname="col2"> <span class="keyword"> File di programma  </span> eseguibili di Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificati </td> 
   <td colname="col2"> Certificati digitali SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componenti </td> 
   <td colname="col2"> <span class="keyword"> File di configurazione del  </span> componente Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componenti per i server di elaborazione </td> 
   <td colname="col2"> <span class="keyword"> File di configurazione del  </span> componente Insight Server per l’elaborazione di  <span class="keyword"> Insight Server  </span> all’interno di un  <span class="keyword"> cluster  </span> Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventi </td> 
   <td colname="col2"> Log degli eventi giornalieri contenenti messaggi di stato degli eventi dettagliati, inclusi messaggi di errore. Gli eventi acquisiti e registrati da <span class="keyword"> Insight Server </span> vengono visualizzati anche nel Visualizzatore eventi di Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registri  </td> 
   <td colname="col2"> <p>File di registro prodotti da <span class="wintitle"> Sensor </span>(s). </p> <p>"Logs" è la directory di registrazione predefinita, ma è possibile che sia stata specificata una directory alternativa nel file <span class="filepath"> communication.cfg </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerche </td> 
   <td colname="col2"> File di ricerca, ad esempio elenchi di robot e motori di ricerca. <span class="keyword"> Insight Server  </span> deve caricare tutti i file di ricerca nella memoria. La dimensione totale di tutti i file di ricerca a cui si fa riferimento nei file di configurazione dei componenti, oltre al sovraccarico (ad esempio, 12 byte per riga per i file <span class="filepath"> FlatFileLookup </span>), non deve superare la memoria fisica o virtuale disponibile dopo il caricamento di tutte le altre applicazioni software. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profili </td> 
   <td colname="col2"> <p>File relativi a ciascun profilo (file di configurazione, area di lavoro e visualizzazione). I profili vengono compilati dai dati di un set di dati. I set di dati includono i dati evento ("Dati registro"); tali dati possono essere acquisiti da <span class="wintitle"> Sensori </span> installati, trasmessi da web beacon o tag di pagina, o da dati di data warehouse. <span class="keyword"> Gli  </span> utenti di Insight con accesso a un determinato profilo possono utilizzare il set di dati elaborati per tale profilo, nonché le aree di lavoro e le visualizzazioni definite all’interno di tale profilo. </p> <p>Le aree di lavoro sono aree di lavoro per l’amministrazione o l’analisi del sistema. Un'area di lavoro può contenere più interfacce che mostrano diversi dettagli sulle prestazioni del sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Aggiornamenti  </span> del software Insight. Gli aggiornamenti software dei report sono anche memorizzati qui. </td> 
  </tr> 
 </tbody> 
</table>

## Directory e file creati dopo l&#39;avvio {#section-ef7408e8fae64454b326ec07453d4628}

Le directory elencate di seguito vengono create dopo la prima registrazione ed esecuzione di [!DNL Insight Server]:

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
   <td colname="col1"> Temp. </td> 
   <td colname="col2"> <p>Posizione dei file temporanei utilizzati da <span class="keyword"> Insight Server </span> durante la rielaborazione e il funzionamento. In genere esiste un file (denominato <span class="filepath"> temp.db </span> per impostazione predefinita) per unità fisica. </p> <p> <span class="keyword"> Per scrivere in questa directory  </span> è necessario configurare Insight Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Traccia </td> 
   <td colname="col2"> Dati di registro ed evento su <span class="keyword"> Insight Server </span>. Utile per la risoluzione dei problemi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utenti </td> 
   <td colname="col2"> Utenti denominati ( <span class="keyword"> Insight </span>) con accesso ai profili sul server. Una directory per ogni utente autorizzato denominato viene creata all'interno della directory Users\ quando l'utente accede per la prima volta a <span class="keyword"> Insight Server </span> tramite <span class="keyword"> Insight </span>. La directory per ogni utente denominato contiene directory corrispondenti a tutti i profili a cui l’utente ha effettuato l’accesso in tale <span class="keyword"> Insight Server </span> e ai relativi file di indirizzo locali. </td> 
  </tr> 
 </tbody> 
</table>
