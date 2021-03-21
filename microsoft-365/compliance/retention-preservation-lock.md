---
title: Usare la protezione dell'archiviazione per limitare le modifiche ai criteri di conservazione e ai criteri per le etichette di conservazione
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Usare la protezione dell'archiviazione con i criteri di conservazione e i criteri delle etichette di conservazione per soddisfare i requisiti normativi e proteggersi dagli amministratori non autorizzati.
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922530"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="4c3f2-103">Usare la protezione dell'archiviazione per limitare le modifiche ai criteri di conservazione e ai criteri per le etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="4c3f2-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="4c3f2-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="4c3f2-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="4c3f2-105">La protezione dell'archiviazione blocca i criteri di conservazione o i criteri per le etichette di conservazione in modo che nessuno, incluso l'amministratore, possa disattivarli, eliminarli o renderli meno restrittivi.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="4c3f2-106">Questa configurazione potrebbe essere necessaria per i requisiti normativi e consente di proteggersi da amministratori non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="4c3f2-107">Quando i criteri di conservazione sono bloccati:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-107">When a retention policy is locked:</span></span>

- <span data-ttu-id="4c3f2-108">Nessuno può disabilitare i criteri o eliminarli</span><span class="sxs-lookup"><span data-stu-id="4c3f2-108">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="4c3f2-109">È possibile aggiungere le posizioni, ma non rimuoverle</span><span class="sxs-lookup"><span data-stu-id="4c3f2-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="4c3f2-110">È possibile estendere un periodo di conservazione, ma non ridurlo</span><span class="sxs-lookup"><span data-stu-id="4c3f2-110">You can extend the retention period but not decrease it</span></span>

<span data-ttu-id="4c3f2-111">Quando i criteri per un’etichetta di conservazione sono bloccati:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-111">When a retention label policy is locked:</span></span>

- <span data-ttu-id="4c3f2-112">Nessuno può disabilitare i criteri o eliminarli</span><span class="sxs-lookup"><span data-stu-id="4c3f2-112">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="4c3f2-113">È possibile aggiungere le posizioni, ma non rimuoverle</span><span class="sxs-lookup"><span data-stu-id="4c3f2-113">Locations can be added but not removed</span></span>
- <span data-ttu-id="4c3f2-114">È possibile aggiungere le etichette, ma non rimuoverle</span><span class="sxs-lookup"><span data-stu-id="4c3f2-114">Labels can be added but not removed</span></span>

<span data-ttu-id="4c3f2-115">In sintesi, i criteri bloccati possono essere aumentati o estesi, ma non ridotti, disabilitati o disattivati.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-115">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c3f2-116">Prima di bloccare un criterio di conservazione o un criterio dell'etichetta di conservazione, è essenziale comprendere l'impatto dell'operazione e verificare se sia necessario all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-116">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="4c3f2-117">Ad esempio, potrebbe essere necessario per rispettare i requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-117">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="4c3f2-118">Dopo l'applicazione del blocco di conservazione, gli amministratori non potranno disabilitare o eliminare il criterio.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-118">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="4c3f2-119">Configurare la protezione dell'archiviazione dopo aver creato i [criteri di conservazione](create-retention-policies.md) o i criteri per le etichette di conservazione da [pubblicare ](create-apply-retention-labels.md) o [applicare automaticamente](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="4c3f2-119">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="4c3f2-120">Il blocco dei criteri dell’etichetta non impedisce a un amministratore di ridurre il periodo di conservazione in un'etichetta inclusa nei criteri bloccati.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-120">Locking a label policy doesn't prevent an administrator from reducing the retention period in a label that is included in the locked policy.</span></span> <span data-ttu-id="4c3f2-121">Questo requisito, insieme ad altre restrizioni, può essere soddisfatto quando si configura un'etichetta per contrassegnare gli elementi come [record normativi](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="4c3f2-121">That requirement, with other restrictions, can be met when you configure a label to mark items as a [regulatory record](records-management.md#records).</span></span>

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="4c3f2-122">Come bloccare i criteri di conservazione o i criteri per le etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="4c3f2-122">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="4c3f2-123">Se è necessario usare la protezione dell'archiviazione, occorre usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-123">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="4c3f2-124">Poiché gli amministratori non possono disabilitare o eliminare i criteri per la conservazione dopo l'applicazione della protezione dell’archiviazione, l'abilitazione di questa caratteristica non è disponibile nell'interfaccia utente per proteggerla dalla configurazione accidentale.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-124">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="4c3f2-125">Tutti i criteri per la conservazione e con qualsiasi configurazione supportano la protezione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-125">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="4c3f2-126">[Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c3f2-126">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="4c3f2-127">Trovare il nome del criterio da bloccare eseguendo [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="4c3f2-127">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="4c3f2-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-128">For example:</span></span>
    
   ![Elenco dei criteri di conservazione in PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="4c3f2-130">Per applicare la protezione dell’archiviazione al criterio, eseguire il cmdlet [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) con il nome del criterio e il parametro *RestrictiveRetention* impostato su true:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-130">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="4c3f2-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-131">For example:</span></span>
    
    ![Parametro RestrictiveRetention in PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="4c3f2-133">Quando viene richiesto, leggere e accettare le restrizioni disponibili in questa configurazione immettendo **Y**:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-133">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![Richiesta di conferma del blocco dei criteri di conservazione in PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="4c3f2-135">La protezione dell'archiviazione è ora inserita nei criteri.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-135">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="4c3f2-136">Per confermare, eseguire di nuovo `Get-RetentionCompliancePolicy`, ma specificare il nome del criterio e visualizzare i parametri dei criteri:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-136">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="4c3f2-137">Dovrebbe essere visualizzato **RestrictiveRetention** è impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="4c3f2-137">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="4c3f2-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c3f2-138">For example:</span></span>

![Criteri bloccati con tutti i parametri visualizzati in PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="4c3f2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c3f2-140">See also</span></span>

[<span data-ttu-id="4c3f2-141">Risorse che consentono di soddisfare i requisiti normativi per la governance delle informazioni e la gestione dei record</span><span class="sxs-lookup"><span data-stu-id="4c3f2-141">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)