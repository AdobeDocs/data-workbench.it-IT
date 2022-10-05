---
description: Data Workbench consente di esportare i file da integrare con l’esportazione Profili e pubblico come parte di un Adobe Experience Cloud integrato.
title: Esportazione del profilo di marketing principale
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
exl-id: 9fc89815-d31d-41a7-a0c0-de1e84b24baa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---

# Esportazione del profilo di marketing principale{#master-marketing-profile-export}

{{eol}}

Data Workbench consente di esportare file da integrare con Profili e pubblico come parte di un Adobe Experience Cloud integrato.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profili e pubblico fa parte del [Servizio Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it), un servizio fondamentale [!DNL Adobe Experience Cloud]. L’esportazione Profili e pubblico consente di condividere i tipi di pubblico nell’Experience Cloud utilizzando un ID Experience Cloud univoco (ECID) assegnato a ogni visitatore e quindi utilizzato da [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=it). La [!DNL ExportIntegration.exe] domanda ( [!DNL E:\Server\Scripts]) viene utilizzata per generare esportazioni MMP e Adobe Target.

**Configurazione del server FSU per l’utilizzo di profili e pubblico**

1. Accedi al tuo server FSU.
1. Apri il file MMPExport.cfg . `Server/Admin/Export/MMPExport.cfg`.
1. Immetti i valori desiderati in tutti i campi. Esempio:

   >[!NOTE]
   >
   >L’integrazione MMP/AAM si basa sul bucket s3 di Amazon per il trasferimento dei dati.
   >
   >
   >Le informazioni s3 richieste per il trasferimento MMP (s3) possono essere ottenute dal team di Audience Manager.

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >La [!DNL MMPExport.cfg]consente inoltre di prendere tutti i record, suddividerli in set e creare blocchi di record. I blocchi di record vengono quindi esportati in Amazon S3. Per creare blocchi di record sono necessari tre parametri obbligatori: [!DNL numRecordsPerChunk], [!DNL numThreads]e [!DNL maxRetriesOnSendFailure].

**Definizione dei parametri**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Intervallo s3</i> </td> 
   <td colname="col2"> Il bucket AWS S3 in cui viene trasferita l’esportazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Directory oggetti s3</i> </td> 
   <td colname="col2"> Un percorso per salvare i file s3. Questo supporta le sottodirectory. <p> <p>Importante: Lo spazio e i caratteri multibyte non sono consentiti nel percorso e creeranno errori nell’esportazione. (È consentita la penna). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Regione s3</i> </td> 
   <td colname="col2"> L’area AWS s3 a cui viene inviata l’esportazione. Es. us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Tasto di accesso s3</i> </td> 
   <td colname="col2"> Chiave di accesso AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Chiave segreta s3</i> </td> 
   <td colname="col2"> Chiave segreta AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>nome del fornitore dati</i> </td> 
   <td colname="col2"> Questo sarà il nome della cartella utilizzato rispettivamente per memorizzare segmenti e caratteristiche in AAM. Deve essere univoco per cliente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ID client</i> </td> 
   <td colname="col2"> Questo è un ID client univoco fornito a un cliente quando è stato eseguito il provisioning per MMP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>segreto client</i> </td> 
   <td colname="col2"> <p><i></i>Questo è un segreto client univoco fornito a un cliente quando viene fornito per MMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> Nome utente MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>password</i> </td> 
   <td colname="col2"> Password MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>Determina la dimensione del blocco in termini di numero di record. </p> <p>L'implementazione ritaglia il valore specificato dall'utente a min = 1000 records&amp;nbsp;(~50 KB chunks)&amp;nbsp;e max = 50000 record (~2,5 MB chunks).&amp;nbsp;Viene utilizzato un valore predefinito di 10000 nel caso in cui l'utente non specifichi questa proprietà di configurazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>Determina il parallelismo della parte di invio del blocco. Accetta un valore compreso tra 1 e 24 thread e il suo valore predefinito è 12 thread. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>Determina il numero di tentativi da eseguire in caso di errori di invio del blocco. Il valore predefinito è 0 e non specifica alcun nuovo tentativo. </p> <p>L'intervallo di sospensione di 2 secondi viene utilizzato tra i tentativi. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Generazione dell&#39;esportazione MMP dal client**

1. Dal client, apri un’area di lavoro e fai clic con il pulsante destro del mouse su **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**.
1. Aggiungi **Livello**.
1. Fai clic con il pulsante destro del mouse sull’intestazione e seleziona **Aggiungi attributi**.
1. Fai clic con il pulsante destro del mouse sull’intestazione e seleziona **Nuova esportazione del profilo di marketing principale**. ![](assets/mmp_mmp_export.png)
1. Espandi **Query**.

   ![](assets/mmp_mmp_query.png)

1. Espandi **Configurazione MMP**.
1. (obbligatorio) Inserisci il **Nome del segmento MMP** e **Campo ID visitatore MMP**. Questi parametri non possono essere lasciati vuoti.
1. La **Nome del segmento MMP** deve corrispondere all’ID segmento definito in MMP.
1. La **ID visitatore MMP** è la colonna dell&#39;attributo definita nel passaggio 4 che corrisponde al **ID visitatore**.
1. Una volta inseriti questi campi, puoi salvare l’esportazione facendo clic con il pulsante destro del mouse sull’intestazione dell’esportazione e scegliendo **Salva** come &quot;User\.export&quot;.
1. Apri **Amministratore** > **Profile Manager** e salva l’esportazione nel profilo .

   Se tutti i dati vengono immessi correttamente, verrà generato un file di esportazione nella FSU ([!DNL Server/Exports]) e trasferirà anche l’esportazione in AWS utilizzando le informazioni in [!DNL MMPExport.cfg]. Il registro di questo viene fornito in [!DNL Server/Trace/]. es. [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| Dettagli di configurazione | Descrizione |
|---|---|
| ID segmento MMP | Obbligatorio. Questo è un identificatore che verrebbe definito per primo in Audience Manager. |
| Campo ID visitatore MMP | Mappa l’ECID. |
