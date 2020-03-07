---
description: Durante la configurazione del set di dati, puoi definire variabili, denominate parametri, per rappresentare valori significativi.
solution: Analytics
title: Definizione dei parametri per l'inclusione di file nei set di dati
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definizione dei parametri per l&#39;inclusione di file nei set di dati{#defining-parameters-in-dataset-include-files}

Durante la configurazione del set di dati, puoi definire variabili, denominate parametri, per rappresentare valori significativi.

Per assegnare un valore a un parametro (ovvero per definire il parametro), è necessario aggiungere il nome e il valore del parametro al vettore Parameters in un’elaborazione di registro o in un [!DNL Transformation Dataset Include] file. Dopo aver definito i parametri, puoi farvi riferimento nei file di configurazione del profilo del dataset. La definizione e il riferimento a tali parametri sono denominati sostituzione dei parametri. L&#39;utilizzo della sostituzione dei parametri durante la configurazione del dataset consente di creare una posizione centralizzata per le definizioni dei parametri. Per aggiornare un parametro a cui viene fatto riferimento più volte o in più file, è necessario apportare la modifica una sola volta.

>[!NOTE]
>
>In questa guida, il termine parametro è stato utilizzato per fare riferimento al nome di qualsiasi impostazione in un file di configurazione (ad esempio Condizione voce di registro, Rielabora o Trasformazioni). Tuttavia, come utilizzato in questa sezione, il parametro si riferisce specificamente a un membro del vettore Parameters in un dataset include file e non al nome di un&#39;impostazione in un file di configurazione.

Nella definizione di un parametro è consigliabile tenere in considerazione i seguenti punti:

* Un parametro deve essere definito esattamente una volta. Pertanto, non è possibile definire la stessa variabile in più set di dati includere file.
* Qualsiasi parametro definito è locale per l&#39;elaborazione del registro o per le fasi di trasformazione, ma è globale tra più file di configurazione del set di dati per quella fase. Ad esempio, se definite un parametro in un [!DNL Transformation Dataset Include] file, il parametro viene definito per l&#39;intera fase di trasformazione e potete farvi riferimento nel [!DNL Transformation.cfg] file e in tutti gli altri [!DNL Transformation Dataset Include] file per i profili ereditati. Il parametro non è definito per l&#39;elaborazione del registro; pertanto, eventuali riferimenti al parametro nel [!DNL Log Processing.cfg] file o in un [!DNL Log Processing Dataset Include] file genererebbero un errore di elaborazione.

**Per definire un parametro**

È possibile definire parametri stringa, numerici e vettoriali in [!DNL Log Processing] e [!DNL Transformation Include] file.

1. Nella finestra workbench dati per il [!DNL Log Processing] file o il [!DNL Transformation Dataset Include] file, fare clic con il pulsante destro del mouse **[!UICONTROL Parameters]**, quindi scegliere **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Selezionate **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** o **[!UICONTROL Vector Parameter]**, e completate i parametri Nome e Valore come descritto nelle sezioni seguenti.

1. Per salvare il set di dati includete il file in cui avete definito il parametro, fate clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fate clic **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

>[!NOTE]
>
>Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

**Per fare riferimento a un parametro**

* Quando si fa riferimento a un parametro definito in un altro file di configurazione del dataset, è necessario digitare il nome come [!DNL $(parameter name)].

Le sezioni seguenti descrivono i tipi di parametri che è possibile definire.

* [Parametri stringa e numerici](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Parametri vettoriali](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

