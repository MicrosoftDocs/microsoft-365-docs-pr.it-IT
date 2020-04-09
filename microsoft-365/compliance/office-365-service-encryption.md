---
title: Servizio di crittografia di Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla crittografia dei dati a livello di servizio in Microsoft Office 365.'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193462"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="74209-103">Servizio di crittografia di Office 365</span><span class="sxs-lookup"><span data-stu-id="74209-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="74209-104">Oltre a utilizzare BitLocker per la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i team utilizzano anche la crittografia del servizio per crittografare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="74209-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="74209-105">La crittografia del servizio consente di eseguire due opzioni di gestione principali:</span><span class="sxs-lookup"><span data-stu-id="74209-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="74209-106">Microsoft gestisce tutte le chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="74209-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="74209-107">Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for business, Skype for business e chat teams.</span><span class="sxs-lookup"><span data-stu-id="74209-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="74209-108">I dati vengono crittografati per impostazione predefinita con le chiavi gestite Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74209-108">Your data is encrypted by default with Microsoft managed keys.</span></span>

- <span data-ttu-id="74209-109">L'organizzazione fornisce le chiavi radice.</span><span class="sxs-lookup"><span data-stu-id="74209-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="74209-110">È possibile gestire queste chiavi utilizzando il Vault Key di Azure.</span><span class="sxs-lookup"><span data-stu-id="74209-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="74209-111">Questa opzione è denominata Customer Key.</span><span class="sxs-lookup"><span data-stu-id="74209-111">This option is called Customer Key.</span></span> <span data-ttu-id="74209-112">La chiave del cliente è attualmente disponibile per i file di Exchange Online, SharePoint Online, OneDrive for business, Skype for business e teams.</span><span class="sxs-lookup"><span data-stu-id="74209-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="74209-113">Se si utilizza il codice "Customer Key", queste chiavi sostituiscono le chiavi gestite Microsoft per crittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="74209-113">If you use Customer Key, these keys replace Microsoft managed keys to encrypt your data.</span></span>

<span data-ttu-id="74209-114">Indipendentemente dall'opzione scelta, la crittografia dei servizi fornisce molteplici vantaggi:</span><span class="sxs-lookup"><span data-stu-id="74209-114">Regardless of the option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="74209-115">Impone l'autenticazione utente per recuperare e decrittografare i dati richiesti da un utente autorizzato.</span><span class="sxs-lookup"><span data-stu-id="74209-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="74209-116">Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="74209-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="74209-117">Consente di migliorare la capacità di Office 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.</span><span class="sxs-lookup"><span data-stu-id="74209-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="74209-118">Per informazioni su come configurare la chiave del cliente per Office 365 per Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i file teams, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="74209-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="74209-119">Crittografia del servizio con la chiave del cliente in Office 365</span><span class="sxs-lookup"><span data-stu-id="74209-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="74209-120">Configurare la chiave cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="74209-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="74209-121">Gestire la chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="74209-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="74209-122">Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="74209-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="74209-123">Comprendere il codice di disponibilità</span><span class="sxs-lookup"><span data-stu-id="74209-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
