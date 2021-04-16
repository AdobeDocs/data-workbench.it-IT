---
description: Il profilo Geografia memorizza una raccolta di livelli e file di immagini.
title: Visualizzare i livelli
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Visualizzare i livelli{#display-layers}

Il profilo Geografia memorizza una raccolta di livelli e file di immagini.

Quando visualizzate un globo, potete selezionare i livelli disponibili da visualizzare per una particolare attività di analisi:

* **Marmo blu 2 km:** Questo strato mostra il globo. Quando questo livello non è selezionato, il globo non è visibile.
* **Coordinate IP:** questo livello del punto elemento visualizza la latitudine e la longitudine delle posizioni nel set di dati in base agli indirizzi IP del visitatore.
* **Punti ZIP:** questo livello visualizza la latitudine e la longitudine delle posizioni nel set di dati in base a un elenco di codici ZIP degli Stati Uniti fornito dall’Adobe. Il file di ricerca [!DNL Zip Points.txt] contiene il codice ZIP, i dati di latitudine e longitudine da visualizzare, mentre il file [!DNL Zip Points.layer] contiene i parametri di configurazione necessari per visualizzare questi dati nel mondo. Entrambi questi file sono memorizzati nella cartella Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Altri nomi di livello disponibili:*** ogni nome di livello rappresenta un  [!DNL .layer] file memorizzato nella cartella Profiles\Geography\Maps folder, Profiles\IP Geo-location\Maps o nella cartella Profiles\IP Geo-intelligence\Maps all&#39;interno della directory di installazione di Insight Server.

>[!NOTE]
>
>Per ottenere il profilo IP Geo-location o IP Geo-intelligence, devi abbonarti rispettivamente al servizio IP Geo-location o IP Geo-intelligence.

Per controllare l&#39;ordine di visualizzazione dei livelli, è possibile utilizzare un file [!DNL order.txt]. Consulta [Personalizzazione dei menu utilizzando i file Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Per attivare/disattivare i livelli in un globo**

* Fai clic con il pulsante destro del mouse all’interno della visualizzazione e fai clic sul nome del livello desiderato. Una X a sinistra del livello indica che il livello è visibile.
