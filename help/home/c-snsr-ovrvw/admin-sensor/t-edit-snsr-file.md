---
description: Il file di configurazione Sensor, txlogd.conf, contiene parametri che Sensor utilizza per stabilire una connessione con il server workbench dati.
solution: Analytics
title: Modifica del file di Sensor txlogd.conf
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---


# Modifica del file di Sensor txlogd.conf{#editing-the-sensor-txlogd-conf-file}

Il file di configurazione Sensor, txlogd.conf, contiene parametri che Sensor utilizza per stabilire una connessione con il server workbench dati.

Questi parametri includono l&#39;indirizzo del server, il numero di porta e il protocollo di comunicazione (HTTP o HTTPS). Il file di configurazione contiene anche opzioni di filtraggio del contenuto del registro e informazioni sull&#39;esperimento controllato. Gli esperimenti controllati consentono ai progettisti del sito di eseguire esperimenti per testare il contenuto o apportare modifiche alla progettazione su un sottoinsieme di tutti i visitatori del sito.

Quando si modificano altri [!DNL txlogd.conf] parametri, come l&#39;indirizzo IP [!DNL data workbench server] o il nome dell&#39; [!DNL Sensor], è possibile semplicemente sostituire [!DNL txlogd.conf] con la versione aggiornata e [!DNL Sensor] le modifiche verranno automaticamente rilevate. In alcuni sistemi, potrebbe non essere possibile modificare o sostituire il file senza arrestare il server Web o il processo del trasmettitore.

**Per aprire e modificare txlogd.conf**

1. Individuate la directory di [!DNL Sensor] installazione e aprite il [!DNL txlogd.conf] file in un editor di testo.
1. Modificate il file come necessario.
1. Salvate e chiudete il file.

   * La posizione del file di configurazione dell&#39;esperimento controllato (definito dal parametro ExpFile nel [!DNL txlogd.conf] file) deve trovarsi in una directory del server Web accessibile agli sviluppatori di contenuti Web o controllata dal sistema di gestione dei contenuti.
   * Il valore nel parametro ExpCookieURL è una pagina virtuale utilizzata per testare i siti Web. A un utente che accede a tale pagina verrà assegnato un nuovo ID di tracciamento.

Per ulteriori informazioni sull&#39;utilizzo [!DNL txlogd.conf], contattare  Adobe Consulting Services.
