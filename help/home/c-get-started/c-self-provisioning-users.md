---
description: Utilizzare Workstation per gestire gli utenti Date Workbench.
title: Provisioning autonomo degli utenti
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Provisioning autonomo degli utenti{#self-provisioning-of-users}

Utilizzare Workstation per gestire gli utenti Date Workbench.

È possibile utilizzare Workstation per connettersi al server Data Workbench impostando il certificato richiesto dall&#39;Adobe. Questo certificato supporta sia la comunicazione SSL che l’autorizzazione per l’utilizzo delle risorse e delle funzionalità concesse in licenza. Nell’autenticazione basata su certificato, è necessario acquisire e impostare più certificati per utilizzare la workstation su più computer. Inoltre, il provisioning degli utenti e le adesioni vengono gestiti per Adobe e devi contattare Adobe per nuovi certificati o per la revoca dei certificati.

A partire da DWB 6.7, Workstation supporta l’autenticazione degli utenti tramite nome utente e password.

Anche se l’autenticazione/autorizzazione basata su certificato continuerà a funzionare per la configurazione, si consiglia vivamente di eseguire la migrazione alla nuova autenticazione basata sulle credenziali. Nell’approccio più recente, gli utenti di Workstation si autenticano tramite Adobe Identity Management System (IMS). Prima di poter utilizzare la workstation, l&#39;amministratore dell&#39;organizzazione deve poter accedere alle funzioni tramite l&#39; [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it) .

Il nuovo modello di autenticazione e provisioning degli utenti consente di:

* Provisioning autonomo di utenti e gruppi tramite Admin Console. Non è necessario contattare Adobe per aggiungere, rimuovere o modificare diritti di licenza per gli utenti.
* Accedere a Workstation da più computer senza perdere lo stato di configurazione accedendo utilizzando le credenziali. La cache locale viene eliminata all’uscita, il profilo corrente viene chiuso e il profilo di configurazione diventa attivo.

## Introduzione

Prima di iniziare, contatta l’Adobe per aggiungere la tua organizzazione nell’Admin Console. A seconda dei servizi acquistati, Adobe eseguirà il provisioning dell’organizzazione per l’utente. Ad esempio, le organizzazioni possono avere accesso al servizio Attribution o alle build Beta o a entrambe. Una volta configurata un&#39;organizzazione, l&#39;amministratore dell&#39;organizzazione può aggiungere utenti e gruppi. Per ulteriori informazioni, consulta [Gestione di utenti e prodotti Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) in Experience Cloud. L’amministratore dell’organizzazione può anche configurare restrizioni di utilizzo per utenti diversi a seconda dei loro ruoli. Ad esempio, gli utenti non pre-release non hanno bisogno dell’accesso alle build Beta.

Ogni utente con provisioning aggiunto a questa organizzazione tramite l’Admin Console avrà accesso all’utilizzo della Data Workbench. I servizi secondari possono essere abilitati o disabilitati solo per ogni utente a seconda dell’accesso al prodotto. Quando un utente viene aggiornato dal certificato a IMS, tutti i dati locali verranno copiati nella nuova directory utente IMS.

>[!NOTE]
>
>Una sessione dura 6 ore sul server e 23 ore sul client a meno che il token di accesso non venga aggiornato. Quando il token viene aggiornato, puoi utilizzare Client senza effettuare di nuovo l’accesso.

È necessario creare almeno una configurazione a livello di prodotto in Admin Console dall’amministratore prima di concedere l’accesso a qualsiasi utente.

Il flag booleano **Use IMS** può essere aggiunto a [!DNL Insight.cfg] per passare alla modalità di certificato. Per informazioni sulla configurazione di Access Control per gli utenti IMS, vedere [Aggiornamento del file di controllo accessi](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Risoluzione dei conflitti

Quando un utente ha effettuato l&#39;accesso a più computer con lo stesso account IMS sullo stesso profilo ed è in modalità offline su uno dei computer, può essere visualizzato un modulo `.conflict` e verrà visualizzata una finestra a comparsa. Ciò si verifica quando c&#39;è una differenza di contenuto con qualsiasi file (aree di lavoro, dimensioni, filtri, ecc.) sincronizzato su entrambi i computer in [!DNL User\Profile\] su server e client . Verrà creato un backup nel file `.conflict` e non verranno persi dati. Un flag booleano in [!DNL Insight.cfg] ti consente di disabilitare questo pop-up di conflitti.

Contrassegno: Notifiche in conflitto

Questo è applicabile per aree di lavoro, metriche, dimensioni, ecc. in Cartella utente.
