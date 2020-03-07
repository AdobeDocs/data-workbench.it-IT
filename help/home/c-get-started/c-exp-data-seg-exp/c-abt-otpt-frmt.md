---
description: Linee guida per la specifica del formato di output.
solution: Analytics
title: Formato di output
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato di output{#output-format}

Linee guida per la specifica del formato di output.

* Ogni metrica o nome di dimensione deve iniziare e terminare con un segno di percentuale (%).

   * %XYZ% specifica l&#39;elemento della dimensione XYZ corrispondente all&#39;elemento di livello. Se la dimensione XYZ non è uno a uno o uno a molti con il livello, viene generato un errore.
   * %=XYZ% specifica il valore della metrica o della formula metrica XYZ per l’elemento di livello specificato.

* I nomi delle dimensioni con due o più parole non richiedono caratteri di sottolineatura.
* I nomi delle metriche che sono due parole o più richiedono caratteri di sottolineatura.

>[!NOTE]
>
>Se si tiene premuto il tasto Ctrl e si fa clic con il pulsante destro del mouse all&#39;interno del [!DNL Output Format] campo, [!DNL Insert menu] viene visualizzato un messaggio. Questo menu contiene un elenco di caratteri speciali (ad esempio, Tab) spesso utilizzati come delimitatori.

Se desiderate esportare i dati sulla durata della sessione per il segmento, dovete creare una nuova metrica basata sulla metrica Durata sessione. La nuova metrica, utilizzabile solo con il [!DNL Output Format] campo di esportazione dei segmenti, consente a Microsoft Excel di interpretare correttamente le sessioni della durata inferiore a un&#39;ora. Per creare una nuova metrica durata sessione, aprite il [!DNL Session Duration.metric] file (da [!DNL Profile Manager]) e inserite un simbolo cancelletto (#) nella stringa ftime: [!DNL ftime = string: %#H:%M:%S]

Il simbolo cancelletto fa sì che un &quot;0&quot; iniziale venga aggiunto alle durate di sessione inferiori a 1 ora. Di conseguenza, Excel interpreta 0:53:21 come 53 minuti e 21 secondi. Salva la nuova metrica con un nome diverso e caricala nel profilo appropriato affinché altri possano utilizzarla facendo clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL User] colonna e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
