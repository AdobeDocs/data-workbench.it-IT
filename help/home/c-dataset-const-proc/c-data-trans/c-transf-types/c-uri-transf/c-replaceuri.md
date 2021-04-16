---
description: La trasformazione ReplaceURI modifica il valore della dimensione URI interna in un nuovo valore.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

La trasformazione ReplaceURI modifica il valore della dimensione URI interna in un nuovo valore.

Se si specifica [!DNL URI Prefix], il valore risultante è semplicemente il prefisso URI concatenato con il valore specificato.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile. |  |
| Ingresso | Il valore da sostituire con l’URI. |  |
| Prefisso URI | Il valore (stringa) da anteporre al valore nel campo [!DNL Input] . |  |

>[!NOTE]
>
>Prima di applicare le trasformazioni [!DNL ReplaceURI], è necessario creare una nuova dimensione semplice con un elemento padre di [!DNL Page View]da una copia di cs-uri-stem o cs-uri. Per assistenza, contatta l&#39;Adobe.

Questo esempio illustra l&#39;utilizzo di [!DNL ReplaceURI] per sostituire le stringhe di query &quot;page=*pageid*&quot; con &quot; [!DNL homepage.html]&quot; ogni volta che *pageid* indica che la pagina principale del sito web è stata visualizzata. Il risultato finale è una visualizzazione più semplice dell’URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Per la trasformazione mostrata, la pagina

* [!DNL www.examplesite.com/info.html?page=1550]

viene modificato in

* [!DNL www.examplesite.com/homepage.html]
