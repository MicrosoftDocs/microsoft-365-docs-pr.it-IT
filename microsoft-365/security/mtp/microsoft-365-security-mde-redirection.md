---
title: Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365
description: Come reindirizzare account e sessioni da Defender for Endpoint al Centro sicurezza Microsoft 365.
keywords: Centro sicurezza Microsoft 365, Introduzione al Centro sicurezza Microsoft 365, reindirizzamento del centro sicurezza
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
ms.openlocfilehash: 626bc9950512438bfa43e6500adf72940ddcbfec
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727566"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="61225-104">Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61225-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="61225-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="61225-105">**Applies to:**</span></span>
- <span data-ttu-id="61225-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61225-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="61225-107">Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="61225-107">Defender for Endpoint</span></span>

<span data-ttu-id="61225-108">In linea con l'approccio tra domini di Microsoft alla protezione dalle minacce con SIEM e XDR (Extended Detection and Response), Microsoft Defender Advanced Threat Protection è stato ridenobrato come Microsoft Defender for Endpoint e l'abbiamo unificato in un unico portale integrato, il Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61225-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="61225-109">Questa guida spiega come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dall'ex portale di Microsoft Defender for Endpoint (securitycenter.windows.com o securitycenter.microsoft.com) al portale del Centro sicurezza Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="61225-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="61225-110">Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 supporta la concessione dell'accesso ai provider di servizi di sicurezza gestiti [(MSSP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) nello stesso modo in cui viene concesso l'accesso nel Centro sicurezza [Microsoft Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)</span><span class="sxs-lookup"><span data-stu-id="61225-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="61225-111">Cosa aspettarsi</span><span class="sxs-lookup"><span data-stu-id="61225-111">What to expect</span></span>
<span data-ttu-id="61225-112">Una volta abilitato il reindirizzamento automatico, gli account che accedono all'ex portale di Microsoft Defender for Endpoint a securitycenter.windows.com o securitycenter.microsoft.com, verranno automaticamente instradati al portale del centro sicurezza Microsoft 365 in security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="61225-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="61225-113">Altre informazioni sulle modifiche: Microsoft Defender for Endpoint nel Centro sicurezza [Microsoft 365.](microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="61225-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="61225-114">Ciò include il reindirizzamento per l'accesso diretto al portale precedente tramite browser, inclusi i collegamenti che puntano al portale di securitycenter.windows.com precedente, ad esempio i collegamenti nelle notifiche di posta elettronica e i collegamenti restituiti dalle chiamate API SIEM.</span><span class="sxs-lookup"><span data-stu-id="61225-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="61225-115">I collegamenti esterni dalle notifiche di posta elettronica o dalle API SIEM attualmente contengono collegamenti a entrambi i portali.</span><span class="sxs-lookup"><span data-stu-id="61225-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="61225-116">Una volta abilitato il reindirizzamento, entrambi i collegamenti puntano al Centro sicurezza Microsoft 365 fino a quando il collegamento precedente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="61225-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="61225-117">Ti invitiamo ad adottare il nuovo collegamento che punta al Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61225-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="61225-118">Per ulteriori informazioni sui collegamenti e il routing, vedere la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="61225-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="61225-119">Routing API SIEM</span><span class="sxs-lookup"><span data-stu-id="61225-119">SIEM API routing</span></span>

|<span data-ttu-id="61225-120">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="61225-120">**Property**</span></span>  |<span data-ttu-id="61225-121">**Destinazione quando il reindirizzamento è DISATTIVATO**</span><span class="sxs-lookup"><span data-stu-id="61225-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="61225-122">**Destinazione quando il reindirizzamento è ON**</span><span class="sxs-lookup"><span data-stu-id="61225-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="61225-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="61225-123">LinkToWDATP</span></span> | <span data-ttu-id="61225-124">Pagina avviso in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="61225-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="61225-125">Pagina avviso in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="61225-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="61225-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="61225-127">Pagina Evento imprevisto in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="61225-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="61225-128">Pagina Evento imprevisto in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="61225-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="61225-129">LinkToMTP</span></span> | <span data-ttu-id="61225-130">Pagina avviso in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="61225-131">Pagina avviso in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="61225-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="61225-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="61225-133">Pagina Evento imprevisto in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="61225-134">Pagina Evento imprevisto in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="61225-135">Notifiche di avviso tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="61225-135">Email alert notifications</span></span>

|<span data-ttu-id="61225-136">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="61225-136">**Property**</span></span>  |<span data-ttu-id="61225-137">**Destinazione quando il reindirizzamento è DISATTIVATO**</span><span class="sxs-lookup"><span data-stu-id="61225-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="61225-138">**Destinazione quando il reindirizzamento è ON**</span><span class="sxs-lookup"><span data-stu-id="61225-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="61225-139">Pagina avviso</span><span class="sxs-lookup"><span data-stu-id="61225-139">Alert page</span></span>  | <span data-ttu-id="61225-140">Pagina avviso in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="61225-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="61225-141">Pagina avviso in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="61225-142">Pagina Evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="61225-142">Incident page</span></span>  |<span data-ttu-id="61225-143">Pagina Evento imprevisto in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="61225-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="61225-144">Pagina Evento imprevisto in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="61225-145">Pagina avviso nel portale del centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="61225-145">Alert page in security center portal</span></span> | <span data-ttu-id="61225-146">Pagina avviso in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="61225-147">Pagina avviso in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="61225-148">Pagina Evento imprevisto nel portale del centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="61225-148">Incident page in security center portal</span></span> | <span data-ttu-id="61225-149">Pagina Evento imprevisto in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="61225-150">Pagina Evento imprevisto in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61225-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="61225-151">Quando ha effetto?</span><span class="sxs-lookup"><span data-stu-id="61225-151">When does this take effect?</span></span> 
<span data-ttu-id="61225-152">Una volta abilitato, questo aggiornamento potrebbe avere effetto quasi immediatamente per alcuni account.</span><span class="sxs-lookup"><span data-stu-id="61225-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="61225-153">Tuttavia, la propagazione del reindirizzamento a ogni account dell'organizzazione potrebbe richiedere più tempo.</span><span class="sxs-lookup"><span data-stu-id="61225-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="61225-154">Gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="61225-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="61225-155">Configurare il reindirizzamento del portale</span><span class="sxs-lookup"><span data-stu-id="61225-155">Set up portal redirection</span></span>
<span data-ttu-id="61225-156">Per avviare il routing degli account al Centro sicurezza Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="61225-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="61225-157">Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="61225-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="61225-158">[Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61225-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="61225-159">Passare a **Impostazioni**  >  **Endpoint Reindirizzamento**  >    >  **portale generale** o fare [clic qui](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="61225-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="61225-160">Attiva l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="61225-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="61225-161">Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale del centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61225-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="61225-162">L'abilitazione di questa impostazione non interromperà le sessioni utente attive.</span><span class="sxs-lookup"><span data-stu-id="61225-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="61225-163">Gli account che si trova in una sessione attiva mentre questa impostazione viene applicata verranno indirizzati al Centro sicurezza Microsoft 365 solo dopo aver terminato la sessione corrente e aver effettuato di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="61225-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="61225-164">Per abilitare o disabilitare questa impostazione, è necessario essere un amministratore globale o disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61225-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="61225-165">È possibile tornare a usare il portale precedente?</span><span class="sxs-lookup"><span data-stu-id="61225-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="61225-166">If something isn't working for you or if there're anything you're unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span><span class="sxs-lookup"><span data-stu-id="61225-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="61225-167">Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattarci usando il modulo Invia feedback.</span><span class="sxs-lookup"><span data-stu-id="61225-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="61225-168">Per ripristinare l'ex portale di Microsoft Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="61225-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="61225-169">[Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61225-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="61225-170">Passare a **Impostazioni**  >  **Endpoint**  >  **Reindirizzamento**  >  **portale generale** o aprire la pagina [qui](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="61225-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="61225-171">Attivare o disattivare l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="61225-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="61225-172">Fai **clic su** & feedback quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="61225-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="61225-173">Questa impostazione può essere nuovamente abilitata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="61225-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="61225-174">Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="61225-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="61225-175">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="61225-175">Related information</span></span>
- [<span data-ttu-id="61225-176">Panoramica del Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61225-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="61225-177">Microsoft Defender for Endpoint nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61225-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="61225-178">Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="61225-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="61225-179">Infografica XDR e SIEM</span><span class="sxs-lookup"><span data-stu-id="61225-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="61225-180">Il nuovo defender</span><span class="sxs-lookup"><span data-stu-id="61225-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="61225-181">Informazioni su Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61225-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="61225-182">Portali di sicurezza Microsoft e centri di amministrazione</span><span class="sxs-lookup"><span data-stu-id="61225-182">Microsoft security portals and admin centers</span></span>](portals.md)
