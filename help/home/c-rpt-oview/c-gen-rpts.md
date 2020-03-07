---
description: Generare rapporti elaborando aree di lavoro e specificandole come rapporti.
solution: Analytics
title: Generazione di rapporti
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generazione di rapporti{#generating-reports}

Generare rapporti elaborando aree di lavoro e specificandole come rapporti.

[!DNL Report] genera i rapporti all&#39;intervallo impostato nel [!DNL Every] parametro del [!DNL Report.cfg] file (ad esempio, [!DNL "day]&quot;, che elabora il rapporto su base giornaliera) e in base alle altre impostazioni del [!DNL Report.cfg] file.

Durante la generazione dei rapporti, la percentuale di completamento viene visualizzata nella [!DNL Reports] scheda sotto la miniatura del rapporto specifico. Se [!DNL Report] si verifica un problema durante la generazione del rapporto, il messaggio di errore più recente viene visualizzato nella [!DNL Reports] scheda della cartella del set di report. Se [!DNL Report] si verifica un errore per un particolare rapporto, continua a elaborare gli altri rapporti del set.

Potete generare i rapporti in un set di rapporti in uno o tutti i formati seguenti utilizzando il [!DNL Report Types] parametro nel [!DNL Report.cfg] file:

* File di Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx])
* File grafico di rete portatile ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Insieme ai tipi di output specificati, [!DNL Report] crea un [!DNL .xml] file con lo stesso nome del report. Questo file *`<report name>`*.xml contiene la descrizione del rapporto visualizzato in Workbench dati nella [!DNL Reports] scheda sotto la miniatura del rapporto. Questa opzione rende la descrizione disponibile per la distribuzione dei rapporti tramite un portale di reporting. Per informazioni su [!DNL Report Portal], consultate [Utilizzo del portale](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)dei report.

>[!NOTE]
>
>Se si ridefinisce una metrica interna, il sistema si comporta in modo imprevisto a causa del valore errato. I rapporti non verranno generati a meno che una metrica non legga il 100%. È consigliabile non modificare le definizioni delle metriche.
