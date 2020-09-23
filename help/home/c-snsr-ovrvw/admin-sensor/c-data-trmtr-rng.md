---
description: Controllare se il trasmettitore è in esecuzione impostando gli avvisi, controllando lo stato del sistema del sensore e altro ancora.
solution: Analytics
title: Conferma dell’esecuzione del Data Transmitter
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# Conferma dell’esecuzione del Data Transmitter{#confirming-that-the-data-transmitter-is-running}

Controllare se il trasmettitore è in esecuzione impostando gli avvisi, controllando lo stato del sistema del sensore e altro ancora.

**Frequenza consigliata:** Ogni 5-10 minuti

* [Verificare che il processo del trasmettitore sia in esecuzione.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurare gli avvisi amministrativi in Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Controllare lo stato del sistema del sensore.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Controllo del processo di trasmettitore {#section-79806fa3b7034a8eaf571a66e24874d7}

Un modo per verificare che il trasmettitore sia in esecuzione è verificare che il processo del [!DNL Sensor] trasmettitore sia in esecuzione su ogni server Web in cui è installata un&#39; [!DNL Sensor] istanza. Nell’elenco dei processi del server Web, il processo del trasmettitore viene visualizzato come &quot;txlogd&quot;. È possibile eseguire questo controllo utilizzando uno strumento di monitoraggio del sistema.

## Impostazione degli avvisi amministrativi nel server di Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Un altro modo per verificare che il trasmettitore sia in esecuzione è quello di impostare avvisi amministrativi automatizzati nel [!DNL data workbench server]. Quando sono stati configurati degli avvisi amministrativi, l&#39;utente [!DNL data workbench server] genera un avviso e-mail quando non ha ricevuto dati da un utente configurato e connesso in precedenza [!DNL Sensor] entro il periodo di tempo specificato nel parametro [!DNL Sensor] Alert Timeout (min) del [!DNL data workbench server’s] file [!DNL Administrative Alerts.cfg] . Per ulteriori informazioni sulla configurazione degli avvisi amministrativi, consulta la Guida all’installazione e all’amministrazione dei prodotti *server*.

## Controllo dello stato del sistema del sensore {#section-de9d7e359242487a9fbead4ed65aebbc}

Un altro modo per verificare che il trasmettitore sia in esecuzione è quello di controllare manualmente la [!DNL Servers Manager] Data Workbench.

**Per visualizzare il pulsante[!DNL Servers Manager]**

* In Data Workbench, fare clic con il pulsante destro del mouse all&#39;interno di un&#39;area di lavoro, fare clic **[!UICONTROL Admin]** e quindi, sotto [!DNL Manage], fare clic **[!UICONTROL Servers]**.

Se l&#39;icona di un trasmettitore [!DNL Sensor] è verde, il trasmettitore è in esecuzione.

Per ulteriori informazioni su [!DNL Servers Manager]di esso, consulta il capitolo relativo alle interfacce amministrative della *Guida[!DNL Sensor]alleDate Workbench*.
