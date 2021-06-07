---
title: Risolvere i Microsoft 365 del servizio Defender
description: Trovare soluzioni e soluzioni alternative per problemi noti Microsoft 365 Defender
keywords: risoluzione dei Microsoft 365 Defender, risoluzione dei problemi, Microsoft Defender per l'identità, problemi, componente aggiuntivo, pagina delle impostazioni
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782742"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="70ae9-104">Risolvere i Microsoft 365 del servizio Defender</span><span class="sxs-lookup"><span data-stu-id="70ae9-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="70ae9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="70ae9-105">**Applies to:**</span></span>
- <span data-ttu-id="70ae9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70ae9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="70ae9-107">In questa sezione vengono risolti i problemi che possono verificarsi quando usi il servizio Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="70ae9-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="70ae9-108">I don't see Microsoft 365 Defender content</span><span class="sxs-lookup"><span data-stu-id="70ae9-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="70ae9-109">Se nel riquadro di spostamento non sono disponibili funzionalità come Eventi imprevisti, Centro notifiche o Ricerca nel portale, è necessario verificare che il tenant abbia le licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="70ae9-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="70ae9-110">Per altre informazioni, vedere [Prerequisiti](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="70ae9-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="70ae9-111">Gli avvisi di Microsoft Defender for Identity non vengono visualizzati negli eventi imprevisti di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70ae9-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="70ae9-112">Se nel tuo ambiente è distribuito Microsoft Defender for Identity ma non vedi gli avvisi di Defender for Identity nell'ambito di eventi imprevisti di Microsoft 365 Defender, dovrai assicurarti che l'integrazione di Microsoft Cloud App Security e Defender for Identity sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="70ae9-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="70ae9-113">Per altre informazioni, vedi [Microsoft Defender per l'integrazione delle identità.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="70ae9-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="70ae9-114">Dove si trova la pagina delle impostazioni per l'attivazione del servizio?</span><span class="sxs-lookup"><span data-stu-id="70ae9-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="70ae9-115">Per attivare Microsoft 365 Defender, **accedere** Impostazioni dal riquadro di spostamento nel centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="70ae9-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="70ae9-116">Questo elemento di spostamento è visibile solo se si dispone delle autorizzazioni e delle [licenze prerequisiti.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="70ae9-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="70ae9-117">Come si crea un'eccezione per il file o l'URL?</span><span class="sxs-lookup"><span data-stu-id="70ae9-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="70ae9-118">Un falso positivo è un file o un URL rilevato come dannoso ma non una minaccia.</span><span class="sxs-lookup"><span data-stu-id="70ae9-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="70ae9-119">Puoi creare indicatori e definire esclusioni per sbloccare e consentire determinati file/URL.</span><span class="sxs-lookup"><span data-stu-id="70ae9-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="70ae9-120">Vedi [Indirizzo falsi positivi/negativi in Defender per Endpoint.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)</span><span class="sxs-lookup"><span data-stu-id="70ae9-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


