---
description: Per abilitare la sperimentazione controllata, un utente con accesso amministratore ai server Web o applicazione deve modificare il parametro ExpFile nel file di configurazione Sensor (in genere denominato tramite txlogd.conf) su ogni server Web o applicativo del cluster Web in cui è installato un sensore.
solution: Analytics,Analytics
title: Abilitazione della sperimentazione controllata
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---


# Abilitazione della sperimentazione controllata{#enabling-controlled-experimentation}

Per abilitare la sperimentazione controllata, un utente con accesso amministratore ai server Web o applicazione deve modificare il parametro ExpFile nel file di configurazione Sensor (in genere denominato tramite txlogd.conf) su ogni server Web o applicativo del cluster Web in cui è installato un sensore.

Inoltre, altri due parametri in questo file possono essere modificati per implementare uno strumento di test (parametro ExpCookieURL) o per rimappare sezioni di grandi dimensioni del sito Web (parametro ExpPartialMatch). Questo capitolo fornisce ulteriori informazioni su questi parametri.

**Per modificare il file txlogd.conf**

Se disponete dell&#39;accesso dell&#39;amministratore, eseguite i seguenti passaggi. Se non disponete dell&#39;accesso di amministratore, contattate l&#39;architetto del sistema per richiedere le modifiche, fornendo i seguenti passaggi.

1. Individuate la cartella di [!DNL Sensor] installazione in un server Web o in un server applicazione nel cluster Web in cui [!DNL Sensor] è installato.
1. Aprite il file di [!DNL Sensor] configurazione (in genere denominato mediante [!DNL txlogd.conf]) utilizzando un editor di testo e modificate il file come indicato in [Modifica del parametro](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

   (e facoltativamente in [Modifica del parametro ExpCookieURL (facoltativo)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) e [Modifica del parametro ExpPartialMatch (facoltativo)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Salvate e chiudete il file.
1. Ripetete questa procedura per ogni server Web o server applicazione nel cluster Web in cui [!DNL Sensor] è installato.
