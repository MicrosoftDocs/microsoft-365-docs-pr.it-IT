---
title: Gestione del consenso dell'utente alle app in Microsoft 365
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
description: Informazioni sul consenso dell'utente alle app e su come attivarle per consentire alle app di terze parti di accedere alle informazioni di Microsoft 365 degli utenti.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999572"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gestione del consenso dell'utente alle app in Microsoft 365

Questa impostazione controlla se gli utenti possono concedere il consenso alle app che usano OpenID Connect e OAuth 2.0 per l'accesso e le richieste di accesso ai dati. Un'app può essere creata all'interno dell'organizzazione oppure da un'altra organizzazione di Office 365 o da terze parti.

Se attivi questa impostazione, queste app chiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirla. Se distoglie questa impostazione, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarle. In questo caso, è consigliabile configurare un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per usare qualsiasi app bloccata.

Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365. Non può invece concedere l'accesso alle informazioni degli altri utenti.

## <a name="turning-user-consent-on-or-off"></a>Attivazione o disattivazione del consenso dell'utente
<a name="__toc379982114"> </a>

Ecco come attivare o disattivare il consenso dell'utente per le app.

1. Nell'interfaccia di amministrazione passare alla **pagina** Impostazioni organizzazione Servizi e quindi selezionare Consenso \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) **utente per le app.**

2. Nella pagina **Consenso utente per le app** seleziona l'opzione per attivare o disattivare il consenso dell'utente.

## <a name="more-info"></a>Altre informazioni
<a name="__toc379982114"> </a>

Per informazioni su come configurare le impostazioni di consenso in Azure Active Directory, vedere Configurare il flusso di lavoro per il [consenso dell'amministratore.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)

Per informazioni sulla gestione del consenso dell'utente alle app, vedere Gestione del consenso alle applicazioni [e valutazione delle richieste di consenso.](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)