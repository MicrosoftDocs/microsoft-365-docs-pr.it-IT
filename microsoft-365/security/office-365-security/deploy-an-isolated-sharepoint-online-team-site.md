---
title: Distribuire un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Sintesi: istruzioni dettagliate per distribuire un nuovo sito del team di SharePoint Online isolato.'
ms.openlocfilehash: 67c6a5304e067ac847c9f8158d48a588ca118220
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "38039115"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="14036-103">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="14036-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="14036-104">**Sintesi:** istruzioni dettagliate per distribuire un nuovo sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="14036-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="14036-p101">In questo articolo viene fornita una guida dettagliata alla distribuzione per creare e configurare un sito del team di SharePoint Online isolato in Microsoft Office 365. Questa procedura presuppone l'utilizzo di tre gruppi di SharePoint predefiniti e dei livelli di autorizzazione corrispondenti, con un singolo gruppo di Azure Active Directory (AD) per ogni livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="14036-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="14036-107">Fase 1: creare e popolare i gruppi di accesso al sito del team</span><span class="sxs-lookup"><span data-stu-id="14036-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="14036-108">In questa fase, vengono creati tre gruppi di accesso basati su Azure AD per i tre gruppi di SharePoint predefiniti e vengono popolati con gli account utente appropriati.</span><span class="sxs-lookup"><span data-stu-id="14036-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14036-p102">La procedura seguente presuppone che tutti gli account utente necessari già esistano e siano dotati delle licenze appropriate. In caso contrario, aggiungerli e assegnare le licenze prima di procedere con il passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14036-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="14036-111">Passaggio 1: elencare gli amministratori di SharePoint Online per il sito</span><span class="sxs-lookup"><span data-stu-id="14036-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="14036-112">Determinare il set di account utente corrispondenti agli amministratori di SharePoint Online per il sito del team isolato.</span><span class="sxs-lookup"><span data-stu-id="14036-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="14036-113">Se si gestiscono account utente e gruppi con Office 365 e si desidera utilizzare Windows PowerShell, fare un elenco dei loro nomi dell'entità utente (UPN), ad esempio, UPN: belindan@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="14036-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="14036-114">Passaggio 2: elencare i membri del sito</span><span class="sxs-lookup"><span data-stu-id="14036-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="14036-115">Determinare il set di account utente corrispondenti ai membri del sito del team isolato, quelli che collaboreranno sulle risorse archiviate nel sito.</span><span class="sxs-lookup"><span data-stu-id="14036-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="14036-p103">Se si gestiscono account utente e gruppi con Office 365 e si desidera utilizzare PowerShell, fare un elenco dei loro UPN. Se sono presenti molti membri del sito, è possibile archiviare l'elenco di UPN in un file di testo e aggiungerli con un singolo comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14036-p103">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs. If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="14036-118">Passaggio 3: elencare i visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="14036-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="14036-119">Determinare il set di account utente corrispondenti ai visualizzatori del sito del tam isolato, quelli che possono visualizzare le risorse archiviate nel sito ma non modificarle o collaborare direttamente sui contenuti.</span><span class="sxs-lookup"><span data-stu-id="14036-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="14036-p104">Se si gestiscono account utente e gruppi con Office 365 e si desidera utilizzare PowerShell, fare un elenco dei loro UPN. Se sono presenti molti membri del sito, è possibile archiviare l'elenco di UPN in un file di testo e aggiungerli con un singolo comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14036-p104">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs. If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="14036-122">I visualizzatori del sito potrebbero includere la direzione esecutiva, i consulenti legali o gli stakeholder interdipartimentali.</span><span class="sxs-lookup"><span data-stu-id="14036-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="14036-123">Passaggio 4: creare i tre gruppi di accesso per il sito di Azure AD</span><span class="sxs-lookup"><span data-stu-id="14036-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="14036-124">È necessario creare i gruppi di accesso seguenti in Azure AD:</span><span class="sxs-lookup"><span data-stu-id="14036-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="14036-125">Amministratori del sito (che contiene l'elenco creato al passaggio 1)</span><span class="sxs-lookup"><span data-stu-id="14036-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="14036-126">Membri del sito (che contiene l'elenco creato al passaggio 2)</span><span class="sxs-lookup"><span data-stu-id="14036-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="14036-127">Visualizzatori del sito (che contiene l'elenco creato al passaggio 3)</span><span class="sxs-lookup"><span data-stu-id="14036-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="14036-128">Nel browser, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) e accedere con le credenziali di un account assegnato con l'amministratore di gestione utenti o con il ruolo Administrator dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="14036-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="14036-129">Nel portale di Azure fare clic su **Azure Active Directory > Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="14036-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="14036-130">Nel pannello **Gruppi - Tutti i gruppi** fare clic su **+ Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="14036-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="14036-131">Nel **nuovo gruppo** Blade:</span><span class="sxs-lookup"><span data-stu-id="14036-131">On the **New Group** blade:</span></span>
    
  - <span data-ttu-id="14036-132">Selezionare **Sicurezza** in **Tipo di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="14036-132">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="14036-133">Digitare il nome del gruppo in **nome**.</span><span class="sxs-lookup"><span data-stu-id="14036-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="14036-134">Digitare una descrizione del gruppo nella **Descrizione del gruppo**.</span><span class="sxs-lookup"><span data-stu-id="14036-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="14036-135">Selezionare **Assegnato** in **Tipo di appartenenza**.</span><span class="sxs-lookup"><span data-stu-id="14036-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="14036-136">Fare clic su **Crea** e quindi chiudere il pannello **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="14036-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="14036-137">Ripetere i passaggi 3-5 per i gruppi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="14036-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14036-138">È necessario utilizzare il portale di Azure per creare i gruppi in modo che dispongano delle funzionalità di Office abilitate.</span><span class="sxs-lookup"><span data-stu-id="14036-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="14036-139">Se un sito di SharePoint Online isolato viene configurato in un secondo momento come sito estremamente riservato con un'etichetta di Azure Information Protection per crittografare i file e assegnare l'autorizzazione a gruppi specifici, è necessario che i gruppi consentiti siano stati creati con le funzionalità di Office abilitate.</span><span class="sxs-lookup"><span data-stu-id="14036-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="14036-140">Non è possibile modificare l'impostazione delle caratteristiche di Office di un gruppo di Azure AD dopo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="14036-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="14036-141">Ecco la configurazione risultante con i tre gruppi di accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="14036-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![I tre gruppi di accesso per la distribuzione di un sito di SharePoint Online isolato.](../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="14036-143">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="14036-143">Step 5.</span></span> <span data-ttu-id="14036-144">Aggiungere gli account utente ai gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="14036-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="14036-145">In questo passaggio, eseguire la procedura riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="14036-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="14036-146">Aggiungere l'elenco di utenti creato nel passaggio 1 al gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="14036-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="14036-147">Aggiungere l'elenco di utenti creato nel passaggio 2 al gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="14036-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="14036-148">Aggiungere l'elenco di utenti creato nel passaggio 3 al gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="14036-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="14036-149">Se si gestiscono gli account utente e i gruppi tramite servizi di dominio Active Directory, aggiungere gli utenti ai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di AD DS e attendere la sincronizzazione con l'abbonamento a Office 365.</span><span class="sxs-lookup"><span data-stu-id="14036-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="14036-150">Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14036-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="14036-151">Se si dispone di nomi di gruppo duplicati per uno qualsiasi dei gruppi di accesso, è consigliabile utilizzare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14036-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="14036-152">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per aggiungere gli account utente e i gruppi corretti ai gruppi di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="14036-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="14036-153">Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="14036-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="14036-154">Successivamente, utilizzare il seguente blocco di comandi per aggiungere un singolo account utente a un gruppo di accesso:</span><span class="sxs-lookup"><span data-stu-id="14036-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="14036-155">Per un file di testo che contiene tutti i comandi di PowerShell e un foglio di lavoro di configurazione di Excel che genera comandi di PowerShell in base ai nomi degli account utente e di gruppo, scaricare [Kit di distribuzione del sito di SharePoint Online Team isolato](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="14036-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="14036-156">Se gli UPN degli account utente per uno dei gruppi di accesso è archiviato in un file di testo, è possibile utilizzare il seguente blocco di comandi PowerShell per aggiungerli tutti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="14036-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="14036-157">Per PowerShell, utilizzare il seguente blocco di comandi per aggiungere un singolo gruppo a un gruppo di accesso:</span><span class="sxs-lookup"><span data-stu-id="14036-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="14036-158">Dovrebbero essere visualizzati i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="14036-158">The results should be the following:</span></span>
  
- <span data-ttu-id="14036-159">Il gruppo di Azure AD degli amministratori del sito contiene gli account utente o i gruppi di amministratori del sito.</span><span class="sxs-lookup"><span data-stu-id="14036-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="14036-160">Il gruppo di Azure AD dei membri del sito contiene gli account utente o i gruppi di membri del sito.</span><span class="sxs-lookup"><span data-stu-id="14036-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="14036-161">Il gruppo di Azure AD dei visualizzatori del sito contiene gli account utente o i gruppi che possono visualizzare solo il contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="14036-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="14036-162">Convalidare l'elenco dei membri del gruppo di ogni gruppo di accesso con l'interfaccia di amministrazione di Microsoft 365 o con il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14036-162">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="14036-163">Di seguito è configurata la configurazione risultante con i tre gruppi di accesso al sito popolati con account utente o gruppi.</span><span class="sxs-lookup"><span data-stu-id="14036-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![I tre gruppi di accesso popolati con gli account utente.](../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="14036-165">Fase 2: creare e configurare il sito del team isolato</span><span class="sxs-lookup"><span data-stu-id="14036-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="14036-166">In questa fase, viene creato il sito di SharePoint Online isolato e vengono configurate le autorizzazioni per i livelli di autorizzazione di SharePoint Online predefiniti affinché vengano utilizzati i nuovi gruppi di accesso basati su Azure AD.</span><span class="sxs-lookup"><span data-stu-id="14036-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="14036-167">Creare innanzitutto il sito del team di SharePoint Online seguendo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="14036-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="14036-168">Accedere all'interfaccia di amministrazione con un account che verrà usato anche per amministrare il sito del team di SharePoint Online (un amministratore di SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="14036-168">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="14036-169">Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="14036-169">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="14036-170">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="14036-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="14036-171">Nella nuova **scheda SharePoint** del browser fare clic su **+ Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="14036-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="14036-172">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="14036-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="14036-173">In **nome sito**Digitare un nome per il sito del team.</span><span class="sxs-lookup"><span data-stu-id="14036-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="14036-174">Nella **Descrizione del sito del team** Digitare una descrizione facoltativa dello scopo del sito.</span><span class="sxs-lookup"><span data-stu-id="14036-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="14036-175">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="14036-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="14036-176">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="14036-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="14036-177">Successivamente, dal nuovo sito del team di SharePoint Online configurare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="14036-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="14036-178">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="14036-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="14036-179">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="14036-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="14036-180">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="14036-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="14036-181">Nella finestra di dialogo **Impostazioni richieste di accesso** deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti richieste di accesso** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="14036-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="14036-182">Nella scheda **autorizzazioni** del browser fare clic \*\* \<su nome sito> membri\*\* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="14036-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="14036-183">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="14036-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="14036-184">Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di Azure AD dei membri del sito di accesso, selezionarlo e fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="14036-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="14036-185">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="14036-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="14036-186">Fare clic su \*\* \<nome sito> proprietari\*\* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="14036-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="14036-187">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="14036-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="14036-188">Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di accesso degli amministratori del sito, selezionarlo e fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="14036-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="14036-189">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="14036-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="14036-190">Fare clic su \*\* \<nome sito> visitatori\*\* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="14036-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="14036-191">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="14036-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="14036-192">Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di Azure AD dei visualizzatori del sito di accesso, selezionarlo e fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="14036-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="14036-193">Chiudere la scheda **Autorizzazioni** del browser.</span><span class="sxs-lookup"><span data-stu-id="14036-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="14036-194">I risultati di queste impostazioni delle autorizzazioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="14036-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="14036-195">Il \*\* \<nome del sito> proprietari\*\* gruppo di SharePoint contiene il gruppo di accesso degli amministratori del sito, in cui tutti i membri hanno il livello di autorizzazione **controllo completo** .</span><span class="sxs-lookup"><span data-stu-id="14036-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="14036-196">Il \*\* \<nome del sito> membri\*\* del gruppo di SharePoint contiene il gruppo di accesso dei membri del sito, in cui tutti i membri hanno il livello di autorizzazione **modifica** .</span><span class="sxs-lookup"><span data-stu-id="14036-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="14036-197">Il \*\* \<nome del sito> visitatori\*\* gruppo di SharePoint contiene il gruppo di accesso dei visualizzatori del sito, in cui tutti i membri hanno il livello di autorizzazione **lettura** .</span><span class="sxs-lookup"><span data-stu-id="14036-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="14036-198">I membri non hanno la possibilità di invitare altri membri o di richiedere l'accesso per utenti non membri.</span><span class="sxs-lookup"><span data-stu-id="14036-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="14036-199">Ecco la configurazione risultante con i tre gruppi di SharePoint per il sito configurati per l'utilizzo dei tre gruppi di accesso, che sono popolati con gli account utente o i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="14036-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![La configurazione finale del sito di SharePoint Online isolato con i gruppi di accesso e gli account utente.](../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="14036-201">I membri del sito, tramite l'appartenenza a uno dei gruppi di accesso, possono ora collaborare utilizzando le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="14036-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="14036-202">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="14036-202">Next step</span></span>

<span data-ttu-id="14036-203">Se è necessario modificare l'appartenenza al gruppo di accesso del sito o creare una cartella di documenti con autorizzazioni personalizzate, vedere [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="14036-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="14036-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14036-204">See Also</span></span>

[<span data-ttu-id="14036-205">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="14036-205">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="14036-206">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="14036-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="14036-207">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="14036-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



