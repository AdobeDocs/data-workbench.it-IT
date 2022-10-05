---
description: Un server di Data Workbench viene a conoscenza di un’origine di dati, ad esempio un sensore, quando riceve dati da tale origine.
title: Informazioni sul tempo “a partire da”
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Informazioni sul tempo “a partire da”{#understanding-as-of-time}

{{eol}}

Un server di Data Workbench viene a conoscenza di un’origine di dati, ad esempio un sensore, quando riceve dati da tale origine.

Il tempo è una garanzia che il [!DNL data workbench server] dispone di dati per tutte le fonti di dati di cui è a conoscenza.

Diciamo che abbiamo una serie di tre [!DNL Sensors] che inviano dati a un [!DNL data workbench server]: WEB1, WEB2 e WEB3. Come [!DNL data workbench server] riceve ed elabora i dati da tali [!DNL Sensors], viene automaticamente da aspettarsi i dati da ciascuna di queste fonti. Il valore A indica l&#39;ultima volta che il valore [!DNL data workbench server] ha ricevuto dati da tutte e tre le fonti.

In termini pratici, il [!DNL data workbench server] si preoccupa solo del tempo e non di quello che potrebbe essere chiamato &quot;tempo muro&quot;, o l&#39;ora da un orologio sul muro. La [!DNL data workbench server] conosce il tempo solo come A del tempo. Ciò è particolarmente importante a scopo di reporting, in quanto garantisce che i rapporti vengano sempre eseguiti in base al tempo impostato, in modo che i rapporti con solo dati parziali non possano mai essere inviati agli utenti finali del sistema.

La [!DNL data workbench server] utilizza i dati inviati dal trasmettitore per fornire il valore A tempo, che si tratti di dati effettivi raccolti dal sito web o di heartbeat periodici inviati dal tuo [!DNL Sensors]. Questi heartbeat hanno due scopi:

1. Per mantenere aperta una connessione permanente HTTP/1.1 tra [!DNL Sensor] e [!DNL data workbench server].

1. Per mantenere aggiornato il valore A del tempo nel caso in cui il traffico del sito web non venga raccolto e inviato al [!DNL data workbench server].
