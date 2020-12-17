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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come configurare la protezione anti-phishing.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702894"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="71927-103">Configurare il sistema anti-phishing</span><span class="sxs-lookup"><span data-stu-id="71927-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="71927-104">Il phishing è un attacco dannoso in cui un messaggio di posta elettronica sembra essere stato inviato da un'origine familiare, ma tenta di raccogliere le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="71927-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="71927-105">Per impostazione predefinita, Microsoft 365 include una protezione anti-phishing, ma è possibile aumentare tale protezione affinando le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="71927-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="71927-106">Diamo un'occhiata.</span><span class="sxs-lookup"><span data-stu-id="71927-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="71927-107">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="71927-107">Try it!</span></span>

1. <span data-ttu-id="71927-108">Nell'interfaccia di amministrazione [https://admin.microsoft.com](https://admin.microsoft.com) , selezionare **sicurezza**, **gestione minacce**, **criteri**, quindi **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="71927-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="71927-109">Selezionare **criteri predefiniti** per affinarla.</span><span class="sxs-lookup"><span data-stu-id="71927-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="71927-110">Nella sezione **rappresentazione** selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="71927-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="71927-111">Andare a **Aggiungi domini per la protezione** e selezionare l'interruttore per includere automaticamente i domini che possiedi.</span><span class="sxs-lookup"><span data-stu-id="71927-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="71927-112">Andare a **azioni**, aprire il menu a discesa **se il messaggio di posta elettronica viene inviato da un utente rappresentato** e scegliere l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="71927-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="71927-113">Aprire l'elenco a discesa **se il messaggio di posta elettronica viene inviato da un dominio rappresentato** e scegliere l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="71927-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="71927-114">Selezionare **Attiva suggerimenti per la sicurezza della rappresentazione**.</span><span class="sxs-lookup"><span data-stu-id="71927-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="71927-115">Scegliere se i suggerimenti devono essere forniti agli utenti quando il sistema rileva utenti, domini o caratteri inusuali rappresentati.</span><span class="sxs-lookup"><span data-stu-id="71927-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="71927-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="71927-116">Select **Save**.</span></span>
1. <span data-ttu-id="71927-117">Selezionare **Intelligence cassetta postale** e verificare che sia attivata.</span><span class="sxs-lookup"><span data-stu-id="71927-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="71927-118">In questo modo il messaggio di posta elettronica può essere più efficiente tramite l'apprendimento dei modelli di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="71927-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="71927-119">Scegliere **Aggiungi mittenti e domini attendibili**.</span><span class="sxs-lookup"><span data-stu-id="71927-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="71927-120">Qui è possibile aggiungere gli indirizzi di posta elettronica o i domini che non devono essere classificati come rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="71927-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="71927-121">Scegliere **rivedere le impostazioni**, verificare che tutto sia corretto, selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="71927-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="71927-122">L'organizzazione ha ora una maggiore protezione dalle minacce di phishing.</span><span class="sxs-lookup"><span data-stu-id="71927-122">Your organization now has better protection from phishing threats.</span></span>