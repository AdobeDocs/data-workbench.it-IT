---
description: Integrare Workbench dati con Adobe Target. Esportare segmenti di dati e compilare automaticamente i file di esportazione.
solution: Analytics
title: Integrazione di Workbench dati con Adobe Target
topic: Data workbench
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integrazione di Workbench dati con Adobe Target

L&#39;integrazione di Adobe Data Workbench con Adobe Target è diventata più semplice grazie alle funzioni Workbench dati, che consentono di esportare segmenti di dati e di compilare automaticamente i file di esportazione.

Adobe Data Workbench offre l&#39;integrazione a ciclo chiuso con Adobe Target per la condivisione di dati e la generazione di rapporti. In Workbench dati è possibile analizzare le popolazioni per segmenti significativi utilizzando tutti i dati disponibili, comprese le conversioni offline attraverso canali quali telefono, store e così via.

Ad esempio, un visitatore cerca le scarpe sul sito Web ma non le converte. Piuttosto, il visitatore scarica un coupon per il 20% di sconto sul prossimo acquisto e poi acquista una camicia nel vostro negozio. Utilizzando Workbench dati, è possibile raccogliere i dati e quindi inviare nuovamente i dati di profilo a Target per mostrare che il visitatore ha acquistato una camicia offline. Potete quindi eseguire il targeting di una campagna che offre una cravatta a quel visitatore, quando normalmente Target potrebbe provare a riimmettere sul mercato le scarpe per quel visitatore.

## Impostazione di Workbench dati con Adobe Target

1. Fare clic con il pulsante destro del mouse sull&#39;intestazione nella [!UICONTROL Detail Table] finestra.

   ![](assets/insight-to-tnt.png)

1. Selezionate **[!UICONTROL New Target Export]** e immettete il nome di un nuovo file di esportazione sotto il **[!UICONTROL Save As]** comando del menu.

1. Fai clic su **[!UICONTROL Save Export File]** (Fine).

   Viene aperta una finestra modello di esportazione.

   Tutte le informazioni di Adobe Target vengono popolate automaticamente. Viene creato l’elenco dei parametri in base a quanto inserito nell’esportazione dei segmenti. Al termine, Workbench dati invierà i dati al server Adobe Target.

   **Nota:** Il file Template deve essere configurato dal [!UICONTROL Profile Architect]. È [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]e [!UICONTROL Mbox Name] necessario inserirla. Se disponete di più siti, compilate più modelli e salvateli sul server. I modelli di Profile Manager si trovano in `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Specificate il parametro di [!UICONTROL mboxPC] query.

   Se il nome dell&#39;attributo Workbench dati è diverso da [!UICONTROL mboxPC], è necessario modificare il parametro Query appropriato e rinominarlo in _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Quando salvate il file di esportazione nel server, l&#39;esportazione verrà avviata. Al termine, l&#39; [!UICONTROL TnTSend.exe] applicazione verrà avviata e inizierà a inviare i dati all&#39;account Target.

## Configurazione di Workbench dati per Target

Completa le seguenti attività in Adobe Target:

Workbench dati sta trasferendo i profili utente ad Adobe Target. Per configurare l&#39;esportazione in Target, dovete configurare e abilitare la relativa API e fornire i **[!UICONTROL clientname]** e **[!UICONTROL domain postfix]** i parametri per il file di configurazione dell&#39;esportazione (`export.cfg`).

È stata aggiunta una nuova opzione booleana **[!UICONTROL Oneshot]** ai file di esportazione dei segmenti. Questa opzione è inclusa nel file modello distribuito con il nuovo profilo. Se [!UICONTROL Oneshot] è impostato su _true_, il `.export` file verrà rinominato `.export.done-TIMESTAMP` al termine dell&#39;esportazione, assicurando che il segmento non venga mai esportato più di una volta. Questo è importante quando si esporta in Adobe Target.

**Nota:** Una chiamata da Workbench dati ad Adobe Target viene conteggiata come una [!UICONTROL mbox] chiamata, che richiede una chiamata per ciascun profilo inviato. Di conseguenza, i costi aumentano se sono richieste più chiamate tra le due soluzioni.

Una configurazione incompleta genera il seguente messaggio di errore nel registro:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configurazione di Adobe Target per Workbench dati

In Adobe Target, non è necessaria alcuna configurazione speciale per consentire al cliente di inviare i dati del profilo. Le informazioni di profilo per un utente vengono in genere trasmesse nella [!UICONTROL mbox] richiesta regolare, e i server renderanno disponibili i parametri di profilo per una configurazione di campagna mirata come funzionalità standard senza alcuna configurazione aggiuntiva.

In Adobe Target è integrata l&#39;integrazione del workbench dati, che può essere abilitata dalla pagina Dettagli cliente utente avanzato. L&#39;abilitazione dell&#39;opzione consente di visualizzare in superficie i segmenti condivisi da Workbench dati in Adobe Target per renderli disponibili per il targeting.

## Impostare il reporting del registro HTTP in ExportIntegration.exe

Riduci i rapporti lunghi a [!UICONTROL HTTP.log] quando utilizzi [!UICONTROL ExportIntegration.exe] per esportare file di integrazione Adobe Target.

Un nuovo file di [!UICONTROL httpLoggingEI.cfg] configurazione (situato in `server\Admin\Export\httpLoggingEI.cfg`) consente di ridurre la registrazione dettagliata nel [!UICONTROL HTTP.log] file per l&#39;esportazione dei dati utilizzando [!UICONTROL ExportIntegration.exe]. Questo consente di interrompere la registrazione dettagliata delle richieste e delle risposte.

La registrazione dettagliata è già acquisita nei [!UICONTROL TnTSend.log] file.

_True_ imposta la registrazione dettagliata e _False_ interrompe la registrazione dettagliata sul [!UICONTROL HTTP.log] file.

Se è impostata su False, al [!UICONTROL HTTP.log] file verrà inviato solo un messaggio di avviso (contenuto Info non inviato).