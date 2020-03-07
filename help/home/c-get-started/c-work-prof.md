---
description: Workbench dati scarica i profili sul computer.
title: Profili
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profiles{#profiles}

Workbench dati scarica i profili sul computer.

Se si sta caricando un profilo per la prima volta, è necessario disporre di una connessione di rete al profilo [!DNL Data Workbench server] e lavorare online in modo che Workbench dati possa scaricare i file necessari dal [!DNL Data Workbench server].

Il download del profilo potrebbe richiedere alcuni minuti. Non iniziare a lavorare con il profilo fino a quando la cache dei dati non inizia a riempirsi, ma non devi aspettare che sia piena. È possibile monitorare l&#39;avanzamento della cache dei dati, l&#39;avanzamento della sincronizzazione del profilo e la data e l&#39;ora dei dati elaborati più di recente, esaminando le barre di stato durante il caricamento del profilo.

>[!NOTE]
>
>I dati non vengono visualizzati nelle visualizzazioni aggiunte fino a quando la cache dei dati non inizia a riempirsi.

Al successivo caricamento del profilo, gli aggiornamenti al profilo e ai relativi dati vengono scaricati solo se si dispone di una connessione di rete al profilo [!DNL Data Workbench server] e se si lavora in linea. Se state lavorando offline, il profilo e i relativi dati vengono caricati dalla cache del computer. In questo caso, state visualizzando la versione del profilo e dei dati scaricati l&#39;ultima volta che avete lavorato online con il profilo. Per ulteriori informazioni sull’utilizzo online e offline, consultate [Utilizzo offline e online](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Per modificare il profilo (utilizzando il [!DNL Profile Manager] o il [!DNL Server Files Manager]), è necessario lavorare online per assicurarsi di disporre della versione più aggiornata del profilo. Per ulteriori informazioni su [!DNL Profile Manager] e [!DNL Server Files Manager], consulta Interfacce [amministrative](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Se non è possibile accedere o caricare un profilo, potrebbe essere necessario confermare quanto segue:

* È disponibile una connessione di rete con il [!DNL Data Workbench server] computer in cui risiede il profilo.
* disponete delle autorizzazioni appropriate per accedere al profilo.

Per assistenza, contattate l&#39;amministratore di sistema.

## Caricamento o sostituzione dei profili {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Avvia Workbench dati.
1. Nella barra laterale, fate clic sul nome del profilo e fate clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, dove il nome *del* profilo è il profilo con cui desiderate lavorare.

   ![](assets/sidebar_profile.png)

Se si tratta della prima volta che caricate il profilo selezionato, potrebbero essere necessari alcuni minuti per scaricare dati sufficienti a compilare una visualizzazione.

## Accesso a un profilo su un cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Utenti di Workbench dati che accedono a un profilo in esecuzione su un

il cluster del server workbench dati identifica solo il server Workbench dati principale nel file di configurazione del Workbench dati ( [!DNL Insight.cfg]). Dal punto di vista dell&#39;utente di Workbench dati, il profilo è accessibile solo su un server Workbench dati (il server Workbench dati master). Tuttavia, le richieste di query degli analisti possono essere indirizzate a qualsiasi server Workbench dati del cluster.

Per ulteriori informazioni sui profili in esecuzione su un cluster di Workbench Server, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*.
