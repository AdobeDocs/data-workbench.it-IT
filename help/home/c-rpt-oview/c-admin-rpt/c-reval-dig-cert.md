---
description: Dopo l'installazione, il certificato digitale rilasciato da Adobe funge da chiave che consente di eseguire Report Server.
title: Nuova convalida del certificato digitale (panoramica)
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# Nuova convalida del certificato digitale{#re-validating-the-digital-certificate}

{{eol}}

Dopo l&#39;installazione, il certificato digitale rilasciato da Adobe funge da chiave che consente di eseguire Report Server.

**Frequenza consigliata:** Se necessario

Per funzionare correttamente, un certificato digitale deve essere corrente.

Per rimanere aggiornato, il certificato digitale deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma questo può variare a seconda del contratto con l’Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalida è assolutamente semplice. [!DNL Report Server] si connette automaticamente al server licenze Adobe e, se necessario, riconvalida il certificato. Se il computer non dispone di accesso a Internet, è necessario scaricare un nuovo certificato convalidato dal server licenze Adobe e installarlo sul computer utilizzando i passaggi descritti in [Download e installazione del certificato digitale](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
