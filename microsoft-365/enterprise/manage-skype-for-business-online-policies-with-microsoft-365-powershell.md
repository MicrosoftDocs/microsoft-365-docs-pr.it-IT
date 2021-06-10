---
title: Gestire i criteri di Skype for Business Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: "Riepilogo: utilizzare PowerShell per gestire le proprietà dell'account utente Skype for Business Online con i criteri."
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916703"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="f2225-103">Gestire i criteri di Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2225-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="f2225-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="f2225-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f2225-105">Per gestire molte proprietà dell'account utente per Skype for Business Online, è necessario specificarle come proprietà dei criteri con PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2225-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f2225-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f2225-106">Before you begin</span></span>

<span data-ttu-id="f2225-107">Utilizzare queste istruzioni per ottenere la configurazione che consenta di eseguire i comandi (ignorare i passaggi già completati):</span><span class="sxs-lookup"><span data-stu-id="f2225-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="f2225-108">Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="f2225-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f2225-109">Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="f2225-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="f2225-110">Installare il [modulo di PowerShell di Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="f2225-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="f2225-111">Aprire il prompt dei comandi Windows PowerShell ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f2225-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="f2225-112">Quando richiesto, immettere il nome e la password dell'account Administrator di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="f2225-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="f2225-113">Gestione dei criteri dell’account utente</span><span class="sxs-lookup"><span data-stu-id="f2225-113">Manage user account policies</span></span>

<span data-ttu-id="f2225-p102">Molte proprietà dell'account utente di Skype for Business online sono configurate utilizzando criteri. I criteri consistono in una raccolta di impostazioni che possono essere applicate a uno o più utenti. Per esaminare la configurazione del criterio, è possibile eseguire il comando di esempio riportato per il criterio FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="f2225-p102">Many Skype for Business Online user account properties are configured by using policies. Policies are simply collections of settings that can be applied to one or more users. To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="f2225-117">Verrà restituito un elemento analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="f2225-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="f2225-118">Nell'esempio riportato, i valori compresi nei criteri determinano le operazioni di comunicazione con utenti federati che Alex può davvero effettuare o meno.</span><span class="sxs-lookup"><span data-stu-id="f2225-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="f2225-119">Ad esempio, la proprietà EnableOutsideAccess deve essere impostata su True affinché un utente possa comunicare con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2225-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="f2225-120">Si noti che questa proprietà non viene visualizzata nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f2225-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f2225-121">Al contrario, la proprietà viene impostata automaticamente su True o False in base alle altre selezioni effettuate.</span><span class="sxs-lookup"><span data-stu-id="f2225-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="f2225-122">Le altre due proprietà di interesse sono:</span><span class="sxs-lookup"><span data-stu-id="f2225-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="f2225-123">**EnableFederationAccess** indica se l'utente può comunicare con utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="f2225-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="f2225-124">**EnablePublicCloudAccess** indica se l'utente può comunicare con gli utenti di Windows Live.</span><span class="sxs-lookup"><span data-stu-id="f2225-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="f2225-p104">Pertanto, non è possibile modificare proprietà correlate alla federazione negli account utente (ad esempio, **Set-CsUser -EnableFederationAccess $True**). Al contrario, a un account viene assegnato un criterio di accesso esterno che dispone dei valori di proprietà desiderati e preconfigurati. Se si desidera che un utente sia in grado di comunicare con gli utenti federati e con gli utenti di Windows Live, è necessario assegnare all'account utente un criterio che consenta questo tipo di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="f2225-p104">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**). Instead, you assign an account an external access policy that has the desired property values preconfigured. If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="f2225-128">Se si desidera sapere se qualche utente è in grado di comunicare con utenti esterni all'organizzazione, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f2225-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="f2225-129">Determinare quali criteri di accesso esterno sono stati assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="f2225-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="f2225-130">Determinare le funzionalità che sono consentite o meno dal criterio.</span><span class="sxs-lookup"><span data-stu-id="f2225-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="f2225-131">Ad esempio, è possibile utilizzare il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f2225-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="f2225-132">Questo comando consente di individuare il criterio assegnato all'utente, quindi di individuare le funzionalità abilitate o disabilitate all'interno del criterio.</span><span class="sxs-lookup"><span data-stu-id="f2225-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="f2225-133">Per gestire Skype for Business criteri online con PowerShell, vedere i cmdlet per:</span><span class="sxs-lookup"><span data-stu-id="f2225-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="f2225-134">[Criteri client](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f2225-134">[Client policy](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="f2225-135">[Criteri conferenza](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f2225-135">[Conferencing policy](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="f2225-136">[Criteri per dispositivi mobili](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f2225-136">[Mobile policy](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="f2225-137">[Criteri di segreteria telefonica online](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f2225-137">[Online Voicemail policy](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="f2225-138">[Criteri di routing vocale](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f2225-138">[Voice Routing policy](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="f2225-p105">Un dial plan di Skype for Business online rappresenta un criterio in tutti i suoi aspetti, con la sola eccezione del nome. Il nome "dial plan" è stato scelto al posto di "criteri di composizione" al fine di essere compatibile con Office Communications Server e con Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2225-p105">A Skype for Business Online dial plan is a policy in every respect except the name. The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="f2225-141">Ad esempio, per esaminare tutti i criteri vocali che possono essere utilizzati, eseguire tale comando:</span><span class="sxs-lookup"><span data-stu-id="f2225-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="f2225-p106">Viene restituito un elenco di tutti i criteri vocali disponibili per l'utente. Tuttavia, tenere presente che non tutti i criteri possono essere assegnati a qualsiasi utente. Ciò si verifica a causa di vari limiti che riguardano le licenze e la posizione geografica. (Il "[percorso di utilizzo](/previous-versions/azure/dn194136(v=azure.100))"). Se si desidera conoscere i criteri di accesso esterno e i criteri di conferenza che possono essere assegnati a un utente particolare, utilizzare comandi analoghi ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2225-p106">That returns a list of all the voice policies available to you. Keep in mind, however, that not all policies can be assigned to all users. This is due to various restrictions involving licensing and geographic location. (The so-called "[usage location](/previous-versions/azure/dn194136(v=azure.100)).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="f2225-p107">Il parametro ApplicableTo limita i dati restituiti ai criteri che possono essere assegnati a specifici utenti (ad esempio, Alex Darrow). A seconda dei limiti relativi alle licenze o al percorso di utilizzo, potrebbe rappresentare un sottogruppo di tutti i criteri disponibili.</span><span class="sxs-lookup"><span data-stu-id="f2225-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="f2225-148">In alcuni casi, le proprietà dei criteri non vengono utilizzate con Microsoft 365, mentre altre possono essere gestite solo dal personale di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2225-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="f2225-p108">Con Skype for Business online, gli utenti devono essere gestiti da un criterio di qualche tipo. Se una proprietà correlata a criteri validi è vuota, significa che l'utente in questione viene gestito da un criterio globale, ovvero un criterio che viene applicato automaticamente a un utente a meno che non venga specificamente assegnato un criterio per utente. Poiché un criterio client per un account utente non è disponibile nell'elenco, viene gestito dal criterio globale. È possibile determinare il criterio client globale con questo comando:</span><span class="sxs-lookup"><span data-stu-id="f2225-p108">With Skype for Business Online, users must be managed by a policy of some kind. If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy. Because we don't see a client policy listed for a user account, it is managed by the global policy. You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="f2225-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2225-153">See also</span></span>

[<span data-ttu-id="f2225-154">Gestire Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2225-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f2225-155">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2225-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f2225-156">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2225-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)