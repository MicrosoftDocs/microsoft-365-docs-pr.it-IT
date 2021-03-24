---
title: Risolvere i problemi del servizio Microsoft 365 Defender
description: Trovare soluzioni e soluzioni per i problemi noti di Microsoft 365 Defender
keywords: risoluzione dei problemi di Microsoft Threat Protection, risoluzione dei problemi, Azure ATP, problemi, componente aggiuntivo, pagina delle impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065898"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="d62fc-104">Risolvere i problemi del servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d62fc-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d62fc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d62fc-105">**Applies to:**</span></span>
- <span data-ttu-id="d62fc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d62fc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d62fc-107">In questa sezione vengono risolti i problemi che possono verificarsi quando si utilizza il servizio Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d62fc-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="d62fc-108">I don't see Microsoft 365 Defender content</span><span class="sxs-lookup"><span data-stu-id="d62fc-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="d62fc-109">Se nel riquadro di spostamento non sono disponibili funzionalità come Eventi imprevisti, Centro notifiche o Ricerca nel portale, è necessario verificare che il tenant abbia le licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="d62fc-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="d62fc-110">Per altre informazioni, vedere [Prerequisiti](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d62fc-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="d62fc-111">Gli avvisi di Microsoft Defender for Identity non vengono visualizzati negli eventi imprevisti di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d62fc-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="d62fc-112">Se nel tuo ambiente è distribuito Microsoft Defender for Identity ma non vedi gli avvisi di Defender for Identity come parte degli incidenti di Microsoft 365 Defender, dovrai assicurarti che l'integrazione di Microsoft Cloud App Security e Defender for Identity sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="d62fc-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="d62fc-113">Per altre informazioni, vedi [Microsoft Defender per l'integrazione delle identità.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="d62fc-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="d62fc-114">Dove si trova la pagina delle impostazioni per attivare il servizio?</span><span class="sxs-lookup"><span data-stu-id="d62fc-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="d62fc-115">Per attivare Microsoft 365 Defender, accedere a **Impostazioni** dal riquadro di spostamento nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d62fc-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="d62fc-116">Questo elemento di spostamento è visibile solo se si dispone delle autorizzazioni e delle [licenze prerequisiti.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="d62fc-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>
