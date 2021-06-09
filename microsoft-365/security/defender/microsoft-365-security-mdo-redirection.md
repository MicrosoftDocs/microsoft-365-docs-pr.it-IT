---
title: Reindirizzamento degli account Office 365 Centro sicurezza e conformità al nuovo Microsoft 365 Defender
description: Come reindirizzare da Defender per Office 365 a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Guida introduttiva a Microsoft 365 Defender, reindirizzamento del centro sicurezza
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842520"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="36790-104">Reindirizzamento degli account da Office 365 Centro sicurezza e conformità a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36790-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="36790-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="36790-105">**Applies to:**</span></span>

- <span data-ttu-id="36790-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36790-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="36790-107">Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="36790-107">Defender for Office 365</span></span>

<span data-ttu-id="36790-108">In questo articolo viene illustrato come instradare gli account a Microsoft 365 Office 365 Defender abilitando il reindirizzamento automatico dal centro sicurezza e conformità (protection.office.com) precedente a Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="36790-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="36790-109">Cosa aspettarsi</span><span class="sxs-lookup"><span data-stu-id="36790-109">What to expect</span></span>
<span data-ttu-id="36790-110">Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità correlate alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati a Microsoft 365 Defender ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="36790-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="36790-111">Altre informazioni sulle modifiche: [Microsoft Defender per Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="36790-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="36790-112">Con il reindirizzamento automatico attivato, gli utenti verranno instradati a Microsoft 365 Defender quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="36790-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="36790-113">Queste includono funzionalità nella sezione Gestione delle minacce e nel dashboard e nei report di Gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="36790-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="36790-114">Gli elementi nel Office 365 sicurezza e conformità non correlati alla sicurezza non vengono reindirizzati a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="36790-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="36790-115">Gli elementi correlati alla conformità sono disponibili nel Centro Microsoft 365 conformità e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="36790-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="36790-116">Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="36790-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="36790-117">Office 365 avvisi di sicurezza vengono visualizzati sia in Microsoft 365 Defender che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="36790-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="36790-118">Configurare il reindirizzamento del portale</span><span class="sxs-lookup"><span data-stu-id="36790-118">Set up portal redirection</span></span>
<span data-ttu-id="36790-119">Per avviare il routing degli account Microsoft 365 Defender in security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="36790-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="36790-120">Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36790-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="36790-121">[Accedi a](https://security.microsoft.com/) Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="36790-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="36790-122">Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="36790-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="36790-123">Attiva l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="36790-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="36790-124">Fai **clic su** Abilita per applicare il reindirizzamento automatico a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="36790-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="36790-125">Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione è applicata non verranno espulsi dalla sessione e verranno instradati a Microsoft 365 Defender solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="36790-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="36790-126">È possibile tornare a usare il portale precedente?</span><span class="sxs-lookup"><span data-stu-id="36790-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="36790-127">Se qualcosa non funziona per te o se c'è qualcosa che non puoi completare tramite Microsoft 365 Defender, vogliamo sentirlo usando l'opzione di feedback del portale.</span><span class="sxs-lookup"><span data-stu-id="36790-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="36790-128">Se si sono verificati problemi con il reindirizzamento, contattaci.</span><span class="sxs-lookup"><span data-stu-id="36790-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="36790-129">Per ripristinare il portale precedente:</span><span class="sxs-lookup"><span data-stu-id="36790-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="36790-130">[Accedere a](https://security.microsoft.com/) Microsoft 365 Defender come amministratore globale o usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36790-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="36790-131">Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="36790-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="36790-132">Attivare o disattivare l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="36790-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="36790-133">Fai **clic su** & feedback quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="36790-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="36790-134">Questa impostazione può essere nuovamente abilitata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="36790-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="36790-135">Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, ovvero securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="36790-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="36790-136">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="36790-136">Related information</span></span>
- [<span data-ttu-id="36790-137">Microsoft 365 Panoramica di Defender</span><span class="sxs-lookup"><span data-stu-id="36790-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="36790-138">Microsoft Defender per Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36790-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="36790-139">Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="36790-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="36790-140">Infografica XDR e SIEM</span><span class="sxs-lookup"><span data-stu-id="36790-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="36790-141">Il nuovo defender</span><span class="sxs-lookup"><span data-stu-id="36790-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="36790-142">Informazioni su Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36790-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="36790-143">Portali di sicurezza Microsoft e centri di amministrazione</span><span class="sxs-lookup"><span data-stu-id="36790-143">Microsoft security portals and admin centers</span></span>](portals.md)
