---
title: Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: informazioni aggiuntive sui servizi per il passaggio da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a servizi di Office 365 nella nuova area datacenter tedesca.'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551954"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="c37e0-103">Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c37e0-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c37e0-104">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="c37e0-104">Frequently asked questions</span></span>

<span data-ttu-id="c37e0-105">**Come si fa a sapere se la mia organizzazione è intaccata?**</span><span class="sxs-lookup"><span data-stu-id="c37e0-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="c37e0-106">Gli amministratori devono verificare `https://portal.microsoftazure.de` se dispongono di dispositivi registrati.</span><span class="sxs-lookup"><span data-stu-id="c37e0-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="c37e0-107">Se nell'organizzazione sono presenti dispositivi registrati, si è coinvolti.</span><span class="sxs-lookup"><span data-stu-id="c37e0-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="c37e0-108">**Qual è l'impatto sui miei utenti?**</span><span class="sxs-lookup"><span data-stu-id="c37e0-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="c37e0-109">Gli utenti di un dispositivo registrato non saranno più in grado di accedere dopo che la migrazione entrerà nella fase di completamento della migrazione di [Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="c37e0-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="c37e0-110">Verificare che tutti i dispositivi siano registrati con l'endpoint globale prima che l'organizzazione sia disconnessa da Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="c37e0-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="c37e0-111">**Quando gli utenti eseguono di nuovo la registrazione dei propri dispositivi?**</span><span class="sxs-lookup"><span data-stu-id="c37e0-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="c37e0-112">È fondamentale per il successo che si annulla la registrazione e la registrazione dei dispositivi solo durante la fase di migrazione [separata da Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="c37e0-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c37e0-113">**Come ripristinare lo stato del dispositivo dopo la migrazione**</span><span class="sxs-lookup"><span data-stu-id="c37e0-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="c37e0-114">Per i dispositivi Windows ibridi AD-joined e di proprietà aziendale che sono registrati con Azure AD, gli amministratori potranno gestire la migrazione di questi dispositivi tramite flussi di lavoro in modalità remota che annullano la registrazione degli Stati obsoleti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="c37e0-115">Per tutti gli altri dispositivi, inclusi i dispositivi personali di Windows registrati in Azure Active Directory, è necessario che l'utente finale esegua manualmente questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c37e0-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="c37e0-116">Per i dispositivi di Azure AD-join, gli utenti devono disporre di un account di amministratore locale per annullare la registrazione e quindi registrare di nuovo i propri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c37e0-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="c37e0-117">Microsoft pubblicherà istruzioni su come ripristinare correttamente lo stato del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="c37e0-118">**Come si può verificare che tutti i dispositivi personali siano registrati nel cloud pubblico?**</span><span class="sxs-lookup"><span data-stu-id="c37e0-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="c37e0-119">Per controllare se i dispositivi sono registrati nel cloud pubblico, è necessario esportare e scaricare l'elenco dei dispositivi dal portale di Azure AD in un foglio di calcolo di Excel.</span><span class="sxs-lookup"><span data-stu-id="c37e0-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="c37e0-120">Filtrare quindi i dispositivi registrati (tramite la colonna _registeredTime_ ) dopo la fase [di migrazione separata da Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="c37e0-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c37e0-121">La registrazione del dispositivo viene disattivata dopo la migrazione del tenant e non può essere abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="c37e0-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="c37e0-122">Se Intune non viene utilizzato, accedere all'abbonamento ed eseguire questo comando per riattivare l'opzione:</span><span class="sxs-lookup"><span data-stu-id="c37e0-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="c37e0-123">Join di Windows Hybrid Azure AD</span><span class="sxs-lookup"><span data-stu-id="c37e0-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="c37e0-124">Giù-livello di Windows</span><span class="sxs-lookup"><span data-stu-id="c37e0-124">Windows down-level</span></span>

<span data-ttu-id="c37e0-125">I dispositivi Windows di _livello inferiore_ sono dispositivi Windows che attualmente eseguono versioni precedenti di Windows, ad esempio Windows 8,1 o Windows 7, o che eseguono versioni di Windows Server precedenti a 2019 e 2016.</span><span class="sxs-lookup"><span data-stu-id="c37e0-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="c37e0-126">Se tali dispositivi sono stati registrati prima, sarà necessario annullare la registrazione e registrare di nuovo tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c37e0-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="c37e0-127">Per determinare se un dispositivo Windows di livello basso è stato precedentemente aggiunto ad Azure AD, utilizzare il seguente comando nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c37e0-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="c37e0-128">Se il dispositivo è stato precedentemente aggiunto ad Azure AD e se il dispositivo dispone di connettività di rete per gli endpoint di Azure AD globali, verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="c37e0-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="c37e0-129">I dispositivi coinvolti avranno lo "stato del dispositivo" con il valore "Unknown".</span><span class="sxs-lookup"><span data-stu-id="c37e0-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="c37e0-130">Se l'output è "dispositivo non aggiunto" o il cui valore "stato del dispositivo" è "OK", ignorare le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c37e0-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="c37e0-131">Solo per i dispositivi che dimostrano che il dispositivo è Unito (in virtù di deviceId, identificazione personale e così via) e il cui valore "stato del dispositivo" è "Unknown", gli amministratori devono eseguire il seguente comando nel contesto di un utente di dominio che esegue l'accesso a un dispositivo di livello più basso:</span><span class="sxs-lookup"><span data-stu-id="c37e0-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="c37e0-132">Il comando precedente deve essere eseguito solo una volta per ogni utente di dominio che accede al dispositivo Windows di livello più basso.</span><span class="sxs-lookup"><span data-stu-id="c37e0-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="c37e0-133">Questo comando deve essere eseguito nel contesto dell'accesso da parte dell'utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="c37e0-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="c37e0-134">È necessario fare attenzione a non eseguire questo comando quando l'utente successivamente accede.</span><span class="sxs-lookup"><span data-stu-id="c37e0-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="c37e0-135">Quando viene eseguito il comando precedente, verrà cancellato lo stato aggiunto del computer ibrido di Azure AD-join locale per l'utente che ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c37e0-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="c37e0-136">E, se il computer è ancora configurato per essere ibrido di Azure AD – aggiunto nel tenant, tenterà di unirsi quando l'utente si riconnette.</span><span class="sxs-lookup"><span data-stu-id="c37e0-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="c37e0-137">Corrente di Windows</span><span class="sxs-lookup"><span data-stu-id="c37e0-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="c37e0-138">Separazione</span><span class="sxs-lookup"><span data-stu-id="c37e0-138">Unjoin</span></span>

<span data-ttu-id="c37e0-139">Per determinare se il dispositivo Windows 10 è stato precedentemente aggiunto ad Azure AD, eseguire il comando riportato di seguito nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c37e0-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c37e0-140">Se il dispositivo è ibrido di Azure AD-join, l'amministratore vedrebbe l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="c37e0-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="c37e0-141">Se l'output è "AzureAdJoined: No", ignorare le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c37e0-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="c37e0-142">Solo per i dispositivi che mostrano che il dispositivo è aggiunto ad Azure AD, eseguire il comando seguente come amministratore per rimuovere lo stato unito del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c37e0-143">Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo sul dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="c37e0-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="c37e0-144">Ibrido AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="c37e0-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="c37e0-145">Il dispositivo viene automaticamente aggiunto ad Azure AD senza l'intervento di un utente o di un amministratore purché il dispositivo disponga di connettività di rete per gli endpoint di Azure AD globali.</span><span class="sxs-lookup"><span data-stu-id="c37e0-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="c37e0-146">Join di Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="c37e0-146">Windows Azure AD Join</span></span>

### <a name="unjoin"></a><span data-ttu-id="c37e0-147">Separazione</span><span class="sxs-lookup"><span data-stu-id="c37e0-147">Unjoin</span></span>

<span data-ttu-id="c37e0-148">Per determinare se il dispositivo Windows 10 è stato precedentemente aggiunto ad Azure AD, è possibile che l'utente o l'amministratore esegua il seguente comando nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c37e0-148">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c37e0-149">Se il dispositivo è aggiunto ad Azure AD, l'utente o l'amministratore vedrebbe l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="c37e0-149">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="c37e0-150">Se l'output è "AzureAdJoined: NO", ignorare le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c37e0-150">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="c37e0-151">Utente: se il dispositivo è collegato a Azure AD, un utente può disconnettersi dal dispositivo dalle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c37e0-151">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="c37e0-152">Verificare che sia presente un account amministratore locale nel dispositivo prima di disconnettersi dal dispositivo da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c37e0-152">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c37e0-153">L'account di amministratore locale è necessario per eseguire l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-153">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="c37e0-154">Amministratore: se l'amministratore dell'organizzazione vuole disgiungere i dispositivi degli utenti che dispongono di Azure AD-join, è possibile eseguire il comando seguente in ogni dispositivo utilizzando un meccanismo, ad esempio criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-154">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="c37e0-155">L'amministratore deve verificare che sia presente un account amministratore locale nel dispositivo prima di disconnettersi dal dispositivo da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c37e0-155">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c37e0-156">L'account di amministratore locale è necessario per eseguire l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-156">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c37e0-157">Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo sul dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="c37e0-157">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="c37e0-158">Join/ri-registrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c37e0-158">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="c37e0-159">L'utente può aggiungere il dispositivo ad Azure AD dalle impostazioni di Windows: **impostazioni > account > accedere al lavoro o all'Istituto di istruzione > Connect**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-159">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="c37e0-160">Windows Azure AD registrato (società di proprietà)</span><span class="sxs-lookup"><span data-stu-id="c37e0-160">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="c37e0-161">Per determinare se il dispositivo Windows 10 è Azure AD – registrato, eseguire il comando riportato di seguito nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c37e0-161">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c37e0-162">Se il dispositivo è registrato con Azure AD, verrà visualizzato il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c37e0-162">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="c37e0-163">Per rimuovere l'account registrato AD Azure AD esistente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c37e0-163">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="c37e0-164">Per rimuovere l'account registrato di Azure AD nel dispositivo, utilizzare CleanupWPJ, uno strumento che è possibile scaricare da qui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="c37e0-164">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="c37e0-165">Estrarre il file ZIP ed eseguire **WPJCleanup. cmd**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-165">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="c37e0-166">Questo strumento avvierà il file eseguibile a destra in base alla versione di Windows nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-166">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="c37e0-167">Utilizzando un meccanismo come criteri di gruppo, l'amministratore può eseguire il comando nel dispositivo nel contesto di qualsiasi utente che ha eseguito l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-167">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="c37e0-168">Per disabilitare le richieste di gestione account Web per la registrazione del dispositivo in Azure AD, aggiungere questo valore del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="c37e0-168">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="c37e0-169">Località: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="c37e0-169">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="c37e0-170">Tipo: DWORD (32 bit)</span><span class="sxs-lookup"><span data-stu-id="c37e0-170">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="c37e0-171">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="c37e0-171">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="c37e0-172">Dati valore: 1</span><span class="sxs-lookup"><span data-stu-id="c37e0-172">Value data: 1</span></span>

<span data-ttu-id="c37e0-173">La presenza di questo valore del registro di sistema deve bloccare il join del posto di lavoro e impedire agli utenti di visualizzare i prompt per aggiungere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-173">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="c37e0-174">Android</span><span class="sxs-lookup"><span data-stu-id="c37e0-174">Android</span></span>

<span data-ttu-id="c37e0-175">Per Android, gli utenti dovranno annullare la registrazione e registrare di nuovo i propri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c37e0-175">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="c37e0-176">Questa operazione può essere eseguita tramite l'app Microsoft Authenticator o l'app portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c37e0-176">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="c37e0-177">Dall'app Microsoft Authenticator, gli utenti possono accedere alle **impostazioni > registrazione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-177">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="c37e0-178">Da lì gli utenti possono annullare la registrazione e registrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-178">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="c37e0-179">Dal portale aziendale, gli utenti possono accedere alla scheda **dispositivi** e rimuovere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-179">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="c37e0-180">Successivamente, eseguire di nuovo la registrazione del dispositivo tramite il portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c37e0-180">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="c37e0-181">Gli utenti possono anche annullare la registrazione e ripetere la registrazione rimuovendo l'account dalla pagina Impostazioni account e quindi aggiungendo di nuovo l'account di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c37e0-181">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="c37e0-182">Per annullare la registrazione e registrare di nuovo il dispositivo su Android utilizzando l'app Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="c37e0-182">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="c37e0-183">Aprire l'app Microsoft Authenticator e passare a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-183">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="c37e0-184">Selezionare **registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-184">Select **Device registration**.</span></span>
3.  <span data-ttu-id="c37e0-185">Annullare la registrazione del dispositivo selezionando **Annulla registrazione**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-185">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="c37e0-186">Per la **registrazione dei dispositivi**, registrare di nuovo il dispositivo digitando l'indirizzo di posta elettronica e quindi selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-186">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="c37e0-187">Per annullare la registrazione e registrare di nuovo un dispositivo Android con la pagina delle impostazioni di Android:</span><span class="sxs-lookup"><span data-stu-id="c37e0-187">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="c37e0-188">Aprire **le impostazioni del dispositivo** e passare a **account**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-188">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="c37e0-189">Selezionare l'account di lavoro che si desidera registrare di nuovo e selezionare **Rimuovi account**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-189">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="c37e0-190">Dopo la rimozione dell'account, selezionare Aggiungi account > account di **lavoro** dalla pagina **account** .</span><span class="sxs-lookup"><span data-stu-id="c37e0-190">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="c37e0-191">Per **join sul posto di lavoro**, digitare l'indirizzo di posta elettronica e selezionare **join** per completare la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-191">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="c37e0-192">Per annullare la registrazione e registrare di nuovo il dispositivo su Android dal portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="c37e0-192">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="c37e0-193">Avviare il portale aziendale e passare alla scheda **dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="c37e0-193">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="c37e0-194">Selezionare il dispositivo per visualizzare i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-194">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="c37e0-195">Dal menu ellissi (tre puntini), selezionare **Rimuovi dispositivo** e completare la rimozione confermando la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-195">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="c37e0-196">Ora è necessario essere disconnessi dall'app portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c37e0-196">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="c37e0-197">Selezionare **Accedi** per registrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-197">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="c37e0-198">Per ulteriori informazioni sulle azioni necessarie durante la fase di migrazione di questo carico di lavoro o impatto su amministrazione o utilizzo, consultare le informazioni su Azure Active Directory in [ulteriori informazioni generali per la migrazione da Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="c37e0-198">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="c37e0-199">iOS</span><span class="sxs-lookup"><span data-stu-id="c37e0-199">iOS</span></span>

<span data-ttu-id="c37e0-200">Nei dispositivi iOS, un utente dovrà rimuovere manualmente qualsiasi account memorizzato nella cache da Microsoft Authenticator, annullare la registrazione del dispositivo e disconnettersi da tutte le app native del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-200">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c37e0-201">Passaggio 1: se presente, rimuovere l'account dall'app Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c37e0-201">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c37e0-202">Toccare l'account nell'app Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c37e0-202">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="c37e0-203">Toccare l'icona **Impostazioni** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="c37e0-203">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="c37e0-204">Se l'icona **Impostazioni** non è visualizzata, potrebbe non essere utilizzata la versione più recente di Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c37e0-204">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="c37e0-205">Toccare il pulsante **Rimuovi account** .</span><span class="sxs-lookup"><span data-stu-id="c37e0-205">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="c37e0-206">Toccare **tutte le app nel dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-206">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c37e0-207">Passaggio 2: annullare la registrazione del dispositivo dall'app Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c37e0-207">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c37e0-208">Toccare l'icona del menu nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="c37e0-208">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="c37e0-209">Toccare **Impostazioni** e quindi **registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c37e0-209">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="c37e0-210">Se l'account è visualizzato, toccare **Annulla registrazione dispositivo** e **continuare** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-210">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="c37e0-211">Non si dovrebbe vedere nessun account dopo.</span><span class="sxs-lookup"><span data-stu-id="c37e0-211">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="c37e0-212">Passaggio 3: disconnettersi da singole app se necessario</span><span class="sxs-lookup"><span data-stu-id="c37e0-212">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="c37e0-213">Gli utenti possono accedere a singole app come Outlook, teams e OneDrive e rimuovere gli account da tali app.</span><span class="sxs-lookup"><span data-stu-id="c37e0-213">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="c37e0-214">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c37e0-214">More information</span></span>

<span data-ttu-id="c37e0-215">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="c37e0-215">Getting started:</span></span>

- [<span data-ttu-id="c37e0-216">Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco</span><span class="sxs-lookup"><span data-stu-id="c37e0-216">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="c37e0-217">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c37e0-217">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="c37e0-218">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="c37e0-218">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="c37e0-219">Esperienza del cliente durante la migrazione</span><span class="sxs-lookup"><span data-stu-id="c37e0-219">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="c37e0-220">Spostamento attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="c37e0-220">Moving through the transition:</span></span>

- [<span data-ttu-id="c37e0-221">Operazioni e impatto delle fasi di migrazione</span><span class="sxs-lookup"><span data-stu-id="c37e0-221">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="c37e0-222">Ulteriore prelavoro</span><span class="sxs-lookup"><span data-stu-id="c37e0-222">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="c37e0-223">Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="c37e0-223">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="c37e0-224">App Cloud:</span><span class="sxs-lookup"><span data-stu-id="c37e0-224">Cloud apps:</span></span>

- [<span data-ttu-id="c37e0-225">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c37e0-225">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="c37e0-226">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="c37e0-226">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="c37e0-227">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c37e0-227">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
