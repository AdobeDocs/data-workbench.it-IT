---
description: Configurare le dimensioni dell'ora in modo che vengano visualizzate correttamente per le impostazioni internazionali.
title: Localizzazione delle dimensioni di ora
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Localizzazione delle dimensioni di ora{#localizing-time-dimensions}

Configurare le dimensioni dell&#39;ora in modo che vengano visualizzate correttamente per le impostazioni internazionali.

È possibile configurare il formato visualizzato delle dimensioni temporali in base alle impostazioni internazionali nel **[!DNL Standard Time Dimensions.cfg]** file (per impostazione predefinita, in **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimensions.cfg]**).

Ad esempio, in America del Nord è possibile indicare la data del 3 maggio 2015 come 5/3/15 oppure **`%m/%d/%y`**. Tuttavia, in altre parti del mondo questo potrebbe essere interpretato come `%d/%m/%y`, o 5 Marzo 2015, a causa di un&#39;ambiguità nei valori. Per evitare questa situazione, un amministratore potrebbe desiderare modificare il formato visualizzato in modo che corrisponda alle aspettative degli utenti in una lingua.

## 1. Sovrascrivi dimensioni tempo predefinito in dimensioni ora standard.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Per abilitare questa funzione, l’amministratore deve ignorare le impostazioni predefinite modificando le dimensioni dell’ora esistenti o creando nuove dimensioni temporali con parametri aggiuntivi.

Segue un esempio di dimensione temporale modificata.

I valori **Formato** per Settimana, Ora, Giorno, Mese e Ora del giorno sono impostati sui valori predefiniti nell&#39;esempio.

>[!NOTE]
>
>Se queste righe vengono omesse, il comportamento di Workbench dati non subirà modifiche e la dimensione verrà compilata utilizzando le impostazioni predefinite.

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

## 2. Configurare il file meta.cfg {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Inoltre, è necessario che l&#39;amministratore del pacchetto aggiunga questi parametri e le relative impostazioni predefinite al **[!DNL meta.cfg]** file del profilo. Questo consente l&#39;editing dalla workstation.

Ecco un estratto da un **[!DNL meta.cfg]** file configurato.

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

Esempio di un **[!DNL meta.cfg]** file nella workstation:

![](assets/dwb_time_format.png)

L&#39;amministratore può quindi accedere al **File Manager**, aprire i file in cui sono configurate le dimensioni dell&#39;ora (ad es., **[!DNL Standard Time Dimensions.cfg]**) e modificarli utilizzando la workstation.
