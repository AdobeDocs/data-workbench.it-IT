---
description: Il profilo Geografia memorizza una raccolta di livelli e file di immagini.
solution: Analytics
title: Visualizzare i livelli
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzare i livelli{#display-layers}

Il profilo Geografia memorizza una raccolta di livelli e file di immagini.

Quando visualizzate un globo, potete selezionare i livelli disponibili da visualizzare per una particolare attività di analisi:

* **Marmo blu 2 km:** Questo livello visualizza il globo. Se questo livello non è selezionato, il globo non è visibile.
* **Coordinate IP:** Questo livello punto elemento visualizza la latitudine e la longitudine delle posizioni nel set di dati in base agli indirizzi IP del visitatore.
* **Punti ZIP:** Questo livello visualizza la latitudine e la longitudine delle posizioni nel set di dati in base a un elenco di codici ZIP statunitensi fornito da Adobe. Il file di [!DNL Zip Points.txt] ricerca contiene i dati del CAP, della latitudine e della longitudine da visualizzare, mentre il [!DNL Zip Points.layer] file contiene i parametri di configurazione necessari per visualizzare questi dati nel mondo. Entrambi i file sono memorizzati nella cartella Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Altri nomi di livello disponibili:*** Ogni nome del livello rappresenta un [!DNL .layer] file memorizzato nella cartella Profiles\Geography\Maps folder, Profili\IP Geo-location\Maps o nella cartella Profiles\IP Geo-intelligence\Maps all&#39;interno della directory di installazione di Insight Server.

>[!NOTE]
>
>Per avere il profilo IP Geo-location o IP Geo-intelligence, è necessario iscriversi rispettivamente al servizio IP Geo-location o IP Geo-intelligence.

Per controllare l’ordine di visualizzazione dei livelli, potete usare un [!DNL order.txt] file. Consultate [Personalizzazione dei menu tramite i file](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

**Per attivare/disattivare i livelli in un globo**

* Fai clic con il pulsante destro del mouse all’interno della visualizzazione e fai clic sul nome del livello desiderato. Una X a sinistra del livello indica che il livello è visibile.

