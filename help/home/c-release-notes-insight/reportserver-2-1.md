---
description: Aggiornamento di sicurezza per il portale dei report Workbench dati.
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

Aggiornamento di sicurezza per il portale dei report Workbench dati.

**Aggiornamento importante sulla sicurezza**

Il portale di report ora offre algoritmi di hashing più potenti con supporto della salatura. Se state effettuando l&#39;aggiornamento a Report Portal 2.1, aggiungete un nuovo campo di testo, PasswordSalt con una dimensione di campo di 20 caratteri nel database users.mdb. Questo campo è necessario per memorizzare il valore della password.
