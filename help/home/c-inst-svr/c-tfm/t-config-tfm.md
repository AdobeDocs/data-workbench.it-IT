---
description: La funzionalità di trasformazione viene eseguita su un computer FSU di Insight Server per abilitare l’esportazione dei dati di origine dei registri da utilizzare in altre applicazioni.
title: Configurazione di Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configurazione di Transform{#configuring-transform}

{{eol}}

La funzionalità di trasformazione viene eseguita su un computer FSU di Insight Server per abilitare l’esportazione dei dati di origine dei registri da utilizzare in altre applicazioni.

[!DNL Transform] può leggere [!DNL .vsl] file, file di registro, file XML e dati ODBC ed esporta i dati come [!DNL .vsl] file, file di testo o file di testo delimitati che possono essere utilizzati dalle routine di caricamento del data warehouse, dalle agenzie di controllo o da altre destinazioni. L’estrazione e la trasformazione dei dati possono essere eseguite in modo continuo o su altra base pianificata. Ogni [!DNL Insight Server] FSU che fornisce l&#39;output dei dati dell&#39;evento alterati deve essere eseguito [!DNL Transform].

>[!NOTE]
>
>In genere, [!DNL Transform] è installato in un [!DNL Insight Server] FSU. Tuttavia, l’implementazione potrebbe richiedere l’installazione di un’ [!DNL Insight Server] DPU Per ulteriori informazioni, contatta l’Adobe .

Per informazioni sui requisiti di sistema per l&#39;installazione, la configurazione e il funzionamento [!DNL Transform], vedi *Requisiti minimi di sistema* documento.

Adobe distribuisce il [!DNL Transform] come profilo all’interno di [!DNL .zip] per [!DNL Insight Server] pacchetto di rilascio. La [!DNL Transform] è un profilo interno che fornisce funzionalità aggiuntive a [!DNL Insight Server]. Come per tutti gli altri profili interni forniti dall’Adobe, il profilo non deve essere modificato. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati.

Il profilo è costituito dai seguenti file:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un file di set di dati di elaborazione del registro include

Tutti questi file si trovano nella [!DNL Dataset] per il profilo.

**Per installare [!DNL Transform] profilo su[!DNL Insight Server]**

>[!NOTE]
>
>Le seguenti istruzioni di installazione presuppongono l&#39;installazione di [!DNL Insight] e stabilisce un collegamento tra [!DNL Insight] e [!DNL Insight Server] su cui stai installando [!DNL Transform]. Se non lo hai fatto, vedi il * [!DNL Insight] Guida utente*.

1. Apri [!DNL .zip] per [!DNL Insight Server] e apri il pacchetto [!DNL Profiles] cartella [!DNL .zip] file.
1. Copia il [!DNL Transform] nella cartella [!DNL Profiles] nella cartella [!DNL Insight Server] directory di installazione. Vuoi finire con un [!DNL ...\Profiles\Transform] cartella [!DNL Insight Server] come illustrato nell’esempio seguente.

   ![Informazioni sul passaggio](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Se hai seguito tutti i passaggi per l&#39;installazione [!DNL Insight Server] (vedi [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), puoi già avere un [!DNL Transform] nella directory Profiles .

1. Utilizza i seguenti passaggi per aggiornare il [!DNL profile.cfg] file del profilo con cui desideri utilizzare [!DNL Transform]. Il set di dati rielabora una volta completati questi passaggi.

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL profile.cfg] viene visualizzata la finestra .

   1. In [!DNL profile.cfg]finestra, clic con il pulsante destro del mouse **[!UICONTROL Directories]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell’elenco delle directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell’ultima directory dell’elenco e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL Transform]
   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe (incluso il profilo), in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.
