---
description: Informazioni sulla risoluzione dei problemi del server Web, ad esempio, se il server Web non è in grado di ruotare o se il server Web non funziona.
solution: Analytics
title: Informazioni sulle cause
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---


# Informazioni sulle cause{#understanding-the-causes}

Informazioni sulla risoluzione dei problemi del server Web, ad esempio, se il server Web non è in grado di ruotare o se il server Web non funziona.

## Quando un server Web viene rimosso dalla rotazione {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Quando un server Web non è in grado di ruotare da un pool di server, ma è collegato con il trasmettitore che invia heartbeat periodici, il tempo impostato viene mantenuto al corrente e non è necessario alcun intervento da parte di nessuno.

## In caso di errore di un server Web {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Quando un server Web è completamente offline a causa di un guasto catastrofico o non invia dati o heartbeat, il tempo di attesa [!DNL data workbench server] si arresta per garantire che rappresenti l&#39;ultima volta che i dati [!DNL data workbench server] ricevuti da TUTTE le origini dati di cui è a conoscenza. Il sistema stesso continua a elaborare i dati, che sono ancora disponibili per l&#39;analisi nella Data Workbench, ma tutto ciò [!DNL data workbench server] che si basa sul tempo come non funziona. Ad esempio, il rapporto Come di tempo attiva e viene utilizzato per creare molte dimensioni derivate nel sistema. Quando il tempo di inattività è terminato, la generazione dei rapporti non viene attivata e queste dimensioni derivate particolari non sono disponibili.

Ad esempio, se WEB2 è stato offline il 15 giugno e non ha inviato alcun dato per cinque giorni, il tempo A è in un certo momento il 15 giugno. La dimensione di ieri, ad esempio, sarebbe il 14 giugno anche se la data odierna è il 20 giugno.
