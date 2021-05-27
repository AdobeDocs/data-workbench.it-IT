---
description: Gli utenti devono disporre di un account valido e devono fornire un nome account e una password quando accedono al Report Portal (Portale dei rapporti).
title: Definire account aggiuntivi
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Definire account aggiuntivi

Gli utenti devono disporre di un account valido e devono fornire un nome account e una password quando accedono al Report Portal (Portale dei rapporti).

Per impostazione predefinita, l’autenticazione utente è abilitata in [!DNL Report Portal].

L&#39;elenco degli account validi per [!DNL Report Portal] viene mantenuto nel file di database [!DNL portal.mdb]. [!DNL Report Portal] è installato con un account con privilegi amministrativi:

* Nome account: test
* Password: user

>[!NOTE]
>
>Per motivi di sicurezza, l&#39;Adobe consiglia di modificare la password dell&#39;account dopo l&#39;installazione di [!DNL Report Portal].

Per aggiungere account utente a [!DNL Report Portal] o modificare le informazioni relative agli account esistenti, utilizzare la scheda [!DNL Admin] nell&#39;interfaccia utente [!DNL Report Portal].

Ogni volta che si aggiunge un nuovo account o si modifica un account esistente, viene inviato un messaggio e-mail di conferma come specificato nel file [!DNL email.asp] nella cartella \*PortalName*\PortalASP . Per ulteriori informazioni, consulta [Modifica il file Email.asp](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Per i passaggi per aggiungere altri utenti, vedere [Uso degli account](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Facoltativamente, puoi disabilitare l’autenticazione utente e consentire l’accesso anonimo a [!DNL Report Portal]. Per i passaggi necessari, consulta le informazioni sul parametro Session(&quot;In&quot;) in [Modifica il file di configurazione della sessione](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
