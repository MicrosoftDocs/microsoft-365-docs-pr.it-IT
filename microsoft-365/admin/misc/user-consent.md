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
description: Informazioni sul consenso dell'utente alle app e su come attivarle per consentire alle app di terze parti di accedere alle informazioni di Microsoft 365 degli utenti.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914559"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gestione del consenso degli utenti alle app in Microsoft 365

Questa impostazione controlla se gli utenti possono concedere il consenso alle app che usano OpenID Connect e OAuth 2.0 per l'accesso e le richieste di accesso ai dati. Un'app può essere creata dall'organizzazione oppure da un'altra organizzazione di Office 365 o da terze parti.

Se attivi questa impostazione, queste app chiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirla. Se distoglie questa impostazione, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarle. In questo caso, è consigliabile configurare un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per usare qualsiasi app bloccata.

Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365. Non può invece concedere l'accesso alle informazioni degli altri utenti.

## <a name="turning-user-consent-on-or-off"></a>Attivazione o disattivazione del consenso dell'utente
<a name="__toc379982114"> </a>

Ecco come attivare o disattivare il consenso dell'utente per le app.

1. Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** \> **impostazioni organizzazione**  >  [Servizi](https://go.microsoft.com/fwlink/p/?linkid=2053743) e quindi selezionare Consenso **utente per le app**.

2. Nella pagina **Consenso utente alle app** seleziona l'opzione per attivare o disattivare il consenso dell'utente.

## <a name="more-info"></a>Altre informazioni
<a name="__toc379982114"> </a>

Per informazioni su come configurare le impostazioni di consenso in Azure Active Directory, vedere [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Per informazioni sulla gestione del consenso degli utenti alle app, vedere Gestione del consenso alle [applicazioni e valutazione delle richieste di consenso.](/azure/active-directory/manage-apps/manage-consent-requests)