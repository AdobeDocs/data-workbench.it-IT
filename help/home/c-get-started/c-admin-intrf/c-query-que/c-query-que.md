---
description: Normalmente, il server di Data Workbench risponde alle query utente in arrivo man mano che vengono ricevute e continua a fornire risultati e aggiornamenti in tempo reale fino a quando l'utente non le richiede più.
title: Coda query
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Coda query{#query-queue}

Normalmente, il server di Data Workbench risponde alle query utente in arrivo man mano che vengono ricevute e continua a fornire risultati e aggiornamenti in tempo reale fino a quando l&#39;utente non le richiede più.

A volte, in particolare nei sistemi con molti utenti di Data Workbench, il numero di query attive richiede più risorse di sistema rispetto a quelle disponibili dal server. [!DNL Query Queue] consente al server di bloccare temporaneamente alcune query fino a quando non saranno disponibili le risorse necessarie per fornire risposte. [!DNL Query Queue] fornisce inoltre funzionalità per assegnare priorità alle query in base a una varietà di parametri, in modo che in caso di conflitto di risorse, le query con priorità più elevata ricevano prima risposta.

Le query da un singolo client o server di report vengono posizionate in un gruppo e pianificate come un&#39;unità. È possibile configurare i monitor delle risorse per limitare la quantità di determinate risorse di sistema utilizzate dalle query. Quando le risorse monitorate consentono la pianificazione di un altro gruppo di query, il gruppo con priorità più elevata è pianificato. Gli utenti le cui query non sono ancora pianificate, a causa di limitazioni delle risorse, non ricevono un errore ma ricevono una notifica che informa che le loro query sono in coda e l&#39;utente può continuare a lavorare sull&#39;esempio locale.

La configurazione predefinita include una configurazione semplice per [!DNL Query Queue], ma la lascia disabilitata. Gli amministratori possono abilitare o disabilitare [!DNL Query Queue], configurare i monitor delle risorse per determinare la quantità di risorse utilizzate per le query e configurare criteri di definizione delle priorità complessi per utenti diversi.

**Per configurare il file Server.cfg per[!DNL Query Queuing]**

1. Apri [!DNL Server.cfg] facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Server.cfg]** e rendilo locale per la modifica.
1. Espandi [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configura i seguenti parametri:

   * **Gruppi di utenti:** ti consente di configurare criteri, utenti e la priorità della coda. Per le definizioni, vedere [Gruppi utente coda query](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).

   * **Attivo:**  (vettore) abilita o disabilita il  [!DNL Query Queue]. I valori validi sono true o false. L&#39;impostazione predefinita è false.

   * **Gruppo di utenti predefinito:**  (stringa) Digitare un nome del gruppo di utenti a cui vengono aggiunti gli utenti, se non sono elencati in alcun gruppo di utenti.
   * **Monitoraggio risorse:**  (vettore) Fai clic con il pulsante destro del mouse per aggiungere un monitoraggio risorse. È possibile specificare se la [!DNL Query Queue] controlla la memoria o il numero di query. Fare clic con il pulsante destro del mouse su **[!UICONTROL Resource Monitor]** per scegliere Monitor budget memoria o Monitor numero di query. Per ulteriori informazioni, consulta [Monitoraggio risorse coda query](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) .

   * **Priorità non toccabile:** (Int) Specifica che i bundle con una priorità maggiore o uguale a questo valore non sono mai prevenuti alla pianificazione di bundle con priorità più alta. Utilizzato in combinazione con la [!DNL Memory Budget Monitor] descritta nella [Tabella dei parametri del gruppo di utenti](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
