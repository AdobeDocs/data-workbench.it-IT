---
description: Controllare se il trasmettitore è in esecuzione impostando gli avvisi, controllando lo stato del sistema del sensore e altro ancora.
title: Conferma dell’esecuzione del Data Transmitter
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Conferma dell’esecuzione del Data Transmitter{#confirming-that-the-data-transmitter-is-running}

{{eol}}

Controllare se il trasmettitore è in esecuzione impostando gli avvisi, controllando lo stato del sistema del sensore e altro ancora.

**Frequenza consigliata:** Ogni 5-10 minuti

* [Controllare che il processo del trasmettitore sia in esecuzione.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurare gli avvisi amministrativi in Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Controllare lo stato del sistema del sensore.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Controllo del processo del trasmettitore {#section-79806fa3b7034a8eaf571a66e24874d7}

Un modo per verificare che il trasmettitore sia in esecuzione è quello di verificare che il [!DNL Sensor] il processo del trasmettitore è in esecuzione su ogni server web in cui un [!DNL Sensor] istanza installata. Il processo del trasmettitore appare come &quot;txlogd&quot; nell’elenco dei processi del server web. È possibile eseguire questo controllo utilizzando uno strumento di monitoraggio del sistema.

## Configurazione degli avvisi amministrativi nel server Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Un altro modo per verificare che il trasmettitore sia in esecuzione è quello di impostare avvisi amministrativi automatizzati nel [!DNL data workbench server]. Quando sono stati configurati avvisi amministrativi, la [!DNL data workbench server] genera un avviso e-mail quando non riceve dati da una connessione configurata e connessa in precedenza [!DNL Sensor] nell&#39;intervallo di tempo specificato nel [!DNL Sensor] Timeout avviso (min) nel [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] file. Per ulteriori informazioni sulla configurazione degli avvisi amministrativi, consulta la sezione *Guida all’installazione e all’amministrazione dei prodotti server*.

## Controllo dello stato del sistema del sensore {#section-de9d7e359242487a9fbead4ed65aebbc}

Un altro modo per verificare che il trasmettitore sia in esecuzione è quello di controllare manualmente il [!DNL Servers Manager] nella Data Workbench.

**Per visualizzare il[!DNL Servers Manager]**

* In Data Workbench, fai clic con il pulsante destro del mouse all’interno di un’area di lavoro e fai clic su **[!UICONTROL Admin]**, quindi sotto [!DNL Manage], fai clic su **[!UICONTROL Servers]**.

Se l’icona di un [!DNL Sensor] è verde, il trasmettitore è in funzione.

Per ulteriori informazioni sulla [!DNL Servers Manager], vedere il capitolo relativo alle interfacce amministrative *Data Workbench [!DNL Sensor] Guida*.
