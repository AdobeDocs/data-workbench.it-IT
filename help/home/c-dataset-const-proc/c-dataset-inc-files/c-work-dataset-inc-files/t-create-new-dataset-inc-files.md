---
description: Passaggi per creare un nuovo set di dati includono file .
title: Creazione di nuovi Dataset Include Files (File inclusi nel set di dati)
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Creazione di nuovi Dataset Include Files (File inclusi nel set di dati){#creating-new-dataset-include-files}

{{eol}}

Passaggi per creare un nuovo set di dati includono file .

È necessario creare un nuovo set di dati che includa un file per eseguire una delle seguenti attività di configurazione del set di dati:

* Specifica dei nuovi campi di dati da passare dall’elaborazione del registro alla trasformazione.
* Definizione di trasformazioni che eseguono una delle seguenti operazioni:

   * Aggiorna i campi di registro esistenti.
   * Produrre nuovi campi da passare dall’elaborazione del registro alla trasformazione o utilizzati per definire dimensioni estese.

      Per informazioni sui tipi di trasformazione disponibili, consulta [Trasformazioni dei dati](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Se definisci le trasformazioni in un nuovo set di dati include file , accertati di tenere presente l’ordine degli input e degli output. Per informazioni sull&#39;ordinamento delle trasformazioni, vedi [Convenzioni per la costruzione di trasformazioni](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Creazione di dimensioni estese. Per informazioni sui tipi di dimensioni disponibili, consulta [Dimension estesi](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Quando lavori nel tuo profilo di set di dati, apri la [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzare il set di dati esistente include i file .

   * Per visualizzare il [!DNL Log Processing Dataset Include] file, fai clic su **[!UICONTROL Log Processing]**.

   * Per visualizzare il [!DNL Transformation Dataset Include] file, fai clic su **[!UICONTROL Transformation]**.

1. Crea un nuovo [!DNL Log Processing] o [!DNL Transformation Dataset Include] eseguendo uno dei seguenti passaggi:

   * In [!DNL User] per la directory Elaborazione log, fai clic su **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Un file denominato [!DNL New Log Processing.cfg] appare nella directory.

   * In [!DNL User] per la directory Transformation, fai clic su **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Un file denominato [!DNL New Transformation.cfg] appare nella directory.

1. Rinomina il nuovo file facendo clic con il pulsante destro del mouse sul relativo segno di spunta nel [!DNL User] e digita il nuovo nome nel parametro File .

   ![Informazioni sul passaggio](assets/vis_ProfileManager_RenameFile.png)

1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file rinominato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra di configurazione.
1. Modifica i parametri nel file di configurazione come appropriato. Vedi [Elaborazione del registro Dataset Include Files (File inclusi)](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) o [File inclusi set di dati di trasformazione](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) per la descrizione dei parametri disponibili.
1. Per salvare le modifiche, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. Per rendere effettive le modifiche apportate localmente, nella [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo di set di dati o del profilo ereditato a cui appartiene il file di set di dati include . La rielaborazione o la riconversione dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

Per modificare un file di inclusione di un set di dati creato, vedi [Modifica di Dataset Include Files (File) esistenti](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
