---
description: In alcuni casi, potrebbe essere necessario aggiungere un computer Insight Server a un cluster Insight Server esistente.
title: Aggiunta di Insight Server a un cluster esistente
uuid: 951bd6fe-14e4-4192-917c-342fde7b43ba
exl-id: 9845c13b-781c-43e9-aaa1-e31418c93ef0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 12%

---

# Aggiunta di Insight Server a un cluster esistente{#adding-insight-servers-to-an-existing-cluster}

In alcuni casi, potrebbe essere necessario aggiungere un computer Insight Server a un cluster Insight Server esistente.

Quando si aggiunge una DPU [!DNL Insight Server] o [!DNL Insight Server] FSU a un cluster, è necessario aggiornare i file di configurazione sul master [!DNL Insight Server] per includere le informazioni sull&#39;indirizzo per i nuovi computer e impostare la nuova DPU o FSU.

>[!NOTE]
>
>Le procedure descritte in questa sezione richiedono [!DNL Insight]. Se non hai installato [!DNL Insight], segui le istruzioni contenute nella * [!DNL Insight] Guida utente* prima di procedere.
