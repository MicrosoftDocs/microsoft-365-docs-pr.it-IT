---
title: Gestione dispositivi mobili in Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso usa Microsoft Intune in Microsoft 365 Enterprise per gestire i dispositivi e le app eseguite nei dispositivi.
ms.openlocfilehash: c486c9ef338ab1bd8959266183da6b79d62b3311
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673182"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="b9e8c-103">Gestione dispositivi mobili in Contoso</span><span class="sxs-lookup"><span data-stu-id="b9e8c-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="b9e8c-104">Microsoft 365 Enterprise include Intune e un set di servizi di Azure per supportare la gestione e la sicurezza di applicazioni e dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="b9e8c-p101">Contoso ha molti dipendenti autorizzati alla mobilità, di cui alcuni hanno uffici nelle sedi di Contoso e altri non hanno un ufficio. Contoso era alla ricerca di un modo per garantire la produttività dei dipendenti mantenendo sicuri i dispositivi, i dati di Contoso archiviati in quei dispositivi e il comportamento dell’applicazione.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="b9e8c-107">Piano</span><span class="sxs-lookup"><span data-stu-id="b9e8c-107">Plan</span></span>

<span data-ttu-id="b9e8c-108">Nelle prime fasi dell’analisi della gestione dei dispositivi mobili per Microsoft 365 Enterprise, Contoso ha identificato i seguenti casi di utilizzo di Intune:</span><span class="sxs-lookup"><span data-stu-id="b9e8c-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="b9e8c-109">Proteggere i dati e la posta elettronica di Exchange Online in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="b9e8c-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="b9e8c-110">Implementare un programma Bring Your Own Device (BYOD) per i dipendenti di Contoso</span><span class="sxs-lookup"><span data-stu-id="b9e8c-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="b9e8c-111">Distribuire ai dipendenti di Contoso telefoni di proprietà dell’organizzazione e tablet condivisi dall’uso limitato</span><span class="sxs-lookup"><span data-stu-id="b9e8c-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="b9e8c-112">Contoso non usa Intune per:</span><span class="sxs-lookup"><span data-stu-id="b9e8c-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="b9e8c-113">Consentire ai dipendenti di accedere a Office 365 in modo sicuro da un chiosco pubblico non gestito</span><span class="sxs-lookup"><span data-stu-id="b9e8c-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="b9e8c-114">Proteggere i dati e la posta elettronica locale così da poter accedervi in modo sicuro dai dispositivi mobili, perché non sono più presenti server locali di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="b9e8c-115">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="b9e8c-115">Deploy</span></span>

<span data-ttu-id="b9e8c-116">Ecco come Contoso ha configurato l’infrastruttura di gestione dei dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="b9e8c-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="b9e8c-117">Ha impostato Intune come autorità di gestione dei dispositivi mobili (MDM) e usa Intune in Azure per amministrare il contenuto e gestire i dispositivi</span><span class="sxs-lookup"><span data-stu-id="b9e8c-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="b9e8c-118">Ha creato gruppi di Azure AD per i dispositivi per la registrazione e le impostazioni di Intune e i criteri di accesso condizionale basati sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="b9e8c-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="b9e8c-119">Per altre informazioni, vedere [Criteri di accesso condizionale di Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="b9e8c-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="b9e8c-120">Ha abilitato la piattaforma per dispositivi Apple per supportare i dipendenti con iPad, iMac, iPhone e telefoni aziendali basati su iPhone</span><span class="sxs-lookup"><span data-stu-id="b9e8c-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="b9e8c-121">Ha creato criteri di termini e condizioni specifichi per Contoso, visualizzati durante l’installazione del Portale aziendale per i dispositivi mobili di Contoso</span><span class="sxs-lookup"><span data-stu-id="b9e8c-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="b9e8c-122">Per i dispositivi non registrati, un set di criteri di gestione di applicazioni per dispositivi mobili (MAM) per richiedere l'autenticazione per accedere ai servizi di Office 365</span><span class="sxs-lookup"><span data-stu-id="b9e8c-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="b9e8c-123">Ha creato criteri di Intune che garantiscono:</span><span class="sxs-lookup"><span data-stu-id="b9e8c-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="b9e8c-124">App consentite</span><span class="sxs-lookup"><span data-stu-id="b9e8c-124">Allowed apps</span></span>
  - <span data-ttu-id="b9e8c-125">Crittografia dei dispositivi per evitare l'accesso non autorizzato</span><span class="sxs-lookup"><span data-stu-id="b9e8c-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="b9e8c-126">Un PIN a sei cifre o una password</span><span class="sxs-lookup"><span data-stu-id="b9e8c-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="b9e8c-127">Un periodo di timout di inattività</span><span class="sxs-lookup"><span data-stu-id="b9e8c-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="b9e8c-128">Protezione antivirus e malware e gli aggiornamenti delle firme con Windows Defender nei dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9e8c-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="b9e8c-129">Aggiornamenti automatici nei dispositivi Windows 10 che includono gli aggiornamenti di sicurezza più recenti</span><span class="sxs-lookup"><span data-stu-id="b9e8c-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="b9e8c-130">Trasferimento dei certificati ai dispositivi gestiti</span><span class="sxs-lookup"><span data-stu-id="b9e8c-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="b9e8c-p102">Una chiara separazione dei dati personali e aziendali. Gli utenti o amministratori possono cancellare in modo selettivo i dati aziendali dal dispositivo, senza modificare i dati personali, ad esempio immagini, account di posta elettronica personale e file personali.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="b9e8c-p103">Dopo la distribuzione, Contoso ha registrato PC e smartphone e tablet di proprietà aziendale, aggiungendoli ai gruppi di dispositivi Intune appropriati, e ha distribuito un programma BYOD che consente ai dipendenti di registrare i loro dispositivi personali. I dispositivi registrati hanno ricevuto i criteri Intune, diventando di conseguenza dispositivi e relative applicazioni gestiti e protetti. I dispositivi non registrati dispongono di criteri di gestione delle applicazioni mobili (MAM) che specificano le applicazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="b9e8c-136">Ecco l'architettura di distribuzione di Gestione dispositivi mobili di Contoso.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Infrastruttura di distribuzione di Gestione dispositivi mobili di Contoso](./media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="b9e8c-138">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b9e8c-138">Next step</span></span>

<span data-ttu-id="b9e8c-139">[Informazioni su](contoso-info-protect.md) come Contoso utilizza la funzionalità di protezione delle informazioni di Microsoft 365 Enterprise per classificare, identificare e proteggere le risorse digitali fondamentali per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9e8c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9e8c-140">See also</span></span>

[<span data-ttu-id="b9e8c-141">Gestione di dispositivi mobili per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e8c-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="b9e8c-142">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="b9e8c-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b9e8c-143">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="b9e8c-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

