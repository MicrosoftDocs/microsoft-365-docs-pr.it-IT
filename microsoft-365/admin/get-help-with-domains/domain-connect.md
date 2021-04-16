---
title: Utilizzo di Domain Connect
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Informazioni su come usare i registrar abilitati per Domain Connect e aggiungere il dominio a Microsoft 365.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860656"
---
# <a name="using-domain-connect"></a><span data-ttu-id="f11ef-103">Utilizzo di Domain Connect</span><span class="sxs-lookup"><span data-stu-id="f11ef-103">Using Domain Connect</span></span>

 <span data-ttu-id="f11ef-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="f11ef-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="f11ef-105">[I registrar ](https://www.domainconnect.org/) abilitati per Domain Connect consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti.</span><span class="sxs-lookup"><span data-stu-id="f11ef-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="f11ef-106">Nella procedura guidata, verrà semplicemente confermato che si è proprietari del dominio e quindi si configurano automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi di Microsoft 365, ad esempio Teams, con il dominio.</span><span class="sxs-lookup"><span data-stu-id="f11ef-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11ef-107">Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="f11ef-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="f11ef-108">Registrar di Domain Connect che si integrano con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f11ef-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="f11ef-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="f11ef-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="f11ef-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="f11ef-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="f11ef-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="f11ef-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="f11ef-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="f11ef-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="f11ef-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="f11ef-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="f11ef-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="f11ef-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="f11ef-115">SecureServer o WildWestDomains (rivenditori GoDaddy che usano l'hosting DNS SecureServer)</span><span class="sxs-lookup"><span data-stu-id="f11ef-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="f11ef-116">MadDog Web Hosting</span><span class="sxs-lookup"><span data-stu-id="f11ef-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
    - [<span data-ttu-id="f11ef-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="f11ef-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="f11ef-118">Cosa succede alla posta elettronica e al sito Web?</span><span class="sxs-lookup"><span data-stu-id="f11ef-118">What happens to my email and website?</span></span>

<span data-ttu-id="f11ef-119">Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutta la posta elettronica per il dominio inizierà a essere inviata a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f11ef-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="f11ef-120">Assicurarsi di aver aggiunto utenti e configurare le cassette postali in Microsoft 365 per tutti coloro che riceve la posta elettronica nel dominio.</span><span class="sxs-lookup"><span data-stu-id="f11ef-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="f11ef-121">Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova.</span><span class="sxs-lookup"><span data-stu-id="f11ef-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="f11ef-122">La procedura di configurazione di Domain Connect non influisce sul sito Web.</span><span class="sxs-lookup"><span data-stu-id="f11ef-122">The Domain Connect setup steps don't affect your website.</span></span>
