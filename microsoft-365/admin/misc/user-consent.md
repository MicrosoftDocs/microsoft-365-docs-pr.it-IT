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
description: Informazioni sul consenso dell'utente alle app e su come attivarle per consentire alle app di terze parti di accedere alle informazioni Microsoft 365 degli utenti.
ms.openlocfilehash: b8f65b50e50b0e0b4d978388463bbd380ca60d4e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624502"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gestione del consenso dell'utente alle app in Microsoft 365

Questa impostazione controlla se gli utenti possono concedere il consenso alle app che usano OpenID Connessione e OAuth 2.0 per l'accesso e le richieste di accesso ai dati. Un'app può essere creata dall'interno dell'organizzazione oppure da un'altra organizzazione Office 365 o da terze parti.

Se attivi questa impostazione, queste app chiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirla. Se distoglie questa impostazione, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarle. In questo caso, è consigliabile configurare un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per usare qualsiasi app bloccata.

Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365. Non può invece concedere l'accesso alle informazioni degli altri utenti.

## <a name="turning-user-consent-on-or-off"></a>Attivazione o disattivazione del consenso dell'utente
<a name="__toc379982114"> </a>

Ecco come attivare o disattivare il consenso dell'utente per le app.

1. Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** Impostazioni organizzazione Servizi e quindi \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) selezionare Consenso **utente per le app**.

2. Nella pagina **Consenso utente alle app** seleziona l'opzione per attivare o disattivare il consenso dell'utente.

## <a name="related-content"></a>Contenuto correlato 
<a name="__toc379982114"> </a>

[Configurare il flusso di lavoro del consenso dell'amministratore](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (articolo)\
[Gestione del consenso alle applicazioni e valutazione delle richieste di consenso](/azure/active-directory/manage-apps/manage-consent-requests) (articolo)