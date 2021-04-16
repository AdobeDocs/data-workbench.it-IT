---
description: Il Worktop consente di determinare facilmente dove viene memorizzato ogni particolare workspace, sia sul server Data Workbench, sul computer locale o su entrambi.
title: Controllo delle versioni file
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# Controllo delle versioni file{#file-versioning}

Il Worktop consente di determinare facilmente dove viene memorizzato ogni particolare workspace, sia sul server Data Workbench, sul computer locale o su entrambi.

## Identificazione delle versioni dei file {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

Un’area di lavoro server viene memorizzata nel server di Data Workbench connesso ed è disponibile per tutti gli utenti che hanno accesso a questo profilo e a questa scheda. Un’area di lavoro del server viene visualizzata come una singola miniatura.

![](assets/wsp_thumb_server.png)

Le aree di lavoro del server vengono memorizzate per impostazione predefinita nella sottocartella appropriata all&#39;interno della cartella Aree di lavoro del server di Data Workbench connesso.

**Locale**

Un’area di lavoro locale è la versione locale di un’area di lavoro server. Un’area di lavoro locale viene visualizzata come due miniature sovrapposte. La miniatura nella parte superiore inizialmente è circondata da un bagliore, che indica che le modifiche recenti sono state apportate localmente all’area di lavoro del server. Questo bagliore si disperde nel tempo.

![](assets/wsp_thumb_local.png)

Le aree di lavoro locali vengono memorizzate per impostazione predefinita nella cartella [!DNL User\working profile name\Workspaces\tab] name all&#39;interno della directory di installazione di Data Workbench (o Insight).

>[!NOTE]
>
>Se si dispone di una versione locale di un&#39;area di lavoro server, è necessario ripristinare la versione del server prima di scaricare una versione aggiornata dell&#39;area di lavoro server. Per ripristinare la versione del server senza modifiche locali, fai clic con il pulsante destro del mouse sulla miniatura dell’area di lavoro locale e fai clic su **[!UICONTROL Revert to server version]**.

**Utente**

Un&#39;area di lavoro utente è un&#39;area di lavoro creata su ed esiste solo nel computer locale. Un&#39;area di lavoro utente viene visualizzata come una singola miniatura con una struttura tratteggiata di un&#39;area di lavoro vuota dietro di essa, a indicare che non è presente un&#39;area di lavoro sorgente sul server di Data Workbench connesso.

![](assets/wsp_thumb_user.png)

Le aree di lavoro utente sono memorizzate per impostazione predefinita nella cartella Nome profilo di lavoro*\Workspaces\*nome scheda* all’interno della directory di installazione di Insight.
