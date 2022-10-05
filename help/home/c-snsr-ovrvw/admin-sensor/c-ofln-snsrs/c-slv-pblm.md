---
description: Quando un server web va offline a causa di un errore, la soluzione è semplice e richiede un utente Data Workbench con i privilegi appropriati per aprire il file Log Processing Mode.cfg e aggiungere l'ID del Sensor (nel nostro esempio, WEB2) alla sezione "Sorgenti offline".
title: Risoluzione del problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Risoluzione del problema{#solving-the-problem}

{{eol}}

Quando un server web va offline a causa di un errore, la soluzione è semplice e richiede un utente Data Workbench con i privilegi appropriati per aprire il file Log Processing Mode.cfg e aggiungere l&#39;ID del Sensor (nel nostro esempio, WEB2) alla sezione &quot;Sorgenti offline&quot;.

Questa sezione del file indica al [!DNL data workbench server] che non dovrebbe più aspettarsi dati da questa origine perché, in realtà, è offline.

>[!NOTE]
>
>Questa modifica non deve essere eseguita da un consulente Adobe. Chiunque abbia i privilegi appropriati per aprire il [!DNL Log Processing Mode.cfg] file può apportare questa modifica.

Se WEB2 inizia a inviare di nuovo i dati, il [!DNL data workbench server] porta la sorgente nuovamente online e regola il valore A del tempo per riflettere l&#39;ultima volta che ha ricevuto dati da tutte le fonti di cui è a conoscenza. In altre parole, i nuovi dati che entrano nel sistema hanno la precedenza su quelli scritti nel [!DNL Log Processing Mode.cfg file].

Se WEB2 torna offline di nuovo, l&#39;opzione A verrà interrotta e sarà necessario modificare il [!DNL Log Processing Mode.cfg] file di nuovo anche se potrebbe già avere WEB2 elencato come origine offline. Si tratta di un manufatto del design del prodotto in linea con la definizione del A del tempo: l&#39;ultima volta che il sistema dispone di dati per tutte le origini note.

Quando aggiungi altri server web (WEB4, WEB5, WEB6) e iniziano a inviare dati a [!DNL data workbench server], non è necessario fare nulla per avere il [!DNL data workbench server] riconoscere le nuove fonti. Il sistema si rende semplicemente conto che dovrebbe aspettarsi dati da queste nuove fonti, come descritto in precedenza.
