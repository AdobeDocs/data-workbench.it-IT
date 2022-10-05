---
description: Il parametro Time Zone nel file Transformation.cfg controlla le dimensioni temporali, le conversioni temporali (ad esempio, definendo il campo x-local-timestring) e la formattazione di tutti gli orari locali nel profilo di set di dati.
title: Fusi orari
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Fusi orari{#time-zones}

{{eol}}

Il parametro Time Zone nel file Transformation.cfg controlla le dimensioni temporali, le conversioni temporali (ad esempio, definendo il campo x-local-timestring) e la formattazione di tutti gli orari locali nel profilo di set di dati.

>[!NOTE]
>
>Il parametro Time Zone non influisce sulle funzionalità a livello di sistema, ad esempio le marche temporali nei registri di stato e evento, espresse nell’ora locale del sistema.

Il parametro Time Zone supporta un formato di fuso orario indipendente dal sistema (&quot;Ora universale coordinata&quot;) del seguente formato:

Fuso orario = stringa: UTC +hhmm dstrisce

Il segno (+) può essere un segno più (+) o meno (-) e *eh* è l’offset da UTC in ore e minuti. Variabile opzionale *ostriche* specifica un insieme di regole per implementare l&#39;ora legale o un criterio di spostamento dell&#39;orologio simile.

Se si specifica *ostriche*, un file delimitato da tabulazioni denominato [!DNL dstrules .dst] deve essere presente nella sottodirectory Dataset\TimeZone del profilo di set di dati. Il file specifica un set di regole indipendente dal fuso orario per l’ora legale. Puoi avere diversi set di regole per diversi anni. La [!DNL DST.dst] il file fornito dall&#39;Adobe nel profilo Base specifica le regole standard statunitensi stabilite dalla legge sulla politica energetica del 2005 (in vigore a partire dal 2007) e le norme statunitensi per gli anni precedenti.

Le voci del fuso orario di esempio sono elencate di seguito:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna dilatazione : Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema del server di Data Workbench, di Data Workbench e [!DNL Report] le macchine non devono essere uguali al fuso orario specificato. Inoltre, tutti i profili di set di dati attivi su un computer server di Data Workbench non devono avere la stessa impostazione di fuso orario.

Adobe consiglia di non eseguire più di un profilo di set di dati su un singolo computer server di Data Workbench o su un cluster di server di Data Workbench.

Gli utenti di Data Workbench visualizzeranno i dati nel fuso orario del profilo di set di dati invece del relativo fuso orario di sistema. L’Adobe consiglia che il fuso orario di sistema per una macchina server di Data Workbench sia lo stesso del fuso orario utilizzato nei relativi set di dati.

>[!NOTE]
>
>È possibile specificare un parametro del fuso orario nel [!DNL Log Processing.cfg] file , dove viene utilizzato per le conversioni temporali durante l’elaborazione del registro. Per informazioni sul parametro Time Zone nella [!DNL Log Processing.cfg] file, vedi [File di configurazione dell’elaborazione del registro](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
