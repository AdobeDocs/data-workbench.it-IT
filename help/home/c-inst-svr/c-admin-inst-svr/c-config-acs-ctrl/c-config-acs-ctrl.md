---
description: Il file di configurazione del controllo di accesso, Access Control.cfg, definisce i gruppi di controllo di accesso in base ai quali Insight Server concede le autorizzazioni ai file in base agli attributi (OU, CN e così via) del certificato della connessione in ingresso.
title: Configurazione del controllo di accesso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configurazione del controllo di accesso{#configuring-access-control}

Il file di configurazione del controllo di accesso, Access Control.cfg, definisce i gruppi di controllo di accesso in base ai quali Insight Server concede le autorizzazioni ai file in base agli attributi (OU, CN e così via) del certificato della connessione in ingresso.

**Frequenza consigliata:** in base alle esigenze

[!DNL Insight Server] fornisce gruppi di controllo di accesso configurabili per gestire la sicurezza delle connessioni a  [!DNL Insight Server]. I gruppi di controllo degli accessi identificano gli utenti autorizzati a eseguire funzioni amministrative tramite [!DNL Insight].

Se è necessario fornire l&#39;accesso a nuovi utenti o a nuovi computer, ad esempio quando si aggiunge un computer a un cluster [!DNL Insight Server], è sufficiente modificare il file di configurazione di Access Control.
