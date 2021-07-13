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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Informazioni sul consenso dell'utente alle app e su come attivarle per consentire alle app di terze parti di accedere alle informazioni Microsoft 365 degli utenti.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391232"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="fc879-103">Gestione del consenso dell'utente alle app in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc879-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="fc879-104">Questa impostazione controlla se gli utenti possono concedere il consenso alle app che usano OpenID Connessione e OAuth 2.0 per l'accesso e le richieste di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="fc879-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="fc879-105">Un'app può essere creata dall'interno dell'organizzazione oppure da un'altra organizzazione Office 365 o da terze parti.</span><span class="sxs-lookup"><span data-stu-id="fc879-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="fc879-106">Se attivi questa impostazione, queste app chiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirla.</span><span class="sxs-lookup"><span data-stu-id="fc879-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="fc879-107">Se distoglie questa impostazione, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarle.</span><span class="sxs-lookup"><span data-stu-id="fc879-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="fc879-108">In questo caso, è consigliabile configurare un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per usare qualsiasi app bloccata.</span><span class="sxs-lookup"><span data-stu-id="fc879-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="fc879-109">Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc879-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="fc879-110">Non può invece concedere l'accesso alle informazioni degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="fc879-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="fc879-111">Attivazione o disattivazione del consenso dell'utente</span><span class="sxs-lookup"><span data-stu-id="fc879-111">Turning user consent on or off</span></span>

<span data-ttu-id="fc879-112">Ecco come attivare o disattivare il consenso dell'utente per le app.</span><span class="sxs-lookup"><span data-stu-id="fc879-112">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="fc879-113">Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** Impostazioni organizzazione Servizi e quindi \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) selezionare Consenso **utente per le app**.</span><span class="sxs-lookup"><span data-stu-id="fc879-113">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="fc879-114">Nella pagina **Consenso utente alle app** seleziona l'opzione per attivare o disattivare il consenso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fc879-114">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="fc879-115">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="fc879-115">Related content</span></span> 

<span data-ttu-id="fc879-116">[Configurare il flusso di lavoro del consenso dell'amministratore](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (articolo)</span><span class="sxs-lookup"><span data-stu-id="fc879-116">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="fc879-117">[Gestione del consenso alle applicazioni e valutazione delle richieste di consenso](/azure/active-directory/manage-apps/manage-consent-requests) (articolo)</span><span class="sxs-lookup"><span data-stu-id="fc879-117">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>