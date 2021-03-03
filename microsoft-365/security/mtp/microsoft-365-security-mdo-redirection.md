---
title: Reindirizzamento degli account da Microsoft Defender per Office 365 al nuovo Centro sicurezza Microsoft 365
description: Come reindirizzare da Defender per Office 365 al Centro sicurezza Microsoft 365.
keywords: Centro sicurezza Microsoft 365, Guida introduttiva al Centro sicurezza Microsoft 365, reindirizzamento del Centro sicurezza
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416795"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="f42c0-104">Reindirizzamento degli account da Microsoft Defender per Office 365 al Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f42c0-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f42c0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f42c0-105">**Applies to:**</span></span>

- <span data-ttu-id="f42c0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f42c0-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f42c0-107">Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f42c0-107">Defender for Office 365</span></span>

<span data-ttu-id="f42c0-108">Questo articolo spiega come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dal precedente Centro sicurezza e conformità (protection.office.com o securitycenter.microsoft.com) al Centro sicurezza Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f42c0-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="f42c0-109">La funzionalità di reindirizzamento del portale è disponibile solo per i clienti di Office 365 E5 e Microsoft Defender per Office P2</span><span class="sxs-lookup"><span data-stu-id="f42c0-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="f42c0-110">Cosa aspettarsi</span><span class="sxs-lookup"><span data-stu-id="f42c0-110">What to expect</span></span>
<span data-ttu-id="f42c0-111">Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità relative alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati al Centro sicurezza Microsoft 365 ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="f42c0-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="f42c0-112">Ulteriori informazioni sulle modifiche: Microsoft Defender per Office 365 nel Centro sicurezza [Microsoft 365.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="f42c0-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="f42c0-113">Con il reindirizzamento automatico attivato, gli utenti verranno instradati al Centro sicurezza Microsoft 365 quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f42c0-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="f42c0-114">Queste includono funzionalità nella sezione Gestione delle minacce, nel dashboard e nei report di Gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="f42c0-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="f42c0-115">Gli elementi nel Centro sicurezza e conformità di Office 365 non correlati alla sicurezza non vengono reindirizzati al Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f42c0-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="f42c0-116">Gli elementi correlati alla conformità sono disponibili nel Centro conformità Microsoft 365 e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f42c0-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="f42c0-117">Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f42c0-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="f42c0-118">Gli avvisi di sicurezza di Office 365 vengono visualizzati sia nel Centro sicurezza Microsoft 365 che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f42c0-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="f42c0-119">Configurare il reindirizzamento del portale</span><span class="sxs-lookup"><span data-stu-id="f42c0-119">Set up portal redirection</span></span>
<span data-ttu-id="f42c0-120">Per avviare il routing degli account al Centro sicurezza Microsoft 365 all'indirizzo security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="f42c0-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="f42c0-121">Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f42c0-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="f42c0-122">[Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f42c0-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="f42c0-123">Passare a **Impostazioni posta** elettronica  >  **& reindirizzamento del** portale di  >  **collaborazione.**</span><span class="sxs-lookup"><span data-stu-id="f42c0-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="f42c0-124">Attiva l'impostazione reindirizzamento **automatico.**</span><span class="sxs-lookup"><span data-stu-id="f42c0-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="f42c0-125">Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f42c0-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="f42c0-126">Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f42c0-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="f42c0-127">È possibile tornare all'uso del portale precedente?</span><span class="sxs-lookup"><span data-stu-id="f42c0-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="f42c0-128">Se qualcosa non funziona per l'utente o se c'è qualcosa che non è possibile completare tramite il portale del Centro sicurezza Microsoft 365, vogliamo ricevere informazioni usando l'opzione di feedback del portale.</span><span class="sxs-lookup"><span data-stu-id="f42c0-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="f42c0-129">Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattare il tuo amico pm direttamente tramite l'anteprima privata o contattarci tramite il modulo invia feedback.</span><span class="sxs-lookup"><span data-stu-id="f42c0-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="f42c0-130">Per ripristinare il portale precedente:</span><span class="sxs-lookup"><span data-stu-id="f42c0-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="f42c0-131">[Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f42c0-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="f42c0-132">Passare a **Impostazioni**  >  **Endpoint**  >  **reindirizzamento**  >  **portale generale.**</span><span class="sxs-lookup"><span data-stu-id="f42c0-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="f42c0-133">Attivare o disattivare l'impostazione reindirizzamento **automatico.**</span><span class="sxs-lookup"><span data-stu-id="f42c0-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="f42c0-134">Fai **clic su** & condividi feedback quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="f42c0-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="f42c0-135">Questa impostazione può essere ri abilitata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f42c0-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="f42c0-136">Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f42c0-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="f42c0-137">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="f42c0-137">Related information</span></span>
- [<span data-ttu-id="f42c0-138">Panoramica del Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f42c0-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="f42c0-139">Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f42c0-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="f42c0-140">Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f42c0-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="f42c0-141">Infografica XDR e SIEM</span><span class="sxs-lookup"><span data-stu-id="f42c0-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="f42c0-142">Il nuovo defender</span><span class="sxs-lookup"><span data-stu-id="f42c0-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="f42c0-143">Informazioni su Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f42c0-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="f42c0-144">Portali di sicurezza Microsoft e centri di amministrazione</span><span class="sxs-lookup"><span data-stu-id="f42c0-144">Microsoft security portals and admin centers</span></span>](portals.md)