---
description: Esportazione, copia e segnalibro dal Worktop.
title: Utilizzo del menu delle miniature di Worktop
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 2%

---

# Utilizzo del menu delle miniature di Worktop{#using-the-worktop-thumbnail-menu}

{{eol}}

Esportazione, copia e segnalibro dal Worktop.

Fai clic con il pulsante destro del mouse su un&#39;area di lavoro per esportare, copiare e contrassegnare le funzioni dal Worktop (Worktop).

![](assets/thumbnail_menu.png)

## Descrizioni interfaccia {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

I seguenti elementi sono disponibili nel [!DNL Worktop] menu miniature:

**Area di lavoro del server:** *name*

Viene visualizzato solo per le aree di lavoro del server non modificate. Identifica l&#39;area di lavoro denominata come l&#39;area di lavoro memorizzata sul server.

**Data:** *giorno e ora*

Data e ora dell’ultima apertura dell’area di lavoro.

**Versione locale di:** *name*

Viene visualizzato solo per le versioni locali delle aree di lavoro del server. Identifica l&#39;area di lavoro denominata come versione locale modificata di un&#39;area di lavoro memorizzata sul server.

**Area di lavoro utente:** *name*

Viene visualizzato solo per le aree di lavoro utente. Identifica l&#39;area di lavoro denominata come area di lavoro esistente solo nel computer locale.

**Calcola in background**

Viene visualizzato solo quando si lavora online. Mantiene in esecuzione in background le query nell’area di lavoro selezionata mentre si continua a lavorare. Quando questa opzione è selezionata, la miniatura visualizza le informazioni seguenti, che indicano l’avanzamento delle query:

* Funzionamento: *n%* - indica che la query è in fase di elaborazione e la percentuale di elaborazione completata.
* *n* Caricamento query MB: dimensione totale del risultato della query. Il caricamento della query è proporzionale al carico di memoria totale del server di Data Workbench, ma non è correlato direttamente. Come regola generale, un carico di query di 10 MB o superiore può causare stress al sistema. Il caricamento della query elencato non tiene conto del clustering.

   >[!NOTE]
   >
   >Se l&#39;opzione Computa in background rimane selezionata, le query nell&#39;area di lavoro selezionata diventano query permanenti, che continuano ad essere aggiornate e utilizzano il caricamento della memoria. Assicurati di deselezionare Calcola in background al termine del lavoro nell&#39;area di lavoro.

**Esporta in Excel**

Esporta i dati dell’area di lavoro nella tabella in Microsoft Excel (file .xls e .xslx). Durante l’esportazione di un’area di lavoro in Excel, Data Workbench esporta dati da determinate visualizzazioni, legende di dimensioni e valori e annotazioni di testo in una nuova cartella di lavoro Excel con una visualizzazione per foglio di lavoro.

**Esporta in modello Excel**

Esporta in un modello Excel (.xltx).

**Copia**

Copia l’area di lavoro. Per ulteriori informazioni sull&#39;incolla di un&#39;area di lavoro copiata, vedere [Copiare e incollare le aree di lavoro esistenti](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Ripristino della versione del server**

Viene visualizzato solo per le versioni locali delle aree di lavoro del server. Elimina la copia locale dell&#39;area di lavoro. L&#39;originale rimane sul server.

**Delete (Elimina)**

Viene visualizzato solo per le aree di lavoro utente. Elimina l&#39;area di lavoro utente, disponibile solo nel computer locale. Per informazioni sull&#39;eliminazione delle aree di lavoro dal server di Data Workbench connesso, vedere [Eliminazione dei file dal profilo di lavoro](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Salva sul server**

Viene visualizzato solo per le versioni locali delle aree di lavoro del server e delle aree di lavoro degli utenti e funziona solo per gli utenti con le autorizzazioni appropriate. Salva la copia locale dell&#39;area di lavoro sul server. Per impostazione predefinita, le aree di lavoro vengono salvate nelle operazioni appropriate `<profile name>\Workspaces\<tab name>` cartella.

**Segnalibro**

Aggiungi ai segnalibri un’area di lavoro per recuperarla rapidamente in un secondo momento.

Icona di un segnalibro ![](assets/bookmark_icon.png) apparirà sopra l&#39;area di lavoro sul piano di lavoro e il nome dell&#39;area di lavoro verrà visualizzato nel pannello Segnalibri. ![](assets/bookmark_worktop.png)
