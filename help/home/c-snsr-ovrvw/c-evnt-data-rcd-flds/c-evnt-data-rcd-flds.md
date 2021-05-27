---
description: I file di registro (.vsl) contengono i campi dei dati evento raccolti dai server da Sensor e utilizzati dal server di Data Workbench nel processo di costruzione del set di dati.
title: Campi record dati evento
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 5%

---

# Campi record dati evento{#event-data-record-fields}

I file di registro (.vsl) contengono i campi dei dati evento raccolti dai server da Sensor e utilizzati dal server di Data Workbench nel processo di costruzione del set di dati.

I nomi dei campi generalmente seguono la convenzione di denominazione per il formato di file di registro esteso W3C. In molti campi sono presenti prefissi che indicano l’origine delle informazioni contenute nel campo:

* &quot;cs&quot; indica la comunicazione dal client al server
* &quot;sc&quot; indica la comunicazione dal server al client
* &quot;s&quot; indica informazioni dal server
* &quot;c&quot; indica informazioni provenienti dal client
* &quot;x&quot; indica le informazioni create da un prodotto di Adobe
