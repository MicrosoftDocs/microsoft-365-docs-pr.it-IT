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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861306"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="b27c6-103">Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="b27c6-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="b27c6-104">I dispositivi aggiunti e registrati di Azure AD connessi a Microsoft Cloud Deutschland devono essere migrati dopo la fase 9 e prima della fase 10.</span><span class="sxs-lookup"><span data-stu-id="b27c6-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="b27c6-105">La migrazione di un dispositivo dipende dal tipo di dispositivi, dal sistema operativo e dalla relazione AAD.</span><span class="sxs-lookup"><span data-stu-id="b27c6-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="b27c6-106">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="b27c6-106">Frequently asked questions</span></span>

<span data-ttu-id="b27c6-107">**Come è possibile sapere se l'organizzazione è interessata?**</span><span class="sxs-lookup"><span data-stu-id="b27c6-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="b27c6-108">Gli amministratori devono controllare se hanno dispositivi registrati o `https://portal.microsoftazure.de` aggiunti ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b27c6-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="b27c6-109">Se l'organizzazione ha dispositivi registrati, l'utente è interessato.</span><span class="sxs-lookup"><span data-stu-id="b27c6-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="b27c6-110">**Qual è l'impatto sugli utenti?**</span><span class="sxs-lookup"><span data-stu-id="b27c6-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="b27c6-111">Gli utenti di un dispositivo registrato non potranno più accedere dopo il completamento della fase di migrazione [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) e la disabilitazione degli endpoint per Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="b27c6-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="b27c6-112">Assicurati che tutti i dispositivi siano registrati con l'endpoint globale prima che l'organizzazione venga disconnessa da Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="b27c6-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="b27c6-113">**Quando gli utenti registrano di nuovo i propri dispositivi?**</span><span class="sxs-lookup"><span data-stu-id="b27c6-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="b27c6-114">È fondamentale annullare la registrazione e registrare di nuovo i dispositivi solo dopo il completamento della fase [9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="b27c6-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="b27c6-115">Devi completare la nuova registrazione prima dell'avvio della fase 10, altrimenti potresti perdere l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="b27c6-116">**Come si ripristina lo stato del dispositivo dopo la migrazione?**</span><span class="sxs-lookup"><span data-stu-id="b27c6-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="b27c6-117">Per i dispositivi Windows di proprietà dell'azienda registrati con Azure AD, gli amministratori saranno in grado di gestire la migrazione di questi dispositivi tramite flussi di lavoro attivati in remoto che annullano la registrazione degli stati dei dispositivi vecchi.</span><span class="sxs-lookup"><span data-stu-id="b27c6-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="b27c6-118">Per tutti gli altri dispositivi, inclusi Windows personali registrati in Azure AD, l'utente finale deve eseguire questi passaggi manualmente.</span><span class="sxs-lookup"><span data-stu-id="b27c6-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="b27c6-119">Per i dispositivi aggiunti ad Azure AD, gli utenti devono disporre di un account amministratore locale per annullare la registrazione e quindi registrare di nuovo i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b27c6-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="b27c6-120">Fai riferimento alle istruzioni dettagliate su come ripristinare correttamente gli stati dei dispositivi di seguito.</span><span class="sxs-lookup"><span data-stu-id="b27c6-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="b27c6-121">**Come è possibile sapere che tutti i dispositivi sono registrati nel cloud pubblico?**</span><span class="sxs-lookup"><span data-stu-id="b27c6-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="b27c6-122">Per verificare se i dispositivi sono registrati nel cloud pubblico, è consigliabile esportare e scaricare l'elenco dei dispositivi dal portale di Azure AD in un foglio di calcolo Excel dati.</span><span class="sxs-lookup"><span data-stu-id="b27c6-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="b27c6-123">Filtrare quindi i dispositivi registrati (utilizzando la colonna _registeredTime)_ dopo la fase di [migrazione Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="b27c6-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="b27c6-124">Considerazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b27c6-124">Additional considerations</span></span>
<span data-ttu-id="b27c6-125">La registrazione del dispositivo viene disattivata dopo la migrazione del tenant e non può essere abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="b27c6-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="b27c6-126">Se Intune non viene usato, accedere alla sottoscrizione ed eseguire questo comando per riattivare l'opzione:</span><span class="sxs-lookup"><span data-stu-id="b27c6-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="b27c6-127">**IMPORTANTE:** L'entità servizio intune verrà abilitata dopo la migrazione di commerce, che implica l'attivazione di Registrazione dispositivi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b27c6-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="b27c6-128">Se è stata bloccata la registrazione dei dispositivi di Azure AD prima della migrazione, è necessario disabilitare l'entità servizio intune con PowerShell per disabilitare di nuovo La registrazione dei dispositivi di Azure AD con il portale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b27c6-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="b27c6-129">È possibile disabilitare l'entità servizio intune con questo comando nella Azure Active Directory PowerShell per Graph modulo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="b27c6-130">Aggiunta ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="b27c6-130">Azure AD Join</span></span>
<span data-ttu-id="b27c6-131">Questo vale per Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b27c6-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="b27c6-132">Se un dispositivo è aggiunto ad Azure AD, deve essere disconnesso da Azure AD ed essere connesso di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="b27c6-133">[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b27c6-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="b27c6-134">Se l'utente è un amministratore del dispositivo Windows 10, l'utente può annullare la registrazione del dispositivo da Azure AD e aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="b27c6-135">Se non dispone di privilegi di amministratore, l'utente deve disporre delle credenziali di un account amministratore locale nel computer.</span><span class="sxs-lookup"><span data-stu-id="b27c6-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="b27c6-136">Un amministratore può creare un account amministratore locale nel dispositivo seguendo questo percorso di configurazione:</span><span class="sxs-lookup"><span data-stu-id="b27c6-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="b27c6-137">*Impostazioni > account > altri account > Credenziali sconosciute > Aggiungi utente senza Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="b27c6-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="b27c6-138">Passaggio 1: Determinare se il dispositivo è aggiunto all'ID Azure</span><span class="sxs-lookup"><span data-stu-id="b27c6-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="b27c6-139">Accedi con gli utenti E-mail e password.</span><span class="sxs-lookup"><span data-stu-id="b27c6-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="b27c6-140">Passare a Impostazioni > account > accesso a lavoro o all'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b27c6-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="b27c6-141">Cercare un utente nell'elenco con **connesso a ... 's Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="b27c6-142">Se esiste un utente connesso, procedere con il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b27c6-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="b27c6-143">In caso contrario, non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="b27c6-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="b27c6-144">Passaggio 2: disconnettere il dispositivo da Azure AD</span><span class="sxs-lookup"><span data-stu-id="b27c6-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="b27c6-145">Toccare **Disconnetti** nell'account aziendale o dell'istituto di istruzione connesso.</span><span class="sxs-lookup"><span data-stu-id="b27c6-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="b27c6-146">Confermare la disconnessione due volte.</span><span class="sxs-lookup"><span data-stu-id="b27c6-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="b27c6-147">Immettere il nome utente e la password dell'amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="b27c6-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="b27c6-148">Il dispositivo è disconnesso.</span><span class="sxs-lookup"><span data-stu-id="b27c6-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="b27c6-149">Riavvia il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="b27c6-150">Passaggio 3: Aggiungere il dispositivo ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="b27c6-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="b27c6-151">l'utente accede con le credenziali dell'amministratore locale</span><span class="sxs-lookup"><span data-stu-id="b27c6-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="b27c6-152">Vai **a** Impostazioni account **e quindi** accedi a Lavoro **o Scuola**</span><span class="sxs-lookup"><span data-stu-id="b27c6-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="b27c6-153">Toccare **Connessione**</span><span class="sxs-lookup"><span data-stu-id="b27c6-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="b27c6-154">**IMPORTANTE:** toccare **Partecipa ad Azure AD**</span><span class="sxs-lookup"><span data-stu-id="b27c6-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="b27c6-155">Immettere l'indirizzo di posta elettronica e la password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b27c6-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="b27c6-156">Il dispositivo è connesso</span><span class="sxs-lookup"><span data-stu-id="b27c6-156">The device is connected</span></span>
6.  <span data-ttu-id="b27c6-157">Riavviare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="b27c6-157">Restart the device</span></span> 
7.  <span data-ttu-id="b27c6-158">firma con l'indirizzo di posta elettronica e la password</span><span class="sxs-lookup"><span data-stu-id="b27c6-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="b27c6-159">Azure AD registrato (di proprietà della società)</span><span class="sxs-lookup"><span data-stu-id="b27c6-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="b27c6-160">Per determinare se Windows 10 dispositivo è registrato con Azure AD, eseguire il comando seguente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b27c6-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="b27c6-161">Se il dispositivo è registrato in Azure AD, verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b27c6-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="b27c6-162">Per rimuovere l'account registrato con Azure AD esistente nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b27c6-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="b27c6-163">Per rimuovere l'account registrato da Azure AD nel dispositivo, usa CleanupWPJ, uno strumento che puoi scaricare da qui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="b27c6-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="b27c6-164">Estrarre il file ZIP ed eseguire **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="b27c6-165">Questo strumento avvierà il file eseguibile giusto in base alla versione Windows nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="b27c6-166">Usando un meccanismo come Criteri di gruppo, l'amministratore può eseguire il comando nel dispositivo nel contesto di qualsiasi utente che ha eseguito l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="b27c6-167">Per disabilitare le istruzioni di Gestione account Web per registrare il dispositivo in Azure AD, aggiungere questo valore del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="b27c6-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="b27c6-168">Posizione: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="b27c6-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="b27c6-169">Tipo: DWORD (32 bit)</span><span class="sxs-lookup"><span data-stu-id="b27c6-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="b27c6-170">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="b27c6-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="b27c6-171">Dati valore: 1</span><span class="sxs-lookup"><span data-stu-id="b27c6-171">Value data: 1</span></span>

<span data-ttu-id="b27c6-172">La presenza di questo valore del Registro di sistema dovrebbe bloccare l'aggiunta all'area di lavoro e impedire agli utenti di visualizzare le istruzioni per l'aggiunta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="b27c6-173">Android</span><span class="sxs-lookup"><span data-stu-id="b27c6-173">Android</span></span>

<span data-ttu-id="b27c6-174">Per Android, gli utenti dovranno annullare la registrazione e registrare di nuovo i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b27c6-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="b27c6-175">Questa operazione può essere eseguita tramite l'app Microsoft Authenticator o l'app Portale aziendale app.</span><span class="sxs-lookup"><span data-stu-id="b27c6-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="b27c6-176">Dall'app Microsoft Authenticator, gli utenti possono passare a **Impostazioni > Registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="b27c6-177">Da qui gli utenti possono annullare la registrazione e registrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="b27c6-178">Dall'Portale aziendale, gli utenti possono passare alla **scheda** Dispositivi e rimuovere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="b27c6-179">Successivamente, registrare di nuovo il dispositivo usando Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="b27c6-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="b27c6-180">Gli utenti possono anche annullare la registrazione e registrare di nuovo rimuovendo l'account dalla pagina delle impostazioni dell'account e quindi aggiungendo di nuovo l'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="b27c6-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="b27c6-181">Per annullare la registrazione e registrare di nuovo il dispositivo in Android usando l'app Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="b27c6-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="b27c6-182">Apri l Microsoft Authenticator app e vai a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="b27c6-183">Selezionare **Registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="b27c6-184">Annulla la registrazione del dispositivo selezionando **Annulla registrazione**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="b27c6-185">Per **Registrazione dispositivo**, registrare di nuovo il dispositivo digitando l'indirizzo di posta elettronica e quindi selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="b27c6-186">Per annullare la registrazione e registrare di nuovo un dispositivo Android con la pagina Impostazioni Android:</span><span class="sxs-lookup"><span data-stu-id="b27c6-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="b27c6-187">Apri **Gestione Impostazioni** e vai a **Account**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="b27c6-188">Selezionare l'account aziendale che si desidera registrare di nuovo e selezionare **Rimuovi account**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="b27c6-189">Dopo aver rimosso l'account, nella **pagina Account** selezionare **Aggiungi account > Account di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="b27c6-190">Per **Workplace Join,** digita il tuo indirizzo e-mail e seleziona **Partecipa** per completare la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="b27c6-191">Per annullare la registrazione e registrare di nuovo il dispositivo su Android da Portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="b27c6-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="b27c6-192">Avvia Portale aziendale e vai alla **scheda** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b27c6-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="b27c6-193">Seleziona il dispositivo per visualizzare i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="b27c6-194">Dal menu con i puntini di sospensione (tre puntini), seleziona **Rimuovi dispositivo** e completa la rimozione confermando nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="b27c6-195">A questo punto dovresti essere disconnesso dall'app Portale aziendale app.</span><span class="sxs-lookup"><span data-stu-id="b27c6-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="b27c6-196">Seleziona **Accedi** per registrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="b27c6-197">Per ulteriori informazioni sulle azioni necessarie durante la fase di migrazione di questo carico di lavoro o sull'impatto sull'amministrazione o sull'utilizzo, consultare le informazioni su Azure Active Directory (Azure AD) in Ulteriori informazioni di Azure AD per la migrazione da [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="b27c6-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="b27c6-198">iOS</span><span class="sxs-lookup"><span data-stu-id="b27c6-198">iOS</span></span>

<span data-ttu-id="b27c6-199">Nei dispositivi iOS, un utente dovrà rimuovere manualmente gli account memorizzati nella cache dal Microsoft Authenticator, annullare la registrazione del dispositivo e disconnettersi da qualsiasi app nativa nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="b27c6-200">Passaggio 1: se presente, rimuovi l'account dall'app Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="b27c6-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="b27c6-201">Tocca l'account nell'app Microsoft Authenticator app.</span><span class="sxs-lookup"><span data-stu-id="b27c6-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="b27c6-202">Tocca **l'Impostazioni** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="b27c6-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="b27c6-203">Se non viene visualizzata **l'icona Impostazioni,** è possibile che non si utilizzi la versione più recente di Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="b27c6-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="b27c6-204">Tocca il **pulsante Rimuovi account.**</span><span class="sxs-lookup"><span data-stu-id="b27c6-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="b27c6-205">Toccare **Tutte le app su questo dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="b27c6-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="b27c6-206">Passaggio 2: annullare la registrazione del dispositivo dall Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="b27c6-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="b27c6-207">Tocca l'icona del menu nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="b27c6-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="b27c6-208">Toccare **Impostazioni** e quindi **Registrazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b27c6-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="b27c6-209">Se viene visualizzato l'account, tocca **Annulla registrazione dispositivo** e **Continua** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b27c6-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="b27c6-210">Dopo questo non dovrebbe essere visualizzato alcun account.</span><span class="sxs-lookup"><span data-stu-id="b27c6-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="b27c6-211">Passaggio 3: Disconnettersi da singole app, se necessario</span><span class="sxs-lookup"><span data-stu-id="b27c6-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="b27c6-212">Gli utenti possono accedere a singole app come Outlook, Teams e OneDrive e rimuovere account da tali app.</span><span class="sxs-lookup"><span data-stu-id="b27c6-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="b27c6-213">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b27c6-213">More information</span></span>

<span data-ttu-id="b27c6-214">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="b27c6-214">Getting started:</span></span>

- [<span data-ttu-id="b27c6-215">Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche</span><span class="sxs-lookup"><span data-stu-id="b27c6-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="b27c6-216">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="b27c6-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="b27c6-217">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="b27c6-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="b27c6-218">Esperienza del cliente durante la migrazione</span><span class="sxs-lookup"><span data-stu-id="b27c6-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="b27c6-219">Passaggio attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="b27c6-219">Moving through the transition:</span></span>

- [<span data-ttu-id="b27c6-220">Azioni ed impatti sulle fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="b27c6-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="b27c6-221">Pre-lavoro aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b27c6-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="b27c6-222">Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="b27c6-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="b27c6-223">App cloud:</span><span class="sxs-lookup"><span data-stu-id="b27c6-223">Cloud apps:</span></span>

- [<span data-ttu-id="b27c6-224">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b27c6-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="b27c6-225">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="b27c6-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="b27c6-226">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b27c6-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)