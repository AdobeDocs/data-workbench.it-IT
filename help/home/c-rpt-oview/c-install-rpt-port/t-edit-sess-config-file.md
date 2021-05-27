---
description: Il Report Portal (Portale dei rapporti) utilizza le informazioni contenute in un file di configurazione denominato global.asa per inizializzare le sessioni utente.
title: Modifica del file di configurazione della sessione
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Modifica del file di configurazione della sessione{#edit-the-session-configuration-file}

Il Report Portal (Portale dei rapporti) utilizza le informazioni contenute in un file di configurazione denominato global.asa per inizializzare le sessioni utente.

Quando installi [!DNL Report Portal], devi modificare questo file come indicato. Il file [!DNL global.asa] risiede in \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Non modificare altri parametri in questo file di configurazione.

1. Sul computer in cui è in esecuzione IIS, apri il file [!DNL global.asa] in un editor di testo come Blocco note.
1. Facoltativo. Per consentire agli utenti di accedere a [!DNL Report Portal] senza autenticazione, cambia il valore del parametro Session(&quot;In&quot;) in true. Il valore predefinito è false, che autentica tutti gli utenti che tentano di accedere a [!DNL Report Portal].
1. Se il [!DNL Report Portal] è installato su un&#39;unità diversa dall&#39;unità C, modificare il valore del parametro Session(&quot;Drive&quot;) nella posizione corretta dell&#39;unità.
1. Per il parametro Session(&quot;DBPath&quot;), modifica il valore per riflettere il percorso del database che contiene le informazioni necessarie per autenticare gli utenti [!DNL Report Portal]. Non includere la lettera di unità, ma assicurarsi di includere una barra finale.

   Esempio: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Salvate il file.
1. Per verificare che i file [!DNL Report Portal] siano stati installati correttamente e possano essere raggiunti tramite la directory virtuale designata, apri la pagina seguente nel browser:

   http://*YourServerAddress*/*NomePortale*

   Esempio:  [!DNL http://localhost/VisualReportPortal]

   Se gli [!DNL Report Portal] ASP sono stati installati correttamente, verrà visualizzata la pagina di accesso al portale. Se questa pagina non viene visualizzata, verifica che gli ASP siano abilitati in IIS e controlla i mapping delle directory virtuali.
