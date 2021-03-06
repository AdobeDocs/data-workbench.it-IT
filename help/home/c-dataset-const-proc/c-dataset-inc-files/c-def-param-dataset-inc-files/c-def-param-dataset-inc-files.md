---
description: Durante la configurazione del set di dati, puoi definire variabili, definite parametri, che rappresentano valori significativi.
title: Definizione dei parametri di Dataset Include Files (File inclusi nel set di dati)
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Definizione dei parametri di Dataset Include Files (File inclusi nel set di dati) {#defining-parameters-in-dataset-include-files}

Durante la configurazione del set di dati, puoi definire variabili, definite parametri, che rappresentano valori significativi.

Per assegnare un valore a un parametro (cioè per definire il parametro), aggiungi il nome e il valore del parametro al vettore Parameters in un file di elaborazione del registro o [!DNL Transformation Dataset Include]. Dopo aver definito i parametri, puoi farvi riferimento nei file di configurazione del profilo del set di dati. La definizione e il riferimento a tali parametri sono denominati sostituzione di parametri. L’utilizzo della sostituzione dei parametri durante la configurazione del set di dati consente di creare una posizione centralizzata per le definizioni dei parametri. Quando devi aggiornare un parametro a cui si fa riferimento più volte o in più file, devi apportare la modifica una sola volta.

>[!NOTE]
>
>In questa guida, il termine parametro è stato utilizzato per fare riferimento al nome di qualsiasi impostazione in un file di configurazione (come Condizione voce di registro, Rielaborazione o Trasformazioni). Tuttavia, come utilizzato in questa sezione, il parametro si riferisce specificamente a un membro del vettore Parameters in un set di dati include file e non al nome di un&#39;impostazione in un file di configurazione.

Quando definisci un parametro, considera quanto segue:

* Un parametro deve essere definito esattamente una volta. Pertanto, non puoi definire la stessa variabile in più file di set di dati che includono.
* Qualsiasi parametro definito è locale per l&#39;elaborazione del registro o per le fasi di trasformazione, ma è globale in più file di configurazione del set di dati per quella fase. Ad esempio, se definisci un parametro in un file [!DNL Transformation Dataset Include], il parametro viene definito per l’intera fase di trasformazione e puoi farvi riferimento nel file [!DNL Transformation.cfg] e in tutti gli altri file [!DNL Transformation Dataset Include] per i profili ereditati. Il parametro non viene definito per l&#39;elaborazione dei log; pertanto, qualsiasi riferimento al parametro nel file [!DNL Log Processing.cfg] o in un file [!DNL Log Processing Dataset Include] genererebbe un errore di elaborazione.

**Per definire un parametro**

È possibile definire parametri stringa, numerici e vettoriali nei file [!DNL Log Processing] e [!DNL Transformation Include].

1. Nella finestra di Data Workbench per il file [!DNL Log Processing] o [!DNL Transformation Dataset Include], fai clic con il pulsante destro del mouse su **[!UICONTROL Parameters]**, quindi fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Selezionare **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** o **[!UICONTROL Vector Parameter]** e completare i parametri Nome e Valore come descritto nelle sezioni seguenti.

1. Per salvare il file di inclusione del set di dati in cui hai definito il parametro, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include.[!DNL Profile Manager]

>[!NOTE]
>
>Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

**Per fare riferimento a un parametro**

* Quando si fa riferimento a un parametro definito in un altro file di configurazione del set di dati, è necessario digitare il nome corrispondente come [!DNL $(parameter name)].

Le sezioni seguenti descrivono i tipi di parametri che è possibile definire.

* [Parametri stringa e numerici](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Parametri vettoriali](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
