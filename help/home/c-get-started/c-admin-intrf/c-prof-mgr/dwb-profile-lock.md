---
description: Il file Internal.cfg applicato in Gestione profili impedisce agli utenti di apportare modifiche ai profili personalizzati dai manager Profilo, Dimensioni, Rapporti, Aree di lavoro, Metriche e Filtri.
title: Blocco dei profili nella workstation
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Blocco dei profili nella workstation{#locking-profiles-in-the-workstation}

Il file Internal.cfg applicato in Gestione profili impedisce agli utenti di apportare modifiche ai profili personalizzati dai manager Profilo, Dimensioni, Rapporti, Aree di lavoro, Metriche e Filtri.

È possibile impedire che i file di profilo vengano modificati e sovrascritti quando si utilizzano i manager salvando il **[!DNL Internal.cfg]** file nel profilo personalizzato in Gestione profili. Questo file di configurazione impedisce agli utenti di sovrascrivere più file quando lavorano nei manager (a cui si accede dal menu **Amministratore** > **Profilo** ).

**Blocco dei profili in Gestione profili**

1. Nell’area di lavoro, fai clic con il pulsante destro del mouse su **Admin** (Amministratore) > **Profile Manager (Gestione** profili).

1. In Gestione **** profili, fai clic con il pulsante destro del mouse **[!DNL Context > Internal.cfg]** e **rendi locale**.

1. Fare clic con il pulsante destro del mouse sulla colonna **Utente** e salvare in un `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Nota**: Solo le modifiche apportate ai file di profilo dai manager vengono impedite quando si salva il profilo **[!DNL Internal.cfg]** in un profilo personalizzato in Gestione profili. È comunque possibile salvare le aree di lavoro sul server dal piano di lavoro utilizzando il comando **Salva sul server** .
