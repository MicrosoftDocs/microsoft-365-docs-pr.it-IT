---
title: Specificare il livello di protezione fornito dal cloud per Microsoft Defender Antivirus
description: Imposta il livello di protezione fornito dal cloud per Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, sicurezza, defender, cloud, aggressività, livello di protezione
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a0c73c8dd341c4940e3eddd4ede75240e57502d6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764122"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="b5ef3-104">Specificare il livello di protezione fornito dal cloud</span><span class="sxs-lookup"><span data-stu-id="b5ef3-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b5ef3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b5ef3-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5ef3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b5ef3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b5ef3-107">Puoi specificare il livello di protezione offerta dal cloud da Microsoft Defender Antivirus usando Microsoft Endpoint Manager (scelta consigliata) o Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="b5ef3-108">La protezione cloud non è semplicemente la protezione per i file archiviati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="b5ef3-109">Il servizio cloud Microsoft Defender Antivirus è un meccanismo per fornire una protezione aggiornata alla rete e ai dispositivi (denominati anche endpoint).</span><span class="sxs-lookup"><span data-stu-id="b5ef3-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="b5ef3-110">La protezione cloud con Microsoft Defender Antivirus usa risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di intelligence per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="b5ef3-111">Microsoft Intune e Microsoft Endpoint Manager fanno ora parte di [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="b5ef3-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="b5ef3-112">Usare Microsoft Endpoint Manager per specificare il livello di protezione fornito dal cloud</span><span class="sxs-lookup"><span data-stu-id="b5ef3-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="b5ef3-113">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="b5ef3-114">Scegliere **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="b5ef3-115">Selezionare un profilo antivirus.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-115">Select an antivirus profile.</span></span> <span data-ttu-id="b5ef3-116">Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="b5ef3-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="b5ef3-117">Selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-117">Select **Properties**.</span></span> <span data-ttu-id="b5ef3-118">Quindi, accanto a **Impostazioni di configurazione** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="b5ef3-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="b5ef3-119">Espandere **Protezione cloud** e  quindi selezionare una delle opzioni seguenti nell'elenco Livello di protezione fornito dal cloud:</span><span class="sxs-lookup"><span data-stu-id="b5ef3-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="b5ef3-120">**High**: applica un livello elevato di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="b5ef3-121">**High plus**: usa **il livello High** e applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client).</span><span class="sxs-lookup"><span data-stu-id="b5ef3-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="b5ef3-122">**Tolleranza zero:** blocca tutti i file eseguibili sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="b5ef3-123">Scegliere **Rivedi e salva** e quindi Salva. </span><span class="sxs-lookup"><span data-stu-id="b5ef3-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="b5ef3-124">Serve aiuto?</span><span class="sxs-lookup"><span data-stu-id="b5ef3-124">Need some help?</span></span> <span data-ttu-id="b5ef3-125">Vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5ef3-125">See the following resources:</span></span>
> - [<span data-ttu-id="b5ef3-126">Configurare Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="b5ef3-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="b5ef3-127">Aggiungere le impostazioni di endpoint protection in Intune</span><span class="sxs-lookup"><span data-stu-id="b5ef3-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="b5ef3-128">Usare Criteri di gruppo per specificare il livello di protezione fornito dal cloud</span><span class="sxs-lookup"><span data-stu-id="b5ef3-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="b5ef3-129">Nel computer di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="b5ef3-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="b5ef3-130">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="b5ef3-131">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**  >  **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="b5ef3-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="b5ef3-132">Espandere l'albero **fino a Componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **MpEngine.**</span><span class="sxs-lookup"><span data-stu-id="b5ef3-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="b5ef3-133">Fare doppio clic **sull'impostazione Seleziona** livello di protezione cloud e impostarla su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="b5ef3-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="b5ef3-134">Selezionare il livello di protezione:</span><span class="sxs-lookup"><span data-stu-id="b5ef3-134">Select the level of protection:</span></span>
    - <span data-ttu-id="b5ef3-135">**Il livello di blocco predefinito** offre un rilevamento sicuro senza aumentare il rischio di rilevare file legittimi.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="b5ef3-136">**Il livello di blocco moderato** fornisce un livello moderato solo per i rilevamenti di probabilità elevata</span><span class="sxs-lookup"><span data-stu-id="b5ef3-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="b5ef3-137">**Un livello di blocco elevato** applica un livello elevato di rilevamento ottimizzando le prestazioni del client (ma può anche offrire maggiori probabilità di falsi positivi).</span><span class="sxs-lookup"><span data-stu-id="b5ef3-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="b5ef3-138">**Il livello alto e di** blocco applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client e aumentare la probabilità di falsi positivi).</span><span class="sxs-lookup"><span data-stu-id="b5ef3-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="b5ef3-139">**Il livello di blocco della tolleranza zero** blocca tutti i file eseguibili sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="b5ef3-140">Sebbene improbabile, l'impostazione di questa opzione su **High** o **High +** potrebbe causare il rilevamento di alcuni file legittimi (anche se si avrà la possibilità di sbloccare o contestare tale rilevamento).</span><span class="sxs-lookup"><span data-stu-id="b5ef3-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="b5ef3-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-141">Click **OK**.</span></span>

7. <span data-ttu-id="b5ef3-142">Distribuire l'oggetto Criteri di gruppo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="b5ef3-143">Vedere [Console Gestione Criteri di gruppo](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="b5ef3-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="b5ef3-144">Si usano oggetti Criteri di gruppo in locale?</span><span class="sxs-lookup"><span data-stu-id="b5ef3-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="b5ef3-145">Scopri come traducono nel cloud.</span><span class="sxs-lookup"><span data-stu-id="b5ef3-145">See how they translate in the cloud.</span></span> <span data-ttu-id="b5ef3-146">Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima .</span><span class="sxs-lookup"><span data-stu-id="b5ef3-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="b5ef3-147">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b5ef3-147">Related articles</span></span>

- [<span data-ttu-id="b5ef3-148">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5ef3-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b5ef3-149">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="b5ef3-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b5ef3-150">Come creare e distribuire criteri antimalware: servizio di protezione cloud</span><span class="sxs-lookup"><span data-stu-id="b5ef3-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)