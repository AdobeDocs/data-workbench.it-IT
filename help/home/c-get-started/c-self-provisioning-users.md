---
description: Utilizzare Workstation per gestire gli utenti di Workbench dati.
title: Provisioning autonomo degli utenti
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Provisioning autonomo degli utenti{#self-provisioning-of-users}

Utilizzare Workstation per gestire gli utenti di Workbench dati.

È possibile utilizzare Workstation per connettersi al server Workbench dati configurando il certificato richiesto da Adobe. Questo certificato supporta sia la comunicazione SSL che l’autorizzazione per l’utilizzo delle risorse e delle funzioni con licenza. Nell&#39;autenticazione basata su certificato, è necessario acquisire e impostare più certificati per utilizzare Workstation su più computer. Inoltre, il provisioning degli utenti e le adesioni vengono gestiti da Adobe e devi contattare Adobe per ottenere nuovi certificati o revoche di certificati.

A partire da DWB 6.7, Workstation supporta l&#39;autenticazione utente tramite nome utente e password.

L&#39;autenticazione/autorizzazione basata su certificato continuerà a funzionare per la configurazione dell&#39;utente, ma si consiglia vivamente di eseguire la migrazione alla nuova autenticazione basata sulle credenziali. Con l&#39;approccio più recente, gli utenti Workstation eseguono l&#39;autenticazione tramite Adobe Identity Management System (IMS). Prima di poter utilizzare la Workstation, è necessario che l&#39;amministratore dell&#39;organizzazione possa accedere alle funzioni tramite [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) .

Il nuovo modello di autenticazione e provisioning utente consente di:

* Provisioning autonomo di utenti e gruppi tramite Admin Console. Non è necessario contattare Adobe per aggiungere, rimuovere o modificare le adesioni di licenza per gli utenti.
* Accesso a Workstation da più computer senza perdere lo stato di configurazione effettuando l&#39;accesso con le credenziali. La cache locale viene eliminata al momento dell&#39;uscita, il profilo corrente viene chiuso e il profilo di configurazione diventa attivo.

## Introduzione

Prima di iniziare, contatta Adobe per aggiungere la tua organizzazione in Admin Console. A seconda dei servizi acquistati, Adobe effettuerà il provisioning dell&#39;organizzazione. Ad esempio, le organizzazioni possono avere accesso al servizio Attribuzione, alle build Beta o a entrambe. Una volta configurata l’organizzazione, l’amministratore dell’organizzazione può aggiungere utenti e gruppi. Per ulteriori informazioni, consulta [Gestione di utenti e prodotti](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud. L&#39;amministratore dell&#39;organizzazione può anche configurare restrizioni d&#39;uso per utenti diversi a seconda dei loro ruoli. Ad esempio, gli utenti non pre-release non hanno bisogno dell&#39;accesso alle build Beta.

Ogni utente con provisioning aggiunto a questa organizzazione tramite Admin Console avrà accesso all&#39;utilizzo di Workbench dati. I servizi secondari possono essere attivati o disattivati solo per ogni utente, a seconda dell&#39;accesso al prodotto. Quando un utente viene aggiornato dal certificato a IMS, tutti i dati locali verranno copiati nella nuova directory utente IMS.

>[!NOTE]
>
>Una sessione dura 6 ore sul server e 23 ore sul client, a meno che il token di accesso non venga aggiornato. Quando il token viene aggiornato, potete utilizzare Client senza effettuare nuovamente l&#39;accesso.

Prima di concedere l’accesso a qualsiasi utente, è necessario creare almeno una configurazione a livello di prodotto in Admin Console dall’amministratore.

È possibile aggiungere il flag booleano **Use IMS** [!DNL Insight.cfg] alla modalità di fallback alla modalità del certificato. Per informazioni sulla configurazione di Access Control per gli utenti IMS, vedere [Aggiornamento del file](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)di controllo degli accessi.

## Risoluzione dei conflitti

Quando un utente ha eseguito l&#39;accesso a più computer con lo stesso account IMS sullo stesso profilo ed è in modalità offline su uno dei computer, un modulo `.conflict` potrebbe e una finestra a comparsa vi informerà. Ciò si verifica quando vi è una differenza di contenuto con qualsiasi file (aree di lavoro, dimensioni, filtri, ecc.) sincronizzato su entrambi i computer in [!DNL User\Profile\] su server e client. Verrà creato un backup nel `.conflict` file e non andranno persi dati. Un flag booleano in [!DNL Insight.cfg] consente di disabilitare la finestra a comparsa di questo conflitto.

Contrassegno: Notifiche in conflitto

Questo è applicabile a aree di lavoro, metriche, dimensioni, ecc. in Cartella utente.
