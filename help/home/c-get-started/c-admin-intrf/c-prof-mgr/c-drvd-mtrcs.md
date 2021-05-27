---
description: Puoi definire nuove metriche (o metriche derivate) e modificare le definizioni di metriche esistenti utilizzando l’Editor metriche.
title: Operazioni con metriche derivate
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Operazioni con metriche derivate{#work-with-derived-metrics}

Puoi definire nuove metriche (o metriche derivate) e modificare le definizioni di metriche esistenti utilizzando l’Editor metriche.

Per ulteriori informazioni sulle metriche rispetto a quelle fornite in questa sezione e in [Sintassi della lingua della query](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f), consulta la *Guida alla metrica, ai Dimension e ai filtri*.

## Creare una metrica derivata {#section-d57b98bf0a9940daba4920ff7efc808d}

Utilizza un [!DNL Metric Editor] per definire una nuova metrica per nome, formula e formato, che viene salvata nella cartella User\*profile_name*\Metrics per un utilizzo successivo.

1. Apri un nuovo [!DNL Metric Editor] utilizzando l&#39;opzione di menu **[!UICONTROL Admin]** > **[!UICONTROL Profile]** oppure facendo clic con il pulsante destro del mouse sulla colonna **[!UICONTROL User]** relativa alla cartella in cui desideri creare la metrica e scegliendo **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Viene visualizzato un [!DNL Metric Editor].

1. Nel parametro Nome , digita un nome per la nuova metrica.

   Gli spazi ( ) sono consentiti quando i caratteri di sottolineatura (_) non lo sono. Inoltre, non è possibile utilizzare i seguenti simboli:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Nel parametro Formula digitare un&#39;espressione per la nuova metrica. I filtri devono essere definiti tra parentesi [ ] nell&#39;espressione.

   Per ulteriori regole di sintassi delle espressioni metriche, consulta [Sintassi per le espressioni metriche](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   La tabella seguente fornisce espressioni di esempio per metriche estese.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Nome della metrica estesa </th> 
      <th colname="col2" class="entry"> Espressione </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Percentuale prime sessioni </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessioni [Session_Number="1"]/Sessions</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Prime sessioni di conversione </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversione [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Valore medio per visitatore </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Valore/Visitatori</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >Quando immetti un’espressione appropriata, la riga di anteprima visualizza il valore della nuova metrica. Se l’espressione contiene un errore, nella riga di anteprima viene visualizzato un messaggio di errore.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (New)]** e fai clic su **[!UICONTROL Save]**.

   Quando salvi la metrica, nel computer viene creato un file che rappresenta la nuova metrica nella cartella Data Workbench Installation directory \User\*profile name*\Metrics .

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Ora puoi utilizzare la nuova metrica in tutto il profilo corrente selezionandola come faresti con una metrica incorporata. Per modificare l&#39;ordine in cui le metriche vengono visualizzate nel menu metriche, consulta [Personalizzazione dei menu utilizzando i file Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

Se desideri che tutti gli utenti del profilo utilizzino la metrica creata, devi pubblicarla nel profilo di lavoro utilizzando [!DNL Profile Manager]. Consulta [Pubblicazione di file nel profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Modificare metriche derivate {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Nella colonna [!DNL Profile Manager] o [!DNL Metrics Manager], nella colonna *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta per il file della metrica che si desidera modificare, quindi fare clic su **[!UICONTROL Make Local]**.
1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file della metrica nella colonna [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Puoi anche aprire un [!DNL Metric Editor] facendo clic con il pulsante destro del mouse su un’area correlata alle metriche all’interno di una visualizzazione per visualizzare il menu delle metriche. Per ulteriori informazioni, consulta [Uso dei menu delle metriche e dei Dimension](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. In [!DNL Metric Editor], modifica e salva la definizione della metrica secondo necessità utilizzando i passaggi 2-4 in [Creazione di nuove metriche derivate](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   Se desideri che tutti gli utenti del profilo utilizzino la metrica modificata, devi pubblicarla nel profilo di lavoro utilizzando [!DNL Profile Manager]. Consulta [Pubblicazione di file nel profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
