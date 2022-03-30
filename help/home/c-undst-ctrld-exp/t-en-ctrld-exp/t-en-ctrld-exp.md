---
description: Per abilitare la sperimentazione controllata, un utente con accesso amministratore ai server web o applicativi deve modificare il parametro ExpFile nel file di configurazione Sensor (in genere denominato utilizzando txlogd.conf) su ogni server web o applicativo nel cluster web in cui è installato un Sensor.
solution: Analytics
title: Abilitazione della sperimentazione controllata
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Abilitazione della sperimentazione controllata{#enabling-controlled-experimentation}

Per abilitare la sperimentazione controllata, un utente con accesso amministratore ai server web o applicativi deve modificare il parametro ExpFile nel file di configurazione Sensor (in genere denominato utilizzando txlogd.conf) su ogni server web o applicativo nel cluster web in cui è installato un Sensor.

Inoltre, altri due parametri in questo file possono essere modificati per implementare uno strumento di test (parametro ExpCookieURL) o per mappare nuovamente grandi sezioni del sito web (parametro ExpPartialMatch). Questo capitolo fornisce ulteriori informazioni su questi parametri.

**Per modificare il file txlogd.conf**

Se disponi dell&#39;accesso come amministratore, completa i passaggi seguenti. Se non disponi dell&#39;accesso di amministratore, contatta l&#39;architetto del sistema per richiedere le modifiche, fornendo loro i seguenti passaggi.

1. Passa a [!DNL Sensor] cartella di installazione su un server web o applicativo nel cluster Web in cui è [!DNL Sensor] è installato.
1. Apri [!DNL Sensor] file di configurazione (in genere denominato utilizzando [!DNL txlogd.conf]) mediante un editor di testo e modifica il file come indicato in [Modifica del parametro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   (e facoltativamente in [Modifica del parametro ExpCookieURL (facoltativo)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) e [Modifica del parametro ExpPartialMatch (facoltativo)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Salva e chiudi il file.
1. Ripetere questa procedura per ogni server Web o application nel cluster Web in cui un [!DNL Sensor] è installato.
