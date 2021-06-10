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
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296481"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="c2882-104">Attivare il ritiro delle definizioni</span><span class="sxs-lookup"><span data-stu-id="c2882-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2882-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c2882-105">**Applies to:**</span></span>

- [<span data-ttu-id="c2882-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c2882-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c2882-107">È possibile configurare il ritiro delle definizioni utilizzando Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c2882-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="c2882-108">Il ritiro delle definizioni controlla se un computer dispone degli aggiornamenti della sicurezza necessari per proteggerlo da una particolare vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="c2882-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="c2882-109">Se il sistema non è vulnerabile all'exploit rilevato da una definizione, tale definizione viene "ritirata".</span><span class="sxs-lookup"><span data-stu-id="c2882-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="c2882-110">Se tutte le informazioni di sicurezza per un determinato protocollo vengono ritirate, il protocollo non viene più analizzato.</span><span class="sxs-lookup"><span data-stu-id="c2882-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="c2882-111">L'abilitazione di questa funzionalità consente di migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c2882-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="c2882-112">In un computer aggiornato con tutti gli aggiornamenti della sicurezza più recenti, la protezione di rete non avrà alcun impatto sulle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="c2882-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="c2882-113">Utilizzare Criteri di gruppo per configurare il ritiro delle definizioni</span><span class="sxs-lookup"><span data-stu-id="c2882-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="c2882-114">Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="c2882-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="c2882-115">Passare a **Configurazione computer** Modelli  >  **amministrativi Windows**  >  **componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**.</span><span class="sxs-lookup"><span data-stu-id="c2882-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="c2882-116">Selezionare **Attiva ritiro definizione.**</span><span class="sxs-lookup"><span data-stu-id="c2882-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="c2882-117">Per impostazione predefinita, questo criterio è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c2882-117">By default, this policy is enabled.</span></span> <span data-ttu-id="c2882-118">Se impostato **su Non configurato,** il ritiro delle definizioni è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c2882-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="c2882-119">Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**</span><span class="sxs-lookup"><span data-stu-id="c2882-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="c2882-120">Selezionare **Abilitato** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="c2882-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="c2882-121">Distribuire l'oggetto Criteri di gruppo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c2882-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="c2882-122">Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="c2882-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="c2882-123">Si usano oggetti Criteri di gruppo in locale?</span><span class="sxs-lookup"><span data-stu-id="c2882-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="c2882-124">Scopri come traducono nel cloud.</span><span class="sxs-lookup"><span data-stu-id="c2882-124">See how they translate in the cloud.</span></span> <span data-ttu-id="c2882-125">Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima .</span><span class="sxs-lookup"><span data-stu-id="c2882-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="c2882-126">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="c2882-126">Related articles</span></span>

- [<span data-ttu-id="c2882-127">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="c2882-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="c2882-128">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="c2882-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="c2882-129">Come creare e distribuire criteri antimalware: servizio di protezione cloud</span><span class="sxs-lookup"><span data-stu-id="c2882-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)