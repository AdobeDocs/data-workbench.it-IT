---
description: Gli utenti devono disporre di un account valido e devono fornire un nome account e una password quando accedono al Report Portal (Portale dei rapporti).
title: Definire account aggiuntivi
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Definire account aggiuntivi

{{eol}}

Gli utenti devono disporre di un account valido e devono fornire un nome account e una password quando accedono al Report Portal (Portale dei rapporti).

Per impostazione predefinita, l’autenticazione utente è abilitata in [!DNL Report Portal].

Elenco di account validi per [!DNL Report Portal] è conservato nel file di database, [!DNL portal.mdb]. [!DNL Report Portal] è installato con un account con privilegi amministrativi:

* Nome account: test
* Password: user

>[!NOTE]
>
>Per motivi di sicurezza, Adobe consiglia di cambiare la password per questo account dopo l&#39;installazione [!DNL Report Portal].

Per aggiungere account utente a [!DNL Report Portal] o modificare le informazioni relative ai conti esistenti, si utilizza il [!DNL Admin] nella scheda [!DNL Report Portal] interfaccia utente.

Ogni volta che aggiungi un nuovo account o ne modifichi uno esistente, viene inviata un’e-mail di conferma come specificato in [!DNL email.asp] nella cartella \*PortalName*\PortalASP. Per ulteriori informazioni, consulta [Modifica il file Email.asp](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Per i passaggi per aggiungere altri utenti, consulta [Utilizzo degli account](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Facoltativamente, puoi disabilitare l’autenticazione utente e consentire l’accesso anonimo a [!DNL Report Portal]. Per i passaggi necessari, consulta le informazioni sul parametro Session(&quot;In&quot;) in [Modifica del file di configurazione della sessione](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
