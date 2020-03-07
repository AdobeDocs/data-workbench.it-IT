---
description: Il portale di report utilizza le informazioni contenute in un file di configurazione denominato global.asa per inizializzare le sessioni utente.
solution: Analytics
title: Modifica del file di configurazione della sessione
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica del file di configurazione della sessione{#edit-the-session-configuration-file}

Il portale di report utilizza le informazioni contenute in un file di configurazione denominato global.asa per inizializzare le sessioni utente.

Al momento dell&#39;installazione [!DNL Report Portal], dovete modificare il file come indicato. Il [!DNL global.asa] file risiede in \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Non modificate altri parametri in questo file di configurazione.

1. Nel computer in cui è in esecuzione IIS, aprite il [!DNL global.asa] file in un editor di testo come Blocco note.
1. Facoltativo. Per consentire agli utenti di accedere [!DNL Report Portal] senza autenticazione, impostate il valore del parametro Session(&quot;In&quot;) su true. Il valore predefinito è false, che esegue l&#39;autenticazione di tutti gli utenti che tentano di accedere [!DNL Report Portal].
1. Se [!DNL Report Portal] è installato su un&#39;unità diversa dall&#39;unità C, modificate il valore del parametro Session(&quot;Drive&quot;) nella posizione corretta dell&#39;unità.
1. Per il parametro Session(&quot;DBPath&quot;), modificate il valore per riflettere il percorso del database che contiene le informazioni necessarie per l&#39;autenticazione [!DNL Report Portal] degli utenti. Non includete la lettera di unità, ma accertatevi di includere una barra finale.

   Esempio: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Salvate il file.
1. Per verificare che i [!DNL Report Portal] file siano stati installati correttamente e possano essere raggiunti attraverso la directory virtuale designata, aprite la pagina seguente nel browser:

   http://*YourServerAddress*/*YourPortalName*

   Esempio: [!DNL http://localhost/VisualReportPortal]

   Se gli [!DNL Report Portal] ASP sono stati installati correttamente, verrà visualizzata la pagina di accesso al portale. Se non viene visualizzata questa pagina, verificare che gli ASP siano abilitati in IIS e, quindi, controllare i mapping delle directory virtuali.

