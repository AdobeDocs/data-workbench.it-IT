---
description: Il piano di lavoro consente di determinare facilmente la posizione di memorizzazione di ogni particolare area di lavoro, sia che si trovi sul server Workbench dati, sul computer locale o su entrambi.
solution: Analytics
title: Versione file
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Versione file{#file-versioning}

Il piano di lavoro consente di determinare facilmente la posizione di memorizzazione di ogni particolare area di lavoro, sia che si trovi sul server Workbench dati, sul computer locale o su entrambi.

## Identificazione delle versioni dei file {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

Un&#39;area di lavoro server è memorizzata nel server Workbench dati connesso ed è disponibile per tutti gli utenti che hanno accesso a questo profilo e a questa scheda. Un’area di lavoro server viene visualizzata come una singola miniatura.

![](assets/wsp_thumb_server.png)

Per impostazione predefinita, le aree di lavoro del server sono memorizzate nella sottocartella appropriata all&#39;interno della cartella Workspaces sul server Workbench dati connesso.

**Local**

Un’area di lavoro locale è la versione locale di un’area di lavoro server. Un’area di lavoro locale viene visualizzata come due miniature sovrapposte. La miniatura nella parte superiore inizialmente è circondata da un bagliore, che indica che le modifiche recenti sono state apportate localmente all’area di lavoro del server. Questo bagliore si dissipa nel tempo.

![](assets/wsp_thumb_local.png)

Per impostazione predefinita, le aree di lavoro locali sono memorizzate nella cartella [!DNL User\working profile name\Workspaces\tab] name all&#39;interno della directory di installazione di Workbench dati (o Insight).

>[!NOTE]
>
>Se disponete di una versione locale di un’area di lavoro server, dovete ripristinare la versione del server prima di scaricare una versione aggiornata dell’area di lavoro del server. Per ripristinare la versione del server senza modifiche locali, fare clic con il pulsante destro del mouse sulla miniatura dell&#39;area di lavoro locale e fare clic **[!UICONTROL Revert to server version]**.

**Utente**

Un’area di lavoro utente è un’area di lavoro creata e che esiste solo sul computer locale. Un&#39;area di lavoro utente viene visualizzata come una miniatura singola con un contorno tratteggiato di un&#39;area di lavoro vuota alle sue spalle, a indicare che non è presente un&#39;area di lavoro di origine nel server Workbench dati connesso.

![](assets/wsp_thumb_user.png)

Per impostazione predefinita, le aree di lavoro dell&#39;utente sono memorizzate nella cartella Utente\*nome profilo di lavoro*\Workspaces\*nome scheda* all&#39;interno della directory di installazione di Insight.
