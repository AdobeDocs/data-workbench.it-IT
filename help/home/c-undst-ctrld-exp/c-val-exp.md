---
description: Dopo aver implementato l'esperimento, verifica che l'esperimento funzioni correttamente.
solution: Analytics,Analytics
title: Convalida dell’esperimento
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Convalida dell’esperimento{#validating-the-experiment}

Dopo aver implementato l&#39;esperimento, verifica che l&#39;esperimento funzioni correttamente.

Come descritto in [Modifica del parametro ExpCookieURL (facoltativo)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), la pagina specificata nel parametro ExpCookieURL nel file di configurazione [!DNL Sensor] può essere utilizzata per inserirsi in un gruppo di esperimenti specifico.

La pagina virtuale predefinita è [!DNL /setcookie.htm], ma è necessario utilizzare il valore impostato nel parametro ExpCookieURL .

## Richiesta della pagina di test {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Per testare un gruppo sperimentale specifico per il tuo sito web, il tuo browser deve essere configurato per accettare i cookie e non devi disporre già di un cookie per questo sito web.

Ogni volta che desideri testare un nuovo gruppo, assicurati di cancellare i cookie per il sito web.

Per inserirsi in un gruppo specifico all’interno di un esperimento specifico, richiede la pagina di test con una stringa di query nel modulo seguente:

[!DNL https://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Ad esempio:

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando la richiesta di URL virtuale viene inviata al server, [!DNL Sensor] ti identifica come membro del gruppo specificato all’interno dell’esperimento specificato e quindi ti reindirizzerà alla directory principale del sito web. Ora puoi passare alla posizione appropriata sul sito web per verificare se viene visualizzato il contenuto corretto per l’esperimento e il gruppo.

Se doveste digitare quanto segue nel browser, il browser mostrerebbe la home page del sito web e vi inserirebbe nel gruppo index2 all&#39;interno dell&#39;esperimento New_Homepage:

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando i visitatori del gruppo index2 richiedono la home page, il collegamento grafico &quot;Richiedi una demo&quot; viene visualizzato più in alto sulla pagina, come nell&#39;immagine seguente:

![](assets/TestPage.png)
