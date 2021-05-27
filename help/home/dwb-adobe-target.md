---
description: Integra Data Workbench con Adobe Target. Esporta segmenti di dati e compila automaticamente i file di esportazione.
title: Integrazione di Data Workbench con Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Integrazione di Data Workbench con Adobe Target

L’integrazione di Adobe Data Workbench con Adobe Target è diventata più semplice grazie alle funzioni Data Workbench per esportare segmenti di dati e compilare automaticamente i file di esportazione.

Adobe Data Workbench fornisce un’integrazione in loop chiusa con Adobe Target per la condivisione dei dati e la generazione di rapporti. All’interno della Data Workbench è possibile analizzare le popolazioni per segmenti significativi utilizzando tutti i dati disponibili, comprese le conversioni offline attraverso canali come il telefono, un negozio e così via.

Ad esempio, un visitatore cerca scarpe sul tuo sito web ma non si converte. Piuttosto, il visitatore scarica un coupon per il 20% del suo acquisto successivo e poi acquista una camicia nel tuo negozio. Utilizzando Data Workbench, puoi raccogliere tali dati e quindi inviare nuovamente i dati del profilo a Target per mostrare che il visitatore ha acquistato una camicia offline. Puoi quindi eseguire il targeting di una campagna che offre una cravatta a quel visitatore, quando normalmente Target potrebbe provare a rivendicare scarpe per quel visitatore.

## Configurare Data Workbench con Adobe Target

1. Fare clic con il pulsante destro del mouse sull&#39;intestazione nella finestra [!UICONTROL Detail Table].

   ![](assets/insight-to-tnt.png)

1. Selezionare **[!UICONTROL New Target Export]** e immettere il nome di un nuovo file di esportazione sotto il comando **[!UICONTROL Save As]** nel menu.

1. Fai clic su **[!UICONTROL Save Export File]**.

   Viene visualizzata una finestra del modello di esportazione.

   Tutte le informazioni di Adobe Target vengono compilate automaticamente. Genera l’elenco dei parametri in base a ciò che inserisci nell’esportazione del segmento. Al termine, Data Workbench invierà i dati al server Adobe Target.

   **Nota:** il file Modello deve essere configurato da  [!UICONTROL Profile Architect]. È necessario immettere i valori [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] e [!UICONTROL Mbox Name]. Se disponi di più siti, compila più modelli e salvalo sul server. I modelli di Profile Manager si trovano in `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Specifica il parametro di query [!UICONTROL mboxPC] .

   Se il nome dell’attributo Data Workbench è diverso da [!UICONTROL mboxPC], è necessario modificare il parametro di query appropriato e rinominarlo in _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Quando salvi il file di esportazione nel server, l’esportazione avrà inizio. Una volta completata, l&#39;applicazione [!UICONTROL TnTSend.exe] avvierà e inizierà a inviare dati all&#39;account Target.

## Configurazione di Data Workbench per Target

Completa le seguenti attività in Adobe Target:

Data Workbench sta passando i profili utente ad Adobe Target. Per configurare l’esportazione in Target, devi configurare e abilitare la relativa API e fornire i parametri **[!UICONTROL clientname]** e **[!UICONTROL domain postfix]** per il file di configurazione dell’esportazione (`export.cfg`).

È stata aggiunta una nuova opzione booleana denominata **[!UICONTROL Oneshot]** ai file di esportazione dei segmenti. Questa opzione è inclusa nel file modello distribuito con il nuovo profilo. Se [!UICONTROL Oneshot] è impostato su _true_, il file `.export` verrà rinominato in `.export.done-TIMESTAMP` al termine dell&#39;esportazione, assicurando che il segmento non venga mai esportato più di una volta. Questo è importante quando si esporta in Adobe Target.

**Nota:** una chiamata da Data Workbench ad Adobe Target conta come  [!UICONTROL mbox] chiamata, che richiede una chiamata per ogni profilo inviato. Di conseguenza, se tra le due soluzioni sono necessarie più chiamate, i costi aumentano.

Una configurazione incompleta genera il seguente messaggio di errore nel registro:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configurazione di Adobe Target per Data Workbench

All’interno di Adobe Target, non è necessaria alcuna configurazione speciale per consentire al cliente di inviare i dati del profilo. Le informazioni di profilo per un utente vengono in genere trasmesse nella normale richiesta [!UICONTROL mbox] e i server renderanno disponibili i parametri di profilo per una configurazione di campagna mirata come funzionalità standard senza alcuna configurazione aggiuntiva.

Adobe Target ha integrato l’integrazione della Data Workbench, che può essere abilitata dalla pagina Dettagli del client super utente . L’abilitazione dell’opzione consente di far superficie ai segmenti condivisi da Data Workbench in Adobe Target per renderli disponibili per il targeting.

## Impostare il reporting del registro HTTP in ExportIntegration.exe

Riduci i rapporti lunghi a [!UICONTROL HTTP.log] quando utilizzi [!UICONTROL ExportIntegration.exe] per esportare file di integrazione Adobe Target.

Un nuovo file di configurazione [!UICONTROL httpLoggingEI.cfg] (che si trova in `server\Admin\Export\httpLoggingEI.cfg`) consente di ridurre la registrazione dettagliata nel file [!UICONTROL HTTP.log] per quando si esportano dati utilizzando [!UICONTROL ExportIntegration.exe]. Questo consente di interrompere la registrazione dettagliata di richieste/risposte.

La registrazione dettagliata è già acquisita nei file [!UICONTROL TnTSend.log].

__ Truesets registrazione dettagliata e  __ Falsestops registrazione dettagliata su  [!UICONTROL HTTP.log] file.

Nell’impostazione False, al file [!UICONTROL HTTP.log] verrà inviato solo un messaggio di avviso (contenuto Info non inviato).
