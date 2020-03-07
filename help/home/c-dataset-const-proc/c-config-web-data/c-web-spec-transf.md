---
description: Informazioni sulle impostazioni Web specifiche definite in DataSet trasformazione Includono i file che vengono recapitati con i profili Adobe per il sito.
solution: Analytics
title: Impostazioni specifiche per il Web per la trasformazione
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Impostazioni specifiche per il Web per la trasformazione{#web-specific-settings-for-transformation}

Informazioni sulle impostazioni Web specifiche definite in DataSet trasformazione Includono i file che vengono recapitati con i profili Adobe per il sito.

Le condizioni, le dimensioni e i parametri definiti da queste impostazioni vengono creati durante la fase di trasformazione della costruzione del dataset.

* [Condizione visualizzazione pagina](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimensione URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimensione referente](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Parametri sessione](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condizione visualizzazione pagina {#section-cc2807a12a88492f8b64a43234a1f835}

L&#39;operazione [!DNL Page View Condition] è una condizione che determina se una particolare voce di registro (ovvero una richiesta di pagina) deve essere inclusa nei dati raccolti sulla cronologia di visualizzazione della pagina di un visitatore. Quando la voce di registro soddisfa i requisiti [!DNL Page View Condition], diventa un elemento della dimensione numerabile Visualizzazione pagina. Se una voce di registro non soddisfa i requisiti, [!DNL Page View Condition]i relativi campi dati sono ancora accessibili da altre dimensioni. Oltre alla dimensione Visualizzazione pagina, i risultati di [!DNL Page View Condition]:

* **[!DNL URI]e[!DNL Page]:**Queste dimensioni sono direttamente influenzate dal[!DNL Page View Condition]. Se la pagina specificata non passa, non[!DNL Page View Condition,]viene inclusa nelle dimensioni URI o Pagina.

* **[!DNL Visitor Page Views]e[!DNL Session Page Views]:**Le dimensioni Visualizzazioni pagina visitatore e Visualizzazioni pagina sessione sono un conteggio del numero di pagine visualizzate rispettivamente da un visitatore a o in una determinata sessione. Le pagine filtrate dall&#39;[!DNL Page View Condition]utente non fanno parte di questo conteggio.

* **Numero sessione:** L’effetto [!DNL Page View Condition] ha un effetto indiretto sulla dimensione Numero sessione. La dimensione Numero sessione viene creata prima della [!DNL Page View Condition]; pertanto, quando si considera [!DNL Session Number] in relazione al [!DNL Page Views], è possibile avere sessioni senza visualizzazioni di pagina.

L’implementazione predefinita di [!DNL Site] include un [!DNL Transformation Dataset Include] file in cui sono definite la dimensione numerabile della visualizzazione pagina e le relative [!DNL Page View Condition] dimensioni.

Per informazioni sulle dimensioni calcolabili, vedere [Dimensioni](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese.

**Per modificare le impostazioni di configurazione per la condizione di visualizzazione pagina**

1. Apri il [!DNL Profile Manager] contenuto nel profilo del set di dati e apri il [!DNL Dataset\Transformation\Traffic\Page View.cfg] file.

   >[!NOTE]
   >
   >Se avete personalizzato l’implementazione di [!DNL Site], il file in cui tali impostazioni di configurazione esistono può essere diverso dalla posizione descritta.

1. Rivedete o modificate i valori dei parametri del [!DNL Page View Condition] modulo in base alle vostre esigenze. Utilizzate l&#39;esempio seguente come guida. In questo file, l&#39; [!DNL Page View Condition] oggetto viene definito da una [!DNL Copy] trasformazione. Si noti che questo file contiene anche la definizione della dimensione numerabile Visualizzazione pagina.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Per informazioni sulle dimensioni calcolabili, vedere [Dimensioni](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese. Per informazioni sulla [!DNL Copy] trasformazione, vedere Trasformazioni [dati](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fare clic su **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

## Dimensione URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Se state lavorando con [!DNL Site], dovete definire la dimensione URI i cui elementi sono gli steli URI delle pagine del sito Web visualizzate. L’implementazione predefinita include un [!DNL Transformation Dataset Include] file in cui è definita la dimensione semplice URI.

Per informazioni sulle dimensioni semplici, consultate [Dimensioni](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese.

**Per modificare le impostazioni di configurazione per la dimensione URI**

1. Apri il [!DNL Profile Manager] contenuto nel profilo del set di dati e apri il [!DNL Dataset\Transformation\Traffic\URI.cfg] file.

   >[!NOTE]
   >
   >Se avete personalizzato l’implementazione di [!DNL Site], il file in cui tali impostazioni di configurazione esistono può essere diverso dalla posizione descritta.

1. Rivedete o modificate i valori dei parametri del file come desiderate. Utilizzate l&#39;esempio e le informazioni seguenti come guide.

![](assets/cfg_WebParameters_URI.png)

Le impostazioni di configurazione per la dimensione URI includono i due parametri seguenti:

* **Distinzione tra maiuscole e minuscole:** True o false. Se true, la lettera maiuscola (superiore/inferiore) viene considerata nell&#39;identificazione di pagine univoche. Il valore predefinito è true.
* **Numero massimo di elementi:** Il numero massimo di elementi (ovvero, URI) per la dimensione URI. Il valore predefinito è 32768.

   >[!NOTE]
   >
   >La modifica di questo valore può causare seri problemi di prestazioni. Non modificate questo valore senza consultare Adobe.

* Salvate il [!DNL URI.cfg] file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fate clic **[!UICONTROL Save]**.

* Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

## Dimensione referente {#section-8a97ec34d18b4814b5f95495ac4f8638}

Se lavori con [!DNL Site], devi definire la dimensione Referente i cui elementi sono costituiti dai domini di secondo livello dei referenti delle prime voci di registro in tutte le sessioni. L’implementazione predefinita include un [!DNL Transformation Dataset Include] file in cui è definita la dimensione semplice Referente.

Per informazioni sulle dimensioni semplici, consultate [Dimensioni](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese.

**Per modificare le impostazioni di configurazione per la dimensione Referente**

1. Apri il [!DNL Profile Manager] contenuto nel profilo del set di dati e apri il [!DNL Dataset\Transformation\Traffic\Referrer.cfg] file.

   >[!NOTE]
   >
   >Se avete personalizzato l’implementazione di [!DNL Site], il file in cui tali impostazioni di configurazione esistono può essere diverso dalla posizione descritta.

1. Rivedete o modificate i valori dei parametri del file come desiderate. Utilizzate l&#39;esempio e le informazioni seguenti come guide.

   ![](assets/cfg_WebParameters_Referrer.png)

   Le impostazioni di configurazione per la dimensione Referente includono il parametro Elementi massimi, che specifica il numero massimo di elementi (cioè, referenti) per la dimensione Referente. Il valore predefinito è 32768.

   >[!NOTE]
   >
   >Nell&#39;esempio precedente, il [!DNL Maximum Elements] parametro è impostato su 0. Se questo parametro è impostato su 0, il server workbench dati utilizza il valore predefinito interno 32768.

1. Salvate il [!DNL Referrer.cfg] file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fate clic **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

## Parametri sessione {#section-0a209b0c504041a5801f7f71a963c8b1}

Se state lavorando con [!DNL Site], potete specificare parametri che definiscono i limiti della sessione di un visitatore su un sito Web. Questi parametri sono validi solo se definiti in un [!DNL Transformation Dataset Include] file all’interno dell’ [!DNL Site] implementazione.

I seguenti parametri sono univoci in quanto possono essere membri del vettore del [!DNL Transformation Dataset Include] file [!DNL Parameters] , oppure possono essere elencati come singoli parametri nel [!DNL Transformation.cfg]file. Un parametro può essere definito esattamente una volta, in modo che questi parametri siano definiti nel [!DNL Transformation.cfg]file o nel [!DNL Parameters] vettore del set di dati includere file - non in entrambi i file.
**Durata massima sessione e timeout sessione**

Durata massima sessione e Timeout sessione sono parametri stringa che definiscono la durata della sessione di un visitatore. Questi parametri funzionano con il parametro Domini interni per determinare la lunghezza della sessione.

Durata massima sessione specifica la durata più lunga della sessione prima dell’avvio di una nuova sessione. In questo modo le pagine Web con contenuto automatico vengono aggiornate e non vengono create sessioni di durata arbitraria. Se il referente di un clic è impostato su una delle voci nel parametro Domini interni, questo timeout viene utilizzato per definire la fine di una sessione. Nessuna sessione può superare la durata massima specificata, indipendentemente dal numero di clic che contiene. Il valore consigliato è 48 ore.

Timeout sessione specifica il tempo che deve trascorrere tra le voci di registro di un determinato visitatore per determinare la fine di una sessione e l’inizio di una nuova sessione (ovvero il timeout tipico utilizzato per definire una sessione utente). Il valore consigliato di questo parametro è 30 minuti. Se il referente di un clic non è impostato su uno dei referenti nel parametro Domini interni, questo timeout viene utilizzato per definire la sessione. Se cs(referrer-domain) per una voce di registro è nell’elenco dei domini interni, la durata massima della sessione determina se la voce di registro corrente fa parte di una sessione esistente o l’inizio di una nuova sessione.

Considerare la situazione in cui un visitatore viene richiamato dal suo computer per un periodo di tempo superiore al timeout sessione mentre si trova nel mezzo della navigazione del sito. Al suo ritorno, continua a navigare dove ha lasciato. Poiché il visitatore non esce mai dal sito o chiude il browser, il cs(referrer-domain) del clic successivo è lo stesso del dominio interno e la sua sessione originale rimane attiva finché non viene raggiunta l’impostazione Durata massima sessione. Se il dominio del sito è elencato come dominio interno e non viene raggiunto il timeout massimo, l&#39;interazione del visitatore viene visualizzata come una singola sessione e non come due sessioni separate. Tuttavia, se il visitatore ritorna al computer e il clic successivo dispone di un referente esterno (o vuoto), inizia una nuova sessione.

>[!NOTE]
>
>La [!DNL Sessionize] trasformazione ha [!DNL Timeout Condition] anche un ruolo nel determinare la durata della sessione di un visitatore. Se il timeout della sessione e la durata massima della sessione non sono validi, [!DNL Timeout Condition] viene verificato se una voce di registro deve essere considerata l’inizio di una nuova sessione. For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Per modificare i parametri Durata massima sessione e Timeout sessione**

Se state lavorando con [!DNL Site], l&#39;implementazione predefinita probabilmente include un [!DNL Transformation Dataset Include] file in cui vengono specificati i nomi e i valori consigliati di questi parametri.

1. Aprite il [!DNL Profile Manager] contenuto nel profilo del set di dati e passate a [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Se avete personalizzato l’implementazione di [!DNL Site], il file in cui questi parametri sono definiti può essere diverso dalla posizione descritta.

1. Modificate i valori dei parametri come desiderate. Accertatevi di specificare le unità desiderate (minuti, ore e così via).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Salvare il [!DNL Session Parameters.cfg] file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** **[!UICONTROL profile name]**, dove il nome del profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

**[!DNL Internal Domains]**

[!DNL Internal Domains] è un parametro vettoriale che elenca gli host a livello di dominio (riferimenti interni) che devono essere trattati come parte di un particolare sito Web. Questi host vengono rimossi dalla dimensione del referente (che è un elenco delle informazioni sul referente esterno). Quando cs(referrer-domain) corrisponde a una qualsiasi delle stringhe elencate nel set di domini interni, Timeout sessione viene ignorato e viene utilizzata la durata massima della sessione per determinare la lunghezza della sessione.

Il parametro Domini interni può essere utilizzato anche per impedire l&#39;avvio di una nuova sessione quando i visitatori si spostano tra i più domini di una società associati in un modo che supera il timeout della sessione. Ad esempio, considerate una società con parti del suo sito suddivise in due domini: uno è registrato ( [!DNL xyz.com]) e l&#39;altro non è registrato ( [!DNL xyz-unlogged.com]). Se questi siti sono integrati in modo da facilitare lo spostamento diretto del traffico tra i due domini, non è consigliabile generare una sessione diversa ogni volta che il visitatore ritorna dal [!DNL xyz-unlogged.com] dominio al [!DNL xyz.com] dominio. L&#39;elenco [!DNL xyz-unlogged.com] come dominio interno impedisce che le sessioni vengano suddivise in più sessioni a causa del traffico tra questi due domini, a condizione che non venga raggiunta l&#39;impostazione Durata massima sessione.

**Per aggiungere un dominio interno**

Se state lavorando con [!DNL Site], l&#39;implementazione predefinita include un [!DNL Transformation Dataset Include] file per la definizione del parametro Domini interni. In questo file, il parametro è denominato; è sufficiente inserire i domini interni che si desidera includere e salvare il file aggiornato.

1. Apri [!DNL Profile Manager] all’interno del profilo del set di dati e vai a [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Se avete personalizzato l&#39;implementazione di [!DNL Site], il file in cui è definito il parametro Domini interni può essere diverso dalla posizione descritta.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Value]** per il parametro vettoriale Domini interni e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Modificate i valori nel modo desiderato.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Salvare il [!DNL Internal Domains.cfg] file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

