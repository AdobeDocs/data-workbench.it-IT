---
description: Puoi personalizzare l’aspetto dei menu, compreso il menu della finestra dell’area di lavoro (a cui puoi accedere facendo clic con il pulsante destro del mouse in un’area di lavoro) e dei menu che elencano metriche, dimensioni e livelli di mappatura.
title: Personalizzare un menu
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Personalizzare un menu{#customize-a-menu}

Puoi personalizzare l’aspetto dei menu, compreso il menu della finestra dell’area di lavoro (a cui puoi accedere facendo clic con il pulsante destro del mouse in un’area di lavoro) e dei menu che elencano metriche, dimensioni e livelli di mappatura.

La gerarchia di qualsiasi menu riflette la struttura della relativa directory nel [!DNL Profile Manager]. Ad esempio, il menu della finestra dell&#39;area di lavoro rispecchia la struttura della directory Menu e il menu metriche rispecchia la struttura della directory Metriche. Per qualsiasi menu, la directory corrispondente può contenere i seguenti elementi:

* **File:** questi file rappresentano le visualizzazioni, le legende, le annotazioni, le interfacce amministrative, le metriche, le dimensioni o i livelli di mappa che possono essere aperti facendo clic sulla voce di menu corrispondente.
* **Un  [!DNL order.txt] file:** questo file specifica l&#39;ordine in cui il menu visualizza le relative voci.
* **Sottodirectory:** ogni sottodirectory rappresenta un sottomenu. Ogni sottodirectory può contenere i propri file, sottodirectory e file [!DNL order.txt].

Ad esempio, il menu [!DNL Add Legend] contiene le voci di menu Metrica, Colore, Valore e Affidabilità, in tale ordine. Al contrario, la directory Menu\Add Legend in [!DNL Profile Manager] contiene i file [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw] e i file [!DNL Value.vw] in ordine alfabetico, nonché un file [!DNL order.txt] per controllare l&#39;ordine degli altri file.
