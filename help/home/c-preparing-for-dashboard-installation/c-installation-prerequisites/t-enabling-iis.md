---
description: Il primo passo è quello di abilitare il ruolo IIS sul server del dashboard.
title: Abilitazione di IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Abilitazione di IIS{#enabling-iis}

{{eol}}

Il primo passo è quello di abilitare il ruolo IIS sul server del dashboard.

1. Sotto **[!UICONTROL Administrative Tools]**, apri **[!UICONTROL Server Manager]**.
1. Fare clic con il pulsante destro del mouse sulla voce di menu Ruoli nella parte sinistra del **[!UICONTROL Server Manager]** finestra.
1. Seleziona **[!UICONTROL Add Roles]**.
1. Seleziona **[!UICONTROL Web Server (IIS)]** e continua con **[!UICONTROL Add Roles Wizard]**. Assicurati che i seguenti servizi ruolo siano abilitati:

   | Funzionalità HTTP comuni |
   |---|
   | Contenuto statico |
   | Documento predefinito |
   | Navigazione nelle directory |
   | Errori HTTP |
   | Reindirizzamento HTTP |

   | Sviluppo di applicazioni |
   |---|
   | ASP.NET |
   | Estensibilità .NET |
   | Estensioni ISAPI |
   | Filtri ISAPI |

   | Salute e diagnostica |
   |---|
   | Registrazione HTTP |
   | Strumenti di registrazione |
   | Monitoraggio richieste |
   | Tracciamento |
   | Registrazione personalizzata |

   | Sicurezza |
   |---|
   | Autenticazione di base |
   | Autenticazione di Windows |
   | Autenticazione URL |
   | Filtro richieste |
   | Restrizioni IP e dominio |

   | Strumenti di gestione |
   |---|
   | Console di gestione IIS |
   | Script e strumenti di gestione IIS |
   | Servizio di gestione |

1. Seguire la procedura guidata per completare l&#39;installazione.
