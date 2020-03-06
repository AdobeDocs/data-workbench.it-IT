---
description: Le informazioni sulle impostazioni specifiche per il Web definite in Log Processing Dataset includono i file che vengono recapitati con i profili Adobe per il sito.
solution: Analytics
title: Impostazioni specifiche per il Web per l'elaborazione del registro
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Impostazioni specifiche per il Web per l&#39;elaborazione del registro{#web-specific-settings-for-log-processing}

Le informazioni sulle impostazioni specifiche per il Web definite in Log Processing Dataset includono i file che vengono recapitati con i profili Adobe per il sito.

Il filtraggio definito da queste impostazioni avviene dopo che le voci di registro lasciano i decodificatori e le trasformazioni vengono applicate, ma prima della valutazione da parte del [!DNL Log Entry Condition].

* [Filtro stato HTTP](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Filtro Robot](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## Filtro stato HTTP {#section-ac66acdcb6aa467d81c3721199e540fd}

È possibile configurare l&#39;implementazione di [!DNL Site] per rimuovere dal set di dati le voci di registro con codici di stato sc pari o superiori a 400. Le richieste riuscite hanno codici di stato inferiori a 400. L’implementazione predefinita include un [!DNL Log Processing Dataset Include] file in cui è configurato il filtro dello stato HTTP.

**Per modificare le impostazioni di configurazione per il filtro dello stato HTTP**

1. Apri il [!DNL Profile Manager] contenuto nel profilo del set di dati e apri il [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] file.

   >[!NOTE]
   >
   >Se avete personalizzato l’implementazione di [!DNL Site], il file in cui tali impostazioni di configurazione esistono può essere diverso dalla posizione descritta.

1. Rivedete o modificate i valori dei parametri del file come desiderate. Utilizzate l&#39;esempio seguente come guida.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Per informazioni sulla [!DNL Range] condizione, vedere [Condizioni](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Salvare il [!DNL HTTP Status Filter.cfg] file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

## Filtro Robot {#section-7f43681dfbc64b969619cb88f97d5ad5}

È possibile configurare l&#39;implementazione di [!DNL Site] per utilizzare i file di ricerca per rimuovere dal set di dati le voci di registro generate da robot noti, script di test e indirizzi IP per gli utenti interni. L&#39;implementazione predefinita include un [!DNL Log Processing Dataset Include] file in cui è configurato il filtraggio automatico.

**Per modificare le impostazioni di configurazione per il filtraggio automatico**

1. Apri il [!DNL Profile Manager] contenuto nel profilo del set di dati e apri il [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] file.

   >[!NOTE]
   >
   >Se avete personalizzato l’implementazione di [!DNL Site], il file in cui tali impostazioni di configurazione esistono può essere diverso dalla posizione descritta.

1. Rivedete o modificate i parametri del file utilizzando l&#39;esempio seguente e le informazioni come guide:

   ![](assets/cfg_WebParameters_RobotFilter.png)

   Il file include un [!DNL NotRobotCondition] che è definito dai tre parametri seguenti:

   * **Filtro del robot senza distinzione tra maiuscole e minuscole:** True o false. Se è true, la lettera maiuscola (superiore/inferiore) non viene considerata nel filtraggio del robot.
   * **File di ricerca robot, baseline:** Il percorso e il nome del file di testo che contiene un elenco di agenti utente del browser che sono robot noti e che devono essere filtrati dal dataset. Adobe fornisce il file di ricerca robot della linea di base. Se non si specifica un percorso, il server workbench dati cerca questo file nella directory Ricerche all&#39;interno della directory di installazione del server workbench dati.
   * **File di ricerca robot, esteso:** Percorso e nome del file di testo facoltativo contenente un elenco di agenti utente del browser o indirizzi IP che definiscono i robot specifici per l&#39;implementazione. Questo elenco può includere robot di monitoraggio interni, script di test e indirizzi IP per gli utenti interni che devono essere filtrati dal dataset. Se non si specifica un percorso, il server workbench dati cerca questo file nella directory Ricerche all&#39;interno della directory di installazione del server workbench dati.
   Se l&#39;agente utente del browser di una voce di registro non è elencato in uno dei file di ricerca, la voce di registro viene considerata generata da un visitatore reale e non viene filtrata dal set di dati.

   >[!NOTE]
   >
   >La corrispondenza nei file di ricerca robot utilizza le sottostringhe da confrontare con i campi di log c-ip e cs(user-agent). Se la stringa di ricerca inizia con &quot;$&quot;, deve corrispondere alla parte anteriore della stringa in fase di test e, se termina con &quot;$&quot;, la stringa di ricerca deve corrispondere alla fine della stringa in fase di test. Se la stringa di ricerca inizia con e termina con &quot;$&quot;, le stringhe devono corrispondere esattamente affinché la voce di registro venga filtrata. Ad esempio, per verificare tutti gli indirizzi IP in un blocco di classe C, si utilizzerebbe una stringa come $231.78.123. per forzare una corrispondenza nella parte anteriore della stringa. Questo corrisponderebbe agli indirizzi da 231.78.123.0 a 231.78.123.255.

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati.

   Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

   >[!NOTE]
   >
   >Se è importante che le voci di registro sottostanti utilizzate per costruire un dataset non cambino (anche se le trasformazioni utilizzate per costruire e aggiornare il dataset e le sue dimensioni cambiano), è necessario controllare la versione del file di ricerca Robot, della baseline e del file di ricerca Robot, esteso. Posizionando un numero di versione su questi file si assicura che gli aggiornamenti ai file di ricerca robot predefiniti non cambino involontariamente i set di dati di reporting creati in precedenza aggiungendo o eliminando le voci in questi file.

