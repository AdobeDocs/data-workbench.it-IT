---
description: I computer server di destinazione che eseguono il servizio di replica di Insight Server devono essere in grado di leggere i file di registro in questo server di ripetizione.
solution: Insight
title: Configurazione del controllo di accesso per i computer di destinazione
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione del controllo di accesso per i computer di destinazione{#configuring-access-control-for-target-machines}

I computer server di destinazione che eseguono il servizio di replica di Insight Server devono essere in grado di leggere i file di registro in questo server di ripetizione.

L&#39;accesso ai computer di destinazione è concesso utilizzando il [!DNL Access Control.cfg] file.

**Per configurare il controllo di accesso per l&#39;accesso per i computer di destinazione[!DNL Insight Server]**

1. Passate alla [!DNL Access Control] cartella nella directory in cui è stata installata la funzionalità Ripetitore.

   Esempio: [!DNL D:\Adobe\Repeater\Access Control]

1. Aprite [!DNL Access Control.cfg] in un editor di testo come Blocco note.
1. Creare un gruppo di accesso per i [!DNL Insight Server] computer che devono accedere ai file di registro su questo server di ripetizione. Assegna a questo gruppo di accesso un nome simile a &quot;Destinazioni di replica&quot;.

       Il seguente frammento di file mostra l’aspetto del gruppo di accesso.
       
       ```
       . . .
       6 = AccessGroup:
       Membri = vettore: N elementi
     0 = stringa: IP:Machine0IPAddress
     1 = stringa: IP:Machine1IPAddress
    . . .
       N = stringa: IP:MachineNIPAddress
     Name = stringa: Destinazioni
 di replica Accesso in     sola lettura = vettore: 1 elementi
     0 = stringa: Accesso in
 lettura/scrittura a EventDataLocation     = vettore: 0 elementi
    . . .
       &quot;
   
   1. Nella sezione Membri, specificate l&#39;indirizzo IP per ogni computer.
   1. Aggiornare il conteggio degli elementi per il vettore Membri per riflettere il numero di indirizzi IP del computer inseriti.
   1. Nella sezione Accesso in sola lettura, specificare la posizione dei dati dell&#39;evento a cui la replica ha accesso. Utilizzate le barre nella specifica del percorso (/). Il percorso predefinito è la [!DNL Logs] cartella del computer ripetitore (/Logs/).
   1. Aggiornare il conteggio degli elementi per il vettore di accesso in sola lettura per riflettere il numero di posizioni inserite.

1. Aggiornate il numero di gruppi di accesso nel vettore Gruppi di controllo di accesso nella parte superiore del file per riflettere l&#39;aggiunta del nuovo gruppo di accesso.

   ```
   Access Control Groups = vector: n items
   ```

1. Salvate il file.
