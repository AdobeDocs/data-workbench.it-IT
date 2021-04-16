---
description: La funzionalità di trasformazione viene eseguita su un computer FSU di Insight Server per abilitare l’esportazione dei dati di origine dei registri da utilizzare in altre applicazioni.
title: Configurazione di Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configurazione di Transform{#configuring-transform}

La funzionalità di trasformazione viene eseguita su un computer FSU di Insight Server per abilitare l’esportazione dei dati di origine dei registri da utilizzare in altre applicazioni.

[!DNL Transform] può leggere  [!DNL .vsl] file, file di registro, file XML e dati ODBC ed esportare i dati come  [!DNL .vsl] file, file di testo o file di testo delimitati che possono essere utilizzati da routine di caricamento del data warehouse, agenzie di controllo o altri oggetti. L’estrazione e la trasformazione dei dati possono essere eseguite in modo continuo o su altra base pianificata. Ogni FSU [!DNL Insight Server] che fornisce l&#39;output dei dati dell&#39;evento alterati deve essere eseguita [!DNL Transform].

>[!NOTE]
>
>In genere, [!DNL Transform] è installato su una FSU [!DNL Insight Server]. Tuttavia, l’implementazione potrebbe richiedere l’installazione su una DPU [!DNL Insight Server]. Per ulteriori informazioni, contatta l’Adobe .

Per informazioni sui requisiti di sistema per l&#39;installazione, la configurazione e il funzionamento [!DNL Transform], vedere il documento *Requisiti minimi di sistema* .

Adobe distribuisce la funzionalità [!DNL Transform] come profilo all&#39;interno del file [!DNL .zip] per il pacchetto di versione [!DNL Insight Server]. Il profilo [!DNL Transform] è un profilo interno che fornisce funzionalità aggiuntive a [!DNL Insight Server]. Come per tutti gli altri profili interni forniti dall’Adobe, il profilo non deve essere modificato. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati.

Il profilo è costituito dai seguenti file:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un file di set di dati di elaborazione del registro include

Tutti questi file si trovano nella cartella [!DNL Dataset] del profilo.

**Per installare il  [!DNL Transform] profilo su[!DNL Insight Server]**

>[!NOTE]
>
>Le istruzioni di installazione seguenti presuppongono che sia stata installata [!DNL Insight] e che sia stata stabilita una connessione tra [!DNL Insight] e [!DNL Insight Server] in cui si sta installando [!DNL Transform]. Se non lo hai fatto, consulta la * [!DNL Insight] Guida utente*.

1. Apri il file [!DNL .zip] per il pacchetto di versione [!DNL Insight Server] e apri la cartella [!DNL Profiles] all’interno del file [!DNL .zip].
1. Copia la cartella [!DNL Transform] nella cartella [!DNL Profiles] nella directory di installazione [!DNL Insight Server]. Vuoi finire con una cartella [!DNL ...\Profiles\Transform] sul tuo [!DNL Insight Server] come mostrato nell&#39;esempio seguente.

   ![Informazioni sul passaggio](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Se hai seguito tutti i passaggi per l’installazione di [!DNL Insight Server] (consulta [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), potresti avere già una cartella [!DNL Transform] nella directory Profiles .

1. Utilizza i passaggi seguenti per aggiornare il file [!DNL profile.cfg] per il profilo con cui desideri utilizzare [!DNL Transform]. Il set di dati rielabora una volta completati questi passaggi.

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra [!DNL profile.cfg].

   1. Nella finestra [!DNL profile.cfg]fare clic con il pulsante destro del mouse su **[!UICONTROL Directories]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell’elenco di directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell’ultima directory nell’elenco e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL Transform]
   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL profile.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe (incluso il profilo), in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.
