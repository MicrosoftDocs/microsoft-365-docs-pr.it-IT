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
ms.openlocfilehash: e69d35f08070e1fe092ca8a9b4aef6d179711121
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717347"
---
# <a name="service-encryption"></a><span data-ttu-id="c37b6-103">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="c37b6-103">Service Encryption</span></span>

<span data-ttu-id="c37b6-104">Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c37b6-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="c37b6-105">La crittografia del servizio consente di eseguire due opzioni di gestione principali:</span><span class="sxs-lookup"><span data-stu-id="c37b6-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="c37b6-106">Chiavi gestite Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c37b6-106">Microsoft managed keys:</span></span> 
<span data-ttu-id="c37b6-107">Microsoft gestisce tutte le chiavi di crittografia, incluse le chiavi radice per la crittografia del servizio.</span><span class="sxs-lookup"><span data-stu-id="c37b6-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="c37b6-108">Questa opzione è attualmente disponibile in SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="c37b6-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="c37b6-109">Questa opzione è attualmente in fase di rollforward per Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c37b6-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="c37b6-110">Le chiavi gestite Microsoft forniscono la crittografia del servizio predefinita, a meno che non si decida di onboard usando la chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="c37b6-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="c37b6-111">Se, in un secondo momento, si decide di non utilizzare la chiave del cliente senza seguire il percorso di eliminazione dei dati, i dati rimarranno crittografati utilizzando le chiavi gestite Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c37b6-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="c37b6-112">I dati vengono sempre crittografati a questo livello predefinito almeno.</span><span class="sxs-lookup"><span data-stu-id="c37b6-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="c37b6-113">Chiave cliente:</span><span class="sxs-lookup"><span data-stu-id="c37b6-113">Customer Key:</span></span> 
<span data-ttu-id="c37b6-114">È possibile specificare le chiavi radice utilizzate con la crittografia del servizio e gestire queste chiavi utilizzando Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c37b6-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="c37b6-115">Microsoft gestisce tutte le altre chiavi.</span><span class="sxs-lookup"><span data-stu-id="c37b6-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="c37b6-116">Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="c37b6-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="c37b6-117">(In precedenza denominato crittografia avanzata con BYOK.</span><span class="sxs-lookup"><span data-stu-id="c37b6-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="c37b6-118">Vedere [miglioramento della trasparenza e del controllo per i clienti di Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale.</span><span class="sxs-lookup"><span data-stu-id="c37b6-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="c37b6-119">La crittografia dei servizi offre molteplici vantaggi.</span><span class="sxs-lookup"><span data-stu-id="c37b6-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="c37b6-120">Ad esempio, Customer Key:</span><span class="sxs-lookup"><span data-stu-id="c37b6-120">For example, Customer Key:</span></span>

- <span data-ttu-id="c37b6-121">Fornisce funzionalità di gestione e protezione dei diritti al di sopra della protezione dalla crittografia avanzata.</span><span class="sxs-lookup"><span data-stu-id="c37b6-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="c37b6-122">Include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.</span><span class="sxs-lookup"><span data-stu-id="c37b6-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="c37b6-123">Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c37b6-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="c37b6-124">Migliora la capacità di Microsoft 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.</span><span class="sxs-lookup"><span data-stu-id="c37b6-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="c37b6-125">Se si utilizza il codice "Customer Key", è possibile generare le proprie chiavi di crittografia utilizzando un modulo di servizio hardware (HSM) locale o un Vault Key di Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="c37b6-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="c37b6-126">Indipendentemente dal modo in cui viene generata la chiave, è possibile utilizzare AKV per controllare e gestire le chiavi di crittografia utilizzate da Office 365.</span><span class="sxs-lookup"><span data-stu-id="c37b6-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="c37b6-127">Dopo aver memorizzato i tasti in AKV, è possibile utilizzarli come radice di uno dei portachiavi che crittografa i dati o i file delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="c37b6-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="c37b6-128">Un altro vantaggio della chiave del cliente è il controllo che si ha sulla capacità di elaborazione dei dati da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c37b6-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="c37b6-129">Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera terminare il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e utilizzare la chiave del cliente come controllo tecnico.</span><span class="sxs-lookup"><span data-stu-id="c37b6-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="c37b6-130">In questo modo, nessuno, incluso Microsoft, può accedere ai dati o elaborarli.</span><span class="sxs-lookup"><span data-stu-id="c37b6-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="c37b6-131">La chiave del cliente è inoltre e complementare all'archivio protetto dei clienti che si utilizza per controllare l'accesso ai dati da parte del personale Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c37b6-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="c37b6-132">Per informazioni su come configurare la chiave del cliente per Microsoft 365 per Exchange Online, Skype for business, SharePoint Online, inclusi i siti del team e OneDrive for business, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c37b6-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="c37b6-133">Crittografia del servizio con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="c37b6-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c37b6-134">Configurare la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="c37b6-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c37b6-135">Gestione della chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="c37b6-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c37b6-136">Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="c37b6-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c37b6-137">Comprendere il codice di disponibilità</span><span class="sxs-lookup"><span data-stu-id="c37b6-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

