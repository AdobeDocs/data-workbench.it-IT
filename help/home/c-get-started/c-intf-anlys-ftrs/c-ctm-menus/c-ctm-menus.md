---
description: Potete personalizzare l’aspetto dei menu, compreso il menu della finestra dell’area di lavoro (a cui si accede facendo clic con il pulsante destro del mouse in qualsiasi area di lavoro) e dei menu in cui sono elencate le metriche, le dimensioni e i livelli di mappa.
solution: Analytics
title: Personalizzare un menu
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalizzare un menu{#customize-a-menu}

Potete personalizzare l’aspetto dei menu, compreso il menu della finestra dell’area di lavoro (a cui si accede facendo clic con il pulsante destro del mouse in qualsiasi area di lavoro) e dei menu in cui sono elencate le metriche, le dimensioni e i livelli di mappa.

La gerarchia di qualsiasi menu rispecchia la struttura della relativa directory nel [!DNL Profile Manager]. Ad esempio, il menu della finestra dell&#39;area di lavoro riflette la struttura della directory Menu e il menu delle metriche riflette la struttura della directory Metrics. Per qualsiasi menu, la directory corrispondente può contenere i seguenti elementi:

* **File:** Questi file rappresentano le visualizzazioni, le legende, le annotazioni, le interfacce amministrative, le metriche, le dimensioni o i livelli di mappa che potete aprire facendo clic sulla voce di menu corrispondente.
* **Un[!DNL order.txt]file:** Questo file specifica in quale ordine il menu visualizza le voci.
* **Sottodirectory:** Ogni sottodirectory rappresenta un sottomenu. Ogni sottodirectory può contenere file, sottodirectory e [!DNL order.txt] file propri.

Ad esempio, il [!DNL Add Legend] menu contiene le voci di menu Metrica, Colore, Valore e Confidenza, in tale ordine. Al confronto, la directory Menu\Add Legend [!DNL Profile Manager] contiene i file [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]e [!DNL Value.vw] i file in ordine alfabetico, nonché un [!DNL order.txt] file per controllare l&#39;ordine degli altri file.
