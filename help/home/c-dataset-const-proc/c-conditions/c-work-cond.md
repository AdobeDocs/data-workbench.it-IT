---
description: Informazioni sull’aggiunta, la rimozione o la copia di una condizione.
title: Utilizzo delle condizioni
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Utilizzo delle condizioni{#working-with-conditions}

{{eol}}

Informazioni sull’aggiunta, la rimozione o la copia di una condizione.

* [Per aggiungere una condizione a un file di configurazione del set di dati](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Per rimuovere una condizione da un file di configurazione del set di dati](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Per copiare una condizione](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Per aggiungere una condizione a un file di configurazione del set di dati {#section-3e2a34db047b462585502f69722f6511}

1. Quando lavori nel tuo profilo di set di dati, utilizza il [!DNL Profile Manager] per aprire il file di configurazione del set di dati da modificare.

   * Per aprire [!DNL Log Processing.cfg] file, vedi [Modifica del file di configurazione dell’elaborazione del registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Per aprire [!DNL Transformation.cfg] file, vedi [Modifica del file di configurazione delle trasformazioni](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Per aprire un [!DNL Dataset Include] file, vedi [Dataset Include Files (File inclusi nel set di dati)](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. All’interno del file di configurazione del set di dati, individua il parametro Condizione voce di registro o Condizione che desideri definire.
1. Fai clic con il pulsante destro del mouse sul parametro e fai clic su **[!UICONTROL Add new]**. Scegli uno dei seguenti tipi di condizioni:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Modifica i parametri della condizione come desiderato. Per la descrizione dei parametri di ciascuna condizione, vedere la sezione appropriata della presente appendice.
1. Per salvare le modifiche, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, nella [!DNL Profile Manager,] fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, dove nome profilo è il nome del profilo di set di dati o del profilo ereditato a cui appartiene il file.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

## Per rimuovere una condizione da un file di configurazione del set di dati {#section-677270f93f1648c3a268ca2aea7d4540}

1. Fare clic con il pulsante destro del mouse sul nome della condizione o sul numero corrispondente alla condizione da rimuovere.
1. Fai clic su **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, dove numero è il numero corrispondente alla condizione che si desidera rimuovere.

## Per copiare una condizione {#section-00617bcf2c274f428686b2ec7f2d1db8}

È possibile copiare una condizione da una posizione a un’altra posizione nello stesso file oppure è possibile copiare una condizione da un file di configurazione del set di dati a un altro.

1. Fare clic con il pulsante destro del mouse sul nome della condizione o sul numero corrispondente alla condizione da copiare, quindi fare clic su **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sul nome o sul numero della condizione in cui si desidera inserire la condizione copiata e fare clic su **[!UICONTROL Paste]**.
