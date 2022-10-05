---
description: Questa è una guida rapida che ti offre i passaggi minimi necessari per convalidare la configurazione FTP interna ed esterna.
title: Convalida dei server FTP interni ed esterni
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 6%

---

# Convalida dei server FTP interni ed esterni{#validation-of-internal-and-external-ftp-servers}

{{eol}}

Questa è una guida rapida che ti offre i passaggi minimi necessari per convalidare la configurazione FTP interna ed esterna.

Un FTP interno viene utilizzato quando un consulente/architetto interno ad Adobe deve connettersi al sito FTP per il caricamento o il download dei file, mentre un FTP esterno è principalmente per te come utente per caricare i file di dati richiesti.

Per ulteriori informazioni sulla configurazione dei server FTP, vedi [Protocollo di trasferimento file](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html).

## Passaggi di convalida - FTP esterno {#section-24428111b5c542ce81a765cd63424b97}

1. Apri un prompt dei comandi. (Windows+R e digitare cmd)
1. Tipo ftp `<ftp server>`
1. Immetti nome utente e password. ![](assets/dwb_impl_ftp1.png)

1. Modificare la directory locale da cui è possibile spostare alcuni file. Usa questo comando:

[!DNL ftp> lcd C:\Users\andixit\Desktop]

directory locale [!DNL C:\Users\andixit\Desktop].

1. Copiare il file dalla posizione locale a quella remota. ![](assets/dwb_impl_ftp2.png)

1. Disconnessione dal server remoto. (Usa sotto il comando)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Un altro modo per convalidare FTP è quello di utilizzare Filezilla. Specificare nome host, nome utente, password e porta. Il lato destro del pannello è un sito remoto e il lato sinistro è un sito locale. Per convalidare FTP, trascina e rilascia i file dal sito locale a quello remoto e v.v.

![](assets/dwb_impl_ftp3.png)

## Passaggi di convalida - FTP interno {#section-b1f7a789ad6848cf9027f7953d81066e}

I passaggi precedenti possono essere seguiti per convalidare l’ftp interno da qualsiasi server Adobe.
