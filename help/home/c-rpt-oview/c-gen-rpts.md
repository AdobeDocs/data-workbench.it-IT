---
description: Genera rapporti elaborando le aree di lavoro e specificandole come rapporti.
title: Generazione di rapporti
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# Generazione di rapporti{#generating-reports}

{{eol}}

Genera rapporti elaborando le aree di lavoro e specificandole come rapporti.

[!DNL Report] genera i rapporti in base all&#39;intervallo impostato nel [!DNL Every] nel [!DNL Report.cfg] (ad esempio [!DNL "day],&quot; che elabora il rapporto su base giornaliera) e basato sull&#39;altro [!DNL Report.cfg] impostazioni file.

Durante la generazione dei rapporti, la percentuale di completamento viene visualizzata nella sezione [!DNL Reports] sotto la miniatura del rapporto specifico. Se [!DNL Report] rileva un problema durante la generazione del rapporto; il messaggio di errore più recente viene visualizzato in [!DNL Reports] nella cartella del set di rapporti. Se [!DNL Report] rileva un errore per un particolare report e continua a elaborare gli altri report nel set.

Puoi generare i rapporti in un set di rapporti in uno o tutti i formati seguenti utilizzando [!DNL Report Types] nel [!DNL Report.cfg] file:

* File Excel Microsoft ( [!DNL .xls] o [!DNL .xlsx])
* File grafico di rete portatile ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Insieme ai tipi di output specificati, [!DNL Report] crea un [!DNL .xml] file con lo stesso nome del report. Questo *`<report name>`* Il file .xml contiene la descrizione del report che viene visualizzata in Data Workbench sul [!DNL Reports] sotto la miniatura del rapporto. In questo modo la descrizione diventa disponibile per la distribuzione dei rapporti tramite un portale di reporting. Per informazioni sulla [!DNL Report Portal], vedi [Utilizzo del Report Portal (Portale dei rapporti)](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Se ridefinisci una metrica interna, il sistema si comporta in modo imprevisto a causa del valore errato. I rapporti non verranno generati a meno che una metrica non legga il 100%. È consigliabile non modificare le definizioni delle metriche.
