---
description: Informazioni sulle impostazioni specifiche per il Web definite in Dataset Include file forniti con profili di Adobe per il sito.
title: Impostazioni specifiche per il web per la trasformazione
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# Impostazioni specifiche per il web per la trasformazione{#web-specific-settings-for-transformation}

Informazioni sulle impostazioni specifiche per il Web definite in Dataset Include file forniti con profili di Adobe per il sito.

Le condizioni, le dimensioni e i parametri definiti da queste impostazioni vengono creati durante la fase di trasformazione della costruzione del set di dati.

* [Page View Condition (Condizione di Vista pagina)](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimension URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimension di riferimento](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Parametri sessione](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Page View Condition (Condizione di Vista pagina){#section-cc2807a12a88492f8b64a43234a1f835}

L’ [!DNL Page View Condition] è un’operazione di condizione che determina se una particolare voce di registro (ovvero una richiesta di pagina) deve essere inclusa nei dati raccolti sulla cronologia di visualizzazione della pagina di un visitatore. Quando la voce di registro soddisfa il valore [!DNL Page View Condition], diventa un elemento della dimensione numerabile Visualizzazione pagina. Se una voce di registro non soddisfa il valore [!DNL Page View Condition], i relativi campi dati sono ancora accessibili da altre dimensioni. Oltre alla dimensione Visualizzazione pagina, i risultati di [!DNL Page View Condition] possono influenzare le seguenti dimensioni:

* **[!DNL URI]e  [!DNL Page]:** queste dimensioni sono direttamente interessate dal  [!DNL Page View Condition]. Se la pagina specificata non supera il valore [!DNL Page View Condition,], non viene inclusa nelle dimensioni URI o Pagina.

* **[!DNL Visitor Page Views]e  [!DNL Session Page Views]:** le dimensioni Visualizzazioni pagina visitatore e Visualizzazioni pagina sessione sono un conteggio del numero di pagine visualizzate rispettivamente da un visitatore a o in una determinata sessione. Le pagine filtrate da [!DNL Page View Condition] non fanno parte di questo conteggio.

* **Numero sessione:** l’ [!DNL Page View Condition] ha un effetto indiretto sulla dimensione Numero sessione. La dimensione Numero sessione viene creata prima di [!DNL Page View Condition]; pertanto, quando si considera [!DNL Session Number] in relazione al [!DNL Page Views], è possibile avere sessioni senza visualizzazioni di pagina.

L’implementazione predefinita di [!DNL Site] include un file [!DNL Transformation Dataset Include] in cui sono definite la dimensione numerabile di Visualizzazione pagina e la relativa [!DNL Page View Condition].

Per informazioni sulle dimensioni conteggiate, vedere [Dimension estesi](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Per modificare le impostazioni di configurazione per Page View Condition**

1. Apri il [!DNL Profile Manager] all’interno del profilo del set di dati e apri il file [!DNL Dataset\Transformation\Traffic\Page View.cfg] .

   >[!NOTE]
   >
   >Se hai personalizzato l&#39;implementazione di [!DNL Site], il file in cui esistono queste impostazioni di configurazione può essere diverso dalla posizione descritta.

1. Rivedi o modifica i valori dei parametri del [!DNL Page View Condition] in base alle esigenze. Utilizza il seguente esempio come guida. In questo file, la [!DNL Page View Condition] è definita da una trasformazione [!DNL Copy]. Tieni presente che questo file contiene anche la definizione della dimensione numerabile Visualizzazione pagina.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Per informazioni sulle dimensioni conteggiate, vedere [Dimension estesi](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Per informazioni sulla trasformazione [!DNL Copy], consulta [Trasformazioni dati](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fai clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include.[!DNL Profile Manager]

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

## Dimension URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Se lavori con [!DNL Site], devi definire la dimensione URI i cui elementi sono gli steli URI delle pagine del sito web visualizzate. L’implementazione predefinita include un file [!DNL Transformation Dataset Include] in cui è definita la dimensione semplice URI.

Per informazioni sulle dimensioni semplici, consulta [Dimension estesi](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Per modificare le impostazioni di configurazione per la dimensione URI**

1. Apri il [!DNL Profile Manager] all’interno del profilo del set di dati e apri il file [!DNL Dataset\Transformation\Traffic\URI.cfg] .

   >[!NOTE]
   >
   >Se hai personalizzato l&#39;implementazione di [!DNL Site], il file in cui esistono queste impostazioni di configurazione può essere diverso dalla posizione descritta.

1. Rivedi o modifica i valori dei parametri del file come desiderato. Utilizza l’esempio e le informazioni seguenti come guide.

![](assets/cfg_WebParameters_URI.png)

Le impostazioni di configurazione per la dimensione URI includono i due parametri seguenti:

* **Sensibile alle maiuscole/minuscole:** True o false. Se true, la lettera maiuscola/minuscola viene considerata nell’identificazione di pagine univoche. Il valore predefinito è vero.
* **Elementi massimi:** il numero massimo di elementi (cioè URI) per la dimensione URI. Il valore predefinito è 32768.

   >[!NOTE]
   >
   >La modifica di questo valore può causare gravi problemi di prestazioni. Non modificare questo valore senza consultare un Adobe.

* Salva il file [!DNL URI.cfg] facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fai clic su **[!UICONTROL Save]**.

* Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include.[!DNL Profile Manager]

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

## Dimension di riferimento {#section-8a97ec34d18b4814b5f95495ac4f8638}

Se lavori con [!DNL Site], devi definire la dimensione Referrer i cui elementi sono costituiti dai domini di secondo livello dei referrer delle prime voci di log in tutte le sessioni. L’implementazione predefinita include un file [!DNL Transformation Dataset Include] in cui è definita la dimensione semplice referente.

Per informazioni sulle dimensioni semplici, consulta [Dimension estesi](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Per modificare le impostazioni di configurazione per la dimensione Referente**

1. Apri il [!DNL Profile Manager] all’interno del profilo del set di dati e apri il file [!DNL Dataset\Transformation\Traffic\Referrer.cfg] .

   >[!NOTE]
   >
   >Se hai personalizzato l&#39;implementazione di [!DNL Site], il file in cui esistono queste impostazioni di configurazione può essere diverso dalla posizione descritta.

1. Rivedi o modifica i valori dei parametri del file come desiderato. Utilizza l’esempio e le informazioni seguenti come guide.

   ![](assets/cfg_WebParameters_Referrer.png)

   Le impostazioni di configurazione per la dimensione referente includono il parametro Elementi massimi , che specifica il numero massimo di elementi (cioè referrer) per la dimensione referente. Il valore predefinito è 32768.

   >[!NOTE]
   >
   >Nell’esempio precedente, il parametro [!DNL Maximum Elements] è impostato su 0. Quando questo parametro è impostato su 0, il server di Data Workbench utilizza il valore predefinito interno di 32768.

1. Salva il file [!DNL Referrer.cfg] facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fai clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include.[!DNL Profile Manager]

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

## Parametri sessione {#section-0a209b0c504041a5801f7f71a963c8b1}

Se lavori con [!DNL Site], puoi specificare parametri che definiscono i limiti della sessione di un visitatore su un sito web. Questi parametri sono validi solo se definiti in un file [!DNL Transformation Dataset Include] all&#39;interno dell&#39;implementazione [!DNL Site].

I seguenti parametri sono univoci in quanto possono essere membri del vettore [!DNL Parameters] del file [!DNL Transformation Dataset Include] oppure possono essere elencati come singoli parametri nel file [!DNL Transformation.cfg]. Un parametro può essere definito esattamente una volta, in modo che questi parametri siano definiti nel file [!DNL Transformation.cfg]o nel vettore [!DNL Parameters] del set di dati include file - non in entrambi i file.
**Durata massima della sessione e timeout della sessione**

Durata massima sessione e Timeout sessione sono parametri stringa che definiscono la lunghezza della sessione di un visitatore. Questi parametri funzionano con il parametro Domini interni per determinare la lunghezza di sessione.

Durata massima sessione specifica la durata più lunga della sessione prima dell’avvio di una nuova sessione. In questo modo le pagine web con contenuto automatico vengono aggiornate dalla creazione di sessioni arbitrariamente lunghe. Se il referente di un clic è impostato su una delle voci nel parametro Domini interni, questo timeout viene utilizzato per definire la fine di una sessione. Nessuna sessione può superare la durata massima della sessione specificata, indipendentemente dal numero di clic che contiene. Il valore consigliato è 48 ore.

Timeout sessione specifica il tempo che deve trascorrere tra le voci di registro di un visitatore specifico per determinare la fine di una sessione e l’inizio di una nuova sessione (ovvero, il timeout tipico utilizzato per definire una sessione utente). Il valore consigliato di questo parametro è di 30 minuti. Se il referente di un clic non è impostato su uno dei referrer nel parametro Domini interni, questo timeout viene utilizzato per definire la sessione. Se cs(referrer-domain) per una voce di registro è nell&#39;elenco dei domini interni, la Durata massima sessione determina se la voce di registro corrente fa parte di una sessione esistente o se inizia una nuova sessione.

Considera una situazione in cui un visitatore viene richiamato dal suo computer per un periodo di tempo più lungo del Timeout sessione mentre si trova nel mezzo della navigazione del sito. Al suo ritorno, continua a navigare dove ha lasciato. Poiché il visitatore non lascia mai il sito o chiude il browser, il cs(referrer-domain) del clic successivo è lo stesso del dominio interno e la sessione originale rimane attiva finché non viene raggiunta l’impostazione Maximum Session Duration (Durata massima sessione). Se il dominio del sito è elencato come dominio interno e il timeout massimo non viene raggiunto, l’interazione del visitatore viene visualizzata come una sessione singola e non come due sessioni separate. Tuttavia, se il visitatore ritorna al computer e il clic successivo dispone di un referente esterno (o vuoto), inizia una nuova sessione.

>[!NOTE]
>
>Anche la trasformazione [!DNL Sessionize] di [!DNL Timeout Condition] svolge un ruolo nel determinare la durata della sessione di un visitatore. Se il timeout della sessione e la durata massima della sessione non sono applicabili, viene controllato [!DNL Timeout Condition] per determinare se una voce di registro deve essere considerata l&#39;inizio di una nuova sessione. Per ulteriori informazioni, consulta [Trasformazioni dati](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Per modificare i parametri di Durata massima sessione e Timeout sessione**

Se lavori con [!DNL Site], l&#39;implementazione predefinita probabilmente include un file [!DNL Transformation Dataset Include] in cui vengono specificati i nomi e i valori consigliati di questi parametri.

1. Apri il [!DNL Profile Manager] all’interno del profilo di set di dati e vai a [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Se hai personalizzato l’implementazione di [!DNL Site], il file in cui sono definiti questi parametri può essere diverso dalla posizione descritta.

1. Modifica i valori dei parametri come desiderato. Assicurati di specificare le unità desiderate (minuti, ore e così via).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Salva il file [!DNL Session Parameters.cfg] facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta del file nella colonna [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, dove il nome del profilo è il nome del profilo di set di dati o il profilo ereditato a cui appartiene il file di set di dati.[!DNL Profile Manager]

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

**[!DNL Internal Domains]**

[!DNL Internal Domains] è un parametro vettoriale che elenca gli host a livello di dominio (riferimenti interni) che devono essere trattati come parte di un particolare sito web. Questi host vengono rimossi dalla dimensione del referente (che è un elenco delle informazioni del referente esterno). Quando cs(referrer-domain) corrisponde a una delle stringhe elencate nel set di domini interni, il timeout della sessione viene ignorato e la durata massima della sessione viene utilizzata per determinare la lunghezza della sessione.

Il parametro Domini interni può essere utilizzato anche per impedire l’inizio di una nuova sessione quando i visitatori si spostano tra i più domini associati di un’azienda in un modo che supera il timeout della sessione. Ad esempio, considera un’azienda con parti del sito suddivise in due domini: uno viene registrato ( [!DNL xyz.com]) e l&#39;altro non viene registrato ( [!DNL xyz-unlogged.com]). Se questi siti sono integrati in modo da facilitare lo spostamento fluido del traffico tra i due domini, non è consigliabile generare una sessione diversa ogni volta che il visitatore ritorna dal dominio [!DNL xyz-unlogged.com] al dominio [!DNL xyz.com]. L’elenco [!DNL xyz-unlogged.com] come dominio interno impedisce la suddivisione delle sessioni in più sessioni a causa del traffico tra questi due domini, purché l’impostazione Maximum Session Duration non venga raggiunta.

**Per aggiungere un dominio interno**

Se lavori con [!DNL Site], l’implementazione predefinita include un file [!DNL Transformation Dataset Include] per la definizione del parametro Domini interni. In questo file, il parametro è denominato; inserisci semplicemente i domini interni che desideri includere e salva il file aggiornato.

1. Apri [!DNL Profile Manager] nel profilo del set di dati e vai a [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Se hai personalizzato l’implementazione di [!DNL Site], il file in cui è definito il parametro Domini interni può essere diverso dalla posizione descritta.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Value]** per il parametro vettoriale Domini interni e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Modifica i valori desiderati.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Salva il file [!DNL Internal Domains.cfg] facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include.[!DNL Profile Manager]

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.
