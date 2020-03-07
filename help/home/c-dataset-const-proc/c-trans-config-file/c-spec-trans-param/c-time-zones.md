---
description: Il parametro Fuso orario nel file Transformation.cfg controlla le dimensioni temporali, le conversioni temporali (ad esempio, la definizione del campo x-local-timestring) e la formattazione di tutte le ore locali nel profilo del dataset.
solution: Analytics
title: Fusi orari
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Fusi orari{#time-zones}

Il parametro Fuso orario nel file Transformation.cfg controlla le dimensioni temporali, le conversioni temporali (ad esempio, la definizione del campo x-local-timestring) e la formattazione di tutte le ore locali nel profilo del dataset.

>[!NOTE]
>
>Il parametro Fuso orario non influisce sulle funzionalità a livello di sistema, come le marche temporali nei registri di stato e evento, espresse nell&#39;ora locale del sistema.

Il parametro Fuso orario supporta un formato di fuso orario indipendente dal sistema (&quot;Ora universale coordinata&quot;) nel seguente formato:

Fuso orario = stringa: UTC +hhmm moduli

Il segno (+) può essere un segno più (+) o meno (-) e *hhmm* è l&#39;offset dall&#39;UTC in ore e minuti. Le *combinazioni* di variabili facoltative specificano un insieme di regole per implementare l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio.

Se si specificano *le specifiche*, all&#39;interno della sottodirectory Dataset\TimeZone del profilo di set di dati deve essere presente un file delimitato da tabulazioni denominato [!DNL dstrules .dst] . Il file specifica un set di regole indipendente dal fuso orario per l&#39;ora legale. Potete avere diversi insiemi di regole per anni diversi. Il [!DNL DST.dst] file fornito da Adobe nel profilo Base specifica le regole standard statunitensi stabilite dal Energy Policy Act del 2005 (in vigore dal 2007) e dalle regole statunitensi per gli anni precedenti.

Le voci del fuso orario di esempio sono elencate di seguito:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna dilatazione : Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema del server workbench dati, del workbench dati e [!DNL Report] dei computer non deve corrispondere al fuso orario specificato. Inoltre, tutti i profili dataset attivi su un computer server workbench dati non devono avere la stessa impostazione di fuso orario.

Adobe consiglia di eseguire non più di un profilo di dataset su un singolo computer server workbench dati o su un cluster di server Workbench dati.

Gli utenti del workbench dati visualizzeranno i dati nel fuso orario del profilo del dataset invece del relativo fuso orario. Adobe consiglia che il fuso orario di sistema per un computer server workbench dati sia lo stesso utilizzato nei set di dati.

>[!NOTE]
>
>Potete specificare un parametro Fuso orario nel [!DNL Log Processing.cfg] file, da usare per le conversioni temporali durante l’elaborazione del registro. Per informazioni sul parametro Fuso orario nel [!DNL Log Processing.cfg] file, vedere File [di configurazione](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)Elaborazione log.

