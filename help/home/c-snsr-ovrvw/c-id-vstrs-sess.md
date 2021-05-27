---
description: Durante la raccolta dei dati evento da un server web, Sensor imposta automaticamente un cookie persistente per ogni visitatore contenente un piccolo identificatore casuale, senza acquisire informazioni identificative personali.
title: In che modo il sensore identifica visitatori e sessioni?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# In che modo il sensore identifica visitatori e sessioni?{#how-does-sensor-identify-visitors-and-sessions}

Durante la raccolta dei dati evento da un server web, Sensor imposta automaticamente un cookie persistente per ogni visitatore contenente un piccolo identificatore casuale, senza acquisire informazioni identificative personali.

Questo cookie di Adobe viene utilizzato per identificare il visitatore univoco e tutte le sessioni correlate.

Per impostazione predefinita, [!DNL Sensor] acquisisce tutti i campi del formato file di registro esteso W3C da ogni intestazione HTTP, ma è possibile configurare [!DNL Sensor] per acquisire qualsiasi intestazione trasmessa tra client e server. Per informazioni sui campi dati evento raccolti da [!DNL Sensor] nei file [!DNL .vsl], vedere [Campi record dati evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Alcuni browser dei visitatori non memorizzano i cookie in modo permanente e un numero molto ridotto di browser non accetta alcun cookie (anche i cookie di sessione). Anche se rappresentano solo una frazione del traffico totale di un sito, possono causare errori di conteggio significativi se ogni visualizzazione di pagina da parte di un visitatore viene conteggiata in modo errato come un’intera sessione, come avviene da alcuni software di analisi dei file di registro. Questo Adobe consente di analizzare i visitatori con e senza l’utilizzo dei cookie.

Per ulteriori informazioni sul filtro sessioni interrotte, consulta la *Guida al sensore di Data Workbench*.
