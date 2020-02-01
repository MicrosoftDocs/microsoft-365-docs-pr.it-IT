---
title: Risoluzione dei problemi relativi al servizio Microsoft Threat Protection
description: Individuare le soluzioni e aggirare i problemi noti relativi a Microsoft Threat Protection
keywords: risoluzione dei problemi relativi alla protezione dalle minacce Microsoft, risoluzione dei problemi, Azure ATP, problemi, componente aggiuntivo, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661982"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="05d16-104">Risoluzione dei problemi relativi al servizio Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="05d16-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="05d16-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="05d16-105">**Applies to:**</span></span>
- <span data-ttu-id="05d16-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="05d16-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="05d16-107">Questa sezione consente di risolvere i problemi che potrebbero verificarsi se si utilizza il servizio Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="05d16-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="05d16-108">Non viene visualizzato il contenuto di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="05d16-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="05d16-109">Se non si visualizzano le funzionalità nel riquadro di spostamento, ad esempio gli eventi non consentiti, il centro azioni o la ricerca nel portale, è necessario verificare che il tenant disponga delle licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="05d16-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="05d16-110">Per altre informazioni, vedere [Prerequisiti](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="05d16-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="05d16-111">Gli avvisi di Azure ATP non sono visualizzati tra gli incidenti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="05d16-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="05d16-112">Se si utilizza Azure ATP nell'ambiente distribuito ma non è possibile vedere gli avvisi di Azure ATP come incidenti di Microsoft Threat Protection, è necessario verificare che sia abilitata l'integrazione di Microsoft Cloud App Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="05d16-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="05d16-113">Per altre informazioni, vedere [Integrazione di Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="05d16-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="05d16-114">Microsoft Threat Protection è disponibile per US Government Community Cloud (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="05d16-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="05d16-115">Al momento non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="05d16-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="05d16-116">Dove si trova la pagina impostazioni per l'attivazione del servizio?</span><span class="sxs-lookup"><span data-stu-id="05d16-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="05d16-117">Per abilitare Microsoft Threat Protection, accedere alle **Impostazioni** dal riquadro di spostamento nel centro sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05d16-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="05d16-118">Questo elemento di spostamento è visibile solo se si dispone delle [autorizzazioni e delle licenze prerequisite](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="05d16-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="05d16-119">È possibile utilizzare un componente aggiuntivo invece delle licenze E5 necessarie?</span><span class="sxs-lookup"><span data-stu-id="05d16-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="05d16-120">Attualmente non sono disponibili componenti aggiuntivi per Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="05d16-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="05d16-121">Visualizzare i requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="05d16-121">See licensing requirements</span></span>](prerequisites.md) 

