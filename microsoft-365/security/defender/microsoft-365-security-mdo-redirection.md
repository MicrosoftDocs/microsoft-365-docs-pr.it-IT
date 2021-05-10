---
title: Reindirizzamento degli account da Microsoft Defender per Office 365 al nuovo centro sicurezza Microsoft 365 sicurezza
description: Come reindirizzare da Defender per Office 365 al centro sicurezza Microsoft 365 sicurezza.
keywords: Microsoft 365 centro sicurezza, Guida introduttiva al centro sicurezza Microsoft 365, reindirizzamento del centro sicurezza
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 40d86f9f3a4896bbe788f0a9894a7e08efe3a690
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301729"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="5b006-104">Reindirizzamento degli account da Microsoft Defender per Office 365 al centro sicurezza Microsoft 365 sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b006-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5b006-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5b006-105">**Applies to:**</span></span>

- <span data-ttu-id="5b006-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b006-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5b006-107">Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5b006-107">Defender for Office 365</span></span>

<span data-ttu-id="5b006-108">In questo articolo viene illustrato come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dall'ex Centro sicurezza e conformità Microsoft (protection.office.com o securitycenter.microsoft.com) al Centro sicurezza Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5b006-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="5b006-109">Cosa aspettarsi</span><span class="sxs-lookup"><span data-stu-id="5b006-109">What to expect</span></span>
<span data-ttu-id="5b006-110">Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità correlate alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati al Centro sicurezza Microsoft 365 ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="5b006-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="5b006-111">Altre informazioni sulle modifiche: [Microsoft Defender per Office 365 nel Centro sicurezza Microsoft 365 sicurezza](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="5b006-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="5b006-112">Con il reindirizzamento automatico attivato, gli utenti verranno instradati Microsoft 365 centro sicurezza quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b006-112">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="5b006-113">Queste includono funzionalità nella sezione Gestione delle minacce e nel dashboard e nei report di Gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="5b006-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="5b006-114">Gli elementi nel Office 365 sicurezza e conformità non correlati alla sicurezza non vengono reindirizzati al Centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5b006-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="5b006-115">Gli elementi correlati alla conformità sono disponibili nel Centro Microsoft 365 conformità e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5b006-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="5b006-116">Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="5b006-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="5b006-117">Office 365 avvisi di sicurezza vengono visualizzati sia nel Centro sicurezza Microsoft 365 che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="5b006-117">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="5b006-118">Configurare il reindirizzamento del portale</span><span class="sxs-lookup"><span data-stu-id="5b006-118">Set up portal redirection</span></span>
<span data-ttu-id="5b006-119">Per avviare l'instradamento degli account al centro sicurezza Microsoft 365 in security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="5b006-119">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="5b006-120">Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b006-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="5b006-121">[Accedi al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5b006-121">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="5b006-122">Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5b006-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="5b006-123">Attiva l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="5b006-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="5b006-124">Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale Microsoft 365 centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5b006-124">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="5b006-125">Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5b006-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="5b006-126">È possibile tornare a usare il portale precedente?</span><span class="sxs-lookup"><span data-stu-id="5b006-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="5b006-127">Se qualcosa non funziona per te o se c'è qualcosa che non puoi completare tramite il portale del centro sicurezza Microsoft 365, vogliamo sentirlo usando l'opzione di feedback del portale.</span><span class="sxs-lookup"><span data-stu-id="5b006-127">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="5b006-128">Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattare il tuo amico pm direttamente tramite l'anteprima privata o contattarci tramite il modulo Invia feedback.</span><span class="sxs-lookup"><span data-stu-id="5b006-128">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="5b006-129">Per ripristinare il portale precedente:</span><span class="sxs-lookup"><span data-stu-id="5b006-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="5b006-130">[Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b006-130">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="5b006-131">Passare a **Impostazioni**  >  **endpoint di**  >  **reindirizzamento**  >  **del portale generale**.</span><span class="sxs-lookup"><span data-stu-id="5b006-131">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="5b006-132">Attivare o disattivare l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="5b006-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="5b006-133">Fai **clic su** & feedback quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="5b006-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="5b006-134">Questa impostazione può essere nuovamente abilitata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="5b006-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="5b006-135">Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5b006-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="5b006-136">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="5b006-136">Related information</span></span>
- [<span data-ttu-id="5b006-137">Panoramica del Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b006-137">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="5b006-138">Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b006-138">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="5b006-139">Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b006-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="5b006-140">Infografica XDR e SIEM</span><span class="sxs-lookup"><span data-stu-id="5b006-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="5b006-141">Il nuovo defender</span><span class="sxs-lookup"><span data-stu-id="5b006-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="5b006-142">Informazioni su Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b006-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="5b006-143">Portali di sicurezza Microsoft e centri di amministrazione</span><span class="sxs-lookup"><span data-stu-id="5b006-143">Microsoft security portals and admin centers</span></span>](portals.md)
