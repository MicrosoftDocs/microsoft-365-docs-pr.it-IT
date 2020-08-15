---
title: Requisiti di sicurezza di rete aggiuntivi per Office 365 GCC High e DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Riepilogo: Office 365 GCC High e DoD presentano requisiti di sicurezza della rete aggiuntivi'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691243"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="80f23-103">Requisiti di sicurezza di rete aggiuntivi per Office 365 GCC High e DOD</span><span class="sxs-lookup"><span data-stu-id="80f23-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="80f23-104">*Questo articolo si applica a Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="80f23-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="80f23-105">Office 365 GCC High e DOD sono ambienti cloud sicuri per soddisfare le esigenze del governo degli Stati Uniti e dei suoi fornitori e appaltatori.</span><span class="sxs-lookup"><span data-stu-id="80f23-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="80f23-106">Tali ambienti cloud dispongono di restrizioni di rete aggiuntive su cui gli endpoint esterni ai servizi sono autorizzati ad accedere.</span><span class="sxs-lookup"><span data-stu-id="80f23-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="80f23-107">I clienti GCC High e DOD che pianificano l'utilizzo di identità federate o di coesistenza ibrida possono richiedere a Microsoft di consentire l'accesso in ingresso e/o in uscita alle distribuzioni locali esistenti.</span><span class="sxs-lookup"><span data-stu-id="80f23-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="80f23-108">Di seguito sono riportati alcuni esempi di attività:</span><span class="sxs-lookup"><span data-stu-id="80f23-108">Examples of these activities include:</span></span>

* <span data-ttu-id="80f23-109">Utilizzo di identità federate (con Active Directory Federation Services o STS supportate simili)</span><span class="sxs-lookup"><span data-stu-id="80f23-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="80f23-110">Coesistenza ibrida con una distribuzione di Exchange Server locale o Skype for business</span><span class="sxs-lookup"><span data-stu-id="80f23-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="80f23-111">Migrazione del contenuto utente esistente da un sistema locale</span><span class="sxs-lookup"><span data-stu-id="80f23-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="80f23-112">Per consentire al servizio di comunicare con gli endpoint locali, è **necessario** inviare un messaggio di posta elettronica a Office 365 Engineering per le modifiche apportate alla rete.</span><span class="sxs-lookup"><span data-stu-id="80f23-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="80f23-113">Tutte le richieste hanno un contratto di servizio di **tre settimane** e non possono essere velocizzate a causa dei controlli di sicurezza e conformità necessari e delle pipeline di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="80f23-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="80f23-114">Sono incluse le richieste di rete onboarding iniziali e tutte le modifiche apportate dopo la migrazione al servizio.</span><span class="sxs-lookup"><span data-stu-id="80f23-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="80f23-115">Verificare che i team di rete siano a conoscenza di questa sequenza temporale e che lo includano nei cicli di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="80f23-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="80f23-116">Inviare un messaggio di posta elettronica a [Office 365 Government Network whitelist](mailto:o365gwlt@microsoft.com) con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="80f23-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="80f23-117">**A**: [Office 365 Government Network whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="80f23-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="80f23-118">**From**: A tenant Administrator-l'invio di messaggi di posta elettronica **deve** corrispondere a un contatto di amministratore globale nel tenant</span><span class="sxs-lookup"><span data-stu-id="80f23-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="80f23-119">**Oggetto di posta elettronica**: Office 365 GCC High Network Request-contoso.onmicrosoft.US (Replace this with your tenant Name)</span><span class="sxs-lookup"><span data-stu-id="80f23-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="80f23-120">Il corpo del messaggio deve includere i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="80f23-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="80f23-121">Nome del tenant dei Microsoft Online Services (ad esempio, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="80f23-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="80f23-122">Una lista di distribuzione di posta elettronica che Microsoft comunica con le comunicazioni in uscita relative alle modifiche alla rete e/o al follow-up per le subnet non valide</span><span class="sxs-lookup"><span data-stu-id="80f23-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="80f23-123">Indicare se si prevede di utilizzare Microsoft teams Hybrid coesistenza con le distribuzioni locali</span><span class="sxs-lookup"><span data-stu-id="80f23-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="80f23-124">URL con accesso esterno a un sistema di identità federata (ad esempio sts.contoso.com) e un intervallo di indirizzi IP nella notazione CIDR (ad esempio, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="80f23-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="80f23-125">URL dell'elenco di revoche di certificati PKI locali e intervallo di indirizzi IP nella notazione CIDR</span><span class="sxs-lookup"><span data-stu-id="80f23-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="80f23-126">Intervallo di indirizzi IP e URL accessibili esternamente per la distribuzione locale di Exchange Server in notazione CIDR</span><span class="sxs-lookup"><span data-stu-id="80f23-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="80f23-127">Intervallo di indirizzi IP e URL accessibili esternamente per la distribuzione locale di Skype for business in notazione CIDR</span><span class="sxs-lookup"><span data-stu-id="80f23-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="80f23-128">Per motivi di sicurezza e conformità, tenere presente le restrizioni seguenti sulla richiesta:</span><span class="sxs-lookup"><span data-stu-id="80f23-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="80f23-129">Vi è un limite di quattro subnet per tenant</span><span class="sxs-lookup"><span data-stu-id="80f23-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="80f23-130">Le subnet devono trovarsi nella notazione CIDR (ad esempio, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="80f23-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="80f23-131">Gli intervalli di subnet non possono essere superiori a/24</span><span class="sxs-lookup"><span data-stu-id="80f23-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="80f23-132">**Non è possibile** soddisfare le richieste di autorizzazione per l'accesso ai servizi cloud commerciali (commercial Office 365, Google G-Suite, Amazon Web Services e così via).</span><span class="sxs-lookup"><span data-stu-id="80f23-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="80f23-133">Dopo che la richiesta è stata ricevuta e approvata da Microsoft, è presente un contratto di servizio per l'implementazione di tre settimane e non può essere velocizzata.</span><span class="sxs-lookup"><span data-stu-id="80f23-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="80f23-134">Si riceverà un riconoscimento iniziale quando è stata ricevuta la richiesta e una conferma finale dopo che è stata completata.</span><span class="sxs-lookup"><span data-stu-id="80f23-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
