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
ms.openlocfilehash: a537cffe253fa20cf6838ddf3fd9a51ec440fe76
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766694"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="cb0a5-103">Creare notifiche per attività di corrispondenza esatta dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="cb0a5-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="cb0a5-104">Quando si [creano tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) nel [log di audit](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) vengono create diverse attività.</span><span class="sxs-lookup"><span data-stu-id="cb0a5-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="cb0a5-105">È possibile usare il cmdlet [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) di PowerShell per creare notifiche che consentono di sapere quando si verificano queste attività:</span><span class="sxs-lookup"><span data-stu-id="cb0a5-105">You can use the [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="cb0a5-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="cb0a5-106">CreateSchema</span></span>
- <span data-ttu-id="cb0a5-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="cb0a5-107">EditSchema</span></span>
- <span data-ttu-id="cb0a5-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="cb0a5-108">RemoveSchema</span></span>
- <span data-ttu-id="cb0a5-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="cb0a5-109">UploadDataFailed</span></span>
- <span data-ttu-id="cb0a5-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="cb0a5-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="cb0a5-111">La possibilità di creare notifiche per le attività EDM è disponibile solo per i cloud World Wide e GCC.</span><span class="sxs-lookup"><span data-stu-id="cb0a5-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="cb0a5-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cb0a5-112">Pre-requisites</span></span>

<span data-ttu-id="cb0a5-113">L'account da usare deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb0a5-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="cb0a5-114">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="cb0a5-114">a global admin</span></span>
- <span data-ttu-id="cb0a5-115">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="cb0a5-115">compliance administrator</span></span>
- <span data-ttu-id="cb0a5-116">Amministratore di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cb0a5-116">Exchange Online administrator</span></span>

<span data-ttu-id="cb0a5-117">Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="cb0a5-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="cb0a5-118">La classificazione basata su EDM è inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="cb0a5-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="cb0a5-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="cb0a5-119">Office 365 E5</span></span>
- <span data-ttu-id="cb0a5-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cb0a5-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="cb0a5-121">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cb0a5-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="cb0a5-122">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="cb0a5-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="cb0a5-123">Per altre informazioni sulle licenze DLP, vedere [Indicazioni sulla gestione delle licenze di Microsoft 365 per la sicurezza e la conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="cb0a5-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="cb0a5-124">Configurare le notifiche per le attività EDM</span><span class="sxs-lookup"><span data-stu-id="cb0a5-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="cb0a5-125">Connettersi a [PowerShell nel Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="cb0a5-125">Connect to the [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="cb0a5-126">Eseguire il cmdlet `New-ProtectionAlert` usando l'attività per cui si vuole creare la notifica.</span><span class="sxs-lookup"><span data-stu-id="cb0a5-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="cb0a5-127">Ad esempio, se si vuole ricevere una notifica quando si verifica l’azione **UploadDataCompleted**, eseguire</span><span class="sxs-lookup"><span data-stu-id="cb0a5-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="cb0a5-128">per l’azione **UploadDataFailed** è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="cb0a5-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="cb0a5-129">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="cb0a5-129">Related articles</span></span>

- [<span data-ttu-id="cb0a5-130">Creare tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)</span><span class="sxs-lookup"><span data-stu-id="cb0a5-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="cb0a5-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="cb0a5-131">New-ProtectionAlert</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) 