---
description: Gli amministratori possono concedere agli utenti della workstation la possibilità parziale di gestire il controllo degli accessi per i gruppi personalizzati.
title: Amministrazione utente dell'accesso dei membri del gruppo
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# User Administration of Group Member Access{#user-administration-of-group-member-access}

Gli amministratori possono concedere agli utenti della workstation la possibilità parziale di gestire il controllo degli accessi per i gruppi personalizzati.

**L&#39;amministrazione autonoma dell&#39;accesso** ai membri del gruppo consente ai non amministratori di aggiungere ed eliminare membri in un gruppo personalizzato. L’amministratore crea un file Elenco **** utenti e imposta l’accesso di gruppo nel file [Access Control.cfg](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) per i nuovi membri del gruppo.

**Accesso a Server Manager**

La configurazione del **[!DNL User List]** file e la sincronizzazione con il **[!DNL Communications.cfg]** file vengono eseguite nell&#39;area di lavoro **Server Manager** .

1. Sul piano di lavoro, fare clic sulla scheda **Admin** > scheda **Dataset e profilo** .

1. Aprire l&#39;area di lavoro **Server Manager** .
1. Fare clic con il pulsante destro del mouse >*nome* del server> nel diagramma e selezionare **File**.

   I file server si apriranno in una tabella con colonne *File*, *`<server name>`* e *Temp*.

1. **Rendi locale** facendo clic con il pulsante destro del mouse nella colonna server di un file server (per questa funzione **[!DNL Access Control]** e per **[!DNL Components/Communications.cfg)]**).

   Nella colonna **Temp** viene visualizzato un segno di spunta bianco. Potete modificarlo nella cartella Temp. Fare clic con il pulsante destro del mouse sul segno di spunta e **salvare il file sul** server. (diventa rosso quando sincronizzato con il server).

## Creare un file User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

L’amministratore deve creare un **[!DNL User List.cfg]** file nella **[!DNL Access Control]** cartella.

1. Fare clic con il pulsante destro del mouse** sulla riga Controllo accesso** nella colonna **Temp** e selezionare **Apri** > **Cartella**. ![](assets/6_4_workstation_groups_3.png)

   La cartella Controllo accesso nella cartella **Temp** si aprirà elencando un singolo **[!DNL Access Control.cfg]** file.

1. Aggiungete un altro file di testo a questa cartella e denominatelo **[!DNL User List.cfg]** (accanto al **[!DNL Access Control.cfg]**).

1. Add the following parameters to the **[!DNL User List.cfg]** file.

Il file Elenco utenti deve contenere un vettore di oggetti **AccessGroup** e ogni oggetto **AccessGroup** deve avere un nome e un vettore di stringhe denominati **Membri**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

È quindi possibile modificare e aggiungere gli utenti nella visualizzazione Workstation del file **[!DNL User List.cfg]**6.

![](assets/6_4_workstation_groups_4.png)

Ecco i parametri più semplici da aggiungere al **[!DNL User List.cfg]** file. I membri possono quindi essere aggiunti nella visualizzazione Workstation.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Come per qualsiasi **[!DNL .cfg]** file modificato manualmente, accertatevi di usare spazi invece delle schede e di prestare molta attenzione agli spazi bianchi e alla sintassi. Se si verifica un errore in questo file, *Adobe Insight Server* ignora il file Elenco utenti.

Al campo **Nome** di ciascun gruppo **di** accesso verrà fatto riferimento all&#39;interno del [!DNL Access Control.cfg] file.

>[!NOTE]
>
>Solo i membri validi con prefissi del servizio di directory, ad esempio **CN:** o **UO:** sono accettati e non possono contenere caratteri jolly (*).

## Configurare il file Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Un amministratore ha attivato prima questa funzione aprendo il file **[!DNL Components]>[!DNL Communications.cfg]**e aggiungendo una nuova chiave con il nome **[!DNL Access Control User List File]**. Il valore stringa di questa chiave è il percorso in cui si trova il nuovo file.

1. Dai file del server, fare clic su **Componenti** e fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del server. Fate clic su **Rendi locale**.

   Nella colonna **Temp** viene visualizzato un segno di spunta bianco.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna **Temp** e selezionare **Apri** > **in Workstation**.

1. Nel file **Communication.cfg** , fai clic con il pulsante destro del mouse sul **componente** e seleziona **Aggiungi chiave personalizzata.** ![](assets/6_4_workstation_groups.png)

1. Digitare il **nome** come file *di elenco utenti per il controllo dell&#39;* accesso e impostare **il tipo** come *stringa*.

   >[!NOTE]
   Non è possibile creare il nuovo file elenco come Percorso. Per ovviare a questo problema, è necessario salvare il file, aprirlo in un editor (Blocco note) e modificare &quot;String&quot; in &quot;Path&quot;:

   Prima:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   Dopo:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. Salvate il **[!DNL Communications.cfg]** file e (se necessario) salvatelo sul server. In questo modo, i componenti del server verranno riavviati per essere certi di non aver commesso errori tali da impedire l&#39;analisi del **[!DNL Communications.cfg]** file.
1. Se il sistema include server di elaborazione, modificate il file di configurazione nel **[!DNL Components for Processing Servers.cfg]** file.
1. Fare clic con il pulsante destro del mouse **[!DNL Communications.cfg]** e salvare sul server.

L&#39;amministratore di Workbench dati può ora confermare che gli utenti previsti hanno accesso al file dell&#39;elenco di utenti e consentire agli utenti di gestire il gruppo. Gli utenti potranno aprire il file Elenco utenti, modificarlo, aggiungere e rimuovere i membri CN o UO in base alle esigenze.

## Sincronizzazione del file Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

L’amministratore può quindi modificare **[!DNL Access Control.cfg]** e inserire i riferimenti al gruppo definito dal file Elenco ** utenti.

I riferimenti al gruppo o ai gruppi devono essere inseriti come qualsiasi altro membro, ma con la seguente sintassi:

```
$(Group Name)
```

Dove &quot;Nome gruppo&quot; corrisponde a quanto definito nel file dell’elenco di utenti, compresi gli spazi vuoti. ![](assets/6_4_workstation_groups_2.png)

A questo punto, l&#39;amministratore di Workbench dati può confermare che alcuni utenti del gruppo hanno accesso al file dell&#39;elenco di utenti. Gli utenti selezionati possono quindi aprire il **[!DNL User List.cfg]** file, modificarlo, aggiungere e rimuovere i membri CN o OU in base alle esigenze.
