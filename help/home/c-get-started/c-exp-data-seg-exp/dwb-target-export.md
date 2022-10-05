---
description: Esporta i dati di Data Workbench in Adobe Target utilizzando TargetBulkUpload.exe dalla tabella dei dettagli.
title: Esportazione in Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---

# Esportazione in Adobe Target{#export-to-adobe-target}

{{eol}}

Esporta i dati di Data Workbench in Adobe Target utilizzando TargetBulkUpload.exe dalla tabella dei dettagli.

Data Workbench consente di esportare i file da integrare con Adobe Target come parte di un Adobe Experience Cloud integrato.

La **[!DNL TargetBulkUpload]** si trova nel *Server\Script* nei file di installazione del server. L&#39;eseguibile dispone di una logica di esecuzione dei tentativi, nonché di una logica aggiuntiva per ottimizzare le prestazioni.

Puoi modificare la `TargetBulkUpload.cfg` e spostalo in *Server/Amministratore/Esportazione* prima di eseguire lo script di caricamento. Ad esempio, puoi impostare un intervallo di timeout massimo su 720 minuti (impostazione predefinita) per timeout del caricamento dopo il periodo specificato.

**Come funziona**

Una volta inviati correttamente i dati a Target, lo stato del caricamento viene monitorato continuamente. Se il caricamento ha esito positivo, viene registrato un messaggio di successo. Se il caricamento non riesce o è in sospeso, il monitoraggio continua. Puoi configurare l’intervallo di timeout nel `TargetBulkUpload.cfg` file. Se il caricamento si blocca su Target, viene registrato un messaggio e lo stato può ancora essere monitorato.

Ci sono due file di log generati nella traccia per l&#39;esportazione attivata in [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

La `targetbulkuploadexportname.log` il file presenta lo stato dettagliato di tutti i record di più batch, il server perimetrale a cui si sta andando e lo stato (riuscito, non riuscito, profilo non trovato, stato sconosciuto e bloccato). Nel caso in cui un lotto sia bloccato, il batch non viene ulteriormente elaborato. Per tenere traccia dello stato è disponibile un URL batch bloccato. Vedi i seguenti dati di esempio dal `targetbulkuploadexportname.log.completed` file:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

Il valore di stato bloccato viene incrementato con la dimensione totale del batch bloccato, indipendentemente dal numero di caricamenti riusciti o non riusciti. Anche il valore delle righe totali viene incrementato dello stesso numero di dimensioni batch bloccate.

>[!NOTE]
>
>In precedenza, i dati DWB venivano esportati utilizzando [!DNL ExportIntegration.exe]. Attualmente solo le esportazioni MMP, CRS e S/FTP vengono utilizzate con questo eseguibile. L&#39;integrazione di Adobe Target utilizza ora [!DNL TargetBulkUpload.exe] nella Data Workbench.
