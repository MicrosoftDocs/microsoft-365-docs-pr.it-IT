---
title: Risolvere i problemi del servizio Microsoft 365 Defender
description: Trovare soluzioni e soluzioni per problemi noti di Microsoft 365 Defender
keywords: risoluzione dei problemi di Microsoft Threat Protection, risoluzione dei problemi, Azure ATP, problemi, componente aggiuntivo, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925719"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="4b501-104">Risolvere i problemi del servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b501-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4b501-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4b501-105">**Applies to:**</span></span>
- <span data-ttu-id="4b501-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b501-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4b501-107">In questa sezione vengono risolti i problemi che possono verificarsi quando si utilizza il servizio Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4b501-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="4b501-108">I don't see Microsoft 365 Defender content</span><span class="sxs-lookup"><span data-stu-id="4b501-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="4b501-109">Se nel riquadro di spostamento non sono disponibili funzionalità come Eventi imprevisti, Centro notifiche o Ricerca nel portale, è necessario verificare che il tenant abbia le licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="4b501-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="4b501-110">Per altre informazioni, vedere [Prerequisiti](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="4b501-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="4b501-111">Gli avvisi di Microsoft Defender per l'identità non vengono visualizzati negli eventi imprevisti di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b501-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="4b501-112">Se nell'ambiente è distribuito Microsoft Defender for Identity, ma gli avvisi di Defender for Identity non vengono visualizzati come parte degli incidenti di Microsoft 365 Defender, è necessario verificare che l'integrazione di Microsoft Cloud App Security e Defender for Identity sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="4b501-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="4b501-113">Per altre informazioni, vedere [Integrazione di Microsoft Defender per l'identità.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="4b501-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="4b501-114">Dove si trova la pagina delle impostazioni per l'attivazione del servizio?</span><span class="sxs-lookup"><span data-stu-id="4b501-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="4b501-115">Per attivare Microsoft 365 Defender, accedere a **Impostazioni** dal riquadro di spostamento nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b501-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="4b501-116">Questo elemento di spostamento è visibile solo se si dispone delle autorizzazioni [e delle licenze prerequisiti.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="4b501-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
