---
description: Utilizzare Workstation per gestire gli utenti Date Workbench.
title: Provisioning autonomo degli utenti
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Provisioning autonomo degli utenti{#self-provisioning-of-users}

{{eol}}

Utilizzare Workstation per gestire gli utenti Date Workbench.

È possibile utilizzare Workstation per connettersi al server Data Workbench impostando il certificato richiesto dall&#39;Adobe. Questo certificato supporta sia la comunicazione SSL che l’autorizzazione per l’utilizzo delle risorse e delle funzionalità concesse in licenza. Nell’autenticazione basata su certificato, è necessario acquisire e impostare più certificati per utilizzare la workstation su più computer. Inoltre, il provisioning degli utenti e le adesioni vengono gestiti per Adobe e devi contattare Adobe per nuovi certificati o per la revoca dei certificati.

A partire da DWB 6.7, Workstation supporta l’autenticazione degli utenti tramite nome utente e password.

Anche se l’autenticazione/autorizzazione basata su certificato continuerà a funzionare per la configurazione, si consiglia vivamente di eseguire la migrazione alla nuova autenticazione basata sulle credenziali. Nell’approccio più recente, gli utenti di Workstation si autenticano tramite Adobe Identity Management System (IMS). Prima di poter utilizzare la Workstation, è necessario che gli sia consentito di accedere alle funzioni tramite la [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it) dall&#39;amministratore dell&#39;organizzazione.

Il nuovo modello di autenticazione e provisioning utente consente di:

* Provisioning autonomo di utenti e gruppi tramite Admin Console. Non è necessario contattare Adobe per aggiungere, rimuovere o modificare diritti di licenza per gli utenti.
* Accedere a Workstation da più computer senza perdere lo stato di configurazione accedendo utilizzando le credenziali. La cache locale viene eliminata all’uscita, il profilo corrente viene chiuso e il profilo di configurazione diventa attivo.

## Introduzione

Prima di iniziare, contatta l’Adobe per aggiungere la tua organizzazione nell’Admin Console. A seconda dei servizi acquistati, Adobe eseguirà il provisioning dell’organizzazione per l’utente. Ad esempio, le organizzazioni possono avere accesso al servizio Attribution o alle build Beta o a entrambe. Una volta configurata un&#39;organizzazione, l&#39;amministratore dell&#39;organizzazione può aggiungere utenti e gruppi. Vedi [Gestione di utenti e prodotti Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) in Experience Cloud per ulteriori informazioni. L’amministratore dell’organizzazione può anche configurare restrizioni di utilizzo per utenti diversi a seconda dei loro ruoli. Ad esempio, gli utenti non pre-release non hanno bisogno dell’accesso alle build Beta.

Ogni utente con provisioning aggiunto a questa organizzazione tramite l’Admin Console avrà accesso all’utilizzo della Data Workbench. I servizi secondari possono essere abilitati o disabilitati solo per ogni utente a seconda dell’accesso al prodotto. Quando un utente viene aggiornato dal certificato a IMS, tutti i dati locali verranno copiati nella nuova directory utente IMS.

>[!NOTE]
>
>Una sessione dura 6 ore sul server e 23 ore sul client a meno che il token di accesso non venga aggiornato. Quando il token viene aggiornato, puoi utilizzare Client senza effettuare di nuovo l’accesso.

È necessario creare almeno una configurazione a livello di prodotto in Admin Console dall’amministratore prima di concedere l’accesso a qualsiasi utente.

Flag booleano **Usa IMS** può essere aggiunto a [!DNL Insight.cfg] per passare alla modalità certificato. Per informazioni sulla configurazione di Access Control per gli utenti IMS, consulta [Aggiornamento del file di controllo di accesso](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Risoluzione dei conflitti

Quando un utente è connesso a più computer con lo stesso account IMS sullo stesso profilo ed è in modalità offline su uno dei computer, un `.conflict` può formarsi e una finestra pop-up vi informerà. Questo si verifica quando c&#39;è una differenza di contenuto con qualsiasi file (aree di lavoro, dimensioni, filtri, ecc.) sincronizzato su entrambe le macchine in [!DNL User\Profile\] su server e client . Verrà creato un backup nel `.conflict` file e nessun dato andrà perso. Flag booleano in [!DNL Insight.cfg] consente di disattivare la finestra a comparsa dei conflitti.

Contrassegno: Notifiche in conflitto

Questo è applicabile per aree di lavoro, metriche, dimensioni, ecc. in Cartella utente.
