---
description: Simile alla trasformazione AppendURI, la trasformazione PrependURI influisce sul campo interno utilizzato dal server workbench dati per costruire la dimensione URI.
solution: Analytics
title: PrependURI
topic: Data workbench
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# PrependURI{#prependuri}

Simile alla trasformazione AppendURI, la trasformazione PrependURI influisce sul campo interno utilizzato dal server workbench dati per costruire la dimensione URI.

La [!DNL PrependURI] trasformazione funziona aggiungendo il valore nel campo di input identificato al fronte del valore attualmente nell’URI.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore immesso non è disponibile. |  |
| Ingresso | Nome del campo il cui valore è preceduto dall’URI. |  |

Nell&#39;esempio seguente il campo s-dns viene semplicemente anteposto all&#39;URI, estendendo la rappresentazione della dimensione URI al dominio richiesto dal dispositivo client.

![](assets/cfg_TransformationType_PrependURI.png)

In questo esempio, anteponendo il campo s-dns all&#39;URI

* [!DNL /modelview.asp&id=login]

restituisce il seguente URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Ora l&#39;URI viene esteso per includere il dominio richiesto.
