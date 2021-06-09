---
title: Come viene garantita la protezione della posta elettronica in Exchange Online
f1.keywords:
- NOCSH
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
description: Oltre al Centro protezione di Office 365 che fornisce informazioni su sicurezza, privacy e conformità per Microsoft 365, è consigliabile sapere in che modo Microsoft protegge i segreti archiviati nei relativi data center. Usiamo una tecnologia denominata Distributed Key Manager (DKM).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906962"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="2060d-104">Modalità di protezione dei segreti di posta elettronica in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2060d-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="2060d-105">In questo articolo viene descritto come Microsoft garantisce la protezione della posta elettronica degli utenti nei datacenter.</span><span class="sxs-lookup"><span data-stu-id="2060d-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="2060d-106">Come vengono protette le informazioni riservate fornite dall'utente?</span><span class="sxs-lookup"><span data-stu-id="2060d-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="2060d-107">Oltre al Centro protezione di Office 365 che fornisce informazioni su [sicurezza, privacy](./get-started-with-service-trust-portal.md)e conformità per Office 365, è consigliabile sapere in che modo Microsoft protegge i segreti forniti nei relativi data center.</span><span class="sxs-lookup"><span data-stu-id="2060d-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="2060d-108">Usiamo una tecnologia denominata Distributed Key Manager (DKM).</span><span class="sxs-lookup"><span data-stu-id="2060d-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="2060d-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) è una funzionalità sul lato client che utilizza un set di chiavi segrete per crittografare e decrittografare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="2060d-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="2060d-110">Solo i membri di un gruppo di sicurezza specifico in Servizi di dominio Active Directory possono accedere a tali chiavi per decrittografare i dati crittografati da DKM.</span><span class="sxs-lookup"><span data-stu-id="2060d-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="2060d-111">In Exchange Online, fanno parte di quel determinato gruppo di sicurezza solo determinati account di servizio nei quali sono in esecuzione i processi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2060d-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="2060d-112">Nell'ambito della procedura operativa standard nel datacenter, le credenziali che fanno parte del gruppo di sicurezza non vengono fornite a nessuno; pertanto, nessuno ha accesso alle chiavi in grado di decrittografare le informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="2060d-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="2060d-p104">Per scopi legati al debug, alla risoluzione dei problemi o al controllo, è necessario che l'amministratore di un datacenter richieda un accesso con privilegi elevati per ottenere le credenziali temporanee relative al gruppo di sicurezza. Questo processo richiede più livelli di approvazione legale. Se viene consentito l'accesso, tutta l'attività viene registrata e controllata. Inoltre, l'accesso viene consentito solo per un determinato intervallo di tempo, al termine del quale scade automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2060d-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="2060d-p105">Per una protezione maggiore, la tecnologia DKM include il rollover della chiave automatico e l'archiviazione. Ciò garantisce ulteriormente che l'utente possa continuare ad accedere ai contenuti meno recenti senza dover usare la stessa chiave per un periodo di tempo indeterminato.
</span><span class="sxs-lookup"><span data-stu-id="2060d-p105">For extra protection, DKM technology includes automated key rollover and archiving. This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="2060d-119">Per cosa si utilizza DKM in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="2060d-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="2060d-120">Microsoft usa [Distributed Key Manager per](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) crittografare i segreti in Exchange Online datacenter.</span><span class="sxs-lookup"><span data-stu-id="2060d-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="2060d-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2060d-121">For example:</span></span>
  
- <span data-ttu-id="2060d-p107">Le credenziali dell'account di posta elettronica per gli account connessi. Gli account connessi sono account di terzi come quelli di Hotmail, Gmail e Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="2060d-p107">Email account credentials for connected accounts. Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo! mail accounts.</span></span>

- <span data-ttu-id="2060d-125">Codice cliente.</span><span class="sxs-lookup"><span data-stu-id="2060d-125">Customer key.</span></span> <span data-ttu-id="2060d-126">Se si usa la [crittografia del servizio con la chiave del](customer-key-overview.md)cliente, si userà Azure Key [Vault](/azure/key-vault/key-vault-whatis) per proteggere i segreti.</span><span class="sxs-lookup"><span data-stu-id="2060d-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2060d-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2060d-127">Related topics</span></span>

[<span data-ttu-id="2060d-128">Crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="2060d-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="2060d-129">Dettagli tecnici di riferimento sulla crittografia</span><span class="sxs-lookup"><span data-stu-id="2060d-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="2060d-130">Garanzia del servizio nel Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="2060d-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
