---
description: Il dashboard richiede alcune autorizzazioni di sola lettura per poter accedere e visualizzare i dati di Data Workbench. I privilegi di scrittura non sono richiesti.
title: Configurazione del controllo di accesso
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# Configurazione del controllo di accesso{#configuring-access-control}

Il dashboard richiede alcune autorizzazioni di sola lettura per poter accedere e visualizzare i dati di Data Workbench. I privilegi di scrittura non sono richiesti.

La configurazione del controllo di accesso comporta la modifica del file [!DNL Access Control.cfg] sulle FSU e l’aggiunta di un nuovo gruppo per concedere l’autorizzazione al dashboard di Data Workbench:

1. Modifica il file [!DNL AccessControl.cfg] (preferibilmente utilizzando la workstation Data Workbench).
1. Crea un nuovo gruppo denominato *Accesso dashboard di Insight*.
1. Sotto i membri di questo gruppo, aggiungi la NC appropriata fornita a questo scopo (Esempio: CN:INSIGHT-USER01). Contattare l&#39;Assistenza clienti Adobe per questo CN.
1. Sotto l’accesso in sola lettura di questo gruppo, modifica l’elenco in modo che rifletta quanto segue:

* /Profili/$
* /Profili/
* /Indirizzi
* /Stato/
* /Utenti/$

1. Rimuovi tutti gli elementi dalla sezione di accesso in lettura e scrittura, in quanto non sono necessarie autorizzazioni di scrittura per il dashboard.
1. Salva le modifiche apportate al file [!DNL AccessControl.cfg] sul server per rendere effettive le autorizzazioni.
