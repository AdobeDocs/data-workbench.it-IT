---
description: Configura le dimensioni ora da visualizzare correttamente per le impostazioni internazionali.
title: Localizzazione delle dimensioni orarie
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
exl-id: 950fe70b-a687-4b9c-b29f-555139740809
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Localizzazione delle dimensioni orarie{#localizing-time-dimensions}

{{eol}}

Configura le dimensioni ora da visualizzare correttamente per le impostazioni internazionali.

Puoi configurare il formato visualizzato delle dimensioni temporali in base alle impostazioni internazionali nella **[!DNL Standard Time Dimensions.cfg]** file (per impostazione predefinita in **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimension.cfg]**).

Ad esempio, in Nord America è possibile indicare la data del 3 maggio 2015 come 3/5/15, oppure **`%m/%d/%y`**. Tuttavia, in altre parti del mondo questo potrebbe essere interpretato come `%d/%m/%y`, o 5 marzo 2015 a causa di un’ambiguità nei valori. Per evitare questa situazione, un amministratore potrebbe voler modificare il formato visualizzato in modo che corrisponda alle aspettative degli utenti in un’impostazione internazionale.

## 1. Ignorare i Dimension di ora predefiniti in Dimension di ora standard.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Per abilitare questa funzione, l’amministratore deve ignorare i valori predefiniti modificando le dimensioni temporali esistenti o creando nuove dimensioni temporali con parametri aggiuntivi.

Segue un esempio di dimensione temporale modificata.

La **Formato** I valori per Settimana, Ora, Giorno, Mese e Ora del giorno sono impostati sui valori predefiniti nell’esempio.

>[!NOTE]
>
>Se queste righe vengono omesse, il comportamento della Data Workbench non viene modificato e la dimensione viene compilata utilizzando i valori predefiniti.

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. Configura il file meta.cfg {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Inoltre, è necessario che l’amministratore del pacchetto aggiunga questi parametri e le relative impostazioni predefinite a **[!DNL meta.cfg]** file. Questo consente l&#39;editing dalla workstation.

Ecco un estratto da una configurazione **[!DNL meta.cfg]** file.

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

Ecco un esempio di **[!DNL meta.cfg]** file nella workstation:

![](assets/dwb_time_format.png)

L’amministratore può quindi accedere al **Gestione file**, apri i file in cui sono configurate le dimensioni temporali (ad esempio, **[!DNL Standard Time Dimensions.cfg]**) e modificali utilizzando nella workstation.
