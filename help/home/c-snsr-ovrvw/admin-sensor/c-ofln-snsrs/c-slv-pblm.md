---
description: Se un server Web non è in linea a causa di un errore, la soluzione è semplice e richiede un utente Workbench dati con privilegi appropriati per aprire il file Log Processing Mode.cfg e aggiungere l'ID del sensore (nel nostro esempio, WEB2) alla sezione "Origini offline".
solution: Insight
title: Risoluzione del problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Risoluzione del problema{#solving-the-problem}

Se un server Web non è in linea a causa di un errore, la soluzione è semplice e richiede un utente Workbench dati con privilegi appropriati per aprire il file Log Processing Mode.cfg e aggiungere l&#39;ID del sensore (nel nostro esempio, WEB2) alla sezione &quot;Origini offline&quot;.

Questa sezione del file indica [!DNL data workbench server] che non deve più aspettarsi dati da questa origine perché, in realtà, è offline.

>[!NOTE]
>
>Questa modifica non deve essere eseguita da un consulente Adobe. Chiunque disponga dei privilegi appropriati per aprire il [!DNL Log Processing Mode.cfg] file può apportare questa modifica.

Se WEB2 ricomincia a inviare i dati, [!DNL data workbench server] riporta l&#39;origine online e regola il tempo di disponibilità in modo da riflettere l&#39;ultima volta che ha ricevuto i dati da tutte le fonti di cui è a conoscenza. In altre parole, i nuovi dati che entrano nel sistema hanno la precedenza su ciò che è scritto nel [!DNL Log Processing Mode.cfg file].

Se WEB2 torna a essere offline, il pulsante A ora si arresterà nuovamente e sarà necessario modificare nuovamente il [!DNL Log Processing Mode.cfg] file anche se potrebbe già avere WEB2 elencato come origine offline. Si tratta di un artefatto del design del prodotto in linea con la definizione del tempo come: l&#39;ultima volta che il sistema dispone di dati per tutte le origini note.

Quando aggiungete altri server Web (WEB4, WEB5, WEB6) e iniziano a inviare dati a [!DNL data workbench server], non dovete fare nulla per far sì che le [!DNL data workbench server] nuove origini vengano riconosciute. Il sistema si rende semplicemente conto che dovrebbe aspettarsi dati da queste nuove fonti, come descritto in precedenza.
