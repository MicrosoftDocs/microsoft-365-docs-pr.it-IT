---
title: Gestione dispositivi mobili in Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere come Contoso usa Microsoft Intune in Microsoft 365 per le aziende per gestire i dispositivi e le app in esecuzione su di essi.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753994"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="3eea2-103">Gestione dispositivi mobili in Contoso</span><span class="sxs-lookup"><span data-stu-id="3eea2-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="3eea2-104">Microsoft 365 per le aziende include Intune e un set di servizi di Azure che supportano la gestione e la sicurezza di dispositivi mobili e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3eea2-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="3eea2-105">Contoso ha molti dipendenti abilitati per i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="3eea2-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="3eea2-106">Alcuni hanno uffici nelle sedi di Contoso e altri non hanno uffici.</span><span class="sxs-lookup"><span data-stu-id="3eea2-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="3eea2-107">Contoso aveva bisogno di un modo per abilitare la produttività dei dipendenti, ma mantenere sicuri i dispositivi, i dati di Contoso archiviati in tali dispositivi e il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3eea2-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="3eea2-108">Piano</span><span class="sxs-lookup"><span data-stu-id="3eea2-108">Plan</span></span>

<span data-ttu-id="3eea2-109">Contoso ha identificato i seguenti casi d'uso di Intune per la gestione dei dispositivi mobili Microsoft 365 per le aziende:</span><span class="sxs-lookup"><span data-stu-id="3eea2-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="3eea2-110">Proteggi Exchange Online e-mail e dati in modo che possano essere accessibili in modo sicuro dai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="3eea2-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="3eea2-111">Implementare un programma BYOD (Bring-Your-Own-Device) per i dipendenti di Contoso.</span><span class="sxs-lookup"><span data-stu-id="3eea2-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="3eea2-112">Emettere telefoni di proprietà dell'organizzazione e tablet condivisi con uso limitato ai dipendenti di Contoso.</span><span class="sxs-lookup"><span data-stu-id="3eea2-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="3eea2-113">Contoso non usa Intune per:</span><span class="sxs-lookup"><span data-stu-id="3eea2-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="3eea2-114">Consentire ai dipendenti di accedere in modo Microsoft 365 da un chiosco pubblico non gestito.</span><span class="sxs-lookup"><span data-stu-id="3eea2-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="3eea2-115">Proteggere la posta elettronica e i dati locali in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili, perché non sono presenti server Microsoft Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="3eea2-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="3eea2-116">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="3eea2-116">Deploy</span></span>

<span data-ttu-id="3eea2-117">Ecco come Contoso ha configurato l’infrastruttura di gestione dei dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="3eea2-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="3eea2-118">Impostare Intune come autorità di gestione dei dispositivi mobili (MDM) e usare Intune in Azure per amministrare il contenuto e gestire i dispositivi</span><span class="sxs-lookup"><span data-stu-id="3eea2-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="3eea2-119">Gruppi Azure Active Directory (Azure AD) creati per i dispositivi per la registrazione e le impostazioni di Intune e i criteri di accesso condizionale basati su dispositivi</span><span class="sxs-lookup"><span data-stu-id="3eea2-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="3eea2-120">Per ulteriori informazioni, vedere [Contoso Conditional Access policies.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)</span><span class="sxs-lookup"><span data-stu-id="3eea2-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="3eea2-121">Abilitata la piattaforma per dispositivi Apple per supportare i dipendenti con iPad, iMac e iPhone e iPhone di proprietà aziendale</span><span class="sxs-lookup"><span data-stu-id="3eea2-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="3eea2-122">Ha creato criteri di termini e condizioni specifichi per Contoso, visualizzati durante l’installazione del Portale aziendale per i dispositivi mobili di Contoso</span><span class="sxs-lookup"><span data-stu-id="3eea2-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="3eea2-123">Per i dispositivi non registrati, è stato implementato un set di criteri di gestione delle applicazioni mobili (MAM) per richiedere l'autenticazione per l'accesso ai Microsoft 365 mobili</span><span class="sxs-lookup"><span data-stu-id="3eea2-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="3eea2-124">Ha creato criteri di Intune che garantiscono:</span><span class="sxs-lookup"><span data-stu-id="3eea2-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="3eea2-125">App consentite.</span><span class="sxs-lookup"><span data-stu-id="3eea2-125">Allowed apps.</span></span>
  - <span data-ttu-id="3eea2-126">Crittografia del dispositivo per impedire l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="3eea2-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="3eea2-127">PIN o password a sei cifre.</span><span class="sxs-lookup"><span data-stu-id="3eea2-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="3eea2-128">Periodo di inattività-timeout.</span><span class="sxs-lookup"><span data-stu-id="3eea2-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="3eea2-129">Protezione antivirus e malware e aggiornamenti delle firme con Windows Defender nei Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3eea2-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="3eea2-130">Aggiornamenti automatici nei Windows 10 che includono gli aggiornamenti della sicurezza più recenti.</span><span class="sxs-lookup"><span data-stu-id="3eea2-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="3eea2-131">Push dei certificati nei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="3eea2-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="3eea2-p102">Una chiara separazione dei dati personali e aziendali. Gli utenti o amministratori possono cancellare in modo selettivo i dati aziendali dal dispositivo, senza modificare i dati personali, ad esempio immagini, account di posta elettronica personale e file personali.</span><span class="sxs-lookup"><span data-stu-id="3eea2-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="3eea2-134">Contoso ha registrato PC distribuiti e smartphone e tablet di proprietà dell'azienda aggiungendoli ai gruppi di dispositivi Intune appropriati.</span><span class="sxs-lookup"><span data-stu-id="3eea2-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="3eea2-135">Hanno inoltre creato un programma BYOD per i dipendenti per registrare i propri dispositivi personali.</span><span class="sxs-lookup"><span data-stu-id="3eea2-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="3eea2-136">I dispositivi registrati ricevono i criteri di Intune, che determinano dispositivi gestiti e protetti e le relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3eea2-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="3eea2-137">I dispositivi che non sono registrati dispongono di criteri maM (Mobile Application Management) che specificano le applicazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="3eea2-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="3eea2-138">Ecco l'architettura di distribuzione della gestione dei dispositivi mobili Contoso.</span><span class="sxs-lookup"><span data-stu-id="3eea2-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Infrastruttura di distribuzione di gestione dei dispositivi mobili Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="3eea2-140">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3eea2-140">Next step</span></span>

<span data-ttu-id="3eea2-141">Informazioni su come Contoso usa [le funzionalità di](contoso-info-protect.md) protezione delle Microsoft 365 per le aziende per classificare, identificare e proteggere le risorse digitali cruciali all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3eea2-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="3eea2-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eea2-142">See also</span></span>

[<span data-ttu-id="3eea2-143">Gestione dei dispositivi per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3eea2-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="3eea2-144">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3eea2-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3eea2-145">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="3eea2-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

