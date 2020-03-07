---
description: Questa è una guida rapida che fornisce i passaggi minimi necessari per convalidare la configurazione dell'FTP interno ed esterno.
title: Convalida dei server FTP interni ed esterni
uuid: bc381c1d-df27-4009-920b-1a804b36c204
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Convalida dei server FTP interni ed esterni{#validation-of-internal-and-external-ftp-servers}

Questa è una guida rapida che fornisce i passaggi minimi necessari per convalidare la configurazione dell&#39;FTP interno ed esterno.

Un FTP interno viene utilizzato quando un consulente/architetto interno ad Adobe deve connettersi al sito FTP per il caricamento o il download di file, mentre un FTP esterno è principalmente destinato all&#39;utente, in qualità di utente, per caricare i file di dati richiesti.

Per ulteriori informazioni sulla configurazione dei server FTP, vedere [File Transfer Protocol](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html).

## Passaggi di convalida - FTP esterno {#section-24428111b5c542ce81a765cd63424b97}

1. Aprite un prompt dei comandi. (Windows+R e digitare cmd)
1. Tipo ftp `<ftp server>`
1. Immettete nome utente e password. ![](assets/dwb_impl_ftp1.png)

1. Modificare la directory locale da cui è possibile spostare alcuni file. Utilizzate questo comando:

[!DNL ftp> lcd C:\Users\andixit\Desktop]

directory locale ora [!DNL C:\Users\andixit\Desktop].

1. Copiare il file dalla posizione locale a quella remota. ![](assets/dwb_impl_ftp2.png)

1. Disconnessione dal server remoto. (Usa sotto, comando)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Un altro modo per convalidare l&#39;FTP è utilizzare Filezilla. Fornite nome host, nome utente, password e porta. Il lato destro del pannello è un sito remoto e il lato sinistro è un sito locale. Per convalidare i file di trascinamento FTP dal sito locale al sito remoto e v.v.

![](assets/dwb_impl_ftp3.png)

## Passaggi di convalida - FTP interno {#section-b1f7a789ad6848cf9027f7953d81066e}

I passaggi precedenti possono essere seguiti per convalidare ftp interno da qualsiasi server Adobe.
