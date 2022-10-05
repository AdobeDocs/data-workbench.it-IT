---
description: Il file Internal.cfg applicato in Profile Manager impedisce che gli utenti apportino modifiche ai profili personalizzati da parte dei gestori di profili, Dimension, rapporti, aree di lavoro, metriche e filtri.
title: Blocco dei profili nella workstation
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 5%

---

# Blocco dei profili nella workstation{#locking-profiles-in-the-workstation}

{{eol}}

Il file Internal.cfg applicato in Profile Manager impedisce che gli utenti apportino modifiche ai profili personalizzati da parte dei gestori di profili, Dimension, rapporti, aree di lavoro, metriche e filtri.

È possibile evitare che i file di profilo vengano modificati e sovrascritti quando si utilizzano i manager salvando il **[!DNL Internal.cfg]** nel profilo personalizzato in Profile Manager. Questo file di configurazione impedisce agli utenti di sovrascrivere più file quando lavorano nei manager (a cui si accede dal **Amministratore** > **Profilo** menu).

**Blocco dei profili in Profile Manager**

1. Nell’area di lavoro, fai clic con il pulsante destro del mouse su **Amministratore** > **Profile Manager**.

1. In **Profile Manager**, fai clic con il pulsante destro del mouse **[!DNL Context > Internal.cfg]** e **Rendi locale**.

1. Fai clic con il pulsante destro del mouse su un segno di spunta **Utente** e salva in una `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Nota**: Solo le modifiche apportate ai file di profilo dai manager vengono impedite quando si salva il **[!DNL Internal.cfg]** a un profilo personalizzato in Profile Manager (Gestione profili). È comunque possibile salvare le aree di lavoro sul server dal Worktop utilizzando **Salva sul server** comando.
