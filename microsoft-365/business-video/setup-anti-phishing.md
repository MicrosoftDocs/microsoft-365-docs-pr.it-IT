---
title: Configurare la protezione anti-phishing
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come configurare la protezione anti-phishing.
ms.openlocfilehash: bcb6b8bac316b4b74c505656cb9a93e7a87e0830
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927875"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="e9a1a-103">Configurare l'anti-phishing</span><span class="sxs-lookup"><span data-stu-id="e9a1a-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="e9a1a-104">Il phishing è un attacco dannoso in cui un messaggio di posta elettronica sembra essere stato inviato da una fonte familiare, ma tenta di raccogliere le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="e9a1a-105">Per impostazione predefinita, Microsoft 365 include una protezione anti-phishing, ma è possibile aumentare tale protezione perfezionando le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="e9a1a-106">Diamo un'occhiata.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="e9a1a-107">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="e9a1a-107">Try it!</span></span>

1. <span data-ttu-id="e9a1a-108">Nell'interfaccia di amministrazione in [https://admin.microsoft.com](https://admin.microsoft.com) , selezionare **Sicurezza**, **Gestione minacce**, **Criteri** e quindi **Anti-phishing ATP.**</span><span class="sxs-lookup"><span data-stu-id="e9a1a-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="e9a1a-109">Selezionare **Criterio predefinito** per perfezionarlo.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="e9a1a-110">Nella sezione **Rappresentazione** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e9a1a-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="e9a1a-111">Passare ad **Aggiungi domini per proteggere e selezionare** l'interruttore per includere automaticamente i domini di cui si è proprietari.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="e9a1a-112">Passare ad **Azioni,** aprire l'elenco a discesa Se il messaggio di posta elettronica viene inviato da un utente rappresentato **e** scegliere l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="e9a1a-113">Aprire l'elenco a discesa **Se la posta elettronica** viene inviata da un dominio rappresentato e scegliere l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="e9a1a-114">Selezionare **Attiva suggerimenti per la sicurezza della rappresentazione.**</span><span class="sxs-lookup"><span data-stu-id="e9a1a-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="e9a1a-115">Scegliere se i suggerimenti devono essere forniti agli utenti quando il sistema rileva utenti, domini o caratteri insoliti.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="e9a1a-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-116">Select **Save**.</span></span>
1. <span data-ttu-id="e9a1a-117">Selezionare **Intelligence per le** cassette postali e verificare che sia attivata.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="e9a1a-118">In questo modo la posta elettronica può essere più efficiente grazie all'apprendimento dei modelli di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="e9a1a-119">Scegliere **Aggiungi mittenti e domini attendibili.**</span><span class="sxs-lookup"><span data-stu-id="e9a1a-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="e9a1a-120">Qui è possibile aggiungere indirizzi di posta elettronica o domini che non devono essere classificati come rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="e9a1a-121">Choose **Review your settings,** make sure everything is correct, select **Save**, then **Close.**</span><span class="sxs-lookup"><span data-stu-id="e9a1a-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="e9a1a-122">L'organizzazione ha ora una protezione migliore dalle minacce di phishing.</span><span class="sxs-lookup"><span data-stu-id="e9a1a-122">Your organization now has better protection from phishing threats.</span></span>