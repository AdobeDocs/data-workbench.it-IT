---
description: La trasformazione ChangeCase modifica le maiuscole/minuscole della stringa nel parametro Input come specificato dal parametro Action.
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

La trasformazione ChangeCase modifica le maiuscole/minuscole della stringa nel parametro Input come specificato dal parametro Action.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Azione | Superiore o inferiore. Specifica se il caso deve essere modificato in alto o in basso. | Lower |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| Ingresso | Nome del campo dalla voce di registro da utilizzare come input. |  |
| Uscita | Nome del campo di output. |  |

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito Web, il caso della stringa all&#39;interno del campo s-dns viene modificato in lettere maiuscole e il nuovo valore viene restituito nel nuovo campo x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)

