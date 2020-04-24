---
title: Utilizzo di Domain Connect
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Informazioni su come utilizzare i registrar abilitati per la connessione al dominio e aggiungere il proprio dominio a Microsoft 365.
ms.openlocfilehash: 6a86783ca880f6cb4ea833e4c2b659de4da5e5c1
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800012"
---
# <a name="using-domain-connect"></a><span data-ttu-id="60fea-103">Utilizzo di Domain Connect</span><span class="sxs-lookup"><span data-stu-id="60fea-103">Using Domain Connect</span></span>

 <span data-ttu-id="60fea-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="60fea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="60fea-105">I registrar abilitati alla [connessione di dominio](https://www.domainconnect.org/) consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti.</span><span class="sxs-lookup"><span data-stu-id="60fea-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="60fea-106">Nella procedura guidata, è sufficiente confermare che si è proprietari del dominio e quindi configurare automaticamente i record del dominio, in modo che la posta elettronica venga a Microsoft 365 e ad altri servizi Microsoft 365, come i team, che collaborino con il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="60fea-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60fea-107">Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="60fea-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="60fea-108">Domain Connect registrar che si integrano con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60fea-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="60fea-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="60fea-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="60fea-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="60fea-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="60fea-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="60fea-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="60fea-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="60fea-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="60fea-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="60fea-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="60fea-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="60fea-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="60fea-115">SecureServer o WildWestDomains (rivenditori GoDaddy con hosting DNS di SecureServer)</span><span class="sxs-lookup"><span data-stu-id="60fea-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="60fea-116">Domini di MadDog</span><span class="sxs-lookup"><span data-stu-id="60fea-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="60fea-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="60fea-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="60fea-118">Cosa succede alla posta elettronica e al sito Web?</span><span class="sxs-lookup"><span data-stu-id="60fea-118">What happens to my email and website?</span></span>

<span data-ttu-id="60fea-119">Dopo aver completato l'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere inviati a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60fea-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="60fea-120">Assicurarsi di aver aggiunto utenti e configurato le cassette postali in Office 365 per tutte le persone che ricevono posta nel dominio.</span><span class="sxs-lookup"><span data-stu-id="60fea-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="60fea-121">Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova.</span><span class="sxs-lookup"><span data-stu-id="60fea-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="60fea-122">I passaggi di installazione di Domain Connect non influiscono sul sito Web.</span><span class="sxs-lookup"><span data-stu-id="60fea-122">The Domain Connect setup steps don't affect your website.</span></span>
