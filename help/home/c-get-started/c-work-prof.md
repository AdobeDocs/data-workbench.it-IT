---
description: Data Workbench scarica i profili nel computer.
title: Profili
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Profili{#profiles}

{{eol}}

Data Workbench scarica i profili nel computer.

Se carichi un profilo per la prima volta, devi disporre di una connessione di rete per [!DNL Data Workbench server] e lavorare online in modo che Data Workbench possa scaricare i file necessari dal [!DNL Data Workbench server].

Il download del profilo potrebbe richiedere alcuni minuti. Non dovresti iniziare a lavorare con il profilo fino a quando la Data Cache non inizia a riempirsi, ma non devi aspettare finché non è piena. Puoi monitorare l’avanzamento della cache dei dati, l’avanzamento della sincronizzazione del profilo e la data e l’ora dei dati elaborati più di recente, guardando le barre di stato al caricamento del profilo.

>[!NOTE]
>
>I dati non vengono visualizzati nelle visualizzazioni aggiunte fino a quando la cache dei dati non inizia a riempirsi.

Al successivo caricamento del profilo, gli aggiornamenti al profilo e ai relativi dati vengono scaricati solo se disponi di una connessione di rete al [!DNL Data Workbench server] e stanno lavorando online. Se lavori offline, il profilo e i relativi dati vengono caricati dalla cache del computer. In questo caso, visualizzi la versione del profilo e dei dati scaricati l’ultima volta che hai lavorato online con il profilo. Per ulteriori informazioni sull&#39;utilizzo online e offline, vedi [Utilizzo offline e online](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Quando devi modificare il tuo profilo (utilizzando [!DNL Profile Manager] o [!DNL Server Files Manager]), devi lavorare online per assicurarti di disporre della versione più aggiornata del profilo. Per ulteriori informazioni sulla [!DNL Profile Manager] e [!DNL Server Files Manager], vedi [Interfacce amministrative](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Se non riesci ad accedere a un profilo o a caricarlo, potrebbe essere necessario confermare quanto segue:

* È disponibile una connessione di rete per [!DNL Data Workbench server] computer in cui risiede il profilo.
* disponi delle autorizzazioni appropriate per accedere al profilo.

Per assistenza, contattare l&#39;amministratore di sistema.

## Caricamento o commutazione dei profili {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Data Workbench Launch.
1. Nella barra laterale, fai clic sul nome del profilo e fai clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, dove *nome profilo* è il profilo con cui desideri lavorare.

   ![](assets/sidebar_profile.png)

Se si tratta della prima volta che carichi il profilo selezionato, potrebbero essere necessari diversi minuti per scaricare dati sufficienti per compilare una visualizzazione.

## Accesso a un profilo in un cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench gli utenti che accedono a un profilo in esecuzione su un

Il cluster del server di Data Workbench identifica solo il server Data Workbench master nel file di configurazione della Data Workbench ( [!DNL Insight.cfg]). Dal punto di vista dell’utente di Data Workbench, il profilo è accessibile su un solo server Data Workbench (il server di Data Workbench principale). Tuttavia, le richieste di query da parte degli analisti possono essere indirizzate a qualsiasi server Data Workbench nel cluster.

Per ulteriori informazioni sui profili in esecuzione su un cluster di Data Workbench Server, consulta la sezione *Guida all’installazione e all’amministrazione dei prodotti server*.
