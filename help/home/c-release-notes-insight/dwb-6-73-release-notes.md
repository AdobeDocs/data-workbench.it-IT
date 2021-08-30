---
description: Nuove funzioni e problemi risolti in Data Workbench 6.73.
title: Note sulla versione di Data Workbench 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 26%

---

# Note sulla versione di Data Workbench 6.73{#data-workbench-release-notes}

Nuove funzioni e problemi risolti in Data Workbench 6.73.

## Correzioni {#section-160baf6ea04c45a993777ee4260691ed}

* È stato corretto un problema in Workstation a causa del quale gli utenti non potevano accedere da alcuni hardware ad alta risoluzione e con valore DPI elevato.
* È stato risolto un problema nel server a causa del quale l’opzione E-mail mancava nei nomi dei file Archivio quando si utilizzava l’accesso IMS.
* OpenSSL è stato aggiornato alla versione 1.1.0h, con diverse correzioni di vulnerabilità e nuovi moduli di cifratura SSL.
* Le librerie open source elencate di seguito sono state aggiornate alle versioni stabili più recenti

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* È stata aggiunta la registrazione di errori quando il numero di righe del file Lookup supera il limite di righe supportate (357913908 righe).

## Problema noto {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation versione 6.73 non si connette ai server Data Workbench versione 6.61 e precedenti. Il motivo è che le versioni precedenti del server utilizzano una forma debole di crittografia non supportata nella versione 6.73. Per abilitare il supporto per le versioni precedenti

   1. Ignora l&#39;elenco Cipers SSL predefinito sul server con un elenco di crittografie avanzate supportato da OpenSSL versione 1.0.1h. Per sovrascrivere, aggiungi la chiave &quot;SSL Cipers&quot; nei file &quot;Communications.cfg&quot; disponibili nelle directory &quot;Components&quot; e &quot;Components for Processing Servers&quot; (Componenti per i server di elaborazione). Ad esempio: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Assicurati che la chiave sia posizionata allo stesso livello della porta SSL. Per ulteriori informazioni, consulta [Impostazioni di configurazione delle comunicazioni](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Posiziona il file trust_ca_cert.pem più recente sul server 6.61 e sui server precedenti. Questa impostazione è applicabile a tutte le versioni di Workstation 6.7x.

Consulta le [note sulla versione archiviate](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) per Data Workbench da 5.3 a 5.52.
