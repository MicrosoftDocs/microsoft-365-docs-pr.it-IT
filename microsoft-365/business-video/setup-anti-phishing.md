---
title: Configurare la protezione anti-phishing
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come configurare la protezione anti-phishing.
ms.openlocfilehash: 32494eda4496d99e5e5f4def213ba7876f6c3183
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580415"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="12dd4-103">Configurare l'anti-phishing</span><span class="sxs-lookup"><span data-stu-id="12dd4-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="12dd4-104">Il phishing è un attacco dannoso in cui un messaggio di posta elettronica sembra essere stato inviato da una fonte familiare, ma tenta di raccogliere le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="12dd4-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="12dd4-105">Per impostazione predefinita, Microsoft 365 protezione anti-phishing, ma è possibile aumentare tale protezione affinando le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="12dd4-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="12dd4-106">Diamo un'occhiata.</span><span class="sxs-lookup"><span data-stu-id="12dd4-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="12dd4-107">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="12dd4-107">Try it!</span></span>

1. <span data-ttu-id="12dd4-108">Nell'interfaccia di amministrazione in [https://admin.microsoft.com](https://admin.microsoft.com) , selezionare **Sicurezza**, **Gestione minacce**, **Criteri**, quindi **ANTI-phishing ATP**.</span><span class="sxs-lookup"><span data-stu-id="12dd4-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="12dd4-109">Selezionare **Criterio predefinito** per affinarlo.</span><span class="sxs-lookup"><span data-stu-id="12dd4-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="12dd4-110">Nella sezione **Rappresentazione** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="12dd4-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="12dd4-111">Vai ad **Aggiungi domini da proteggere e** seleziona l'interruttore per includere automaticamente i domini di cui sei proprietario.</span><span class="sxs-lookup"><span data-stu-id="12dd4-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="12dd4-112">Vai a **Azioni**, apri l'elenco a discesa Se la **posta** elettronica viene inviata da un utente rappresentato e scegli l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="12dd4-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="12dd4-113">Aprire l'elenco a discesa **Se la posta elettronica viene inviata da un** dominio rappresentato e scegliere l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="12dd4-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="12dd4-114">Seleziona **Attiva suggerimenti per la sicurezza per la rappresentazione.**</span><span class="sxs-lookup"><span data-stu-id="12dd4-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="12dd4-115">Scegliere se i suggerimenti devono essere forniti agli utenti quando il sistema rileva utenti, domini o caratteri insoliti.</span><span class="sxs-lookup"><span data-stu-id="12dd4-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="12dd4-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="12dd4-116">Select **Save**.</span></span>
1. <span data-ttu-id="12dd4-117">Selezionare **Intelligence cassetta postale** e verificare che sia attivato.</span><span class="sxs-lookup"><span data-stu-id="12dd4-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="12dd4-118">Ciò consente alla posta elettronica di essere più efficiente imparando i modelli di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="12dd4-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="12dd4-119">Scegliere **Aggiungi mittenti e domini attendibili**.</span><span class="sxs-lookup"><span data-stu-id="12dd4-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="12dd4-120">Qui puoi aggiungere indirizzi di posta elettronica o domini che non devono essere classificati come rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="12dd4-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="12dd4-121">Scegliere **Rivedi le impostazioni,** assicurarsi che tutto sia corretto, selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="12dd4-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="12dd4-122">L'organizzazione ora ha una protezione migliore dalle minacce di phishing.</span><span class="sxs-lookup"><span data-stu-id="12dd4-122">Your organization now has better protection from phishing threats.</span></span>