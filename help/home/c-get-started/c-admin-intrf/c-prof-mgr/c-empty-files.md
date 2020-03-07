---
description: Se non disponete dell'autorizzazione per eliminare i file da un profilo o non desiderate eliminarli definitivamente, potete utilizzare file vuoti (a zero byte) per nascondere i file.
solution: Analytics
title: Nascondere un file svuotandolo (zero byte)
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nascondere un file svuotandolo (zero byte){#hide-a-file-by-emptying-it-zero-byte}

Se non disponete dell&#39;autorizzazione per eliminare i file da un profilo o non desiderate eliminarli definitivamente, potete utilizzare file vuoti (a zero byte) per nascondere i file.

In [!DNL Profile Manager], un trattino (-), invece di un segno di spunta, in una colonna identifica un file a byte zero.

![](assets/vis_ProfMgr_Zero-byte.png)

A differenza degli altri metodi per nascondere i file (ad esempio [!DNL order.txt], il parametro Show e il parametro Hidden), Workbench dati considera i file con zero byte come inesistenti. Ad esempio, se si azzera una dimensione utilizzata in una visualizzazione o una definizione di metrica, Workbench dati genera un errore per tale visualizzazione o metrica, rispettivamente.

Questa funzionalità è utile per diversi motivi, ad esempio per eseguire le operazioni seguenti:

* **Rendere un file inutilizzabile** in Workbench dati senza richiedere le autorizzazioni di profilo necessarie per eliminare il file.
* **Sposta una metrica, una dimensione o un filtro** in un&#39;altra posizione senza richiedere le autorizzazioni di profilo necessarie per eliminare il file dalla posizione originale.
* **Nascondere le voci di menu.** Ad esempio, il [!DNL Base] profilo ha una [!DNL Metric Legend] definizione nel [!DNL Metric.vw] file. Supponiamo che la società abbia creato tre legende metriche da visualizzare in un sottomenu Aggiungi legenda > Metrica. È possibile azzerare il file del [!DNL Base] profilo [!DNL Metric.vw] in modo da visualizzare solo il nuovo sottomenu e tre nuove legende metriche.

**Per nascondere un file**

1. In [!DNL Profile Manager], aprite le cartelle e sottocartelle necessarie per individuare il file a zero.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file, quindi fare clic **[!UICONTROL Make Local]**.
1. Aprite il file locale ed eliminatene il contenuto.
1. Salvate e chiudete il file.

