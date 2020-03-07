---
description: La trasformazione ReplaceURI modifica il valore nella dimensione URI interna in un nuovo valore.
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

La trasformazione ReplaceURI modifica il valore nella dimensione URI interna in un nuovo valore.

Se [!DNL URI Prefix] viene specificato, il valore risultante è semplicemente il prefisso URI concatenato con il valore immesso.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore immesso non è disponibile. |  |
| Ingresso | Il valore da sostituire all’URI. |  |
| Prefisso URI | Il valore (stringa) da anteporre al valore nel [!DNL Input] campo. |  |

>[!NOTE]
>
>Prima di applicare [!DNL ReplaceURI] le trasformazioni, è necessario creare una nuova dimensione semplice con un elemento padre di [!DNL Page View]da una copia di cs-uri-stem o cs-uri. Per assistenza, contattate Adobe.

Questo esempio illustra l’utilizzo di [!DNL ReplaceURI] per sostituire le stringhe di query &quot;page=*pageid*&quot; con &quot; [!DNL homepage.html]&quot; ogni volta che *pageid* indica che è stata visualizzata la pagina iniziale del sito Web. Il risultato finale è una visualizzazione più semplice dell’URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Per la trasformazione visualizzata, la pagina

* [!DNL www.examplesite.com/info.html?page=1550]

vengono modificati in

* [!DNL www.examplesite.com/homepage.html]

