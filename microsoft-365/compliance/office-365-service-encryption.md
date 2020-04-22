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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632241"
---
# <a name="service-encryption"></a><span data-ttu-id="36f33-103">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="36f33-103">Service Encryption</span></span>

<span data-ttu-id="36f33-104">Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="36f33-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="36f33-105">La crittografia del servizio consente di eseguire due opzioni di gestione principali:</span><span class="sxs-lookup"><span data-stu-id="36f33-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="36f33-106">Microsoft gestisce tutte le chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="36f33-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="36f33-107">Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for business e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="36f33-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="36f33-108">L'organizzazione fornisce le chiavi radice.</span><span class="sxs-lookup"><span data-stu-id="36f33-108">Your organization supplies the root keys.</span></span> <span data-ttu-id="36f33-109">È possibile gestire queste chiavi utilizzando il Vault Key di Azure.</span><span class="sxs-lookup"><span data-stu-id="36f33-109">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="36f33-110">Questa opzione è denominata Customer Key.</span><span class="sxs-lookup"><span data-stu-id="36f33-110">This option is called Customer Key.</span></span> <span data-ttu-id="36f33-111">La chiave del cliente è attualmente disponibile per i file di Exchange Online, SharePoint Online, OneDrive for business, Skype for business e teams.</span><span class="sxs-lookup"><span data-stu-id="36f33-111">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="36f33-112">Se si utilizza il codice "Customer Key", queste chiavi sostituiscono le chiavi gestite da Microsoft per crittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="36f33-112">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="36f33-113">La crittografia dei servizi offre molteplici vantaggi.</span><span class="sxs-lookup"><span data-stu-id="36f33-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="36f33-114">Ad esempio, Customer Key:</span><span class="sxs-lookup"><span data-stu-id="36f33-114">For example, Customer Key:</span></span>

- <span data-ttu-id="36f33-115">Fornisce funzionalità di gestione e protezione dei diritti al di sopra della protezione dalla crittografia avanzata.</span><span class="sxs-lookup"><span data-stu-id="36f33-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="36f33-116">Include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.</span><span class="sxs-lookup"><span data-stu-id="36f33-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="36f33-117">Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="36f33-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="36f33-118">Migliora la capacità di Microsoft 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.</span><span class="sxs-lookup"><span data-stu-id="36f33-118">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="36f33-119">Customer Key</span><span class="sxs-lookup"><span data-stu-id="36f33-119">Customer Key</span></span>

<span data-ttu-id="36f33-120">Se si utilizza il codice "Customer Key", è possibile generare le proprie chiavi di crittografia utilizzando un modulo di servizio hardware (HSM) locale o un Vault Key di Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="36f33-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="36f33-121">Indipendentemente dal modo in cui viene generata la chiave, è possibile utilizzare AKV per controllare e gestire le chiavi di crittografia utilizzate da Office 365.</span><span class="sxs-lookup"><span data-stu-id="36f33-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="36f33-122">Dopo aver memorizzato i tasti in AKV, è possibile utilizzarli come radice di uno dei portachiavi che crittografa i dati o i file delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="36f33-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="36f33-123">Un altro vantaggio della chiave del cliente è il controllo che si ha sulla capacità di elaborazione dei dati da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36f33-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="36f33-124">Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera terminare il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e utilizzare la chiave del cliente come controllo tecnico.</span><span class="sxs-lookup"><span data-stu-id="36f33-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="36f33-125">In questo modo, nessuno, incluso Microsoft, può accedere ai dati o elaborarli.</span><span class="sxs-lookup"><span data-stu-id="36f33-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="36f33-126">La chiave del cliente è inoltre e complementare all'archivio protetto dei clienti che si utilizza per controllare l'accesso ai dati da parte del personale Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36f33-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="36f33-127">Per informazioni su come configurare la chiave del cliente per Microsoft 365 per Exchange Online, Skype for business, SharePoint Online, inclusi i siti del team e OneDrive for business, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="36f33-127">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="36f33-128">Crittografia del servizio con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="36f33-128">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="36f33-129">Configurare la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="36f33-129">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="36f33-130">Gestione della chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="36f33-130">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="36f33-131">Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="36f33-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="36f33-132">Comprendere il codice di disponibilità</span><span class="sxs-lookup"><span data-stu-id="36f33-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
