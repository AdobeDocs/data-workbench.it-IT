---
description: Esportazione, copia e segnalibro dal piano di lavoro.
solution: Analytics
title: Utilizzo del menu delle miniature di Worktop
topic: Data workbench
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilizzo del menu delle miniature di Worktop{#using-the-worktop-thumbnail-menu}

Esportazione, copia e segnalibro dal piano di lavoro.

Fare clic con il pulsante destro del mouse su un&#39;area di lavoro per esportare, copiare e contrassegnare le funzioni dal piano di lavoro.

![](assets/thumbnail_menu.png)

## Descrizioni interfaccia {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Nel menu delle [!DNL Worktop] miniature sono disponibili i seguenti elementi:

**Area di lavoro server:** *name*

Viene visualizzato solo per le aree di lavoro del server non modificate. Identifica l’area di lavoro con nome come l’area di lavoro memorizzata sul server.

**Data:** *giorno e ora*

Data e ora dell’ultima apertura dell’area di lavoro.

**Versione locale di:** *name*

Viene visualizzato solo per le versioni locali delle aree di lavoro del server. Identifica l’area di lavoro con nome come versione locale modificata di un’area di lavoro memorizzata sul server.

**Area di lavoro utente:** *name*

Viene visualizzata solo per le aree di lavoro utente. Identifica l&#39;area di lavoro denominata come area di lavoro esistente solo sul computer locale.

**Calcola in background**

Viene visualizzato solo quando si lavora online. Mantiene le query nell&#39;area di lavoro selezionata in esecuzione in background mentre si continua a lavorare. Quando è selezionata, la miniatura visualizza le informazioni seguenti, che indicano l&#39;avanzamento delle query:

* Funzionamento: *n%* - indica che la query è in elaborazione e che la percentuale di elaborazione è completa.
* *N* MB Query Load: dimensione totale del risultato della query. Il caricamento della query è proporzionale al carico di memoria totale del server Workbench dati, ma non è correlato direttamente. Come linea guida, un carico di query di 10 MB o superiore potrebbe mettere a dura prova il sistema. Il caricamento della query elencato non prende in considerazione il clustering.

   >[!NOTE]
   >
   >Se l&#39;opzione Calcola in background rimane selezionata, le query nell&#39;area di lavoro selezionata diventano query permanenti, che continuano ad essere aggiornate e utilizzano il carico di memoria. Deselezionate l’opzione Calcola in background al termine del lavoro nell’area di lavoro.

**Esporta in Excel**

Esportate i dati dell’area di lavoro in una tabella in Microsoft Excel (file .xls e .xslx). Quando si esporta un&#39;area di lavoro in Excel, Workbench dati esporta dati da determinate visualizzazioni, legende di dimensioni e valori e annotazioni di testo in una nuova cartella di lavoro Excel con una visualizzazione per foglio di lavoro.

**Esporta in modello Excel**

Esportazione in un modello Excel (.xltx).

**Copia**

Copia l’area di lavoro. Per ulteriori informazioni sull’inserimento di un’area di lavoro copiata, vedere [Copia e Incolla delle aree di lavoro](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65)esistenti.

**Ripristino della versione del server**

Viene visualizzato solo per le versioni locali delle aree di lavoro del server. Elimina la copia locale dell’area di lavoro. L&#39;originale rimane sul server.

**Elimina**

Viene visualizzata solo per le aree di lavoro utente. Elimina l&#39;area di lavoro utente, disponibile solo nel computer locale. Per informazioni sull&#39;eliminazione delle aree di lavoro dal server Workbench dati connesso, vedere [Eliminazione dei file dal profilo](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b)di lavoro.

**Salva nel server**

Viene visualizzato solo per le versioni locali delle aree di lavoro del server e delle aree di lavoro degli utenti e funziona solo per gli utenti con le autorizzazioni appropriate. Salva la copia locale dell’area di lavoro sul server. Per impostazione predefinita, le aree di lavoro vengono salvate nella `<profile name>\Workspaces\<tab name>` cartella di lavoro appropriata.

**Segnalibro**

Aggiungi ai segnalibri un’area di lavoro per recuperarla rapidamente in un secondo momento.

Sopra l&#39;area di lavoro sul piano di lavoro ![](assets/bookmark_icon.png) verrà visualizzata un&#39;icona di segnalibro, che verrà visualizzata nel pannello Segnalibri. ![](assets/bookmark_worktop.png)

