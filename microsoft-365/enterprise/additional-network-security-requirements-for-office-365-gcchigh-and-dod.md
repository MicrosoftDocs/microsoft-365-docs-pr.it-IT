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
description: 'Riepilogo: Office 365 GCC high e DoD hanno requisiti di sicurezza di rete aggiuntivi'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691243"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="afa9d-103">Altri requisiti di sicurezza della rete per Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="afa9d-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="afa9d-104">*Questo articolo si applica Office 365 GCC high, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="afa9d-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="afa9d-105">Office 365 GCC High e DOD sono ambienti cloud sicuri per soddisfare le esigenze del governo degli Stati Uniti e dei suoi fornitori e appaltatori.</span><span class="sxs-lookup"><span data-stu-id="afa9d-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="afa9d-106">Questi ambienti cloud hanno restrizioni di rete aggiuntive a cui gli endpoint esterni a cui i servizi possono accedere.</span><span class="sxs-lookup"><span data-stu-id="afa9d-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="afa9d-107">GCC I clienti high e DOD che pianificano di utilizzare le identità federate o la coesistenza ibrida potrebbero richiedere a Microsoft di consentire l'accesso in ingresso e/o in uscita alle distribuzioni locali esistenti.</span><span class="sxs-lookup"><span data-stu-id="afa9d-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="afa9d-108">Esempi di queste attività sono:</span><span class="sxs-lookup"><span data-stu-id="afa9d-108">Examples of these activities include:</span></span>

* <span data-ttu-id="afa9d-109">Utilizzo di identità federate (con Active Directory Federation Services o un servizio token di sicurezza supportato simile)</span><span class="sxs-lookup"><span data-stu-id="afa9d-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="afa9d-110">Coesistenza ibrida con una distribuzione locale Exchange Server o Skype for Business locale</span><span class="sxs-lookup"><span data-stu-id="afa9d-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="afa9d-111">Migrazione del contenuto utente esistente da un sistema locale</span><span class="sxs-lookup"><span data-stu-id="afa9d-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="afa9d-112">Per consentire al servizio di comunicare con gli  endpoint locali, è necessario inviare un messaggio di posta elettronica Office 365 progettazione per le modifiche di rete.</span><span class="sxs-lookup"><span data-stu-id="afa9d-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="afa9d-113">Tutte le richieste hanno **un** contratto di servizio di tre settimane e non possono essere accelerate a causa dei controlli di sicurezza e conformità necessari e delle pipeline di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="afa9d-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="afa9d-114">Sono incluse le richieste di rete di onboarding iniziali e le eventuali modifiche dopo la migrazione al servizio.</span><span class="sxs-lookup"><span data-stu-id="afa9d-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="afa9d-115">Assicurarsi che i team di rete siano a conoscenza di questa sequenza temporale e di includerla nei cicli di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="afa9d-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="afa9d-116">Inviare un messaggio di posta [elettronica Office 365 Government whitelist di rete](mailto:o365gwlt@microsoft.com) con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="afa9d-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="afa9d-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="afa9d-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="afa9d-118">**Da**: un amministratore tenant: il messaggio di posta **elettronica di invio deve** corrispondere a un contatto amministratore globale nel tenant</span><span class="sxs-lookup"><span data-stu-id="afa9d-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="afa9d-119">**Oggetto di** posta elettronica : Office 365 GCC high network request - contoso.onmicrosoft.us (sostituire questo con il nome del tenant)</span><span class="sxs-lookup"><span data-stu-id="afa9d-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="afa9d-120">Il corpo del messaggio deve includere i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="afa9d-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="afa9d-121">Nome Microsoft Online Services tenant (ad esempio, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="afa9d-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="afa9d-122">Una lista di distribuzione di posta elettronica con cui Microsoft comunicherà per le comunicazioni in corso relative alle modifiche di rete e/o al follow-up per subnet non valide</span><span class="sxs-lookup"><span data-stu-id="afa9d-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="afa9d-123">Indicare se si prevede di usare Microsoft Teams coesistenza ibrida con le distribuzioni locali</span><span class="sxs-lookup"><span data-stu-id="afa9d-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="afa9d-124">URL accessibile esternamente dal sistema di identità federata (ad esempio sts.contoso.com) e intervallo di indirizzi IP nella notazione CIDR (ad esempio 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="afa9d-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="afa9d-125">URL e intervallo di indirizzi IP dell'elenco di revoche di certificati PKI locali nella notazione CIDR</span><span class="sxs-lookup"><span data-stu-id="afa9d-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="afa9d-126">URL e intervallo di indirizzi IP accessibili esternamente Exchange Server distribuzione locale nella notazione CIDR</span><span class="sxs-lookup"><span data-stu-id="afa9d-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="afa9d-127">URL e intervallo di indirizzi IP accessibili esternamente Skype for Business distribuzione locale nella notazione CIDR</span><span class="sxs-lookup"><span data-stu-id="afa9d-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="afa9d-128">Per motivi di sicurezza e conformità, tenere presenti le restrizioni seguenti per la richiesta:</span><span class="sxs-lookup"><span data-stu-id="afa9d-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="afa9d-129">Esiste una limitazione di quattro subnet per tenant</span><span class="sxs-lookup"><span data-stu-id="afa9d-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="afa9d-130">Le subnet devono essere in notazione CIDR (ad esempio 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="afa9d-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="afa9d-131">Gli intervalli di subnet non possono essere superiori a /24</span><span class="sxs-lookup"><span data-stu-id="afa9d-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="afa9d-132">Non **è possibile** soddisfare le richieste per consentire l'accesso ai servizi cloud commerciali (Office 365, Google G-Suite, Amazon Web Services e così via)</span><span class="sxs-lookup"><span data-stu-id="afa9d-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="afa9d-133">Dopo che la richiesta è stata ricevuta e approvata da Microsoft, è previsto un contratto di servizio di tre settimane per l'implementazione e non può essere accelerato.</span><span class="sxs-lookup"><span data-stu-id="afa9d-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="afa9d-134">Riceverai un riconoscimento iniziale quando abbiamo ricevuto la richiesta e una conferma finale una volta completata.</span><span class="sxs-lookup"><span data-stu-id="afa9d-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
