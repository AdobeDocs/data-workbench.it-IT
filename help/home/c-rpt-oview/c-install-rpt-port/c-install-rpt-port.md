---
description: Per utilizzare Report Portal, è necessario installare e configurare un set di pagine ASP (Application Server Pages) in IIS.
solution: Analytics
title: Installazione del portale di report
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installazione del portale di report{#installing-the-report-portal}

Per utilizzare Report Portal, è necessario installare e configurare un set di pagine ASP (Application Server Pages) in IIS.

**Prima di iniziare**

Le procedure descritte in questo capitolo descrivono come installare e configurare [!DNL Report Portal]. Per completare queste procedure, è necessario:

* Installare Microsoft IIS e conoscerne la versione.
* Conoscere i nomi dei set di report i cui rapporti sono visualizzati da [!DNL Report Portal].
* Conoscere la posizione della directory in cui [!DNL Report Server] viene salvato l&#39;output per questi set di report. Verificate che il server applicazioni IIS abbia accesso a questa directory.

>[!NOTE]
>
>* Per essere visualizzati utilizzando [!DNL Report Portal], i rapporti devono seguire convenzioni di denominazione specifiche. Inoltre, la directory in cui vengono salvati i report deve seguire una struttura prestabilita. Per una descrizione di questi requisiti, consultate [Assicurare che i set di report siano compatibili con il portale dei report...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Le password nel portale di report ora sono conformi allo standard AES-256 bit. Se si esegue l&#39;aggiornamento a Report Portal 2.0, aumentare il campo Dimensione campo per password da 50 a 150 nel database **users.mdb** . È necessario aumentare le dimensioni del campo per inserire le password con la crittografia aggiornata.
>* Se state effettuando l&#39;aggiornamento a Report Portal 2.0, aumentate la dimensione del campo per il campo **Password** da 50 a 150 nel database users.mdb. È necessario aumentare le dimensioni del campo per inserire le password con la crittografia aggiornata.
>* Il portale di report ora offre algoritmi di hashing più potenti con supporto della salatura. Se state effettuando l&#39;aggiornamento a **Report Portal 2.1**, aggiungete un nuovo campo di testo, *PasswordSalt* , con una dimensione del campo pari a 20 caratteri nel [!DNL users.mdb]database. Questo campo è necessario per memorizzare il valore della password.
>



