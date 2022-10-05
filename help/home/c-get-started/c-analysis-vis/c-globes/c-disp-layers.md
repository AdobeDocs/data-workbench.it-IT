---
description: Il profilo Geografia memorizza una raccolta di livelli e file di immagini.
title: Visualizzare i livelli
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Visualizzare i livelli{#display-layers}

{{eol}}

Il profilo Geografia memorizza una raccolta di livelli e file di immagini.

Quando visualizzate un globo, potete selezionare i livelli disponibili da visualizzare per una particolare attività di analisi:

* **Marmo blu 2 km:** Questo livello mostra il globo. Quando questo livello non è selezionato, il globo non è visibile.
* **Coordinate IP:** Questo livello punto elemento visualizza la latitudine e la longitudine delle posizioni nel set di dati in base agli indirizzi IP del visitatore.
* **Punti ZIP:** Questo livello visualizza la latitudine e la longitudine delle posizioni nel set di dati in base a un elenco di codici ZIP degli Stati Uniti fornito da Adobe. La [!DNL Zip Points.txt] il file di ricerca contiene il codice ZIP, i dati di latitudine e longitudine da visualizzare, mentre il [!DNL Zip Points.layer] il file contiene i parametri di configurazione necessari per visualizzare questi dati sul globo. Entrambi i file sono memorizzati nella cartella Profiles\Geography\Maps all&#39;interno della directory di installazione del server Data Workbench.

* ***Altri nomi di livello disponibili:*** Ogni nome di livello rappresenta un [!DNL .layer] file memorizzato nella cartella Profiles\Geography\Maps, nella cartella Profiles\IP Geo-location\Maps o nella cartella Profiles\IP Geo-intelligence\Maps all&#39;interno della directory di installazione di Insight Server.

>[!NOTE]
>
>Per ottenere il profilo IP Geo-location o IP Geo-intelligence, devi abbonarti rispettivamente al servizio IP Geo-location o IP Geo-intelligence.

Per controllare l&#39;ordine di visualizzazione dei livelli, puoi utilizzare un [!DNL order.txt] file. Vedi [Personalizzazione dei menu tramite i file Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Per attivare/disattivare i livelli in un globo**

* Fai clic con il pulsante destro del mouse all’interno della visualizzazione e fai clic sul nome del livello desiderato. Una X a sinistra del livello indica che il livello è visibile.
