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
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla resilienza dei dati in Microsoft Office 365.'
ms.openlocfilehash: 5b22584e677dd4815b991b4e95b5ad59feb2fbc2
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799546"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="3c0ce-103">Servizio di crittografia di Office 365</span><span class="sxs-lookup"><span data-stu-id="3c0ce-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="3c0ce-104">Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="3c0ce-105">La crittografia del servizio consente di eseguire due opzioni di gestione principali:</span><span class="sxs-lookup"><span data-stu-id="3c0ce-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="3c0ce-106">Microsoft gestisce tutte le chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="3c0ce-107">Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for business e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="3c0ce-108">Il cliente fornisce le chiavi radice utilizzate con la crittografia del servizio e il cliente gestisce queste chiavi utilizzando Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="3c0ce-109">Microsoft gestisce tutte le altre chiavi.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="3c0ce-110">Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="3c0ce-111">(In precedenza denominato crittografia avanzata con BYOK.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="3c0ce-112">Vedere [miglioramento della trasparenza e del controllo per i clienti di Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="3c0ce-113">La crittografia dei servizi offre molteplici vantaggi.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="3c0ce-114">Ad esempio, Customer Key:</span><span class="sxs-lookup"><span data-stu-id="3c0ce-114">For example, Customer Key:</span></span>

- <span data-ttu-id="3c0ce-115">Fornisce funzionalità di gestione e protezione dei diritti al di sopra della protezione dalla crittografia avanzata.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="3c0ce-116">Include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="3c0ce-117">Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="3c0ce-118">Consente di migliorare la capacità di Office 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="3c0ce-119">Customer Key</span><span class="sxs-lookup"><span data-stu-id="3c0ce-119">Customer Key</span></span>

<span data-ttu-id="3c0ce-120">Se si utilizza il codice "Customer Key", è possibile generare le proprie chiavi di crittografia utilizzando un modulo di servizio hardware (HSM) locale o un Vault Key di Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="3c0ce-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="3c0ce-121">Indipendentemente dal modo in cui viene generata la chiave, è possibile utilizzare AKV per controllare e gestire le chiavi di crittografia utilizzate da Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="3c0ce-122">Dopo aver memorizzato i tasti in AKV, è possibile utilizzarli come radice di uno dei portachiavi che crittografa i dati o i file delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="3c0ce-123">Un altro vantaggio della chiave del cliente è il controllo che si ha sulla capacità di elaborazione dei dati da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="3c0ce-124">Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera terminare il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e utilizzare la chiave del cliente come controllo tecnico.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="3c0ce-125">In questo modo, nessuno, incluso Microsoft, può accedere ai dati o elaborarli.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="3c0ce-126">La chiave del cliente è inoltre e complementare all'archivio protetto dei clienti che si utilizza per controllare l'accesso ai dati da parte del personale Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="3c0ce-127">Per informazioni su come configurare Customer Key per Office 365 per Exchange Online, Skype for business, SharePoint Online, inclusi i siti del team e OneDrive for business, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c0ce-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="3c0ce-128">Crittografia del servizio con la chiave del cliente in Office 365</span><span class="sxs-lookup"><span data-stu-id="3c0ce-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3c0ce-129">Configurare la chiave cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="3c0ce-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3c0ce-130">Gestire la chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="3c0ce-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="3c0ce-131">Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="3c0ce-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3c0ce-132">Comprendere il codice di disponibilità</span><span class="sxs-lookup"><span data-stu-id="3c0ce-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 