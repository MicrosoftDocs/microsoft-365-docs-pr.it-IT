---
title: Attivare il ritiro delle definizioni per Antivirus Microsoft Defender
description: Attivare il ritiro delle definizioni per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, difensore, ritiro delle definizioni
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903805"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="8213d-104">Attivare il ritiro delle definizioni</span><span class="sxs-lookup"><span data-stu-id="8213d-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8213d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8213d-105">**Applies to:**</span></span>

- [<span data-ttu-id="8213d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8213d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8213d-107">È possibile configurare il ritiro delle definizioni utilizzando Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="8213d-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="8213d-108">Il ritiro delle definizioni controlla se un computer dispone degli aggiornamenti della sicurezza necessari per proteggerlo da una particolare vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="8213d-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="8213d-109">Se il sistema non è vulnerabile all'exploit rilevato da una definizione, tale definizione viene "ritirata".</span><span class="sxs-lookup"><span data-stu-id="8213d-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="8213d-110">Se tutte le informazioni di sicurezza per un determinato protocollo vengono ritirate, il protocollo non viene più analizzato.</span><span class="sxs-lookup"><span data-stu-id="8213d-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="8213d-111">L'abilitazione di questa funzionalità consente di migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8213d-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="8213d-112">In un computer aggiornato con tutti gli aggiornamenti della sicurezza più recenti, la protezione di rete non avrà alcun impatto sulle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="8213d-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="8213d-113">Utilizzare Criteri di gruppo per configurare il ritiro delle definizioni</span><span class="sxs-lookup"><span data-stu-id="8213d-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="8213d-114">Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="8213d-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="8213d-115">Passare a **Configurazione computer** Modelli  >  **amministrativi Windows**  >  **componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**.</span><span class="sxs-lookup"><span data-stu-id="8213d-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="8213d-116">Selezionare **Attiva ritiro definizione.**</span><span class="sxs-lookup"><span data-stu-id="8213d-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="8213d-117">Per impostazione predefinita, questo criterio è abilitato.</span><span class="sxs-lookup"><span data-stu-id="8213d-117">By default, this policy is enabled.</span></span> <span data-ttu-id="8213d-118">Se impostato **su Non configurato,** il ritiro delle definizioni è abilitato.</span><span class="sxs-lookup"><span data-stu-id="8213d-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="8213d-119">Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**</span><span class="sxs-lookup"><span data-stu-id="8213d-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="8213d-120">Selezionare **Abilitato** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="8213d-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="8213d-121">Distribuire l'oggetto Criteri di gruppo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8213d-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="8213d-122">Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="8213d-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="8213d-123">Si usano oggetti Criteri di gruppo in locale?</span><span class="sxs-lookup"><span data-stu-id="8213d-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="8213d-124">Scopri come traducono nel cloud.</span><span class="sxs-lookup"><span data-stu-id="8213d-124">See how they translate in the cloud.</span></span> <span data-ttu-id="8213d-125">Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima .</span><span class="sxs-lookup"><span data-stu-id="8213d-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
