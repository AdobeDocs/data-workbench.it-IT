---
description: Dopo aver implementato l'esperimento, è necessario verificare il corretto funzionamento dell'esperimento.
solution: Analytics,Analytics
title: Convalida dell’esperimento
topic: Data workbench
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---


# Convalida dell’esperimento{#validating-the-experiment}

Dopo aver implementato l&#39;esperimento, è necessario verificare il corretto funzionamento dell&#39;esperimento.

Come discusso in [Modifica del parametro ExpCookieURL (facoltativo)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), la pagina specificata nel parametro ExpCookieURL nel file di [!DNL Sensor] configurazione può essere utilizzata per inserirsi in un gruppo di esperimenti specifico.

La pagina virtuale predefinita è [!DNL /setcookie.htm], ma è necessario utilizzare il valore impostato nel parametro ExpCookieURL.

## Richiesta della pagina di test {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Per testare un gruppo di esperimenti specifico per il sito Web, il browser deve essere configurato per accettare i cookie e non è già necessario avere un cookie per il sito Web.

Ogni volta che desiderate testare un nuovo gruppo, accertatevi di cancellare i cookie per il sito Web.

Per inserirvi in un gruppo specifico all’interno di un esperimento specifico, richiedete alla pagina di test una stringa di query nel modulo seguente:

[!DNL http://] *&lt;[!DNL sitename/?Experiment Name=Group Name]>*

Ad esempio:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando la richiesta di URL virtuale viene inviata al server, [!DNL Sensor] vi identifica come membri del gruppo specificato nell’esperimento specificato e quindi vi reindirizzerà alla directory principale del sito Web. Ora potete passare alla posizione appropriata sul sito Web per verificare se il contenuto corretto viene visualizzato per l’esperimento e il gruppo.

Se doveste digitare quanto segue nel browser, il browser visualizzerebbe la home page del sito Web e vi inserirebbe nel gruppo index2 all&#39;interno dell&#39;esperimento New_Homepage:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando i visitatori del gruppo index2 richiedono la pagina principale, il collegamento grafico &quot;Richiedi una demo&quot; viene visualizzato più in alto sulla pagina, come nel grafico seguente:

![](assets/TestPage.png)

