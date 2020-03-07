---
description: Informazioni sull’aggiunta, la rimozione o la copia di una condizione.
solution: Analytics
title: Utilizzo Delle Condizioni
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Utilizzo Delle Condizioni{#working-with-conditions}

Informazioni sull’aggiunta, la rimozione o la copia di una condizione.

* [Aggiunta di una condizione a un file di configurazione del set di dati](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Rimozione di una condizione da un file di configurazione del set di dati](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Per copiare una condizione](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Aggiunta di una condizione a un file di configurazione del set di dati {#section-3e2a34db047b462585502f69722f6511}

1. Quando lavori nel profilo del set di dati, usa [!DNL Profile Manager] per aprire il file di configurazione del set di dati da modificare.

   * Per aprire il [!DNL Log Processing.cfg] file, vedere [Modifica del file](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)di configurazione dell&#39;elaborazione del registro.

   * Per aprire il [!DNL Transformation.cfg] file, vedere [Modifica del file](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)di configurazione delle trasformazioni.

   * Per aprire un [!DNL Dataset Include] file, vedere [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. All&#39;interno del file di configurazione del dataset, individuare il parametro Condizione voce di registro o Condizione che si desidera definire.
1. Fate clic con il pulsante destro del mouse sul parametro e fate clic **[!UICONTROL Add new]**. Scegliete uno dei seguenti tipi di condizione:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Modificate i parametri della condizione come desiderato. Per una descrizione dei parametri di ciascuna condizione, vedere la sezione appropriata della presente appendice.
1. Per salvare le modifiche, fate clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fate clic su **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, fare clic con il pulsante [!DNL Profile Manager,] destro del mouse sul segno di spunta del file nella [!DNL User] colonna, quindi fare clic su **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato cui appartiene il file.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

## Rimozione di una condizione da un file di configurazione del set di dati {#section-677270f93f1648c3a268ca2aea7d4540}

1. Fare clic con il pulsante destro del mouse sul nome della condizione o sul numero corrispondente alla condizione da rimuovere.
1. Fare clic su **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, dove il numero corrisponde alla condizione da rimuovere.

## Per copiare una condizione {#section-00617bcf2c274f428686b2ec7f2d1db8}

È possibile copiare una condizione da una posizione a un&#39;altra nello stesso file, oppure è possibile copiare una condizione da un file di configurazione del set di dati a un altro.

1. Fare clic con il pulsante destro del mouse sul nome della condizione o sul numero corrispondente alla condizione che si desidera copiare, quindi fare clic **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sul nome o sul numero della condizione sotto la quale si desidera inserire la condizione copiata e fare clic **[!UICONTROL Paste]**.

