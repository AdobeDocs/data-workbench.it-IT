---
description: Il dashboard richiede determinate autorizzazioni di sola lettura per poter accedere e visualizzare i dati del workbench dati. I privilegi di scrittura non sono richiesti.
solution: Analytics
title: Configurazione del controllo di accesso
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione del controllo di accesso{#configuring-access-control}

Il dashboard richiede determinate autorizzazioni di sola lettura per poter accedere e visualizzare i dati del workbench dati. I privilegi di scrittura non sono richiesti.

La configurazione del controllo di accesso prevede la modifica del [!DNL Access Control.cfg] file sugli FSU e l&#39;aggiunta di un nuovo gruppo per concedere l&#39;autorizzazione al dashboard del workbench dati:

1. Modificare il [!DNL AccessControl.cfg] file (preferibilmente utilizzando la workstation workbench dati).
1. Create un nuovo gruppo denominato *Insight Dashboard Access*.
1. Per i membri di questo gruppo, aggiungete il CN appropriato fornito a tale scopo (esempio: CN:INSIGHT-USER01). Contatta l’Assistenza clienti Adobe per ottenere questo CN.
1. Sotto l’accesso in sola lettura di questo gruppo, modificate l’elenco in modo che rifletta quanto segue:

* /Profili/$
* /Profili/
* /Indirizzi
* /Stato/
* /Utenti/$

1. Rimuovete tutti gli elementi dalla sezione di accesso in lettura/scrittura, in quanto non sono necessarie autorizzazioni di scrittura per il dashboard.
1. Salvate le modifiche al [!DNL AccessControl.cfg] file sul server per rendere effettive le autorizzazioni.
