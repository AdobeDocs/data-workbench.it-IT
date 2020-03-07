---
description: Informazioni sui parametri Sensor txlogd.conf richiesti.
solution: Insight
title: Parametri richiesti
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Required Parameters{#required-parameters}

Informazioni sui parametri Sensor txlogd.conf richiesti.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In questo parametro... </th> 
   <th colname="col2" class="entry"> Specifica... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Stringa di caratteri che identifica in modo univoco questo <span class="wintitle"> sensore</span>. </p> <p> <span class="wintitle"> Sensor</span> associa il SensorID a ogni record di evento che invia al server <span class="keyword"></span>workbench dati. SensorID consente di distinguere i dati dell'evento da questo server Web dai dati dell'evento acquisiti da altri <span class="wintitle"> sensori</span>. </p> <p>Sebbene un SensorID possa essere costituito da qualsiasi stringa di caratteri, per convenzione viene utilizzato il nome del server Web i cui eventi viene acquisito dal <span class="wintitle"> Sensor</span> . L'utilizzo del nome del server come SensorID facilita la determinazione dell'origine di un evento durante la fase di analisi. Inoltre, garantisce che il SensorID sia univoco nell'implementazione. </p> <p>Esempio: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>L'indirizzo del server <span class="keyword"> workbench</span> dati a cui questo <span class="wintitle"> sensore</span> invia i dati dell'evento. </p> <p>Nota:  <p>Quando si lavora in un ambiente cluster, <span class="wintitle"> Sensor</span> deve essere configurato per accedere al server <span class="keyword"></span> workbench dati master per evitare problemi di sincronizzazione. In Workbench dati è possibile visualizzare informazioni sui server <span class="keyword"> workbench di elaborazione dati nel cluster utilizzando la voce di menu Server correlati in</span> Server Manager <span class="wintitle"></span>. Per ulteriori informazioni su <span class="wintitle"> Server Manager</span>, vedere la <i><span class="keyword"> Guida ai sensori di Workbench</span><span class="wintitle"> dati</span></i>. </p> <p>Se il server Web è in grado di risolvere i nomi dei server tramite DNS, potete specificare l'indirizzo del server per nome. In caso contrario, è necessario specificare l'indirizzo IP numerico del server. </p> <p>Esempio: <span class="filepath"> ServerAddress 10.1.0.7</span> o </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Indica se <span class="wintitle"> Sensor</span> comunica con il server <span class="keyword"> workbench</span> dati utilizzando HTTP o HTTPS. Impostate su "on" per HTTPS o "off" per HTTP. </p> <p>Esempio: <span class="filepath"> SSL su</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>La porta su cui il server <span class="keyword"> workbench</span> dati ascolta i dati dell'evento. </p> <p>Esempio: Porta <span class="filepath"> server 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Obbligatorio solo se il parametro SSL è impostato su "on". </p> <p>Il nome comune del server <span class="keyword"> workbench</span> dati a cui questo <span class="wintitle"> sensore</span> invia i dati dell'evento. </p> <p>Il valore specificato deve corrispondere esattamente al nome comune visualizzato nel certificato di licenza del server <span class="keyword"> workbench</span> dati. </p> <p>Esempio: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Obbligatorio solo se il parametro SSL è impostato su "on". </p> <p>La directory in cui si trova il file dell'autorità di certificazione (<span class="filepath"> trust_ca_cert.pem</span>) </p> <p>Esempi: </p> <p> <span class="filepath"> CertPath /usr/local/visalSensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Non necessario per le installazioni <span class="wintitle"> Sensor</span> su computer server Microsoft Windows 2000 o 2003 con Internet Information Service (IIS) versione 5.x o 6.x. </p> <p>Il nome completo del file della coda del disco. </p> <p>Sebbene sia possibile assegnare un nome qualsiasi a questo file, per convenzione il file della coda è denominato <span class="filepath"> VisualSensor.dat</span>. </p> <p>Per le installazioni <span class="wintitle"> Sensor</span> su Unix, è possibile inserire questo file ovunque. In Windows con un server Web Java, è necessario inserire il file nella stessa directory del trasmettitore. Per tutti gli altri server Web, questo file deve risiedere nella directory /var/queue. </p> <p>Esempio: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Nota:  Verificate che il dispositivo a cui assegnate questo file disponga di spazio sufficiente per contenere una coda delle dimensioni desiderate. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Un numero intero che rappresenta la dimensione del file della coda del disco in MB. </p> <p>Per le installazioni <span class="wintitle"> Sensor</span> in Microsoft Windows, il file coda stesso viene creato nella stessa directory del trasmettitore ed è denominato <span class="filepath"> Diskq2000.log</span>. </p> <p>L'esempio seguente imposta la dimensione della coda su 200 MB: </p> <p>QueueSize 200 </p> <p>L’esempio seguente imposta la dimensione della coda su 2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

