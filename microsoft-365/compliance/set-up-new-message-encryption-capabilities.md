---
title: Configurare le nuove funzionalità di Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Scopri di più sulle nuove funzionalità crittografiche di Office 365, che consentono di comunicare tramite posta elettronica in sicurezza con le persone all’interno e all’esterno dell’organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf37826c3e1e349947ab83fe211f9406a765e5ea
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876305"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="4b5bd-103">Configurare le nuove funzionalità di Message Encryption</span><span class="sxs-lookup"><span data-stu-id="4b5bd-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="4b5bd-104">Le nuove funzionalità di Office 365 Message Encryption (OME) consentono alle organizzazioni di condividere la posta elettronica protetta con qualsiasi dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="4b5bd-105">Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Microsoft 365, oltre che con clienti che usano Outlook.com, Gmail e altri servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="4b5bd-106">Seguire questa procedura per verificare che le nuove funzionalità di OME siano disponibili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="4b5bd-107">Verificare che Azure Rights Management sia attivo</span><span class="sxs-lookup"><span data-stu-id="4b5bd-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="4b5bd-108">Le nuove funzionalità di OME sfruttano le caratteristiche di protezione di [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), la tecnologia usata da [Azure Information Protection](/azure/information-protection/what-is-azure-rms) per proteggere i messaggi di posta elettronica e i documenti tramite crittografia e controlli di accesso.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="4b5bd-109">L'unico requisito necessario per usare le nuove funzionalità di OME è che [Azure Rights Management](/azure/information-protection/what-is-azure-rms) debba essere attivato nel tenant dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="4b5bd-110">In tal caso, Microsoft 365 attiva automaticamente le nuove funzionalità di OME e non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="4b5bd-111">Azure RMS viene attivato automaticamente anche per la maggior parte dei piani idonei, pertanto non è necessario eseguire alcuna operazione a tal riguardo.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="4b5bd-112">Per altre informazioni, vedere [Attivazione di Azure Rights Management](/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-112">See [Activating Azure Rights Management](/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4b5bd-113">Se si usa Active Directory Rights Management Services (AD RMS) con Exchange Online, è necessario [eseguire la migrazione ad Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) prima di poter usare le nuove funzionalità di OME.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="4b5bd-114">OME non è compatibile con AD RMS.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-114">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="4b5bd-115">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-115">For more information, see:</span></span>

- <span data-ttu-id="4b5bd-116">[Quali abbonamenti sono necessari per usare le nuove funzionalità di OME? ](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) per verificare se il piano di abbonamento include Azure Information Protection (che include le funzionalità di Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="4b5bd-117">Per informazioni sull'acquisto di un abbonamento idoneo, vedere [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="4b5bd-118">Attivazione manuale di Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="4b5bd-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="4b5bd-119">Se è stato disabilitato Azure RMS o se non è stato attivato automaticamente, è possibile attivarlo manualmente in:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="4b5bd-120">**Interfaccia di amministrazione di Microsoft 365**: per istruzioni, vedere [Come attivare Azure Rights Management dall'interfaccia di amministrazione](/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="4b5bd-121">**Portale di Azure**: per istruzioni, vedere [Come attivare Azure Rights Management dal Portale di Azure](/azure/information-protection/activate-azure).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="4b5bd-122">Configurare la gestione della chiave tenant di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4b5bd-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="4b5bd-123">Questo passo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-123">This is an optional step.</span></span> <span data-ttu-id="4b5bd-124">A Microsoft è consentita la gestione della chiave radice di Azure Information Protection per impostazione predefinita ed è la procedura consigliata per la maggior parte delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="4b5bd-125">Se questo è il caso, non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="4b5bd-126">Ci sono diversi motivi, ad esempio i requisiti di conformità, che possono richiedere di generare e gestire una chiave radice, nota anche come bring your own key (BYOK).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="4b5bd-127">In questo caso, è consigliabile completare i passaggi necessari prima di configurare le nuove funzionalità di OME.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="4b5bd-128">Per altre informazioni, vedere [Pianificazione e implementazione della chiave tenant di Azure Information Protection](/information-protection/plan-design/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-128">See [Planning and implementing your Azure Information Protection tenant key](/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="4b5bd-129">Verificare la nuova configurazione di OME in PowerShell di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4b5bd-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="4b5bd-130">È possibile verificare se il tenant di Microsoft 365 è configurato correttamente per l'uso delle nuove funzionalità di OME disponibili in [PowerShell di Exchange Online](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>
  
1. <span data-ttu-id="4b5bd-131">[Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) usando un account con autorizzazioni di amministratore globale nel tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-131">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="4b5bd-132">Eseguire il cmdlet Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="4b5bd-133">Dovrebbe essere visualizzato un valore di $True per il parametro AzureRMSLicensingEnabled, che indica che OME è configurato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="4b5bd-134">Se non lo è, usare Set-IRMConfiguration per impostare il valore di AzureRMSLicensingEnabled su $True per abilitare OME.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="4b5bd-135">Eseguire il cmdlet Test-IRMConfiguration usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="4b5bd-136">**Esempio**:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="4b5bd-137">L'inserimento di un indirizzo di posta elettronica del mittente è facoltativo, ma forza il sistema a eseguire ulteriori controlli.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="4b5bd-138">Usare l'indirizzo e-mail di un utente nel tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="4b5bd-139">Il risultato dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="4b5bd-140">Il nome dell'organizzazione sostituirà *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="4b5bd-141">I nomi dei modelli predefiniti potrebbero essere diversi rispetto a quelli visualizzati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="4b5bd-142">Per altre informazioni, vedere [Configurazione e gestione dei modelli per Azure Information Protection](/azure/information-protection/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-142">See [Configuring and managing templates for Azure Information Protection](/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="4b5bd-143">Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="4b5bd-144">Passaggi successivi: definire le regole del flusso di posta per usare le nuove funzionalità di OME</span><span class="sxs-lookup"><span data-stu-id="4b5bd-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="4b5bd-p110">Se in precedenza sono state configurate regole del flusso di posta per crittografare la posta elettronica nell'organizzazione, è necessario aggiornare le regole esistenti per usare le nuove funzionalità di OME. Per le nuove distribuzioni, è necessario creare nuove regole per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-p110">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities. For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4b5bd-147">In caso contrario, gli utenti continueranno a ricevere messaggi crittografati che usano il formato dell'allegato HTML precedente invece della nuova esperienza di OME.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="4b5bd-148">Le regole del flusso di posta elettronica determinano le condizioni con cui i messaggi di posta elettronica devono essere crittografati e le condizioni per rimuovere la crittografia.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="4b5bd-149">Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati al momento dell'invio.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="4b5bd-150">Per altre passaggi sulla creazione delle regole del flusso di posta elettronica di OME, vedere [Definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="4b5bd-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="4b5bd-151">Aggiornare le regole esistenti per usare le nuove funzionalità di OME:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="4b5bd-152">Nell'interfaccia di amministrazione di Microsoft 365, passare a **Interfacce di amministrazione > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="4b5bd-153">Nell'interfaccia di amministrazione di Exchange, passare a **Flusso di posta > Regole**.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="4b5bd-154">Per ogni regola, in **Fai quanto segue**:</span><span class="sxs-lookup"><span data-stu-id="4b5bd-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="4b5bd-155">Selezionare **Modifica la sicurezza del messaggio**.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="4b5bd-156">Selezionare **Applica Office 365 Message Encryption e la protezione tramite diritti**.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="4b5bd-157">Selezionare un modello RMS dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="4b5bd-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-158">Select **Save**.</span></span>
    - <span data-ttu-id="4b5bd-159">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b5bd-159">Select **OK**.</span></span>