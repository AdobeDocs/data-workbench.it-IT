---
description: Workbench dati consente di esportare i file da integrare con Profili e pubblico come parte di un Adobe Experience Cloud integrato.
title: Esportazione profilo marketing principale
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Esportazione profilo marketing principale{#master-marketing-profile-export}

Workbench dati consente di esportare i file da integrare con Profili e pubblico come parte di un Adobe Experience Cloud integrato.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profili e pubblico fa parte del servizio [Experience Cloud Identity, un servizio di base del servizio](https://docs.adobe.com/content/help/en/id-service/using/home.html)[!DNL Adobe Experience Cloud]. L&#39;esportazione di profili e audience consente di condividere i tipi di pubblico in Experience Cloud tramite un Experience Cloud ID (ECID) univoco assegnato a ogni visitatore e quindi utilizzato da [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html). L&#39; [!DNL ExportIntegration.exe] applicazione ( [!DNL E:\Server\Scripts]) viene utilizzata per generare esportazioni MMP e Adobe Target.

**Configurazione del server FSU per l’uso di profili e audience**

1. Accedere al server FSU.
1. Aprite il file MMPExport.cfg. `Server/Admin/Export/MMPExport.cfg`.
1. Immettete i valori in tutti i campi come richiesto. Ad esempio:

   >[!NOTE]
   >
   >L&#39;integrazione MMP/AAM si basa sul bucket s3 di Amazon per il trasferimento dei dati.
   >
   >
   >Le informazioni s3 richieste per il trasferimento MMP (s3) possono essere ottenute dal team Audience Manager.

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
   >Il [!DNL MMPExport.cfg]file consente inoltre di prendere tutti i record, suddividerli in set e creare blocchi di record. I blocchi di record vengono quindi esportati in Amazon S3. Per creare blocchi di record sono necessari tre parametri obbligatori: [!DNL numRecordsPerChunk], [!DNL numThreads], e [!DNL maxRetriesOnSendFailure].

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
   <td colname="col1"> <i>s3 Bucket</i> </td> 
   <td colname="col2"> Il bucket AWS S3 in cui viene trasferita l'esportazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>directory oggetti s3</i> </td> 
   <td colname="col2"> Un percorso per salvare i file s3. Questo supporta le sottodirectory. <p> <p>Importante:  Spazio e caratteri multibyte non sono consentiti nel percorso e creeranno errori nell'esportazione. (È consentito attivare la penna). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>regione s3</i> </td> 
   <td colname="col2"> Regione AWS s3 a cui viene inviata l'esportazione. Ex. us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Access Key</i> </td> 
   <td colname="col2"> Chiave di accesso AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Chiave segreta s3</i> </td> 
   <td colname="col2"> Chiave segreta AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>nome provider dati</i> </td> 
   <td colname="col2"> Questo sarà il nome della cartella utilizzato per memorizzare segmenti e caratteristiche in AAM, rispettivamente. Deve essere univoco per cliente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ID client</i> </td> 
   <td colname="col2"> Si tratta di un ID client univoco fornito a un cliente quando viene eseguito il provisioning per MMP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>segreto cliente</i> </td> 
   <td colname="col2"> <p><i></i>Questo è un segreto cliente univoco fornito a un cliente quando viene fornito per MMP. </p> </td> 
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
   <td colname="col2"> <p>Determina la dimensione del blocco in termini di numero di record. </p> <p>L'implementazione ritaglia il valore specificato dall'utente su min = 1000 record&amp;nbsp;(~50 KB blocchi)&amp;nbsp;e max = 50000 record (~2,5 MB blocchi).&amp;nbsp;Un valore predefinito pari a 10000 viene utilizzato nel caso in cui l'utente non specifichi questa proprietà di configurazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThread</i> </td> 
   <td colname="col2"> <p>Determina il parallelismo della parte di invio della parte di invio della parte. Accetta un valore compreso tra 1 e 24 thread e il valore predefinito è 12 thread. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailed</i> </td> 
   <td colname="col2"> <p>Determina il numero di tentativi da effettuare in caso di errori di invio blocco. Il valore predefinito è 0 e non specifica alcun tentativo. </p> <p>L'intervallo di sospensione di 2 secondi viene utilizzato tra i tentativi. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Generazione dell&#39;esportazione MMP dal client**

1. Dal client, aprite un’area di lavoro e fate clic con il pulsante destro del mouse **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**.
1. Aggiungi **livello**.
1. Fare clic con il pulsante destro del mouse sull&#39;intestazione e selezionare **Aggiungi attributi**.
1. Fate clic con il pulsante destro del mouse sull’intestazione e selezionate **Nuova esportazione** profilo marketing principale. ![](assets/mmp_mmp_export.png)
1. Espandete **Query**.

   ![](assets/mmp_mmp_query.png)

1. Espandete Configurazione **** MMP.
1. (richiesto) Immettete il nome **del segmento** MMP e il campo **ID visitatore** MMP. Questi parametri non possono essere lasciati vuoti.
1. Il nome **segmento** MMP deve corrispondere all’ID segmento definito nell’MMP.
1. L’ID **visitatore** MMP è la colonna dell’attributo definita al punto 4 che corrisponde all’ID **** visitatore.
1. Una volta immessi questi campi, potete salvare l’esportazione facendo clic con il pulsante destro del mouse sull’intestazione dell’esportazione e scegliendo **Salva** come &quot;Utente\.esportazione&quot;.
1. Apri **Admin** > **Profile Manager** e salva l’esportazione nel profilo.

   Se tutti i dati sono immessi correttamente, questo genererà un file di esportazione nella FSU ([!DNL Server/Exports]) e trasferirà anche l&#39;esportazione in AWS utilizzando le informazioni in [!DNL MMPExport.cfg]. Il registro di questo viene fornito in [!DNL Server/Trace/]. ad esempio, [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

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

| Dettagli configurazione | Descrizione |
|---|---|
| ID segmento MMP | Obbligatorio. Si tratta di un identificatore che verrà definito per primo in Audience Manager. |
| Campo ID visitatore MMP | Mappare l’ECID. |

