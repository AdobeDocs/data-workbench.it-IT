---
description: Dopo l'installazione, il certificato digitale emesso da Adobe funge da chiave per l'esecuzione del server di report.
solution: Analytics
title: Nuova convalida del certificato digitale
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nuova convalida del certificato digitale{#re-validating-the-digital-certificate}

Dopo l&#39;installazione, il certificato digitale emesso da Adobe funge da chiave per l&#39;esecuzione del server di report.

**Frequenza consigliata:** Se necessario

Per funzionare correttamente, è necessario che sia corrente un certificato digitale.

Per restare aggiornati, il certificato digitale deve essere convalidato nuovamente su base regolare (generalmente, ogni 30 giorni, ma questo può variare a seconda del contratto con Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalidazione è completamente trasparente. [!DNL Report Server] si connette automaticamente ad Adobe License Server e, se necessario, riconvalida il certificato. Se il computer non dispone dell&#39;accesso a Internet, è necessario scaricare un nuovo certificato convalidato dal server delle licenze Adobe e installarlo sul computer utilizzando i passaggi forniti in [Download e installazione del certificato](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)digitale.
