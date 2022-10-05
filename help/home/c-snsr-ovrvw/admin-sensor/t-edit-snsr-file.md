---
description: Il file di configurazione Sensor, txlogd.conf, contiene parametri utilizzati da Sensor per stabilire una connessione con il server di Data Workbench.
title: Modifica del file di Sensor txlogd.conf
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Modifica del file di Sensor txlogd.conf{#editing-the-sensor-txlogd-conf-file}

{{eol}}

Il file di configurazione Sensor, txlogd.conf, contiene parametri utilizzati da Sensor per stabilire una connessione con il server di Data Workbench.

Questi parametri includono l’indirizzo del server, il numero di porta e il protocollo di comunicazione (HTTP o HTTPS). Il file di configurazione contiene anche opzioni di filtro del contenuto di registro e informazioni di esperimento controllate. Gli esperimenti controllati consentono ai designer del sito di eseguire esperimenti per testare il contenuto o modificare la progettazione su un sottoinsieme di tutti i visitatori del sito.

Quando si cambiano gli altri [!DNL txlogd.conf] , come l&#39;indirizzo IP del [!DNL data workbench server] o il nome [!DNL Sensor], puoi semplicemente sostituire [!DNL txlogd.conf] con la versione aggiornata e [!DNL Sensor] acquisirà automaticamente le modifiche. Su alcuni sistemi, potrebbe non essere possibile modificare o sostituire il file senza interrompere il server web o il processo del trasmettitore.

**Per aprire e modificare txlogd.conf**

1. Sfoglia il [!DNL Sensor] directory di installazione e aprire [!DNL txlogd.conf] in un editor di testo.
1. Modifica il file come necessario.
1. Salva e chiudi il file.

   * La posizione del file di configurazione dell&#39;esperimento controllato (definito dal parametro ExpFile nel [!DNL txlogd.conf] file) deve trovarsi in una directory sul server web accessibile agli sviluppatori di contenuti web o controllata dal sistema di gestione dei contenuti.
   * Il valore nel parametro ExpCookieURL è una pagina virtuale utilizzata per testare i siti web. A un utente che accede a tale pagina verrà assegnato un nuovo ID di tracciamento.

Per ulteriori informazioni sull’utilizzo di [!DNL txlogd.conf], contattare l&#39;Adobe Consulting Services.
