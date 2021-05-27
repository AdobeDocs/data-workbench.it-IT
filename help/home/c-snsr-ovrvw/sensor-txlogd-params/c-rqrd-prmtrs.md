---
description: Informazioni sui parametri Sensor txlogd.conf richiesti.
title: Parametri richiesti
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Parametri richiesti{#required-parameters}

Informazioni sui parametri Sensor txlogd.conf richiesti.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In questo parametro.. </th> 
   <th colname="col2" class="entry"> Specifica... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Una stringa di caratteri che identifica in modo univoco questo <span class="wintitle"> sensore</span>. </p> <p> <span class="wintitle"> </span> Sensorattacca il SensorID a ogni record di evento che invia al server di  <span class="keyword"> Data Workbench</span>. SensorID consente di distinguere i dati evento da questo server web dai dati evento acquisiti da altri <span class="wintitle"> Sensor</span>. </p> <p>Anche se un SensorID può essere costituito da qualsiasi stringa di caratteri, per convenzione viene utilizzato il nome del server web di cui vengono acquisiti gli eventi da <span class="wintitle"> Sensor</span> . L’utilizzo del nome server come SensorID facilita la determinazione dell’origine di un evento durante la fase di analisi. Inoltre, garantisce che il SensorID sia univoco all'interno dell'implementazione. </p> <p>Esempio: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IndirizzoServer </td> 
   <td colname="col2"> <p>Indirizzo del server di Data Workbench <span class="keyword"></span> a cui questo <span class="wintitle"> Sensor</span> invia i dati dell’evento. </p> <p>Nota:  <p>Quando si lavora in un ambiente cluster, <span class="wintitle"> Sensor</span> deve essere configurato per accedere al server principale <span class="keyword"> di Data Workbench</span> per evitare problemi di sincronizzazione. In Data Workbench è possibile visualizzare informazioni sull'elaborazione dei server di Data Workbench <span class="keyword"> </span> nel cluster utilizzando la voce di menu Server correlati nel <span class="wintitle"> Server Manager</span>. Per ulteriori informazioni su <span class="wintitle"> Server Manager</span>, consulta la Guida <i><span class="keyword"></span><span class="wintitle"> Sensor</span></i> Data Workbench. </p> <p>Se il server web è in grado di risolvere i nomi dei server tramite DNS, è possibile specificare l’indirizzo del server per nome. In caso contrario, è necessario specificare l’indirizzo IP numerico del server. </p> <p>Esempio: <span class="filepath"> ServerAddress 10.1.0.7</span> o </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Se <span class="wintitle"> Sensor</span> comunica con <span class="keyword"> il server di Data Workbench</span> tramite HTTP o HTTPS. Imposta su "on" per HTTPS o "off" per HTTP. </p> <p>Esempio: <span class="filepath"> SSL su</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta server </td> 
   <td colname="col2"> <p>La porta su cui il server di Data Workbench <span class="keyword"></span> ascolta i dati dell’evento. </p> <p>Esempio: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Obbligatorio solo se il parametro SSL è impostato su "on". </p> <p>Il nome comune del server di Data Workbench <span class="keyword"></span> a cui questo <span class="wintitle"> Sensor</span> invia i dati dell’evento. </p> <p>Il valore specificato deve corrispondere esattamente al nome comune visualizzato nel certificato di licenza <span class="keyword"> data workbench server</span> . </p> <p>Esempio: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Obbligatorio solo se il parametro SSL è impostato su "on". </p> <p>La directory in cui si trova il file dell'autorità di certificazione (<span class="filepath"> trust_ca_cert.pem</span>) </p> <p>Esempi: </p> <p> <span class="filepath"> CertPath /usr/local/visualSensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FileCoda </td> 
   <td colname="col2"> <p>Non necessario per le installazioni <span class="wintitle"> Sensor</span> su computer server Microsoft Windows 2000 o 2003 che eseguono Internet Information Service (IIS) versioni 5.x o 6.x. </p> <p>Nome completo del file della coda del disco. </p> <p>Anche se è possibile assegnare un nome qualsiasi a questo file, per convenzione, il file della coda si chiama <span class="filepath"> VisualSensor.dat</span>. </p> <p>Per le installazioni <span class="wintitle"> Sensor</span> su Unix, puoi inserire questo file ovunque. Su Windows che esegue un server web Java, è necessario inserire questo file nella stessa directory del trasmettitore. Per tutti gli altri server web, questo file deve risiedere nella directory /var/queue . </p> <p>Esempio: <span class="filepath"> File di coda /var/queue/VisualSensor.dat</span> </p> <p> <p>Nota:  Assicurati che il dispositivo a cui assegni questo file abbia spazio libero sufficiente per contenere una coda delle dimensioni necessarie. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Un numero intero che rappresenta la dimensione del file della coda del disco in MB. </p> <p>Per le installazioni di <span class="wintitle"> Sensor</span> in Microsoft Windows, il file della coda stesso viene creato nella stessa directory del trasmettitore ed è denominato <span class="filepath"> Diskq2000.log</span>. </p> <p>L'esempio seguente imposta la dimensione della coda su 200 MB: </p> <p>DimensioneCoda 200 </p> <p>L’esempio seguente imposta la dimensione della coda su 2 GB: </p> <p>Dimensione coda 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
