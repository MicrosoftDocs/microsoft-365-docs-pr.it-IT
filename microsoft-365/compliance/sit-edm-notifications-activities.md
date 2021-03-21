---
title: Creare notifiche per attività di corrispondenza esatta dei dati (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come creare notifiche per le attività di corrispondenza esatta dei dati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919362"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="bde08-103">Creare notifiche per attività di corrispondenza esatta dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="bde08-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="bde08-104">Quando si [creano tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) nel [log di audit](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) vengono create diverse attività.</span><span class="sxs-lookup"><span data-stu-id="bde08-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="bde08-105">È possibile usare il cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) di PowerShell per creare notifiche che consentono di sapere quando si verificano queste attività:</span><span class="sxs-lookup"><span data-stu-id="bde08-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="bde08-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="bde08-106">CreateSchema</span></span>
- <span data-ttu-id="bde08-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="bde08-107">EditSchema</span></span>
- <span data-ttu-id="bde08-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="bde08-108">RemoveSchema</span></span>
- <span data-ttu-id="bde08-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="bde08-109">UploadDataFailed</span></span>
- <span data-ttu-id="bde08-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="bde08-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="bde08-111">La possibilità di creare notifiche per le attività EDM è disponibile solo per i cloud World Wide e GCC.</span><span class="sxs-lookup"><span data-stu-id="bde08-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="bde08-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bde08-112">Pre-requisites</span></span>

<span data-ttu-id="bde08-113">L'account da usare deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="bde08-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="bde08-114">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="bde08-114">a global admin</span></span>
- <span data-ttu-id="bde08-115">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="bde08-115">compliance administrator</span></span>
- <span data-ttu-id="bde08-116">Amministratore di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bde08-116">Exchange Online administrator</span></span>

<span data-ttu-id="bde08-117">Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="bde08-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="bde08-118">La classificazione basata su EDM è inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="bde08-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="bde08-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="bde08-119">Office 365 E5</span></span>
- <span data-ttu-id="bde08-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bde08-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="bde08-121">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bde08-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="bde08-122">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="bde08-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="bde08-123">Per altre informazioni sulle licenze DLP, vedere [Indicazioni sulla gestione delle licenze di Microsoft 365 per la sicurezza e la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="bde08-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="bde08-124">Configurare le notifiche per le attività EDM</span><span class="sxs-lookup"><span data-stu-id="bde08-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="bde08-125">Connettersi a [PowerShell nel Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="bde08-125">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="bde08-126">Eseguire il cmdlet `New-ProtectionAlert` usando l'attività per cui si vuole creare la notifica.</span><span class="sxs-lookup"><span data-stu-id="bde08-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="bde08-127">Ad esempio, se si vuole ricevere una notifica quando si verifica l’azione **UploadDataCompleted**, eseguire</span><span class="sxs-lookup"><span data-stu-id="bde08-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="bde08-128">per l’azione **UploadDataFailed** è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="bde08-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="bde08-129">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="bde08-129">Related articles</span></span>

- [<span data-ttu-id="bde08-130">Creare tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)</span><span class="sxs-lookup"><span data-stu-id="bde08-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="bde08-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="bde08-131">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)