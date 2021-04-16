---
description: Informazioni sull’aggiunta, la rimozione o la copia di una condizione.
title: Utilizzo delle condizioni
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Utilizzo delle condizioni{#working-with-conditions}

Informazioni sull’aggiunta, la rimozione o la copia di una condizione.

* [Per aggiungere una condizione a un file di configurazione del set di dati](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Per rimuovere una condizione da un file di configurazione del set di dati](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Per copiare una condizione](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Per aggiungere una condizione a un file di configurazione del set di dati {#section-3e2a34db047b462585502f69722f6511}

1. Quando lavori nel tuo profilo di set di dati, utilizza [!DNL Profile Manager] per aprire il file di configurazione del set di dati da modificare.

   * Per aprire il file [!DNL Log Processing.cfg], vedere [Modifica del file di configurazione dell&#39;elaborazione del registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Per aprire il file [!DNL Transformation.cfg], consulta [Modifica del file di configurazione delle trasformazioni](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Per aprire un file [!DNL Dataset Include], consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati).

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

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, dove nome profilo è il nome del profilo di set di dati o del profilo ereditato a cui appartiene il file.[!DNL Profile Manager,]

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

## Per rimuovere una condizione da un file di configurazione del set di dati {#section-677270f93f1648c3a268ca2aea7d4540}

1. Fare clic con il pulsante destro del mouse sul nome della condizione o sul numero corrispondente alla condizione da rimuovere.
1. Fare clic su **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, dove il numero corrisponde alla condizione da rimuovere.

## Per copiare una condizione {#section-00617bcf2c274f428686b2ec7f2d1db8}

È possibile copiare una condizione da una posizione a un’altra posizione nello stesso file oppure è possibile copiare una condizione da un file di configurazione del set di dati a un altro.

1. Fare clic con il pulsante destro del mouse sul nome della condizione o sul numero corrispondente alla condizione che si desidera copiare, quindi fare clic su **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sul nome o sul numero della condizione sotto la quale si desidera inserire la condizione copiata e fare clic su **[!UICONTROL Paste]**.
