---
title: Gestione dispositivi mobili in Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sul modo in cui Contoso utilizza Microsoft Intune in Microsoft 365 per l'organizzazione per gestire i propri dispositivi e le app in esecuzione su di essi.
ms.openlocfilehash: d3f973827a9b05a415efe9225a2bdb3d83ccaf38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649646"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="fc253-103">Gestione dispositivi mobili in Contoso</span><span class="sxs-lookup"><span data-stu-id="fc253-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="fc253-104">Microsoft 365 per Enterprise include Intune e un set di servizi di Azure che supportano la gestione e la sicurezza di dispositivi mobili e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fc253-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="fc253-p101">Contoso dispone di molti dipendenti abilitati per dispositivi mobili. Alcuni dispongono di uffici nelle posizioni di Contoso e alcuni di essi non hanno uffici. Contoso aveva bisogno di un modo per abilitare la produttività dei dipendenti, ma mantenere i dispositivi, i dati di Contoso archiviati in tali dispositivi e il comportamento dell'applicazione sicuro.</span><span class="sxs-lookup"><span data-stu-id="fc253-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="fc253-108">Piano</span><span class="sxs-lookup"><span data-stu-id="fc253-108">Plan</span></span>

<span data-ttu-id="fc253-109">Contoso ha identificato i seguenti casi di utilizzo di Intune di gestione dei dispositivi mobili per Microsoft 365 per Enterprise:</span><span class="sxs-lookup"><span data-stu-id="fc253-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="fc253-110">Proteggere la posta elettronica e i dati di Exchange online in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="fc253-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="fc253-111">Implementare un programma Bring-Your-Own-Device (BYOD) per i dipendenti di contoso.</span><span class="sxs-lookup"><span data-stu-id="fc253-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="fc253-112">Emettere i telefoni di proprietà dell'organizzazione e le tavolette condivise con utilizzo limitato ai dipendenti di contoso.</span><span class="sxs-lookup"><span data-stu-id="fc253-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="fc253-113">Contoso non utilizza Intune per:</span><span class="sxs-lookup"><span data-stu-id="fc253-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="fc253-114">Consentire ai dipendenti di accedere in modo sicuro a Microsoft 365 da un chiosco pubblico non gestito.</span><span class="sxs-lookup"><span data-stu-id="fc253-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="fc253-115">Proteggere la posta elettronica e i dati locali in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili, perché non sono presenti server di Microsoft Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="fc253-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="fc253-116">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="fc253-116">Deploy</span></span>

<span data-ttu-id="fc253-117">Ecco come Contoso ha configurato l’infrastruttura di gestione dei dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="fc253-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="fc253-118">Impostare Intune come autorità di gestione dei dispositivi mobili (MDM) e utilizzare Intune su Azure per amministrare il contenuto e gestire i dispositivi</span><span class="sxs-lookup"><span data-stu-id="fc253-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="fc253-119">Creato gruppi di Azure Active Directory (Azure AD) per i dispositivi per la registrazione e le impostazioni di Intune e i criteri di accesso condizionale basati su dispositivo</span><span class="sxs-lookup"><span data-stu-id="fc253-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="fc253-120">Per ulteriori informazioni, vedere [criteri di accesso condizionale contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="fc253-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="fc253-121">Ha abilitato la piattaforma per dispositivi Apple per supportare i dipendenti con iPads, iMac e iPhone e iPhone di proprietà aziendale</span><span class="sxs-lookup"><span data-stu-id="fc253-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="fc253-122">Ha creato criteri di termini e condizioni specifichi per Contoso, visualizzati durante l’installazione del Portale aziendale per i dispositivi mobili di Contoso</span><span class="sxs-lookup"><span data-stu-id="fc253-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="fc253-123">Per i dispositivi non registrati, è stata implementata una serie di criteri di gestione delle applicazioni mobili (MAM) per richiedere l'autenticazione per l'accesso ai servizi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc253-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="fc253-124">Ha creato criteri di Intune che garantiscono:</span><span class="sxs-lookup"><span data-stu-id="fc253-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="fc253-125">App consentite.</span><span class="sxs-lookup"><span data-stu-id="fc253-125">Allowed apps.</span></span>
  - <span data-ttu-id="fc253-126">Crittografia del dispositivo per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="fc253-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="fc253-127">PIN o password A sei cifre.</span><span class="sxs-lookup"><span data-stu-id="fc253-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="fc253-128">Un periodo di inattività-timeout.</span><span class="sxs-lookup"><span data-stu-id="fc253-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="fc253-129">Protezione antivirus e antimalware e aggiornamenti delle firme con Windows Defender nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fc253-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="fc253-130">Aggiornamenti automatici nei dispositivi Windows 10 che includono gli aggiornamenti della sicurezza più recenti.</span><span class="sxs-lookup"><span data-stu-id="fc253-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="fc253-131">Push dei certificati nei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="fc253-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="fc253-p102">Una chiara separazione dei dati personali e aziendali. Gli utenti o amministratori possono cancellare in modo selettivo i dati aziendali dal dispositivo, senza modificare i dati personali, ad esempio immagini, account di posta elettronica personale e file personali.</span><span class="sxs-lookup"><span data-stu-id="fc253-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="fc253-134">Contoso ha registrato i PC distribuiti e gli smartphone e Tablet di proprietà dell'azienda aggiungendoli ai gruppi di dispositivi di Intune corretti.</span><span class="sxs-lookup"><span data-stu-id="fc253-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="fc253-135">Hanno inoltre stabilito un programma di BYOD per i dipendenti che iscrivono i propri dispositivi personali.</span><span class="sxs-lookup"><span data-stu-id="fc253-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="fc253-136">I dispositivi registrati ricevono criteri di Intune, che determinano i dispositivi gestiti e protetti e le relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fc253-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="fc253-137">I dispositivi non registrati dispongono di criteri di gestione delle applicazioni mobili (MAM) che specificano le applicazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="fc253-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="fc253-138">Di seguito è indicato l'architettura di distribuzione di gestione dei dispositivi mobili contoso.</span><span class="sxs-lookup"><span data-stu-id="fc253-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Infrastruttura di distribuzione di gestione dei dispositivi mobili contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="fc253-140">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="fc253-140">Next step</span></span>

<span data-ttu-id="fc253-141">[Scopri](contoso-info-protect.md) come Contoso utilizza le funzionalità di protezione delle informazioni di Microsoft 365 per l'organizzazione per classificare, identificare e proteggere le risorse digitali cruciali all'interno della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="fc253-141">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc253-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc253-142">See also</span></span>

[<span data-ttu-id="fc253-143">Gestione dei dispositivi per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc253-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="fc253-144">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="fc253-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fc253-145">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="fc253-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

