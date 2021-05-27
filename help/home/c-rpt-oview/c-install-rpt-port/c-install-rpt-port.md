---
description: Per utilizzare Report Portal (Portale dei rapporti), è necessario installare e configurare un set di pagine server applicazioni (ASP) in IIS.
title: Installazione del Report Portal (Portale dei rapporti)
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Installazione del Report Portal (Portale dei rapporti) {#installing-the-report-portal}

Per utilizzare Report Portal (Portale dei rapporti), è necessario installare e configurare un set di pagine server applicazioni (ASP) in IIS.

**Prima di iniziare**

Le procedure descritte in questo capitolo descrivono come installare e configurare [!DNL Report Portal]. Per completare queste procedure, devi:

* Avere installato Microsoft IIS e conoscerne la versione.
* Conoscere i nomi dei set di rapporti i cui rapporti sono visualizzati da [!DNL Report Portal].
* Conoscere la posizione della directory in cui [!DNL Report Server] salva l&#39;output per questi set di rapporti. Assicurati che il server dell&#39;applicazione IIS abbia accesso a questa directory.

>[!NOTE]
>
>* Per essere visualizzati utilizzando [!DNL Report Portal], i rapporti devono seguire convenzioni di denominazione specifiche. Inoltre, la directory in cui vengono salvati i report deve seguire una struttura prescritta. Per una descrizione di questi requisiti, consulta [Verifica della compatibilità dei set di rapporti con il Report Portal (Portale dei rapporti)...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Le password nel portale dei report ora sono conformi a AES-256 bit. Se si esegue l&#39;aggiornamento a Report Portal 2.0, aumentare il campo Dimensione campo per password da 50 a 150 nel database **users.mdb**. È necessario aumentare le dimensioni del campo per disporre le password con crittografia aggiornata.
>* Se stai eseguendo l&#39;aggiornamento a Report Portal 2.0, aumenta la dimensione del campo **Password** da 50 a 150 nel database users.mdb. È necessario aumentare le dimensioni del campo per disporre le password con crittografia aggiornata.
>* Il Report Portal (Portale dei rapporti) ora dispone di algoritmi di hashing più efficaci con supporto per la salatura. Se stai eseguendo l’aggiornamento a **Report Portal (Portale dei rapporti) 2.1**, aggiungi un nuovo campo di testo, *PasswordSalt* con dimensioni del campo pari a 20 caratteri nel database [!DNL users.mdb]di . Questo campo è necessario per memorizzare il sale password.

>


