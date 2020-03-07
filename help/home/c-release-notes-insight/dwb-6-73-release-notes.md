---
description: Nuove funzioni e problemi risolti in Workbench dati 6.73.
title: Note sulla versione di Workbench dati 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.73 Release Notes{#data-workbench-release-notes}

Nuove funzioni e problemi risolti in Workbench dati 6.73.

## Data Workbench 6.73 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Nuove funzioni e problemi risolti in Workbench dati 6.73.

## Problemi risolti {#section-160baf6ea04c45a993777ee4260691ed}

* È stato corretto un problema in Workstation a causa del quale gli utenti non potevano accedere da alcuni hardware ad alta risoluzione e con valore DPI elevato.
* È stato risolto un problema nel server in cui l&#39;e-mail mancava nei nomi dei file di archivio quando si utilizzava l&#39;accesso IMS.
* OpenSSL è stato aggiornato alla versione 1.1.0h, con diverse correzioni di vulnerabilità e nuovi moduli di cifratura SSL.
* Aggiornate le librerie open source elencate di seguito alle ultime versioni stabili

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* È stata aggiunta la registrazione di errori quando il numero di righe del file Lookup supera il limite di righe supportate (357913908 righe).

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* La versione 6.73 di Workbench dati non si collega ai server Workbench dati 6.61 e versioni precedenti. Il motivo è che le versioni server precedenti utilizzano una forma debole di caratteri non supportata nella versione 6.73. Per abilitare il supporto per le versioni precedenti

   1. Ignorare l’elenco Cipher SSL predefinito sul server con un elenco di crittografia avanzato supportato da OpenSSL versione 1.0.1h. Per ignorare, aggiungete la chiave &quot;SSL Cipher&quot; nei file ‘Communications.cfg’ disponibili nelle directory ‘Components’ e ‘Components for Processing Servers’. Ad esempio: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Verificate che la chiave sia posizionata allo stesso livello della porta SSL. Per informazioni dettagliate, consulta Impostazioni di configurazione [delle comunicazioni](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Inserite l&#39;ultimo file trust_ca_cert.pem sul server 6.61 e sui server precedenti. Questa impostazione è applicabile a tutte le versioni di Workstation 6.7x.

Vedere [le note](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) di rilascio archiviate per Workbench dati da 5.3 a 5.52.
