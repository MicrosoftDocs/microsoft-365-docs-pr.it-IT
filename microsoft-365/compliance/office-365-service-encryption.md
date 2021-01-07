---
title: Crittografia del servizio
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
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777051"
---
# <a name="service-encryption"></a><span data-ttu-id="038d1-103">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="038d1-103">Service Encryption</span></span>

<span data-ttu-id="038d1-104">Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="038d1-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="038d1-105">La crittografia del servizio consente di eseguire due opzioni di gestione principali:</span><span class="sxs-lookup"><span data-stu-id="038d1-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="038d1-106">Chiavi gestite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="038d1-106">Microsoft-managed keys</span></span>
<span data-ttu-id="038d1-107">Microsoft gestisce tutte le chiavi di crittografia, incluse le chiavi radice per la crittografia del servizio.</span><span class="sxs-lookup"><span data-stu-id="038d1-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="038d1-108">Questa opzione è attualmente abilitata per impostazione predefinita per Exchange Online, SharePoint Online, OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="038d1-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="038d1-109">Le chiavi gestite da Microsoft forniscono la crittografia del servizio predefinita, a meno che non si decida di onboard usando la chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="038d1-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="038d1-110">Se, in un secondo momento, si decide di non utilizzare la chiave del cliente senza seguire il percorso di eliminazione dei dati, i dati rimarranno crittografati utilizzando le chiavi gestite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="038d1-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="038d1-111">I dati vengono sempre crittografati a questo livello predefinito almeno.</span><span class="sxs-lookup"><span data-stu-id="038d1-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="038d1-112">Customer Key</span><span class="sxs-lookup"><span data-stu-id="038d1-112">Customer Key</span></span>
<span data-ttu-id="038d1-113">È possibile specificare le chiavi radice utilizzate con la crittografia del servizio e gestire queste chiavi utilizzando Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="038d1-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="038d1-114">Microsoft gestisce tutte le altre chiavi.</span><span class="sxs-lookup"><span data-stu-id="038d1-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="038d1-115">Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="038d1-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="038d1-116">(In precedenza denominato crittografia avanzata con BYOK.</span><span class="sxs-lookup"><span data-stu-id="038d1-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="038d1-117">Vedere [miglioramento della trasparenza e del controllo per i clienti di Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale.</span><span class="sxs-lookup"><span data-stu-id="038d1-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="038d1-118">La crittografia dei servizi offre molteplici vantaggi:</span><span class="sxs-lookup"><span data-stu-id="038d1-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="038d1-119">Fornisce un ulteriore livello di protezione sulla parte superiore di BitLocker.</span><span class="sxs-lookup"><span data-stu-id="038d1-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="038d1-120">Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dell'applicazione archiviati o elaborati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="038d1-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="038d1-121">Include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.</span><span class="sxs-lookup"><span data-stu-id="038d1-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="038d1-122">Consente di migliorare la capacità di Microsoft 365 di soddisfare le esigenze dei clienti che hanno requisiti di conformità specifici per quanto riguarda la crittografia.</span><span class="sxs-lookup"><span data-stu-id="038d1-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="038d1-123">Se si utilizza il codice "Customer Key", è possibile generare le proprie chiavi di crittografia utilizzando un modulo di servizio hardware (HSM) locale o un Vault Key di Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="038d1-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="038d1-124">Indipendentemente dal modo in cui viene generata la chiave, è possibile utilizzare AKV per controllare e gestire le chiavi di crittografia utilizzate da Office 365.</span><span class="sxs-lookup"><span data-stu-id="038d1-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="038d1-125">Dopo aver memorizzato i tasti in AKV, è possibile utilizzarli come radice di uno dei portachiavi che crittografa i dati o i file delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="038d1-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="038d1-126">Un altro vantaggio della chiave del cliente è il controllo che si ha sulla capacità di elaborazione dei dati da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="038d1-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="038d1-127">Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera terminare il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e utilizzare la chiave del cliente come controllo tecnico.</span><span class="sxs-lookup"><span data-stu-id="038d1-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="038d1-128">La rimozione dei dati garantisce che nessuno, incluso Microsoft, possa accedere ai dati o elaborarli.</span><span class="sxs-lookup"><span data-stu-id="038d1-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="038d1-129">La chiave del cliente è inoltre e complementare all'archivio protetto dei clienti che si utilizza per controllare l'accesso ai dati da parte del personale Microsoft.</span><span class="sxs-lookup"><span data-stu-id="038d1-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="038d1-130">Per informazioni su come configurare la chiave del cliente per Microsoft 365 per Exchange Online, Skype for business, SharePoint Online, inclusi i siti del team e OneDrive for business, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="038d1-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="038d1-131">Crittografia del servizio con Customer Key</span><span class="sxs-lookup"><span data-stu-id="038d1-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="038d1-132">Configurare la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="038d1-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="038d1-133">Gestione della chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="038d1-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="038d1-134">Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="038d1-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="038d1-135">Comprendere il codice di disponibilità</span><span class="sxs-lookup"><span data-stu-id="038d1-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

