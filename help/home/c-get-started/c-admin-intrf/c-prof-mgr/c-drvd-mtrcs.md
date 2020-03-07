---
description: Puoi definire nuove metriche (o metriche derivate) e modificare le definizioni delle metriche esistenti utilizzando l'Editor metriche.
solution: Analytics
title: Operazioni con metriche derivate
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Operazioni con metriche derivate{#work-with-derived-metrics}

Puoi definire nuove metriche (o metriche derivate) e modificare le definizioni delle metriche esistenti utilizzando l&#39;Editor metriche.

Per ulteriori informazioni sulle metriche rispetto a quelle fornite in questa sezione e in Sintassi [della lingua](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)query, vedere la Guida *alla* metrica, alle dimensioni e ai filtri.

## Creare una metrica derivata {#section-d57b98bf0a9940daba4920ff7efc808d}

Potete utilizzare una metrica [!DNL Metric Editor] per definire nome, formula e formato, che verrà salvata nella cartella Utente\*profile_name*\Metrics per un utilizzo successivo.

1. Apri una nuova [!DNL Metric Editor] utilizzando l’opzione di menu **[!UICONTROL Admin]** > **[!UICONTROL Profile]** oppure facendo clic con il pulsante destro del mouse sulla **[!UICONTROL User]** colonna della cartella in cui vuoi creare la metrica e scegliendo **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Viene [!DNL Metric Editor] visualizzato un messaggio.

1. Nel parametro Name digitare un nome per la nuova metrica.

   Si noti che gli spazi ( ) sono consentiti mentre i caratteri di sottolineatura (_) non lo sono. Inoltre, non è possibile utilizzare i seguenti simboli:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Nel parametro Formula, digita un&#39;espressione per la nuova metrica. I filtri devono essere definiti tra parentesi [ ] nell&#39;espressione.

   Per ulteriori regole di sintassi delle espressioni metriche, consultate [Sintassi delle espressioni](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)metriche.

   La tabella seguente fornisce espressioni di esempio per le metriche estese.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Nome metrica estesa </th> 
      <th colname="col2" class="entry"> Espressione </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Percentuale prime sessioni </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessioni [Session_Number="1"]/Sessioni</span> </p> </td> 
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
   >Quando viene immessa un&#39;espressione appropriata, la riga di anteprima mostra il valore della nuova metrica. Se si verifica un errore nell&#39;espressione, la riga di anteprima visualizza un messaggio di errore.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (New)]** e fare clic **[!UICONTROL Save]**.

   Quando si salva la metrica, nel computer viene creato un file che rappresenta la nuova metrica nella directory di installazione di Workbench dati \User\*profile*\Metrics folder.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Ora puoi usare la nuova metrica in tutto il profilo corrente selezionandola come faresti con qualsiasi metrica incorporata. Per modificare l&#39;ordine di visualizzazione delle metriche nel menu delle metriche, vedere [Personalizzazione dei menu tramite i file](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

Se desiderate che tutti gli utenti del profilo utilizzino la metrica creata, dovete pubblicarla nel profilo di lavoro utilizzando il [!DNL Profile Manager]. Consultate [Pubblicazione dei file nel profilo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)di lavoro.

## Modificare metriche derivate {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Nella colonna [!DNL Profile Manager] o [!DNL Metrics Manager], nella colonna del nome *del* profilo, fare clic con il pulsante destro del mouse sul segno di spunta per il file della metrica che si desidera modificare, quindi fare clic su **[!UICONTROL Make Local]**.
1. Fare clic con il pulsante destro del mouse sul segno di spunta per il file della metrica nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Puoi anche aprire un oggetto facendo clic con il pulsante destro del mouse su un’area correlata alle metriche all’interno di una visualizzazione per visualizzare il menu delle metriche. [!DNL Metric Editor] Per ulteriori informazioni, vedere [Uso dei menu](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)Metrica e Dimensione.

1. In [!DNL Metric Editor], modifica e salva la definizione della metrica secondo necessità utilizzando i passaggi da 2 a 4 in [Creazione di nuove metriche](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)derivate.

   Se desiderate che tutti gli utenti del profilo utilizzino la metrica modificata, dovete pubblicarla nel profilo di lavoro utilizzando il [!DNL Profile Manager]. Consultate [Pubblicazione dei file nel profilo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)di lavoro.

