---
description: Sono disponibili cinque gruppi di controllo di accesso predefiniti, ma potete creare e gestire altri gruppi in base alle vostre esigenze.
solution: Analytics
title: Informazioni sui gruppi di controllo di accesso
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---


# Informazioni sui gruppi di controllo di accesso{#understanding-access-control-groups}

Sono disponibili cinque gruppi di controllo di accesso predefiniti, ma potete creare e gestire altri gruppi in base alle vostre esigenze.

È possibile definire i membri di ciascun gruppo di controllo di accesso, nonché le directory a cui ciascun gruppo dispone dell&#39;accesso in sola lettura o in lettura e scrittura.

I gruppi predefiniti sono definiti come segue:

| Gruppo | Descrizione |
|---|---|
| Amministratori | Consente l&#39;accesso a tutte le directory e ai file. L&#39;indirizzo IP predefinito è 127.0.0.1 (host locale). |
| Sensori | Consente l&#39;accesso solo ai file utilizzati per [!DNL Sensor] trasmettere i dati. |
| Utenti | Consente l&#39;accesso in sola lettura agli elementi richiesti per l&#39;esecuzione di attività di analisi di base da parte di un [!DNL Insight] &#39;utente. |
| Power Users | Consente l&#39;accesso in sola lettura agli elementi richiesti per l&#39;esecuzione di attività di analisi di base da parte dell&#39; [!DNL Insight] utente, nonché l&#39;accesso in lettura e scrittura alla [!DNL Profiles] cartella per la modifica dei profili. |
| Server cluster | Consente l&#39;accesso ai server [!DNL Insight Servers] designati come server cluster. |
| Server di report | Consente l&#39;accesso ai [!DNL Report] computer che si connettono al [!DNL Insight Server]. |

I membri di un gruppo di controllo di accesso sono definiti utilizzando i loro indirizzi IP o le informazioni sul certificato SSL.

Se un certificato SSL non è disponibile, è possibile utilizzare un indirizzo IP per definire un membro del gruppo. L’installazione tipica di [!DNL Insight] include un certificato SSL, mentre l’utilizzo di certificati per [!DNL Sensor(s)] è facoltativo. Per [!DNL Insight Server]i server cluster vengono definiti utilizzando indirizzi IP invece dei certificati SSL.

I codici seguenti possono essere utilizzati per definire i membri del gruppo:

| Codice tipi di accesso | Definizione |
|---|---|
| O | Organizzazione |
| CN | Nome comune |
| L | Località |
| ST | Stato o provincia |
| C | Paese |
| OU | Unità organizzativa |
| E-mail | Indirizzo e-mail |

