---
description: Un server workbench dati viene a conoscenza di un'origine dati, come un sensore, quando riceve i dati da tale origine.
solution: Insight
title: Informazioni sul tempo di utilizzo
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sul tempo di utilizzo{#understanding-as-of-time}

Un server workbench dati viene a conoscenza di un&#39;origine dati, come un sensore, quando riceve i dati da tale origine.

Il valore A tempo è una garanzia che i dati [!DNL data workbench server] sono disponibili per tutte le origini dati di cui sono a conoscenza.

Supponiamo di disporre di tre serie [!DNL Sensors] che inviano dati a un [!DNL data workbench server]: WEB1, WEB2 e WEB3. Man mano che [!DNL data workbench server] riceve ed elabora i dati da tali [!DNL Sensors], viene automaticamente ad aspettarsi i dati da ciascuna di queste origini. L&#39;ora Come indica l&#39;ultima volta che i dati [!DNL data workbench server] ricevuti da tutte e tre le origini.

In pratica, l&#39; [!DNL data workbench server] unica preoccupazione riguarda il tempo come e non quello che potrebbe essere chiamato &quot;tempo muro&quot;, o l&#39;ora da un orologio sul muro. Il tempo [!DNL data workbench server] conosce solo come il tempo. Ciò è particolarmente importante ai fini della segnalazione, in quanto garantisce che i report vengano sempre eseguiti in base al tempo previsto, in modo da garantire che i report con solo dati parziali non possano mai essere inviati agli utenti finali del sistema.

I [!DNL data workbench server] dati inviati dal trasmettitore vengono utilizzati per fornire i dati relativi al tempo, sia che si tratti di dati effettivi raccolti dal sito Web, sia che si tratti di heartbeat periodici inviati dall&#39;utente [!DNL Sensors]. Questi heartbeat servono due scopi:

1. Per mantenere una connessione HTTP/1.1 persistente aperta tra [!DNL Sensor] e [!DNL data workbench server].

1. Per mantenere aggiornato il tempo impostato nel caso in cui il traffico del sito Web non venga raccolto e inviato al [!DNL data workbench server].

