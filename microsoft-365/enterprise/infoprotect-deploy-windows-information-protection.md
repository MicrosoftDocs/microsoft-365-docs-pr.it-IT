---
title: 'Passaggio 4: Configurare Windows Information Protection'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni e distribuzione di Windows Information Protection in Microsoft 365.
ms.openlocfilehash: 66c9e10772edb0782096ba120858e895684255b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631646"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="d586b-103">Passaggio 4: Configurare Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="d586b-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="d586b-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d586b-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d586b-106">Con più dispositivi personali usati per lavoro, aumenta il rischio per le applicazioni e i dispositivi di una perdita di dati aziendali privati.</span><span class="sxs-lookup"><span data-stu-id="d586b-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="d586b-107">Ad esempio, un dipendente invia inavvertitamente l'immagine di un piano di marketing per un prodotto futuro attualmente in un sito di social networking o salva un file contenente informazioni strettamente riservate nel proprio sistema pubblico di archiviazione cloud.</span><span class="sxs-lookup"><span data-stu-id="d586b-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="d586b-108">Windows Information Protection (WIP) consente di evitare questi tipi di perdita di dati nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d586b-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="d586b-109">Per ulteriori informazioni, vedere [Proteggere i dati dell'organizzazione con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="d586b-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="d586b-110">In Microsoft 365 Enterprise, WIP è una combinazione di Windows 10 Enterprise e Microsoft Intune, incluso nell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="d586b-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="d586b-111">Per distribuire WIP nell'organizzazione con Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="d586b-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="d586b-112">Registrare i dispositivi Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="d586b-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="d586b-113">È necessario farlo nella [Fase 5: gestione di dispositivi mobili](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="d586b-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="d586b-114">Creare un [Criterio di Intune per WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="d586b-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="d586b-115">Verificare che l'elenco di applicazioni protette sia stato compilato.</span><span class="sxs-lookup"><span data-stu-id="d586b-115">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="d586b-116">Scegliere il livello di protezione del WIP.</span><span class="sxs-lookup"><span data-stu-id="d586b-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="d586b-117">È possibile usare WIP anche con [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="d586b-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="d586b-118">Vedere [Procedure consigliate per WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="d586b-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="d586b-119">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d586b-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d586b-120">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d586b-120">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="d586b-122">Configurare la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="d586b-122">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


