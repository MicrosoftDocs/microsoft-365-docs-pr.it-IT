---
title: Crittografia per i dati in transito
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Una breve spiegazione del modo in cui Microsoft crittografa i dati in transito nei suoi Data Center.
ms.openlocfilehash: 645294522185a631012c1654fbad96ba0a21b33e
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943305"
---
# <a name="encryption-for-data-in-transit"></a><span data-ttu-id="862e0-103">Crittografia per i dati in transito</span><span class="sxs-lookup"><span data-stu-id="862e0-103">Encryption for data in transit</span></span>

<span data-ttu-id="862e0-104">Oltre a proteggere i dati dei clienti a riposo, Microsoft utilizza le tecnologie di crittografia per proteggere i dati dei clienti in transito.</span><span class="sxs-lookup"><span data-stu-id="862e0-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect customer data in transit.</span></span> 

<span data-ttu-id="862e0-105">I dati sono in transito:</span><span class="sxs-lookup"><span data-stu-id="862e0-105">Data is in transit:</span></span>

- <span data-ttu-id="862e0-106">Quando un computer client comunica con un server Microsoft;</span><span class="sxs-lookup"><span data-stu-id="862e0-106">when a client machine communicates with a Microsoft server;</span></span>
- <span data-ttu-id="862e0-107">Quando un server Microsoft comunica con un altro server Microsoft; e</span><span class="sxs-lookup"><span data-stu-id="862e0-107">when a Microsoft server communicates with another Microsoft server; and</span></span>
- <span data-ttu-id="862e0-108">Quando un server Microsoft comunica con un server non Microsoft (ad esempio, Exchange Online recapitare la posta elettronica a un server di posta elettronica di terze parti).</span><span class="sxs-lookup"><span data-stu-id="862e0-108">when a Microsoft server communicates with a non-Microsoft server (e.g., Exchange Online delivering email to a third-party email server).</span></span>

<span data-ttu-id="862e0-109">Le comunicazioni tra i datacenter tra i server Microsoft si verificano su TLS o IPsec e tutti i server con accesso client negoziano una sessione sicura tramite TLS con i propri computer (ad esempio, Exchange Online utilizza TLS 1,2 con il valore di crittografia a 256 bit (FIPS 140-2 Level 2-convalidato).</span><span class="sxs-lookup"><span data-stu-id="862e0-109">Inter-data center communications between Microsoft servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="862e0-110">(Vedere [informazioni di riferimento tecnico sulla crittografia](technical-reference-details-about-encryption.md) per un elenco dei gruppi di crittografia TLS supportati da Office 365). Questo vale per i protocolli utilizzati da client quali Outlook, Skype for business, Microsoft teams e Outlook sul Web (ad esempio, HTTP, POP3 e così via).</span><span class="sxs-lookup"><span data-stu-id="862e0-110">(See [Technical reference details about encryption](technical-reference-details-about-encryption.md) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, Microsoft Teams, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="862e0-111">I certificati pubblici vengono emessi da Microsoft IT SSL tramite SSLAdmin, uno strumento interno di Microsoft per proteggere la riservatezza delle informazioni trasmesse.</span><span class="sxs-lookup"><span data-stu-id="862e0-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="862e0-112">Tutti i certificati emessi da Microsoft hanno una lunghezza minima di 2048 bit e la conformità di WebTrust richiede SSLAdmin per assicurarsi che i certificati vengano emessi solo per gli indirizzi IP pubblici di proprietà di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="862e0-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="862e0-113">Tutti gli indirizzi IP che non rispondono a questo criterio vengono instradati tramite un processo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="862e0-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="862e0-114">Tutti i dettagli sull'implementazione, ad esempio la versione di TLS utilizzata, l'abilitazione del segreto di inoltro (FS), l'ordine delle suite di crittografia e così via, sono disponibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="862e0-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="862e0-115">Un modo per visualizzare questi dettagli consiste nell'utilizzare un sito Web di terze parti, ad esempio [Qualys SSL Labs](https://www.ssllabs.com).</span><span class="sxs-lookup"><span data-stu-id="862e0-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="862e0-116">Di seguito sono riportati i collegamenti alle pagine di test automatizzate di Qualys che visualizzano le informazioni relative ai servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="862e0-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="862e0-117">Portale di Office 365</span><span class="sxs-lookup"><span data-stu-id="862e0-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="862e0-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="862e0-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="862e0-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="862e0-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="862e0-120">Skype for business (SIP)</span><span class="sxs-lookup"><span data-stu-id="862e0-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="862e0-121">Skype for business (Web)</span><span class="sxs-lookup"><span data-stu-id="862e0-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="862e0-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="862e0-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="862e0-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="862e0-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="862e0-124">Per Exchange Online Protection, gli URL variano in base ai nomi dei tenant; Tuttavia, tutti i clienti possono testare Microsoft 365 utilizzando **Microsoft-com.mail.Protection.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="862e0-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Microsoft 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
