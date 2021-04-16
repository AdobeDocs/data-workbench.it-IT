---
description: Sono disponibili cinque gruppi di controllo accessi predefiniti, ma puoi creare e gestire altri gruppi in base alle esigenze.
title: Informazioni sui gruppi di controllo di accesso
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---

# Informazioni sui gruppi di controllo di accesso{#understanding-access-control-groups}

Sono disponibili cinque gruppi di controllo accessi predefiniti, ma puoi creare e gestire altri gruppi in base alle esigenze.

È possibile definire i membri di ciascun gruppo di controllo degli accessi, nonché le directory a cui ogni gruppo ha accesso in sola lettura o in sola lettura.

I gruppi predefiniti sono definiti come segue:

| Gruppo | Descrizione |
|---|---|
| Amministratori | Consente l&#39;accesso a tutte le directory e a tutti i file. L’indirizzo IP predefinito è 127.0.0.1 (host locale). |
| Sensori | Consente l&#39;accesso solo ai file utilizzati da [!DNL Sensor] per trasmettere i dati. |
| Utenti | Consente l’accesso in sola lettura agli elementi necessari a un utente [!DNL Insight] per eseguire attività di analisi di base. |
| Alimentazione | Consente l’accesso in sola lettura agli elementi necessari affinché un utente [!DNL Insight] esegua attività di analisi di base, oltre all’accesso in lettura e scrittura alla cartella [!DNL Profiles] per la modifica dei profili. |
| Server cluster | Consente l&#39;accesso a [!DNL Insight Servers] designati come server cluster. |
| Server di rapporto | Consente l&#39;accesso a [!DNL Report] computer che si collegano a [!DNL Insight Server]. |

I membri di un gruppo di controllo accessi vengono definiti utilizzando i loro indirizzi IP o le informazioni sul certificato SSL.

Se un certificato SSL non è disponibile, è possibile utilizzare un indirizzo IP per definire un membro del gruppo. L’installazione tipica di [!DNL Insight] include un certificato SSL, mentre l’utilizzo di certificati per [!DNL Sensor(s)] è facoltativo. Per [!DNL Insight Server], i cluster server sono definiti utilizzando indirizzi IP invece dei certificati SSL.

Per definire i membri del gruppo è possibile utilizzare i seguenti codici:

| Codice dei tipi di accesso | Definizione |
|---|---|
| O | Organizzazione |
| CN | Nome comune |
| L | Località |
| ST | Stato o provincia |
| C | Paese |
| OU | Unità organizzativa |
| E-mail | Indirizzo e-mail |
