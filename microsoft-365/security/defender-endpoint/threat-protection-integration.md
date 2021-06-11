---
title: Integrare Microsoft Defender for Endpoint con altre soluzioni Microsoft
description: Scopri come Microsoft Defender for Endpoint si integra con altre soluzioni Microsoft, tra cui Microsoft Defender for Identity e Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, accesso condizionale, office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb6d93017f138ce898d25f7d76e05cdcf3e90c5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878569"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="8e733-104">Microsoft Defender per Endpoint e altre soluzioni Microsoft</span><span class="sxs-lookup"><span data-stu-id="8e733-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8e733-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8e733-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e733-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8e733-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8e733-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e733-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8e733-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8e733-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8e733-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8e733-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="8e733-110">Integrazione con altre soluzioni Microsoft</span><span class="sxs-lookup"><span data-stu-id="8e733-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="8e733-111">Microsoft Defender for Endpoint si integra direttamente con varie soluzioni Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e733-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="8e733-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="8e733-112">Azure Defender</span></span>
<span data-ttu-id="8e733-113">Microsoft Defender for Endpoint offre una soluzione completa di protezione del server, tra cui funzionalità di rilevamento e risposta degli endpoint (EDR) nei Windows server.</span><span class="sxs-lookup"><span data-stu-id="8e733-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="8e733-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="8e733-114">Azure Sentinel</span></span>
<span data-ttu-id="8e733-115">Il connettore Microsoft Defender for Endpoint consente di trasmettere gli avvisi da Microsoft Defender per Endpoint in Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="8e733-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="8e733-116">In questo modo sarà possibile analizzare in modo più completo gli eventi di sicurezza all'interno dell'organizzazione e creare playbook per una risposta efficace e immediata.</span><span class="sxs-lookup"><span data-stu-id="8e733-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="8e733-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="8e733-117">Azure Information Protection</span></span>
<span data-ttu-id="8e733-118">L'integrazione di Azure Information Protection è stata recentemente deprecata poiché le funzionalità DLP degli endpoint incorporano una soluzione di individuazione e protezione migliorata per i dati sensibili archiviati nei dispositivi endpoint, che facilita una maggiore visibilità e integrazione tra le soluzioni.</span><span class="sxs-lookup"><span data-stu-id="8e733-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="8e733-119">Questo è stato annunciato nel [blog seguente.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)</span><span class="sxs-lookup"><span data-stu-id="8e733-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="8e733-120">È consigliabile che i clienti si spostino all'uso di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="8e733-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="8e733-121">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="8e733-121">Conditional Access</span></span>
<span data-ttu-id="8e733-122">Il punteggio di rischio del dispositivo dinamico di Microsoft Defender for Endpoint è integrato nella valutazione dell'accesso condizionale, assicurando che solo i dispositivi sicuri hanno accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="8e733-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="8e733-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8e733-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="8e733-124">Microsoft Cloud App Security sfrutta i segnali degli endpoint di Microsoft Defender for Endpoint per consentire la visibilità diretta sull'utilizzo delle applicazioni cloud, incluso l'uso di servizi cloud (IT shadow) non supportati da tutti i dispositivi monitorati da Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8e733-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="8e733-125">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="8e733-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="8e733-126">Le attività sospette sono processi in esecuzione in un contesto utente.</span><span class="sxs-lookup"><span data-stu-id="8e733-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="8e733-127">L'integrazione tra Microsoft Defender for Endpoint e Microsoft Defender for Identity offre la flessibilità di condurre un'indagine sulla sicurezza informatica tra le attività e le identità.</span><span class="sxs-lookup"><span data-stu-id="8e733-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="8e733-128">Microsoft Defender per Office</span><span class="sxs-lookup"><span data-stu-id="8e733-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="8e733-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) aiuta a proteggere l'organizzazione dal malware nei messaggi di posta elettronica o nei file tramite collegamenti sicuri, allegati sicuri, funzionalità avanzate di anti-phishing e spoofing intelligence.</span><span class="sxs-lookup"><span data-stu-id="8e733-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="8e733-130">L'integrazione tra Microsoft Defender per Office 365 e Microsoft Defender for Endpoint consente agli analisti della sicurezza di passare a monte per analizzare il punto di ingresso di un attacco.</span><span class="sxs-lookup"><span data-stu-id="8e733-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="8e733-131">Attraverso la condivisione delle informazioni sulle minacce, gli attacchi possono essere contenuti e bloccati.</span><span class="sxs-lookup"><span data-stu-id="8e733-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="8e733-132">Defender per Office 365 dati vengono visualizzati per gli eventi negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="8e733-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="8e733-133">Per gli avvisi, i dati Office 365 defender vengono visualizzati in base alla prima attività.</span><span class="sxs-lookup"><span data-stu-id="8e733-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="8e733-134">Successivamente, i dati non sono più disponibili in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e733-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="8e733-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8e733-135">Skype for Business</span></span>
<span data-ttu-id="8e733-136">L Skype for Business integra consente agli analisti di comunicare con un utente o un proprietario di dispositivo potenzialmente compromesso tramite un semplice pulsante del portale.</span><span class="sxs-lookup"><span data-stu-id="8e733-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="8e733-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e733-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="8e733-138">Con Microsoft 365 Defender, Microsoft Defender for Endpoint e varie soluzioni di sicurezza Microsoft formano una famiglia di prodotti di difesa aziendale unificata pre e post-violazione che si integra in modo nativo tra endpoint, identità, posta elettronica e applicazioni per rilevare, prevenire, analizzare e rispondere automaticamente ad attacchi sofisticati.</span><span class="sxs-lookup"><span data-stu-id="8e733-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint, and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="8e733-139">Altre informazioni su Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e733-139">Learn more about Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-365-defender)


## <a name="related-topics"></a><span data-ttu-id="8e733-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8e733-140">Related topics</span></span>
- [<span data-ttu-id="8e733-141">Configurare l'integrazione e altre funzionalità avanzate</span><span class="sxs-lookup"><span data-stu-id="8e733-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="8e733-142">Microsoft 365 Panoramica di Defender</span><span class="sxs-lookup"><span data-stu-id="8e733-142">Microsoft 365 Defender overview</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="8e733-143">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e733-143">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="8e733-144">Proteggere utenti, dati e dispositivi con accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="8e733-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
