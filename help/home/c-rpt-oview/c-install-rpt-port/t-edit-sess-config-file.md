---
description: Il Report Portal (Portale dei rapporti) utilizza le informazioni contenute in un file di configurazione denominato global.asa per inizializzare le sessioni utente.
title: Modifica del file di configurazione della sessione
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Modifica del file di configurazione della sessione{#edit-the-session-configuration-file}

{{eol}}

Il Report Portal (Portale dei rapporti) utilizza le informazioni contenute in un file di configurazione denominato global.asa per inizializzare le sessioni utente.

Quando installi [!DNL Report Portal], devi modificare il file come indicato. La [!DNL global.asa] Il file si trova nella cartella \*PortalName*\PortalASP\.

>[!NOTE]
>
>Non modificare altri parametri in questo file di configurazione.

1. Sul computer in cui è in esecuzione IIS, apri la [!DNL global.asa] in un editor di testo come Blocco note.
1. Facoltativo. Per consentire agli utenti di accedere [!DNL Report Portal] senza autenticazione, modifica il valore del parametro Session(&quot;In&quot;) in true. Il valore predefinito è false, che autentica tutti gli utenti che tentano di accedere [!DNL Report Portal].
1. Se [!DNL Report Portal] è installato su un&#39;unità diversa dall&#39;unità C, cambia il valore del parametro Session(&quot;Drive&quot;) nella posizione corretta dell&#39;unità.
1. Per il parametro Session(&quot;DBPath&quot;), modifica il valore per riflettere il percorso del database che contiene le informazioni necessarie per l’autenticazione [!DNL Report Portal] utenti. Non includere la lettera di unità, ma assicurarsi di includere una barra finale.

   Esempio: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Salvate il file.
1. Per verificare che [!DNL Report Portal] i file sono stati installati correttamente e possono essere raggiunti attraverso la directory virtuale designata, apri la seguente pagina nel browser:

   https://*YourServerAddress*/*NomePortale*

   Esempio: [!DNL https://localhost/VisualReportPortal]

   Se la [!DNL Report Portal] ASP installati correttamente. Viene visualizzata la pagina di accesso al portale. Se questa pagina non viene visualizzata, verifica che gli ASP siano abilitati in IIS e controlla i mapping delle directory virtuali.
