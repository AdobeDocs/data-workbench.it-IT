---
description: Genera rapporti elaborando le aree di lavoro e specificandole come rapporti.
title: Generazione di rapporti
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# Generazione di rapporti{#generating-reports}

Genera rapporti elaborando le aree di lavoro e specificandole come rapporti.

[!DNL Report] genera i rapporti in base all’intervallo impostato nel  [!DNL Every] parametro nel  [!DNL Report.cfg] file (ad esempio  [!DNL "day]&quot;, che elabora il rapporto su base giornaliera) e in base alle altre impostazioni di  [!DNL Report.cfg] file.

Durante la generazione dei rapporti, la percentuale di completamento viene visualizzata nella scheda [!DNL Reports] sotto la miniatura del rapporto specifico. Se [!DNL Report] rileva un problema durante la generazione del rapporto, il messaggio di errore più recente viene visualizzato nella scheda [!DNL Reports] della cartella del set di rapporti. Se [!DNL Report] rileva un errore per un particolare rapporto, continua a elaborare gli altri rapporti del set.

Puoi generare i rapporti in un set di rapporti in uno o tutti i formati seguenti utilizzando il parametro [!DNL Report Types] nel file [!DNL Report.cfg] :

* File Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx])
* File grafico di rete portatile ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Insieme ai tipi di output specificati, [!DNL Report] crea un file [!DNL .xml] denominato uguale al rapporto. Questo file *`<report name>`*.xml contiene la descrizione del rapporto che viene visualizzata in Data Workbench nella scheda [!DNL Reports] sotto la miniatura del rapporto. In questo modo la descrizione diventa disponibile per la distribuzione dei rapporti tramite un portale di reporting. Per informazioni su [!DNL Report Portal], consulta [Utilizzo del Report Portal (Portale dei rapporti)](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Se ridefinisci una metrica interna, il sistema si comporta in modo imprevisto a causa del valore errato. I rapporti non verranno generati a meno che una metrica non legga il 100%. È consigliabile non modificare le definizioni delle metriche.
