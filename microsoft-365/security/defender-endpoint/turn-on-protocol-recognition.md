---
title: Attivare il riconoscimento del protocollo per Antivirus Microsoft Defender
description: Attivare il riconoscimento protocollo per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, difensore, riconoscimento protocollo
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296478"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="6e241-104">Attivare il riconoscimento del protocollo</span><span class="sxs-lookup"><span data-stu-id="6e241-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6e241-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6e241-105">**Applies to:**</span></span>

- [<span data-ttu-id="6e241-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6e241-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6e241-107">Questa impostazione dei criteri consente di configurare il riconoscimento del protocollo per la protezione della rete da exploit di vulnerabilità note.</span><span class="sxs-lookup"><span data-stu-id="6e241-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="6e241-108">Se si abilita o non si configura questa impostazione, verrà abilitato il riconoscimento del protocollo.</span><span class="sxs-lookup"><span data-stu-id="6e241-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="6e241-109">Se disabiliti questa impostazione, il riconoscimento del protocollo verrà disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6e241-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="6e241-110">Utilizzare Criteri di gruppo per configurare il riconoscimento protocollo</span><span class="sxs-lookup"><span data-stu-id="6e241-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="6e241-111">Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="6e241-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="6e241-112">Passare a **Configurazione computer** Modelli  >  **amministrativi Windows**  >  **componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**.</span><span class="sxs-lookup"><span data-stu-id="6e241-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="6e241-113">Selezionare **riconoscimento protocollo**.</span><span class="sxs-lookup"><span data-stu-id="6e241-113">Select **protocol recognition**.</span></span> <span data-ttu-id="6e241-114">Per impostazione predefinita, questo criterio è abilitato.</span><span class="sxs-lookup"><span data-stu-id="6e241-114">By default, this policy is enabled.</span></span> <span data-ttu-id="6e241-115">Se impostato **su Non configurato,** il ritiro delle definizioni è abilitato.</span><span class="sxs-lookup"><span data-stu-id="6e241-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="6e241-116">Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**</span><span class="sxs-lookup"><span data-stu-id="6e241-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="6e241-117">Selezionare **Abilitato** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="6e241-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="6e241-118">Distribuire l'oggetto Criteri di gruppo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="6e241-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="6e241-119">Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="6e241-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="6e241-120">Si usano oggetti Criteri di gruppo in locale?</span><span class="sxs-lookup"><span data-stu-id="6e241-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="6e241-121">Scopri come traducono nel cloud.</span><span class="sxs-lookup"><span data-stu-id="6e241-121">See how they translate in the cloud.</span></span> <span data-ttu-id="6e241-122">Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima .</span><span class="sxs-lookup"><span data-stu-id="6e241-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="6e241-123">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6e241-123">Related articles</span></span>

- [<span data-ttu-id="6e241-124">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="6e241-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="6e241-125">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="6e241-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="6e241-126">Come creare e distribuire criteri antimalware: servizio di protezione cloud</span><span class="sxs-lookup"><span data-stu-id="6e241-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)