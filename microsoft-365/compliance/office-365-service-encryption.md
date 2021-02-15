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
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058549"
---
# <a name="service-encryption"></a><span data-ttu-id="a3e6a-103">Crittografia del servizio</span><span class="sxs-lookup"><span data-stu-id="a3e6a-103">Service Encryption</span></span>

<span data-ttu-id="a3e6a-104">Oltre a usare la crittografia a livello di volume, Exchange Online, Microsoft Teams, SharePoint Online e OneDrive for Business usano anche la crittografia del servizio per crittografare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="a3e6a-105">La crittografia del servizio consente due opzioni di gestione delle chiavi:</span><span class="sxs-lookup"><span data-stu-id="a3e6a-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="a3e6a-106">Chiavi gestite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3e6a-106">Microsoft-managed keys</span></span>
<span data-ttu-id="a3e6a-107">Microsoft gestisce tutte le chiavi crittografiche, incluse le chiavi radice per la crittografia del servizio.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="a3e6a-108">Questa opzione è attualmente abilitata per impostazione predefinita per Exchange Online, SharePoint Online, OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="a3e6a-109">Le chiavi gestite da Microsoft forniscono la crittografia del servizio predefinita, a meno che tu non decida di eseguire l'onboard usando Customer Key.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="a3e6a-110">Se, in un secondo momento, decidi di smettere di usare Customer Key senza seguire il percorso di eliminazione dei dati, i dati rimangono crittografati usando le chiavi gestite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="a3e6a-111">I dati vengono sempre crittografati almeno a questo livello predefinito.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="a3e6a-112">Customer Key</span><span class="sxs-lookup"><span data-stu-id="a3e6a-112">Customer Key</span></span>
<span data-ttu-id="a3e6a-113">Le chiavi radice utilizzate con la crittografia del servizio vengono fornite e gestite tramite Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="a3e6a-114">Microsoft gestisce tutte le altre chiavi.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="a3e6a-115">Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="a3e6a-116">In precedenza noto come crittografia avanzata con BYOK.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="a3e6a-117">Per l'annuncio originale, vedere Migliorare la trasparenza e il controllo per i clienti di [Office 365.](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)</span><span class="sxs-lookup"><span data-stu-id="a3e6a-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="a3e6a-118">La crittografia del servizio offre diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="a3e6a-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="a3e6a-119">Fornisce un ulteriore livello di protezione su BitLocker.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="a3e6a-120">Separa gli amministratori del sistema operativo Windows dall'accesso ai dati dell'applicazione archiviati o elaborati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="a3e6a-121">Include un'opzione Customer Key che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="a3e6a-122">Migliora la capacità di Microsoft 365 di soddisfare le esigenze dei clienti che hanno requisiti di conformità specifici relativi alla crittografia.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="a3e6a-123">Usando Customer Key, puoi generare chiavi crittografiche usando un modulo del servizio hardware (HSM) locale o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="a3e6a-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="a3e6a-124">Indipendentemente da come viene generata la chiave, si usa AKV per controllare e gestire le chiavi di crittografia usate da Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="a3e6a-125">Una volta archiviate in AKV, le chiavi possono essere utilizzate come radice di uno dei keychains che crittografa i dati o i file della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="a3e6a-126">Un altro vantaggio di Customer Key è il controllo che hai sulla capacità di Microsoft di elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="a3e6a-127">Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera interrompere il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e usare Customer Key come controllo tecnico.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="a3e6a-128">La rimozione dei dati garantisce che nessuno, incluso Microsoft, possa accedere o elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="a3e6a-129">Customer Key è in aggiunta e complementare a Customer Lockbox che usi per controllare l'accesso ai dati da parte del personale Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3e6a-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="a3e6a-130">Per informazioni su come configurare Customer Key per Microsoft 365 per Exchange Online, Microsoft Teams, SharePoint Online, inclusi i siti del team e OneDrive for Business, vedere questi articoli:</span><span class="sxs-lookup"><span data-stu-id="a3e6a-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="a3e6a-131">Crittografia del servizio con Customer Key</span><span class="sxs-lookup"><span data-stu-id="a3e6a-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="a3e6a-132">Configurare Customer Key</span><span class="sxs-lookup"><span data-stu-id="a3e6a-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="a3e6a-133">Gestire Customer Key</span><span class="sxs-lookup"><span data-stu-id="a3e6a-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="a3e6a-134">Implementare o ruotare una chiave cliente o una chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="a3e6a-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="a3e6a-135">Informazioni sulla chiave di disponibilità</span><span class="sxs-lookup"><span data-stu-id="a3e6a-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
