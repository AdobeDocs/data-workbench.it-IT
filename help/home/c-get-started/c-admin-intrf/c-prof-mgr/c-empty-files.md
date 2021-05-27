---
description: Se non si dispone dell'autorizzazione per eliminare i file da un profilo o non si desidera eliminare un file in modo permanente, è possibile utilizzare file vuoti (zero byte) per nascondere i file.
title: Nascondere un file svuotandone il contenuto (zero byte)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Nascondere un file svuotandone il contenuto (zero byte){#hide-a-file-by-emptying-it-zero-byte}

Se non si dispone dell&#39;autorizzazione per eliminare i file da un profilo o non si desidera eliminare un file in modo permanente, è possibile utilizzare file vuoti (zero byte) per nascondere i file.

In [!DNL Profile Manager], un trattino (-), invece di un segno di spunta, in una colonna identifica un file a byte zero.

![](assets/vis_ProfMgr_Zero-byte.png)

A differenza degli altri metodi per nascondere i file (ad esempio [!DNL order.txt], il parametro Show e il parametro Hidden), Data Workbench considera i file privi di valore come inesistenti. Ad esempio, se scarichi zero una dimensione utilizzata in una visualizzazione o una definizione di metrica, Data Workbench genera un errore per tale visualizzazione o metrica, rispettivamente.

Questa funzionalità è utile per diversi motivi, ad esempio per eseguire le seguenti operazioni:

* **Rendi un file** inutilizzabile la Data Workbench senza richiedere le autorizzazioni di profilo necessarie per eliminare il file.
* **Sposta una metrica, una dimensione o un** filtro in un’altra posizione senza richiedere le autorizzazioni di profilo necessarie per eliminare il file dalla posizione originale.
* **Nascondi voci di menu.** Ad esempio, il  [!DNL Base] profilo ha una  [!DNL Metric Legend] definizione nel  [!DNL Metric.vw] file . Supponiamo che la tua azienda abbia creato tre legende metriche da visualizzare in un sottomenu Aggiungi legenda > Metrica . È possibile aggiungere un byte zero al file di profilo [!DNL Base] [!DNL Metric.vw] in modo che vengano visualizzate solo il nuovo sottomenu e tre nuove legende di metrica.

**Per nascondere un file**

1. In [!DNL Profile Manager], apri le cartelle e le sottocartelle necessarie per individuare il file a byte zero.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file e fai clic su **[!UICONTROL Make Local]**.
1. Apri il file locale ed elimina il relativo contenuto.
1. Salva e chiudi il file.
