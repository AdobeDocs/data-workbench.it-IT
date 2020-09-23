---
description: Il file di configurazione di Access Control, Access Control.cfg, definisce i gruppi di controllo di accesso tramite i quali Insight Server concede le autorizzazioni ai file in base agli attributi (OU, CN e così via) del certificato della connessione in entrata.
solution: Analytics
title: Configurazione del controllo di accesso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# Configurazione del controllo di accesso{#configuring-access-control}

Il file di configurazione di Access Control, Access Control.cfg, definisce i gruppi di controllo di accesso tramite i quali Insight Server concede le autorizzazioni ai file in base agli attributi (OU, CN e così via) del certificato della connessione in entrata.

**Frequenza consigliata:** Se necessario

[!DNL Insight Server] fornisce gruppi di controllo di accesso configurabili per gestire la sicurezza delle connessioni a [!DNL Insight Server]. I gruppi di controllo degli accessi identificano gli utenti ai quali è consentito eseguire funzioni amministrative tramite [!DNL Insight].

Se è necessario fornire l&#39;accesso a nuovi utenti o nuovi computer, ad esempio quando si aggiunge un computer a un [!DNL Insight Server] cluster, è sufficiente modificare il file di configurazione Controllo accesso.
