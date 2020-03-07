---
description: Durante la raccolta dei dati dell'evento da un server Web, Sensor imposta automaticamente un cookie permanente per ogni visitatore contenente un piccolo identificatore casuale, senza acquisire alcuna informazione di identificazione personale.
solution: Insight
title: In che modo il sensore identifica visitatori e sessioni?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# In che modo il sensore identifica visitatori e sessioni?{#how-does-sensor-identify-visitors-and-sessions}

Durante la raccolta dei dati dell&#39;evento da un server Web, Sensor imposta automaticamente un cookie permanente per ogni visitatore contenente un piccolo identificatore casuale, senza acquisire alcuna informazione di identificazione personale.

Questo cookie Adobe viene utilizzato per identificare il visitatore univoco e tutte le sessioni correlate.

Per impostazione predefinita, [!DNL Sensor] acquisisce tutti i campi W3C Extended Log File Format da ciascuna intestazione HTTP, ma è possibile configurare [!DNL Sensor] per acquisire qualsiasi intestazione trasmessa tra il client e il server. Per informazioni sui campi di dati dell&#39;evento raccolti da [!DNL Sensor] nei [!DNL .vsl] file, consultate Campi [di record dati](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)evento.

Alcuni browser dei visitatori non memorizzano i cookie in modo persistente, e un numero molto limitato di browser dei visitatori non accettano i cookie (anche i cookie di sessione). Anche se rappresentano solo una frazione del traffico totale di un sito, possono causare errori di conteggio significativi se ogni visualizzazione di pagina da parte di tale visitatore viene conteggiata erroneamente come un&#39;intera sessione, come avviene con alcuni software di analisi dei file di registro. Adobe risolve questo problema consentendo di analizzare i visitatori con e senza utilizzare i cookie.

Per ulteriori informazioni sul filtro sessioni interrotte, vedere la Guida *ai sensori di Workbench* dati.
