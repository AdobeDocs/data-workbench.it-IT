---
description: I computer di Target Insight Server che eseguono il servizio di replica di Insight Server devono essere in grado di leggere i file di registro su questo server di ripetizione.
title: Configurazione del controllo di accesso per i computer di destinazione
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# Configurazione del controllo di accesso per i computer di destinazione{#configuring-access-control-for-target-machines}

I computer di Target Insight Server che eseguono il servizio di replica di Insight Server devono essere in grado di leggere i file di registro su questo server di ripetizione.

L&#39;accesso ai computer di destinazione viene concesso utilizzando il file [!DNL Access Control.cfg] .

**Per configurare il controllo di accesso per l&#39;accesso da parte dei  [!DNL Insight Server] computer di destinazione**

1. Passa alla cartella [!DNL Access Control] nella directory in cui è stata installata la funzionalità Repeater (Ripetitore).

   Esempio: [!DNL D:\Adobe\Repeater\Access Control]

1. Apri [!DNL Access Control.cfg] in un editor di testo come Blocco note.
1. Creare un gruppo di accesso per i computer [!DNL Insight Server] che devono accedere ai file di registro in questo server ripetitore. Assegna a questo gruppo di accesso un nome simile a &quot;Destinazioni di replica&quot;.

   Il seguente frammento di file mostra l’aspetto del gruppo di accesso.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. Nella sezione Membri specificare l&#39;indirizzo IP di ogni computer.
   1. Aggiornare il conteggio degli elementi per il vettore Membri per riflettere il numero di indirizzi IP del computer inseriti.
   1. Nella sezione Accesso in sola lettura, specificare la posizione dei dati dell&#39;evento a cui la replica esegue l&#39;accesso. Utilizzare le barre nella specifica del percorso (/). Il percorso predefinito è la cartella [!DNL Logs] sul computer Repeater (/Logs/).
   1. Aggiorna il conteggio degli elementi per il vettore di accesso in sola lettura per riflettere il numero di posizioni inserite.

1. Aggiorna il numero di gruppi di accesso nel vettore Gruppi di controllo accessi nella parte superiore del file per riflettere l&#39;aggiunta del nuovo gruppo di accesso.

   ```
   Access Control Groups = vector: n items
   ```

1. Salvate il file.
