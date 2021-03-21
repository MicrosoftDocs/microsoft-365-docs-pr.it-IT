---
title: Visualizzare lo stato di sincronizzazione della directory in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In questo articolo viene illustrato come controllare lo stato della sincronizzazione della directory in Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924661"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Visualizzare lo stato di sincronizzazione della directory in Microsoft 365

Se è stato integrato Servizi di dominio Active Directory locale con Azure Active Directory (Azure AD) sincronizzando l'ambiente locale con Microsoft 365, è anche possibile controllare lo stato della sincronizzazione.
  
## <a name="view-directory-synchronization-status"></a>Visualizzare lo stato della sincronizzazione della directory

- Accedi all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) e scegli **Stato DirSync** nella home page.
- In alternativa, è possibile passare a **Utenti** Utenti attivi e nella pagina \>  **Utenti** attivi scegliere **Altro** \> **Sincronizzazione directory.** Nel riquadro **Sincronizzazione directory** scegliere **Vai a Gestione DirSync.**

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informazioni nella pagina Gestisci sincronizzazione directory

Nella tabella seguente sono elencate le funzionalità su cui è possibile ottenere informazioni nella pagina.
  
Se si verifica un problema con la sincronizzazione della directory, gli errori sono elencati anche in questa pagina. Per ulteriori informazioni sui diversi errori che possono verificarsi, vedere Identificare gli errori di [sincronizzazione della directory in Microsoft 365.](identify-directory-synchronization-errors.md)
  
|Elemento|Scopo|
|:-----|:-----|
|**Domini verificati** | Numero di domini nel tenant di Microsoft 365 di cui si è verificato il proprio proprietario. |
|**Domini non verificati** | Domini aggiunti, ma non verificati. |
|**Sincronizzazione directory abilitata** |Vero o Falso. Specifica se è stata abilitata la sincronizzazione della directory. |
|**Sincronizzazione directory più recente** | Data e ora dell'ultima esecuzione della sincronizzazione della directory. Se l'ultima sincronizzazione è stata più di tre giorni fa, verranno visualizzati un avviso e un collegamento a uno strumento di risoluzione dei problemi. |
|**Sincronizzazione password abilitata** | Vero o Falso. Specifica se si dispone della sincronizzazione dell'hash delle password tra il tenant locale e il tenant di Microsoft 365. |
|**Ultima sincronizzazione password** | Data e ora dell'ultima esecuzione della sincronizzazione dell'hash delle password. Se l'ultima sincronizzazione è stata più di tre giorni fa, verranno visualizzati un avviso e un collegamento a uno strumento di risoluzione dei problemi. |
|**Versione client di sincronizzazione della directory** | Contiene un collegamento di download se è stata rilasciata una nuova versione di Azure AD Connect. |
|**Account del servizio di sincronizzazione della directory** | Visualizza il nome dell'account del servizio di sincronizzazione della directory di Microsoft 365. |
|||

## <a name="monitor-synchronization-health"></a>Monitorare l'integrità della sincronizzazione

In questa sezione verrà installato un agente di Azure AD Connect Health in ogni controller di dominio AD DS locale per monitorare l'infrastruttura di gestione delle identità e i servizi di sincronizzazione forniti da Azure AD Connect. Le informazioni sul monitoraggio vengono rese disponibili nel portale di Azure AD Connect Health, dove è possibile visualizzare avvisi, il monitoraggio delle prestazioni, analisi sull'utilizzo e altre informazioni.

La decisione di progettazione chiave su come usare Azure AD Connect Health si basa sul modo in cui si utilizza Azure AD Connect:

- Se si usa l'opzione **autenticazione gestita** iniziare con [Uso di Azure AD Connect Health con la sincronizzazione](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) per comprendere e configurare Azure AD Connect Health.
- Se si stanno sincronizzando soli i nomi di account e gruppi tramite l'**autenticazione federata** con Active Directory Federation Services (AD FS), iniziare con [Uso di Azure AD Connect Health con AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) per comprendere e configurare Azure AD Connect Health.

Al termine, avrai a che fare con:

- L'agente di Azure AD Connect Health è installato su ciascuno dei server del provider di identità locale.
- Il portale di Azure AD Connect Health mostra lo stato corrente dell'infrastruttura locale e delle attività di sincronizzazione con il tenant di Azure AD per l’abbonamento a Microsoft 365.