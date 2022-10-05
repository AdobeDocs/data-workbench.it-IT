---
description: Simile alla trasformazione AppendURI, la trasformazione PrependURI influisce sul campo interno utilizzato dal server di Data Workbench per creare la dimensione URI.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 5%

---

# PrependURI{#prependuri}

{{eol}}

Simile alla trasformazione AppendURI, la trasformazione PrependURI influisce sul campo interno utilizzato dal server di Data Workbench per creare la dimensione URI.

La [!DNL PrependURI] La trasformazione funziona aggiungendo il valore nel campo di input identificato davanti al valore attualmente presente nell’URI.

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile. |  |
| Ingresso | Nome del campo il cui valore è preceduto dall’URI. |  |

Nell’esempio seguente viene semplicemente anteposto il campo s-dns all’URI, estendendo la rappresentazione della dimensione URI al dominio richiesto dal dispositivo client.

![](assets/cfg_TransformationType_PrependURI.png)

In questo esempio, anteporre il campo s-dns all’URI

* [!DNL /modelview.asp&id=login]

restituisce il seguente URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Ora l’URI viene esteso per includere il dominio richiesto.
