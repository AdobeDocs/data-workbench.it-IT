---
description: Gli utenti devono avere un account valido e fornire un nome account e una password quando accedono al portale dei report.
solution: Analytics
title: Definisci account aggiuntivi
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definisci account aggiuntivi{#define-additional-accounts}

Gli utenti devono avere un account valido e fornire un nome account e una password quando accedono al portale dei report.

Per impostazione predefinita, l&#39;autenticazione utente è abilitata in [!DNL Report Portal].

L&#39;elenco di account validi [!DNL Report Portal] viene mantenuto nel file di database, [!DNL portal.mdb]. [!DNL Report Portal] è installato con un account con privilegi amministrativi:

* Nome account: test
* Password: user

>[!NOTE]
>
>Per motivi di sicurezza, Adobe consiglia di cambiare la password per questo account dopo l&#39;installazione [!DNL Report Portal].

Per aggiungere account utente [!DNL Report Portal] o modificare le informazioni relative agli account esistenti, utilizzate la [!DNL Admin] scheda nell&#39;interfaccia [!DNL Report Portal] utente.

Ogni volta che aggiungete un nuovo account o modificate un account esistente, viene inviato un messaggio e-mail di conferma come specificato nel [!DNL email.asp] file nella cartella \*PortalName*\PortalASP. Per ulteriori informazioni, consultate [Modificare il file](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)Email.asp.

Per i passaggi per aggiungere altri utenti, consultate [Utilizzo degli account](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Facoltativamente, potete disabilitare l&#39;autenticazione utente e consentire l&#39;accesso anonimo a [!DNL Report Portal]. Per i passaggi necessari, consultate le informazioni sul parametro Session(&quot;In&quot;) in [Modifica del file](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)di configurazione della sessione.

