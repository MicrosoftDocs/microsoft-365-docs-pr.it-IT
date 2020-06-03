---
title: Gestione del consenso degli utenti alle app in Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Informazioni sul consenso degli utenti per le app e su come attivarle per consentire alle app di terze parti di accedere all'informazione Microsoft 365.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498318"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gestione del consenso degli utenti alle app in Microsoft 365

Questa impostazione consente di controllare se gli utenti possono concedere il consenso alle app che utilizzano OpenID Connect e OAuth 2,0 per l'accesso e le richieste di accedere ai dati. Un'app può essere creata dall'interno dell'organizzazione oppure può provenire da un'altra organizzazione di Office 365 o da terze parti.

Se si attiva questa impostazione, tali app richiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirli. Se questa impostazione viene disattivata, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarli. In questo caso, prendere in considerazione la configurazione di un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per l'utilizzo di qualsiasi applicazione bloccata.

Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365. Non può invece concedere l'accesso alle informazioni degli altri utenti.

## <a name="turning-user-consent-on-or-off"></a>Attivazione o disattivazione del consenso dell'utente
<a name="__toc379982114"> </a>

Ecco come abilitare o disabilitare l'autorizzazione utente per le app.

1. Nell'interfaccia di amministrazione, passare alla pagina **Impostazioni** \> **org Settings**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) , quindi selezionare **consenso utente per le app**.

2. Nella pagina **autorizzazioni utente per le app** selezionare l'opzione per abilitare o disabilitare il consenso dell'utente.

## <a name="more-info"></a>Altre informazioni
<a name="__toc379982114"> </a>

Per informazioni su come configurare le impostazioni di consenso in Azure Active Directory, leggere [configurare il flusso di lavoro di approvazione dell'amministratore](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Per ulteriori informazioni sulla gestione del consenso degli utenti alle app, vedere [Managing consenso to Applications and valutare le richieste di consenso](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).