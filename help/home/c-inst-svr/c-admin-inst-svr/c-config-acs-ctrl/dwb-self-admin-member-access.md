---
description: Gli amministratori possono concedere agli utenti della workstation la possibilità parziale di gestire il controllo degli accessi per i gruppi personalizzati.
title: Amministrazione utente dell’accesso dei membri del gruppo
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Amministrazione utente dell’accesso dei membri del gruppo{#user-administration-of-group-member-access}

{{eol}}

Gli amministratori possono concedere agli utenti della workstation la possibilità parziale di gestire il controllo degli accessi per i gruppi personalizzati.

**Autoamministrazione dell&#39;accesso dei membri del gruppo** consente ai non amministratori di aggiungere ed eliminare membri in un gruppo personalizzato. L&#39;amministratore crea un **Elenco utenti** imposta l&#39;accesso di gruppo nel [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) per i nuovi membri del gruppo.

**Accesso a Server Manager**

Impostazione della **[!DNL User List]** e sincronizzarlo con il **[!DNL Communications.cfg]** viene eseguito nel **Server Manager** workspace.

1. Sul piano di lavoro, fai clic sul pulsante **Amministratore** scheda > **Set di dati e profilo** scheda .

1. Apri **Server Manager** workspace.
1. Clic con il pulsante destro del mouse >*nome del server*> nel diagramma e seleziona **File**.

   I file server si apriranno in una tabella con colonne *File*, *`<server name>`* e *Temp.*.

1. **Rendi locale** facendo clic con il pulsante destro del mouse nella colonna server di un file server (per questa funzione **[!DNL Access Control]** e **[!DNL Components/Communications.cfg)]**.

   Nella **Temp.** colonna. È possibile modificare nella cartella Temp. Quindi fai clic con il pulsante destro del mouse sul segno di spunta e **Salva in** il server. (diventa rosso quando sincronizzato con il server).

## Creare un file User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

L&#39;amministratore deve creare un **[!DNL User List.cfg]** nel **[!DNL Access Control]** cartella.

1. Fai clic con il pulsante destro del mouse** sulla riga Controllo accesso* nella **Temp.** e seleziona **Apri** > **Cartella**. ![](assets/6_4_workstation_groups_3.png)

   La cartella Controllo di accesso nel **Temp.** aprirà l&#39;elenco di un singolo **[!DNL Access Control.cfg]** file.

1. Aggiungi un altro file di testo a questa cartella e denominalo **[!DNL User List.cfg]** (accanto al **[!DNL Access Control.cfg]**).

1. Aggiungi i seguenti parametri al **[!DNL User List.cfg]** file.

Il file Elenco utenti deve contenere un vettore **AccessGroup** e ogni **AccessGroup** l&#39;oggetto deve avere un nome e un vettore di stringhe denominate **Membri**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Puoi quindi modificare e aggiungere gli utenti nella vista Workstation del **[!DNL User List.cfg]**file.

![](assets/6_4_workstation_groups_4.png)

Questi sono i parametri più basilari da aggiungere al **[!DNL User List.cfg]** file. I membri possono quindi essere aggiunti nella vista Workstation.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Come qualsiasi **[!DNL .cfg]** file che si modifica manualmente, assicurarsi di utilizzare spazi invece delle schede e di prestare molta attenzione allo spazio vuoto e alla sintassi. Un errore in questo file causerà *Server Adobe Insight* per ignorare il file Elenco utenti.

La **Nome** campo in ogni **Gruppo di accesso** viene fatto riferimento all&#39;interno di [!DNL Access Control.cfg] file.

>[!NOTE]
>
>Solo membri validi con prefissi del servizio directory, ad esempio **NC:** o **UO:** sono accettati e non possono contenere caratteri jolly (&#42;).

## Imposta il file Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Per prima cosa, un amministratore attiva questa funzione aprendo **[!DNL Components]>[!DNL Communications.cfg]** e aggiunta di una nuova chiave con il nome **[!DNL Access Control User List File]**. Il valore stringa di questa chiave è il percorso in cui si troverà il nuovo file.

1. Dai file del server, fai clic su **Componenti** e fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del server. Fai clic su **Rendi locale**.

   Nella **Temp.** colonna.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nel **Temp.** e seleziona **Apri** > **in Workstation**.

1. In **Communication.cfg** file, fai clic con il pulsante destro del mouse **component** e seleziona **Aggiungi chiave personalizzata.** ![](assets/6_4_workstation_groups.png)

1. Digita il **Nome** come *File elenco utenti controllo accesso* e impostare **Di Tipo** come *Stringa*.

   >[!NOTE]
   >
   >Non è possibile creare il nuovo file elenco come percorso. Per risolvere il problema, è necessario salvare il file, aprirlo in un editor (Blocco note) e modificare &quot;Stringa&quot; in &quot;Percorso&quot;:

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

1. Salva il **[!DNL Communications.cfg]** e, se necessario, salvarlo sul server. In questo modo i componenti del server verranno riavviati per assicurarsi di non aver commesso errori che potrebbero impedire il **[!DNL Communications.cfg]** file da analizzare.
1. Se il sistema include server di elaborazione, modifica il file di configurazione nel **[!DNL Components for Processing Servers.cfg]** file.
1. Fai clic con il pulsante destro del mouse **[!DNL Communications.cfg]** e salva sul server.

L’amministratore di Data Workbench può ora confermare che gli utenti a cui è destinato l’accesso hanno accesso al file dell’elenco utenti e consentire agli utenti di gestire il gruppo. Gli utenti potranno aprire il file Elenco utenti, modificarlo e aggiungere e rimuovere i membri CN o OU in base alle esigenze.

## Sincronizzazione del file Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

L’amministratore può quindi modificare il **[!DNL Access Control.cfg]** e inserire i riferimenti al gruppo o ai gruppi definiti dalla *Elenco utenti* file.

I riferimenti al gruppo o ai gruppi devono essere inseriti come qualsiasi altro membro, ma con la seguente sintassi:

```
$(Group Name)
```

Dove &quot;Nome gruppo&quot; corrisponde a ciò che è definito nel file elenco utenti, inclusi gli spazi bianchi. ![](assets/6_4_workstation_groups_2.png)

A questo punto, l’amministratore di Data Workbench può confermare che alcuni utenti del gruppo hanno accesso al file dell’elenco utenti. Gli utenti selezionati possono quindi aprire la **[!DNL User List.cfg]** archiviare, modificarlo e aggiungere e rimuovere i membri CN o OU in base alle esigenze.
