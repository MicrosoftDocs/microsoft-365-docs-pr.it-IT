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
description: In questo articolo, informazioni su come è possibile controllare lo stato della sincronizzazione della directory in Office 365.
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326950"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Visualizzare lo stato di sincronizzazione della directory in Microsoft 365

Se sono stati integrati i servizi di dominio Active Directory (AD DS) locali con Azure Active Directory (Azure AD) sincronizzando l'ambiente locale con Microsoft 365, è anche possibile controllare lo stato della sincronizzazione.
  
## <a name="view-directory-synchronization-status"></a>Visualizzare lo stato della sincronizzazione della directory

- Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) e scegliere **stato dirsync** nella Home page.
- In alternativa, è possibile accedere agli utenti attivi **degli utenti** \> **Active users**, quindi nella pagina **utenti attivi** scegliere **altre** \> **sincronizzazione della directory**. Nel riquadro di **sincronizzazione della directory** scegliere **Vai a gestione dirsync**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informazioni sulla pagina Gestisci sincronizzazione directory

Nella tabella seguente sono elencate le funzionalità che consentono di ottenere informazioni sulla pagina.
  
Se si verifica un problema con la sincronizzazione della directory, anche gli errori sono elencati in questa pagina. Per ulteriori informazioni sui diversi errori che potrebbero verificarsi, vedere [identificare gli errori di sincronizzazione della directory in Microsoft 365](identify-directory-synchronization-errors.md).
  
|Elemento|Scopo|
|:-----|:-----|
|**Domini verificati** | Il numero di domini nel tenant Microsoft 365 verificato che si è proprietari. |
|**Domini non verificati** | Domini che sono stati aggiunti, ma non sono stati verificati. |
|**Sincronizzazione della directory attivata** |True o false. Specifica se è stata abilitata la sincronizzazione della directory. |
|**Sincronizzazione della directory più recente** | Ultima esecuzione della sincronizzazione della directory. Verrà visualizzato un messaggio di avviso e un collegamento a uno strumento per la risoluzione dei problemi se l'ultima sincronizzazione è stata più di tre giorni fa. |
|**Sincronizzazione password attivata** | True o false. Specifica se si dispone della sincronizzazione hash delle password tra il tenant locale e quello Microsoft 365. |
|**Sincronizzazione ultima password** | L'ultima volta che è stata eseguita la sincronizzazione hash password. Verrà visualizzato un messaggio di avviso e un collegamento a uno strumento per la risoluzione dei problemi se l'ultima sincronizzazione è stata più di tre giorni fa. |
|**Versione client di sincronizzazione della directory** | Contiene un collegamento di download se è stata rilasciata una nuova versione di Azure AD Connect. |
|**Account del servizio di sincronizzazione della directory** | Visualizza il nome dell'account del servizio di sincronizzazione della directory Microsoft 365. |
|||

## <a name="monitor-synchronization-health"></a>Monitorare l'integrità della sincronizzazione

In questa sezione verrà installato un agente di Azure AD Connect Health in ogni controller di dominio AD DS locale per monitorare l'infrastruttura di gestione delle identità e i servizi di sincronizzazione forniti da Azure AD Connect. Le informazioni sul monitoraggio vengono rese disponibili nel portale di Azure AD Connect Health, dove è possibile visualizzare avvisi, il monitoraggio delle prestazioni, analisi sull'utilizzo e altre informazioni.

La decisione di progettazione chiave su come usare Azure AD Connect Health si basa sul modo in cui si utilizza Azure AD Connect:

- Se si usa l'opzione **autenticazione gestita** iniziare con [Uso di Azure AD Connect Health con la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) per comprendere e configurare Azure AD Connect Health.
- Se si stanno sincronizzando soli i nomi di account e gruppi tramite l'**autenticazione federata** con Active Directory Federation Services (AD FS), iniziare con [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) per comprendere e configurare Azure AD Connect Health.

Al termine, è possibile eseguire le operazioni seguenti:

- L'agente di Azure AD Connect Health è installato su ciascuno dei server del provider di identità locale.
- Il portale di Azure AD Connect Health mostra lo stato corrente dell'infrastruttura locale e delle attività di sincronizzazione con il tenant di Azure AD per l’abbonamento a Microsoft 365.

