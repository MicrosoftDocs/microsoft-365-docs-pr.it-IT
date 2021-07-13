---
title: Requisiti per Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP), ottenere un elenco di requisiti da utilizzare Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395187"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="5f185-103">Requisiti per Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="5f185-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="5f185-104">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i requisiti elencati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5f185-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="5f185-105">Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="5f185-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="5f185-106">Microsoft 365 Lighthouse è un portale di amministrazione che consente ai provider di servizi gestiti (MSP) di proteggere e gestire dispositivi, dati e utenti su larga scala per i clienti di piccole e medie imprese (SMB).</span><span class="sxs-lookup"><span data-stu-id="5f185-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="5f185-107">Gli SSP devono essere registrati nel programma Cloud Solution Provider (CSP) come rivenditore indiretto o partner di Fatturazione diretta per usare Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="5f185-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="5f185-108">Inoltre, ogni tenant del cliente MSP deve essere idoneo per Microsoft 365 Lighthouse soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f185-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="5f185-109">Privilegi di amministratore delegato (DAP) per msp</span><span class="sxs-lookup"><span data-stu-id="5f185-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="5f185-110">Almeno una licenza Microsoft 365 Business Premium licenza</span><span class="sxs-lookup"><span data-stu-id="5f185-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="5f185-111">Meno di 500 utenti con licenza</span><span class="sxs-lookup"><span data-stu-id="5f185-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="5f185-112">Requisiti per abilitare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="5f185-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="5f185-113">Per visualizzare i dispositivi tenant dei clienti nelle pagine di gestione dei dispositivi, un msp deve:</span><span class="sxs-lookup"><span data-stu-id="5f185-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="5f185-114">Registrare tutti i dispositivi dei clienti in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="5f185-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="5f185-115">Per altre informazioni, vedi [Registrare i dispositivi in Microsoft Intune](/mem/intune/enrollment/).</span><span class="sxs-lookup"><span data-stu-id="5f185-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="5f185-116">Assegnare criteri di conformità a tutti i dispositivi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="5f185-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="5f185-117">Per ulteriori informazioni, vedere [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="5f185-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="5f185-118">Requisiti per l'abilitazione della gestione degli utenti</span><span class="sxs-lookup"><span data-stu-id="5f185-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="5f185-119">Per visualizzare i dati dei clienti nei report nelle pagine di gestione degli utenti, inclusi gli utenti rischiosi, l'autenticazione a più fattori e la reimpostazione della password, i tenant dei clienti devono disporre di licenze per Azure Active Directory Premium P1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5f185-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="5f185-120">Azure AD Premium P1 è incluso in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="5f185-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="5f185-121">Requisiti per l'abilitazione della gestione delle minacce</span><span class="sxs-lookup"><span data-stu-id="5f185-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="5f185-122">Per visualizzare i dispositivi tenant dei clienti e le minacce nelle pagine di gestione delle minacce, è necessario registrare tutti i dispositivi tenant dei clienti in Microsoft Endpoint Manager (MEM) e proteggerli eseguendo Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5f185-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="5f185-123">Per altre informazioni, vedi [Registrare i dispositivi in Microsoft Intune](/mem/intune/enrollment/).</span><span class="sxs-lookup"><span data-stu-id="5f185-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="5f185-124">Antivirus Microsoft Defender fa parte del sistema operativo Windows ed è abilitato per impostazione predefinita nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5f185-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="5f185-125">Se si utilizza una soluzione antivirus non Microsoft e non Antivirus Microsoft Defender, Antivirus Microsoft Defender viene disabilitata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5f185-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="5f185-126">Quando si disinstalla la soluzione antivirus non Microsoft, l'Antivirus Microsoft Defender viene attivata automaticamente per proteggere i dispositivi Windows dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="5f185-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="5f185-127">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="5f185-127">Related content</span></span>   

<span data-ttu-id="5f185-128">[Configurare Microsoft 365 Lighthouse sicurezza del portale](m365-lighthouse-configure-portal-security.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="5f185-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="5f185-129">[Microsoft 365 Lighthouse panoramica della pagina Conformità dispositivo](m365-lighthouse-device-compliance-page-overview.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="5f185-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="5f185-130">[Microsoft 365 Lighthouse panoramica della pagina Utenti](m365-lighthouse-users-page-overview.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="5f185-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="5f185-131">[Microsoft 365 Lighthouse panoramica della pagina gestione delle minacce](m365-lighthouse-threat-management-page-overview.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="5f185-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="5f185-132">[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml)   (articolo)</span><span class="sxs-lookup"><span data-stu-id="5f185-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

