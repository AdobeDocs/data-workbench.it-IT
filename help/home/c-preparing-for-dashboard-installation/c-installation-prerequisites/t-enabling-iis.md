---
description: Il primo passaggio consiste nell'abilitare il ruolo IIS sul server dashboard.
solution: Analytics
title: Abilitazione di IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abilitazione di IIS{#enabling-iis}

Il primo passaggio consiste nell&#39;abilitare il ruolo IIS sul server dashboard.

1. In **[!UICONTROL Administrative Tools]**, aprire il **[!UICONTROL Server Manager]**.
1. Fare clic con il pulsante destro del mouse sulla voce di menu Ruoli nella parte sinistra della **[!UICONTROL Server Manager]** finestra.
1. Select **[!UICONTROL Add Roles]**.
1. Seleziona **[!UICONTROL Web Server (IIS)]** e continua con il **[!UICONTROL Add Roles Wizard]**. Accertatevi che i seguenti servizi ruolo siano abilitati:

   | Funzioni HTTP comuni |
   |---|
   | Contenuto statico |
   | Documento predefinito |
   | Esplorazione directory |
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
   | Richiedi monitor |
   | Tracing |
   | Registrazione personalizzata |

   | Sicurezza |
   |---|
   | Autenticazione di base |
   | Autenticazione Windows |
   | Autenticazione URL |
   | Richiedi filtro |
   | Restrizioni IP e dominio |

   | Strumenti di gestione |
   |---|
   | Console di gestione IIS |
   | Script e strumenti di gestione IIS |
   | Servizio di gestione |

1. Seguire la procedura guidata per completare l&#39;installazione.
