---
title: Specificare set di definizioni aggiuntive per l'ispezione del traffico di rete per Antivirus Microsoft Defender
description: Specificare ulteriori set di definizioni per l'ispezione del traffico di rete per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, defender, ispezione del traffico di rete
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300196"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="b4f68-104">Specificare ulteriori set di definizioni per l'ispezione del traffico di rete</span><span class="sxs-lookup"><span data-stu-id="b4f68-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4f68-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b4f68-105">**Applies to:**</span></span>

- [<span data-ttu-id="b4f68-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b4f68-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b4f68-107">È possibile specificare ulteriori set di definizioni per l'ispezione del traffico di rete utilizzando Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b4f68-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="b4f68-108">Utilizzare Criteri di gruppo per specificare ulteriori set di definizioni per l'ispezione del traffico di rete</span><span class="sxs-lookup"><span data-stu-id="b4f68-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="b4f68-109">Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="b4f68-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="b4f68-110">Vai a **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**.</span><span class="sxs-lookup"><span data-stu-id="b4f68-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="b4f68-111">Selezionare **Specificare ulteriori set di definizioni per l'ispezione del traffico di rete.**</span><span class="sxs-lookup"><span data-stu-id="b4f68-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="b4f68-112">Per impostazione predefinita, questo criterio è impostato su **Non configurato**.</span><span class="sxs-lookup"><span data-stu-id="b4f68-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="b4f68-113">Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**</span><span class="sxs-lookup"><span data-stu-id="b4f68-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="b4f68-114">Selezionare **Abilitato** e quindi nella **sezione Opzioni** selezionare **Mostra...**.</span><span class="sxs-lookup"><span data-stu-id="b4f68-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="b4f68-115">Aggiungere voci all'elenco e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="b4f68-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="b4f68-116">Ogni voce deve essere elencata come coppia nome-valore, dove il nome è una rappresentazione di stringa di un GUID del set di definizioni.</span><span class="sxs-lookup"><span data-stu-id="b4f68-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="b4f68-117">Ad esempio, il GUID del set di definizioni per abilitare l'intelligence di sicurezza di test è definito come: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="b4f68-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="b4f68-118">Il valore non viene utilizzato, pertanto è consigliabile impostarlo su `0` .</span><span class="sxs-lookup"><span data-stu-id="b4f68-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="b4f68-119">Selezionare **OK** e quindi distribuire l'oggetto Criteri di gruppo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b4f68-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="b4f68-120">Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="b4f68-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="b4f68-121">Si usano oggetti Criteri di gruppo in locale?</span><span class="sxs-lookup"><span data-stu-id="b4f68-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="b4f68-122">Scopri come traducono nel cloud.</span><span class="sxs-lookup"><span data-stu-id="b4f68-122">See how they translate in the cloud.</span></span> <span data-ttu-id="b4f68-123">Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima .</span><span class="sxs-lookup"><span data-stu-id="b4f68-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="b4f68-124">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b4f68-124">Related articles</span></span>

- [<span data-ttu-id="b4f68-125">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b4f68-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="b4f68-126">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="b4f68-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="b4f68-127">Come creare e distribuire criteri antimalware: servizio di protezione cloud</span><span class="sxs-lookup"><span data-stu-id="b4f68-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)