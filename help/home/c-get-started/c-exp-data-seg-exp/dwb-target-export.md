---
description: Esporta dati Workbench dati in Adobe Target utilizzando TargetBulkUpload.exe dalla tabella dei dettagli.
title: Esporta in Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esporta in Adobe Target{#export-to-adobe-target}

Esporta dati Workbench dati in Adobe Target utilizzando TargetBulkUpload.exe dalla tabella dei dettagli.

Workbench dati consente di esportare i file da integrare con Adobe Target come parte di un Adobe Experience Cloud integrato.

Il **[!DNL TargetBulkUpload]** file si trova nella cartella *Server\Scripts* dei file di installazione del server. L&#39;eseguibile dispone di logica dei tentativi, oltre a logica aggiuntiva per ottimizzare le prestazioni.

Potete modificare il `TargetBulkUpload.cfg` file e spostarlo nella cartella *Server/Admin/Export* prima di eseguire lo script di caricamento. Ad esempio, potete impostare un intervallo di timeout massimo su 720 minuti (impostazione predefinita) per timeout del caricamento dopo il periodo specificato.

**Come funziona**

Dopo che i dati sono stati inviati a Target, lo stato del caricamento viene monitorato in modo continuo. Se il caricamento ha esito positivo, viene registrato un messaggio di riuscita. Se il caricamento non riesce o è in sospeso, il monitoraggio continua. Puoi configurare l’intervallo di timeout nel `TargetBulkUpload.cfg` file. Se il caricamento si blocca in Target, viene registrato un messaggio e lo stato può essere monitorato.

Nella traccia dell’esportazione attivata sono generati due file di registro in [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

Il `targetbulkuploadexportname.log` file ha lo stato dettagliato per tutti i record di più batch, il server periferico a cui si riferiscono e lo stato (riuscito, non riuscito, profilo non trovato, stato sconosciuto e bloccato). Nel caso in cui si riscontri che un lotto è bloccato, il lotto non viene ulteriormente elaborato. È disponibile un URL batch bloccato per tenere traccia dello stato. Vedere i seguenti dati di esempio dal `targetbulkuploadexportname.log.completed` file:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

Il valore di stato bloccato viene incrementato con la dimensione batch bloccata totale, indipendentemente dal numero di caricamenti riusciti o non riusciti. Anche il valore delle righe totali viene incrementato dello stesso numero di dimensioni batch bloccate.

>[!NOTE]
>
>Precedentemente, i dati DWB venivano esportati tramite [!DNL ExportIntegration.exe]. Attualmente solo le esportazioni MMP, CRS e S/FTP sono utilizzate con questo eseguibile. L&#39;integrazione con Adobe Target ora utilizza il [!DNL TargetBulkUpload.exe] componente in Workbench dati.

