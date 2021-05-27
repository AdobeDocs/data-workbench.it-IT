---
description: Linee guida per specificare il formato di output.
title: Formato di output
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Formato di output{#output-format}

Linee guida per specificare il formato di output.

* Ogni metrica o nome di dimensione deve iniziare e terminare con un segno di percentuale (%).

   * %XYZ% specifica l&#39;elemento della dimensione XYZ corrispondente all&#39;elemento di Livello. Viene generato un errore se la dimensione XYZ non è uno a uno o uno a molti con Livello.
   * %=XYZ% specifica il valore della metrica o della formula metrica XYZ per l’elemento specificato di Livello.

* I nomi di Dimension con due parole o più non richiedono caratteri di sottolineatura.
* I nomi delle metriche che sono due parole o più richiedono caratteri di sottolineatura.

>[!NOTE]
>
>Se tieni premuto il tasto Ctrl e fai clic con il pulsante destro del mouse all&#39;interno del campo [!DNL Output Format] , viene visualizzato un [!DNL Insert menu]. Questo menu contiene un elenco di caratteri speciali (ad esempio, Tab) che vengono spesso utilizzati come delimitatori.

Se desideri esportare i dati della durata della sessione per il segmento, devi creare una nuova metrica basata sulla metrica Durata sessione . La nuova metrica, utilizzabile solo con il campo [!DNL Output Format] di esportazione dei segmenti, consente a Microsoft Excel di interpretare correttamente le sessioni che durano meno di un&#39;ora. Per creare una nuova metrica di durata della sessione, apri il file [!DNL Session Duration.metric] (da [!DNL Profile Manager]) e inserisci un cancelletto (#) nella stringa ftime: [!DNL ftime = string: %#H:%M:%S]

Il simbolo cancelletto fa sì che un &quot;0&quot; iniziale sia aggiunto alle durate di sessione inferiori a 1 ora. Di conseguenza, Excel interpreta 0:53:21 come 53 minuti e 21 secondi. Salva la nuova metrica con un nome diverso e caricala nel profilo appropriato affinché altri possano usarla facendo clic con il pulsante destro del mouse sul segno di spunta del file nella colonna [!DNL User] e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
