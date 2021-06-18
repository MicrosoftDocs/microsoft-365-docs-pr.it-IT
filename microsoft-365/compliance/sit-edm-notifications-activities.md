---
title: Creare notifiche per attività di corrispondenza esatta dei dati
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
ms.openlocfilehash: 15aa8f2bda76d56d3e35af8e884193193bb78d40
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007562"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="77dcd-103">Creare notifiche per attività di corrispondenza esatta dei dati</span><span class="sxs-lookup"><span data-stu-id="77dcd-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="77dcd-104">Quando si [creano tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) nel [log di audit](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) vengono create diverse attività.</span><span class="sxs-lookup"><span data-stu-id="77dcd-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="77dcd-105">È possibile usare il cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) di PowerShell per creare notifiche che consentono di sapere quando si verificano queste attività:</span><span class="sxs-lookup"><span data-stu-id="77dcd-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="77dcd-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="77dcd-106">CreateSchema</span></span>
- <span data-ttu-id="77dcd-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="77dcd-107">EditSchema</span></span>
- <span data-ttu-id="77dcd-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="77dcd-108">RemoveSchema</span></span>
- <span data-ttu-id="77dcd-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="77dcd-109">UploadDataFailed</span></span>
- <span data-ttu-id="77dcd-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="77dcd-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="77dcd-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="77dcd-111">Pre-requisites</span></span>

<span data-ttu-id="77dcd-112">L'account da usare deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="77dcd-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="77dcd-113">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="77dcd-113">a global admin</span></span>
- <span data-ttu-id="77dcd-114">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="77dcd-114">compliance administrator</span></span>
- <span data-ttu-id="77dcd-115">Amministratore di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="77dcd-115">Exchange Online administrator</span></span>

<span data-ttu-id="77dcd-116">Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="77dcd-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="77dcd-117">La classificazione basata su EDM è inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="77dcd-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="77dcd-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="77dcd-118">Office 365 E5</span></span>
- <span data-ttu-id="77dcd-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="77dcd-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="77dcd-120">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="77dcd-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="77dcd-121">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="77dcd-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="77dcd-122">Per altre informazioni sulle licenze DLP, vedere [Indicazioni sulla gestione delle licenze di Microsoft 365 per la sicurezza e la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="77dcd-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="77dcd-123">Configurare le notifiche per le attività EDM</span><span class="sxs-lookup"><span data-stu-id="77dcd-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="77dcd-124">Connettersi a [PowerShell nel Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="77dcd-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="77dcd-125">Eseguire il cmdlet `New-ProtectionAlert` usando l'attività per cui si vuole creare la notifica.</span><span class="sxs-lookup"><span data-stu-id="77dcd-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="77dcd-126">Ad esempio, se si vuole ricevere una notifica quando si verifica l’azione **UploadDataCompleted**, eseguire</span><span class="sxs-lookup"><span data-stu-id="77dcd-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="77dcd-127">per l’azione **UploadDataFailed** è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="77dcd-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="77dcd-128">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="77dcd-128">Related articles</span></span>

- [<span data-ttu-id="77dcd-129">Creare tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)</span><span class="sxs-lookup"><span data-stu-id="77dcd-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="77dcd-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="77dcd-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)