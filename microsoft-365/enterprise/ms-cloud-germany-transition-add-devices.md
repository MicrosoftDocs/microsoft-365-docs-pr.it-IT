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
description: 'Riepilogo: informazioni aggiuntive sui dispositivi sui servizi quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a Office 365 servizi nella nuova area data center tedesca.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928157"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="7b21d-103">Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="7b21d-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7b21d-104">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="7b21d-104">Frequently asked questions</span></span>

<span data-ttu-id="7b21d-105">**Come è possibile sapere se l'organizzazione è interessata?**</span><span class="sxs-lookup"><span data-stu-id="7b21d-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="7b21d-106">Gli amministratori devono `https://portal.microsoftazure.de` controllare se hanno dispositivi registrati.</span><span class="sxs-lookup"><span data-stu-id="7b21d-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="7b21d-107">Se l'organizzazione ha dispositivi registrati, l'utente è interessato.</span><span class="sxs-lookup"><span data-stu-id="7b21d-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="7b21d-108">**Qual è l'impatto sugli utenti?**</span><span class="sxs-lookup"><span data-stu-id="7b21d-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="7b21d-109">Gli utenti di un dispositivo registrato non potranno più accedere dopo che la migrazione ha completato la fase di migrazione [di Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="7b21d-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="7b21d-110">Assicurati che tutti i dispositivi siano registrati con l'endpoint globale prima che l'organizzazione venga disconnessa da Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="7b21d-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="7b21d-111">**Quando gli utenti registrano di nuovo i propri dispositivi?**</span><span class="sxs-lookup"><span data-stu-id="7b21d-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="7b21d-112">È fondamentale annullare la registrazione e registrare di nuovo i dispositivi solo durante la fase di migrazione [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="7b21d-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="7b21d-113">**Come si ripristina lo stato del dispositivo dopo la migrazione?**</span><span class="sxs-lookup"><span data-stu-id="7b21d-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="7b21d-114">Per i dispositivi Windows ibridi aggiunti ad Azure AD e di proprietà dell'azienda registrati con Azure AD, gli amministratori saranno in grado di gestire la migrazione di questi dispositivi tramite flussi di lavoro attivati in remoto che annullano la registrazione degli stati dei dispositivi vecchi.</span><span class="sxs-lookup"><span data-stu-id="7b21d-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="7b21d-115">Per tutti gli altri dispositivi, inclusi Windows personali registrati in Azure AD, l'utente finale deve eseguire questi passaggi manualmente.</span><span class="sxs-lookup"><span data-stu-id="7b21d-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="7b21d-116">Per i dispositivi aggiunti ad Azure AD, gli utenti devono disporre di un account amministratore locale per annullare la registrazione e quindi registrare di nuovo i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7b21d-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="7b21d-117">Microsoft pubblicherà istruzioni su come ripristinare correttamente lo stato del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="7b21d-118">**Come è possibile sapere che tutti i dispositivi sono registrati nel cloud pubblico?**</span><span class="sxs-lookup"><span data-stu-id="7b21d-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="7b21d-119">Per verificare se i dispositivi sono registrati nel cloud pubblico, è consigliabile esportare e scaricare l'elenco dei dispositivi dal portale di Azure AD in un foglio di calcolo Excel dati.</span><span class="sxs-lookup"><span data-stu-id="7b21d-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="7b21d-120">Filtrare quindi i dispositivi registrati (utilizzando la colonna _registeredTime)_ dopo la fase di [migrazione Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="7b21d-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="7b21d-121">La registrazione del dispositivo viene disattivata dopo la migrazione del tenant e non può essere abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="7b21d-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="7b21d-122">Se Intune non viene usato, accedere alla sottoscrizione ed eseguire questo comando per riattivare l'opzione:</span><span class="sxs-lookup"><span data-stu-id="7b21d-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="7b21d-123">Aggiunta ad Azure AD ibrido</span><span class="sxs-lookup"><span data-stu-id="7b21d-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="7b21d-124">Windows livello inferiore</span><span class="sxs-lookup"><span data-stu-id="7b21d-124">Windows down-level</span></span>

<span data-ttu-id="7b21d-125">_Windows_ dispositivi di livello inferiore sono dispositivi Windows che attualmente eseguono versioni precedenti di Windows (ad esempio Windows 8.1 o Windows 7) o che eseguono versioni di Windows Server precedenti alla 2019 e alla 2016.</span><span class="sxs-lookup"><span data-stu-id="7b21d-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="7b21d-126">Se tali dispositivi sono stati registrati in precedenza, dovrai annullare la registrazione e registrare di nuovo tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7b21d-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="7b21d-127">Per determinare se Windows dispositivo di livello inferiore è stato aggiunto in precedenza ad Azure AD, usa il comando seguente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7b21d-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="7b21d-128">Se il dispositivo è stato aggiunto in precedenza ad Azure AD e se il dispositivo dispone di connettività di rete agli endpoint globali di Azure AD, verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7b21d-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="7b21d-129">I dispositivi interessati avranno lo "stato del dispositivo" con valore "Sconosciuto".</span><span class="sxs-lookup"><span data-stu-id="7b21d-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="7b21d-130">Se l'output è "Dispositivo non aggiunto" o il cui valore "Stato dispositivo" è "Ok", ignora le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7b21d-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="7b21d-131">Solo per i dispositivi che mostrano che il dispositivo è unito (in virtù di deviceId, identificazione personale e così via) e il cui valore "Stato dispositivo" è "Sconosciuto", gli amministratori devono eseguire il comando seguente nel contesto di un utente di dominio che accede su un dispositivo di livello inferiore di questo tipo:</span><span class="sxs-lookup"><span data-stu-id="7b21d-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="7b21d-132">Il comando precedente deve essere eseguito una sola volta per ogni utente di dominio che accede Windows dispositivo di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="7b21d-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="7b21d-133">Questo comando deve essere eseguito nel contesto dell'accesso dell'utente del dominio.</span><span class="sxs-lookup"><span data-stu-id="7b21d-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="7b21d-134">È necessario fare attenzione a non eseguire questo comando quando l'utente accede successivamente.</span><span class="sxs-lookup"><span data-stu-id="7b21d-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="7b21d-135">Quando viene eseguito il comando precedente, cancella lo stato aggiunto del computer locale aggiunto ad Azure AD ibrido per l'utente che ha eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7b21d-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="7b21d-136">Inoltre, se il computer è ancora configurato per essere aggiunto ad Azure AD ibrido nel tenant, tenterà di partecipare quando l'utente esegue di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7b21d-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="7b21d-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="7b21d-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="7b21d-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="7b21d-138">Unjoin</span></span>

<span data-ttu-id="7b21d-139">Per determinare se il Windows 10 è stato aggiunto in precedenza ad Azure AD, eseguire il comando seguente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7b21d-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="7b21d-140">Se il dispositivo è aggiunto ad Azure AD ibrido, l'amministratore visualizza l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7b21d-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="7b21d-141">Se l'output è "AzureAdJoined : No", ignorare le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7b21d-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="7b21d-142">Solo per i dispositivi che mostrano che il dispositivo è aggiunto ad Azure AD, esegui il comando seguente come amministratore per rimuovere lo stato aggiunto del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="7b21d-143">Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo nel Windows dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="7b21d-144">Hybrid AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="7b21d-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="7b21d-145">Il dispositivo viene aggiunto automaticamente ad Azure AD senza l'intervento dell'utente o dell'amministratore, purché il dispositivo abbia connettività di rete agli endpoint globali di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b21d-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="7b21d-146">Aggiunta ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b21d-146">Azure AD Join</span></span>

<span data-ttu-id="7b21d-147">**IMPORTANTE:** L'entità servizio intune verrà abilitata dopo la migrazione di commerce, che implica l'attivazione di Registrazione dispositivi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b21d-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="7b21d-148">Se è stata bloccata la registrazione dei dispositivi di Azure AD prima della migrazione, è necessario disabilitare l'entità servizio intune con PowerShell per disabilitare di nuovo La registrazione dei dispositivi di Azure AD con il portale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b21d-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="7b21d-149">È possibile disabilitare l'entità servizio intune con questo comando nella Azure Active Directory PowerShell per Graph modulo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="7b21d-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="7b21d-150">Unjoin</span></span>

<span data-ttu-id="7b21d-151">Per determinare se il Windows 10 è stato aggiunto in precedenza ad Azure AD, l'utente o l'amministratore può eseguire il comando seguente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7b21d-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="7b21d-152">Se il dispositivo viene aggiunto ad Azure AD, l'utente o l'amministratore visualizza l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7b21d-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="7b21d-153">Se l'output è "AzureAdJoined : NO", ignorare le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7b21d-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="7b21d-154">Utente: se il dispositivo è aggiunto ad Azure AD, un utente può scollegare il dispositivo dalle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7b21d-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="7b21d-155">Verificare che nel dispositivo sia presente un account amministratore locale prima di scollegare il dispositivo da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b21d-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="7b21d-156">L'account amministratore locale è necessario per accedere di nuovo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="7b21d-157">Amministratore: se l'amministratore dell'organizzazione vuole scollegare i dispositivi degli utenti aggiunti ad Azure AD, può farlo eseguendo il comando seguente in ognuno dei dispositivi usando un meccanismo come Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="7b21d-158">L'amministratore deve verificare che nel dispositivo sia presente un account amministratore locale prima di scollegare il dispositivo da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b21d-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="7b21d-159">L'account amministratore locale è necessario per accedere di nuovo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="7b21d-160">Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo nel Windows dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="7b21d-161">Aggiunta/ri-registrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b21d-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="7b21d-162">L'utente può aggiungere il dispositivo ad Azure AD da Windows impostazioni: Impostazioni > **Account > Access Work Or School > Connessione**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="7b21d-163">Azure AD registrato (di proprietà della società)</span><span class="sxs-lookup"><span data-stu-id="7b21d-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="7b21d-164">Per determinare se Windows 10 dispositivo è registrato con Azure AD, eseguire il comando seguente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7b21d-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="7b21d-165">Se il dispositivo è registrato in Azure AD, verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7b21d-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="7b21d-166">Per rimuovere l'account registrato con Azure AD esistente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7b21d-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="7b21d-167">Per rimuovere l'account registrato da Azure AD nel dispositivo, usa CleanupWPJ, uno strumento che puoi scaricare da qui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="7b21d-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="7b21d-168">Estrarre il file ZIP ed eseguire **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="7b21d-169">Questo strumento avvierà il file eseguibile giusto in base alla versione Windows nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="7b21d-170">Usando un meccanismo come Criteri di gruppo, l'amministratore può eseguire il comando nel dispositivo nel contesto di qualsiasi utente che ha eseguito l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="7b21d-171">Per disabilitare le istruzioni di Gestione account Web per registrare il dispositivo in Azure AD, aggiungere questo valore del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="7b21d-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="7b21d-172">Posizione: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="7b21d-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="7b21d-173">Tipo: DWORD (32 bit)</span><span class="sxs-lookup"><span data-stu-id="7b21d-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="7b21d-174">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="7b21d-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="7b21d-175">Dati valore: 1</span><span class="sxs-lookup"><span data-stu-id="7b21d-175">Value data: 1</span></span>

<span data-ttu-id="7b21d-176">La presenza di questo valore del Registro di sistema dovrebbe bloccare l'aggiunta all'area di lavoro e impedire agli utenti di visualizzare le istruzioni per l'aggiunta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="7b21d-177">Android</span><span class="sxs-lookup"><span data-stu-id="7b21d-177">Android</span></span>

<span data-ttu-id="7b21d-178">Per Android, gli utenti dovranno annullare la registrazione e registrare di nuovo i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7b21d-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="7b21d-179">Questa operazione può essere eseguita tramite l'app Microsoft Authenticator o l'app Portale aziendale app.</span><span class="sxs-lookup"><span data-stu-id="7b21d-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="7b21d-180">Dall'app Microsoft Authenticator, gli utenti possono passare a **Impostazioni > Registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="7b21d-181">Da qui gli utenti possono annullare la registrazione e registrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="7b21d-182">Dall'Portale aziendale, gli utenti possono passare alla **scheda** Dispositivi e rimuovere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="7b21d-183">Successivamente, registrare di nuovo il dispositivo usando Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="7b21d-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="7b21d-184">Gli utenti possono anche annullare la registrazione e registrare di nuovo rimuovendo l'account dalla pagina delle impostazioni dell'account e quindi aggiungendo di nuovo l'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="7b21d-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="7b21d-185">Per annullare la registrazione e registrare di nuovo il dispositivo in Android usando l'app Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="7b21d-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="7b21d-186">Apri l Microsoft Authenticator app e vai a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="7b21d-187">Selezionare **Registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="7b21d-188">Annulla la registrazione del dispositivo selezionando **Annulla registrazione**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="7b21d-189">Per **Registrazione dispositivo**, registrare di nuovo il dispositivo digitando l'indirizzo di posta elettronica e quindi selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="7b21d-190">Per annullare la registrazione e registrare di nuovo un dispositivo Android con la pagina Impostazioni Android:</span><span class="sxs-lookup"><span data-stu-id="7b21d-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="7b21d-191">Apri **Gestione Impostazioni** e vai a **Account**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="7b21d-192">Selezionare l'account aziendale che si desidera registrare di nuovo e selezionare **Rimuovi account**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="7b21d-193">Dopo aver rimosso l'account, nella **pagina Account** selezionare **Aggiungi account > Account di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="7b21d-194">Per **Workplace Join,** digita il tuo indirizzo e-mail e seleziona **Partecipa** per completare la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="7b21d-195">Per annullare la registrazione e registrare di nuovo il dispositivo su Android da Portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="7b21d-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="7b21d-196">Avvia Portale aziendale e vai alla **scheda** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7b21d-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="7b21d-197">Seleziona il dispositivo per visualizzare i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="7b21d-198">Dal menu con i puntini di sospensione (tre puntini), seleziona **Rimuovi dispositivo** e completa la rimozione confermando nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="7b21d-199">A questo punto dovresti essere disconnesso dall'app Portale aziendale app.</span><span class="sxs-lookup"><span data-stu-id="7b21d-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="7b21d-200">Seleziona **Accedi** per registrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="7b21d-201">Per ulteriori informazioni sulle azioni necessarie durante la fase di migrazione di questo carico di lavoro o sull'impatto sull'amministrazione o sull'utilizzo, consultare le informazioni su Azure Active Directory (Azure AD) in Ulteriori informazioni di Azure AD per la migrazione da [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="7b21d-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="7b21d-202">iOS</span><span class="sxs-lookup"><span data-stu-id="7b21d-202">iOS</span></span>

<span data-ttu-id="7b21d-203">Nei dispositivi iOS, un utente dovrà rimuovere manualmente gli account memorizzati nella cache dal Microsoft Authenticator, annullare la registrazione del dispositivo e disconnettersi da qualsiasi app nativa nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="7b21d-204">Passaggio 1: se presente, rimuovi l'account dall'app Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="7b21d-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="7b21d-205">Tocca l'account nell'app Microsoft Authenticator app.</span><span class="sxs-lookup"><span data-stu-id="7b21d-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="7b21d-206">Tocca **l'Impostazioni** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="7b21d-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="7b21d-207">Se non viene visualizzata **l'icona Impostazioni,** è possibile che non si utilizzi la versione più recente di Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="7b21d-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="7b21d-208">Tocca il **pulsante Rimuovi account.**</span><span class="sxs-lookup"><span data-stu-id="7b21d-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="7b21d-209">Toccare **Tutte le app su questo dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="7b21d-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="7b21d-210">Passaggio 2: annullare la registrazione del dispositivo dall Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="7b21d-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="7b21d-211">Tocca l'icona del menu nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="7b21d-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="7b21d-212">Toccare **Impostazioni** e quindi **Registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="7b21d-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="7b21d-213">Se viene visualizzato l'account, tocca **Annulla registrazione dispositivo** e **Continua** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7b21d-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="7b21d-214">Dopo questo non dovrebbe essere visualizzato alcun account.</span><span class="sxs-lookup"><span data-stu-id="7b21d-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="7b21d-215">Passaggio 3: Disconnettersi da singole app, se necessario</span><span class="sxs-lookup"><span data-stu-id="7b21d-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="7b21d-216">Gli utenti possono accedere a singole app come Outlook, Teams e OneDrive e rimuovere account da tali app.</span><span class="sxs-lookup"><span data-stu-id="7b21d-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="7b21d-217">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7b21d-217">More information</span></span>

<span data-ttu-id="7b21d-218">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="7b21d-218">Getting started:</span></span>

- [<span data-ttu-id="7b21d-219">Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche</span><span class="sxs-lookup"><span data-stu-id="7b21d-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="7b21d-220">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="7b21d-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="7b21d-221">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="7b21d-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="7b21d-222">Esperienza del cliente durante la migrazione</span><span class="sxs-lookup"><span data-stu-id="7b21d-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="7b21d-223">Passaggio attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="7b21d-223">Moving through the transition:</span></span>

- [<span data-ttu-id="7b21d-224">Azioni ed impatti sulle fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="7b21d-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="7b21d-225">Pre-lavoro aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="7b21d-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="7b21d-226">Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="7b21d-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="7b21d-227">App cloud:</span><span class="sxs-lookup"><span data-stu-id="7b21d-227">Cloud apps:</span></span>

- [<span data-ttu-id="7b21d-228">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7b21d-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="7b21d-229">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="7b21d-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="7b21d-230">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b21d-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)