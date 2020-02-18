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
ms.openlocfilehash: 655ff33c3fd1bba822937618d801db76b7881977
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067163"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="aa96e-103">Passaggio 4: Configurare Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="aa96e-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="aa96e-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="aa96e-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="aa96e-106">Con più dispositivi personali usati per lavoro, aumenta il rischio per le applicazioni e i dispositivi di una perdita di dati aziendali privati.</span><span class="sxs-lookup"><span data-stu-id="aa96e-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="aa96e-107">Ad esempio, un dipendente invia inavvertitamente l'immagine di un piano di marketing per un prodotto futuro attualmente in un sito di social networking o salva un file contenente informazioni strettamente riservate nel proprio sistema pubblico di archiviazione cloud.</span><span class="sxs-lookup"><span data-stu-id="aa96e-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="aa96e-108">Windows Information Protection (WIP) consente di evitare questi tipi di perdita di dati nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="aa96e-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="aa96e-109">Per ulteriori informazioni, vedere [Proteggere i dati dell'organizzazione con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="aa96e-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="aa96e-110">In Microsoft 365 Enterprise, WIP è una combinazione di Windows 10 Enterprise e Microsoft Intune, incluso nell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="aa96e-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="aa96e-111">Per distribuire WIP nell'organizzazione con Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="aa96e-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="aa96e-112">Registrare i dispositivi Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="aa96e-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="aa96e-113">È necessario farlo nella [Fase 5: gestione di dispositivi mobili](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="aa96e-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="aa96e-114">Creare un [Criterio di Intune per WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="aa96e-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="aa96e-115">Verificare che l'elenco di applicazioni protette sia stato compilato.</span><span class="sxs-lookup"><span data-stu-id="aa96e-115">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="aa96e-116">Scegliere il livello di protezione del WIP.</span><span class="sxs-lookup"><span data-stu-id="aa96e-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="aa96e-117">È possibile usare WIP anche con [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="aa96e-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="aa96e-118">Vedere [Procedure consigliate per WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="aa96e-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="aa96e-119">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="aa96e-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="aa96e-120">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="aa96e-120">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="aa96e-122">Configurare i criteri di prevenzione della perdita dei dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa96e-122">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


