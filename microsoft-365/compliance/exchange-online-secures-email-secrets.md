---
title: Come viene garantita la protezione della posta elettronica in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Oltre al Centro protezione di Office 365 che fornisce informazioni sulla sicurezza, la privacy e la conformità per Office 365, è possibile che si desideri sapere in che modo Office 365 consente di proteggere i segreti forniti nei propri datacenter. Viene utilizzata una tecnologia denominata Distributed Key Manager (DKM).
ms.openlocfilehash: 8350785968c68b22c58be17ec68d94ff908c95d9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083651"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="3e20d-104">Modalità di protezione dei segreti di posta elettronica in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3e20d-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="3e20d-105">In questo articolo viene descritto come Microsoft garantisce la protezione della posta elettronica degli utenti nei datacenter.</span><span class="sxs-lookup"><span data-stu-id="3e20d-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="3e20d-106">Come vengono protette le informazioni riservate fornite dall'utente?</span><span class="sxs-lookup"><span data-stu-id="3e20d-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="3e20d-107">Oltre al Centro protezione di Office 365 che fornisce [informazioni sulla sicurezza, la privacy e la conformità per office 365](https://go.microsoft.com/fwlink/?linkid=874644), è possibile che si desideri sapere in che modo Office 365 consente di proteggere i segreti forniti nei propri datacenter.</span><span class="sxs-lookup"><span data-stu-id="3e20d-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="3e20d-108">Viene utilizzata una tecnologia denominata Distributed Key Manager (DKM).</span><span class="sxs-lookup"><span data-stu-id="3e20d-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="3e20d-109">[Gestione delle chiavi distribuite](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) è una funzionalità sul retro del client che utilizza un set di chiavi segrete per crittografare e decrittografare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="3e20d-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="3e20d-110">Solo i membri di un gruppo di sicurezza specifico in Servizi di dominio Active Directory possono accedere a tali chiavi per decrittografare i dati crittografati da DKM.</span><span class="sxs-lookup"><span data-stu-id="3e20d-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="3e20d-111">In Exchange Online, fanno parte di quel determinato gruppo di sicurezza solo determinati account di servizio nei quali sono in esecuzione i processi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e20d-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="3e20d-112">Nell'ambito della procedura operativa standard nel datacenter, le credenziali che fanno parte del gruppo di sicurezza non vengono fornite a nessuno; pertanto, nessuno ha accesso alle chiavi in grado di decrittografare le informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="3e20d-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="3e20d-p104">Per scopi legati al debug, alla risoluzione dei problemi o al controllo, è necessario che l'amministratore di un datacenter richieda un accesso con privilegi elevati per ottenere le credenziali temporanee relative al gruppo di sicurezza. Questo processo richiede più livelli di approvazione legale. Se viene consentito l'accesso, tutta l'attività viene registrata e controllata. Inoltre, l'accesso viene consentito solo per un determinato intervallo di tempo, al termine del quale scade automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3e20d-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="3e20d-117">Per una protezione maggiore, la tecnologia DKM include il rollover della chiave automatico e l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3e20d-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="3e20d-118">Ciò garantisce ulteriormente che l'utente possa continuare ad accedere ai contenuti meno recenti senza dover usare la stessa chiave per un periodo di tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="3e20d-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="3e20d-119">Per cosa si utilizza DKM in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="3e20d-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="3e20d-120">Microsoft utilizza [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) per crittografare i segreti nei datacenter di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3e20d-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="3e20d-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3e20d-121">For example:</span></span>
  
- <span data-ttu-id="3e20d-122">Credenziali dell'account di posta elettronica per gli account connessi.</span><span class="sxs-lookup"><span data-stu-id="3e20d-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="3e20d-123">Gli account connessi sono account di terze parti, ad esempio Hotmail, Gmail e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3e20d-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="3e20d-124">account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3e20d-124">mail accounts.</span></span>
    
- <span data-ttu-id="3e20d-125">Chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="3e20d-125">Customer key.</span></span> <span data-ttu-id="3e20d-126">Se si utilizza il [codice "Customer Key" in Office 365](controlling-your-data-using-customer-key.md), è possibile utilizzare [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) per salvaguardare i segreti.</span><span class="sxs-lookup"><span data-stu-id="3e20d-126">If you are using [Customer Key in Office 365](controlling-your-data-using-customer-key.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="3e20d-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3e20d-127">Related topics</span></span>

[<span data-ttu-id="3e20d-128">Crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="3e20d-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="3e20d-129">Dettagli tecnici di riferimento sulla crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="3e20d-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="3e20d-130">Garanzia del servizio nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="3e20d-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

