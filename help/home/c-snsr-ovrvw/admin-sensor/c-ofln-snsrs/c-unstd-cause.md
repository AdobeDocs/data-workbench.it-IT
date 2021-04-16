---
description: Informazioni sulla risoluzione dei problemi del server web, ad esempio se il server web è fuori rotazione o se il server web non riesce.
title: Informazioni sulle cause
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Informazioni sulle cause{#understanding-the-causes}

Informazioni sulla risoluzione dei problemi del server web, ad esempio se il server web è fuori rotazione o se il server web non riesce.

## Quando un server Web viene eliminato dalla rotazione {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Quando un server web viene fuori dalla rotazione da un pool di server, ma è altrimenti connesso con il trasmettitore che invia heartbeat periodici, il tempo di notifica viene mantenuto corrente e non è necessario alcun intervento da parte di nessuno.

## In caso di errore di un server Web {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Quando un server web è offline completamente a causa di un errore catastrofico, o non invia dati o heartbeat, il tempo A si arresta al [!DNL data workbench server] per garantire che rappresenti l&#39;ultima volta che [!DNL data workbench server] ha ricevuto dati da TUTTE le origini dati di cui è consapevole. Il sistema stesso continua a elaborare i dati, che sono ancora disponibili per l&#39;analisi in Data Workbench, ma qualsiasi elemento in [!DNL data workbench server] basato sul valore A del tempo non funziona. Ad esempio, il tempo impostato attiva il reporting e viene utilizzato per creare molte dimensioni derivate nel sistema. Quando il valore A partire dal tempo si interrompe, la generazione di rapporti non viene attivata e queste particolari dimensioni derivate non sono disponibili.

Ad esempio, se WEB2 è stato offline il 15 giugno e non ha inviato dati per cinque giorni, l&#39;orario impostato sarebbe a un certo punto il 15 giugno. La dimensione di Ieri, ad esempio, sarebbe il 14 giugno anche se la data di oggi è il 20 giugno.
