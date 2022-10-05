---
description: Puoi personalizzare l’aspetto dei menu, compreso il menu della finestra dell’area di lavoro (a cui puoi accedere facendo clic con il pulsante destro del mouse in un’area di lavoro) e dei menu che elencano metriche, dimensioni e livelli di mappatura.
title: Personalizzare un menu
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Personalizzare un menu{#customize-a-menu}

{{eol}}

Puoi personalizzare l’aspetto dei menu, compreso il menu della finestra dell’area di lavoro (a cui puoi accedere facendo clic con il pulsante destro del mouse in un’area di lavoro) e dei menu che elencano metriche, dimensioni e livelli di mappatura.

La gerarchia di qualsiasi menu rispecchia la struttura della relativa directory [!DNL Profile Manager]. Ad esempio, il menu della finestra dell&#39;area di lavoro rispecchia la struttura della directory Menu e il menu metriche rispecchia la struttura della directory Metriche. Per qualsiasi menu, la directory corrispondente può contenere i seguenti elementi:

* **File:** Questi file rappresentano le visualizzazioni, le legende, le annotazioni, le interfacce amministrative, le metriche, le dimensioni o i livelli di mappa che è possibile aprire facendo clic sulla voce di menu corrispondente.
* **Un [!DNL order.txt] file:** Questo file specifica l&#39;ordine in cui il menu visualizza le relative voci.
* **Sottodirectory:** Ogni sottodirectory rappresenta un sottomenu. Ciascuna sottodirectory può contenere i propri file, sottodirectory e [!DNL order.txt] file.

Ad esempio, il [!DNL Add Legend] contiene le voci di menu Metrica, Colore, Valore e Affidabilità, in tale ordine. Al confronto, la directory Menu\Add Legend in [!DNL Profile Manager] contiene i file [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]e [!DNL Value.vw] file in ordine alfabetico, nonché [!DNL order.txt] per controllare l&#39;ordine degli altri file.
