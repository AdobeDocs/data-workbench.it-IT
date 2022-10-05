---
description: Il dashboard richiede alcune autorizzazioni di sola lettura per poter accedere e visualizzare i dati di Data Workbench. I privilegi di scrittura non sono richiesti.
title: Configurazione del controllo di accesso al dashboard
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 2%

---

# Configurazione del controllo di accesso al dashboard{#configuring-dashboard-access-control}

{{eol}}

Il dashboard richiede alcune autorizzazioni di sola lettura per poter accedere e visualizzare i dati di Data Workbench. I privilegi di scrittura non sono richiesti.

La configurazione del controllo di accesso comporta la modifica del [!DNL Access Control.cfg] file sulle FSU e aggiunta di un nuovo gruppo per concedere l’autorizzazione al dashboard di Data Workbench:

1. Modifica le [!DNL AccessControl.cfg] file (preferibilmente utilizzando la workstation Data Workbench).
1. Crea un nuovo gruppo denominato *Accesso al dashboard di Insight*.
1. Sotto i membri di questo gruppo, aggiungi la NC appropriata fornita a questo scopo (Esempio: CN:INSIGHT-USER01). Contattare l&#39;Assistenza clienti Adobe per questo CN.
1. Sotto l’accesso in sola lettura di questo gruppo, modifica l’elenco in modo che rifletta quanto segue:

* /Profili/$
* /Profili/
* /Indirizzi
* /Stato/
* /Utenti/$

1. Rimuovi tutti gli elementi dalla sezione di accesso in lettura e scrittura, in quanto non sono necessarie autorizzazioni di scrittura per il dashboard.
1. Salva le modifiche apportate al [!DNL AccessControl.cfg] al server per rendere effettive le autorizzazioni.
