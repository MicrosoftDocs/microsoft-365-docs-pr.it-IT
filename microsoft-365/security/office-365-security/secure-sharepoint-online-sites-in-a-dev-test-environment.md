---
title: Proteggere i siti di SharePoint Online in un ambiente di sviluppo/test
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Riepilogo: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati in un ambiente di sviluppo/test.'
ms.openlocfilehash: d60d113f9b8eac453e8a516b4d5e373896ace0ec
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084909"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a><span data-ttu-id="e1cd5-103">Proteggere i siti di SharePoint Online in un ambiente di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="e1cd5-103">Secure SharePoint Online sites in a dev/test environment</span></span>

 <span data-ttu-id="e1cd5-104">**Riepilogo:** creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati in un ambiente di sviluppo/test.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in a dev/test environment.</span></span>
  
<span data-ttu-id="e1cd5-105">Questo articolo contiene istruzioni dettagliate per la creazione di un ambiente di sviluppo e test che includa i quattro tipi diversi di sito del team di SharePoint Online per la [soluzione di protezione di siti e file di SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-105">This article provides step-by-step instructions to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) solution.</span></span>
  
![Tutti i quattro siti del team nell’ambiente di sviluppo/test protetto di SharePoint Online.](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
<span data-ttu-id="e1cd5-107">Usare questo ambiente di sviluppo e test per sperimentare i comportamenti della protezione delle informazioni e ottimizzare le impostazioni in base alle esigenze specifiche prima di distribuire siti del team di SharePoint Online nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-107">Use this dev/test environment to experiment with the information protection behaviors and fine-tune settings for your specific needs before deploying SharePoint Online team sites in production.</span></span>
  
## <a name="phase-1-create-your-devtest-environment"></a><span data-ttu-id="e1cd5-108">Fase 1: Creare l'ambiente di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="e1cd5-108">Phase 1: Create your dev/test environment</span></span>

<span data-ttu-id="e1cd5-109">In questa fase si ottengono le sottoscrizioni di valutazione per Office 365 ed Enterprise Mobility + Security (EMS) per un'organizzazione fittizia.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-109">In this phase, you obtain trial subscriptions for Office 365 and Enterprise Mobility + Security (EMS) for a fictional organization.</span></span>
  
<span data-ttu-id="e1cd5-110">Per prima cosa, seguire le istruzioni della **fase 2** nell'articolo relativo all'[ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-110">First, follow the instructions in **Phase 2** of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="e1cd5-111">Iscriversi quindi per la sottoscrizione di valutazione di EMS e aggiungerla alla stessa organizzazione della sottoscrizione di prova di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-111">Next, sign up for the EMS trial subscription and add it to the same organization as your Office 365 trial subscription.</span></span>
  
1. <span data-ttu-id="e1cd5-112">Se necessario, accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-112">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="e1cd5-113">Nel riquadro di spostamento sinistro fare clic su **Fatturazione > Acquisto di servizi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-113">In the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="e1cd5-p101">Nella pagina **Acquisto di servizi**, individuare la voce **Enterprise Mobility + Security E5**. Posizionare il puntatore del mouse su di essa e fare clic su **Avvia la versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-p101">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
4. <span data-ttu-id="e1cd5-116">Nella pagina **Conferma l'ordine**, fare clic su **Prova adesso**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-116">On the **Confirm your order** page, click **Try now**.</span></span>
    
5. <span data-ttu-id="e1cd5-117">Nella pagina **Ricevuta ordine** fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-117">On the **Order receipt** page, click **Continue**.</span></span>
    
<span data-ttu-id="e1cd5-118">Abilitare quindi la licenza Enterprise Mobility + Security E5 per l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-118">Next, enable the Enterprise Mobility + Security E5 license for your global administrator account.</span></span>
  
1. <span data-ttu-id="e1cd5-119">Nella scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Utenti > Utenti attivi** nel riquadro di spostamento di sinistra.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
2. <span data-ttu-id="e1cd5-120">Fare clic sull'account amministratore globale e quindi su **Modifica** per le **licenze del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
3. <span data-ttu-id="e1cd5-121">Nel riquadro **Licenze per i prodotti**, impostare la licenza per i prodotti di **Enterprise Mobility + Security E5** su **Attiva**, fare clic su **Salva** e quindi fare doppio clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="e1cd5-122">Fase 2: Creare e configurare i gruppi e gli utenti di Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="e1cd5-122">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="e1cd5-123">In questa fase vengono creati e configurati i gruppi e gli utenti di Azure AD per l'organizzazione fittizia.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-123">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="e1cd5-124">Innanzitutto, creare un set di gruppi per un'organizzazione tipica con il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-124">First, create a set of groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="e1cd5-p102">Creare una scheda separata nel browser, quindi passare al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com). Se necessario, accedere con le credenziali dell'account amministratore globale della sottoscrizione di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-p102">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="e1cd5-127">Nel portale di Azure fare clic su **Azure Active Directory > Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-127">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="e1cd5-128">Nel pannello **Gruppi - Tutti i gruppi** fare clic su **+ Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-128">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="e1cd5-129">Nel pannello **Gruppo**:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-129">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="e1cd5-130">Selezionare **Office 365** in **Tipo di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-130">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="e1cd5-131">Digitare **C-Suite** in **Nome**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-131">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="e1cd5-132">Selezionare **Assegnato** in **Tipo di appartenenza**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-132">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="e1cd5-133">Fare clic su **Crea** e quindi chiudere il pannello **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-133">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="e1cd5-134">Ripetere i passaggi da 3 a 5 per i nomi dei gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-134">Repeat steps 3-5 for the following group names:</span></span>
    
  - <span data-ttu-id="e1cd5-135">IT staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-135">IT staff</span></span>
    
  - <span data-ttu-id="e1cd5-136">Research staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-136">Research staff</span></span>
    
  - <span data-ttu-id="e1cd5-137">Regular staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-137">Regular staff</span></span>
    
  - <span data-ttu-id="e1cd5-138">Marketing staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-138">Marketing staff</span></span>
    
  - <span data-ttu-id="e1cd5-139">Sales staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-139">Sales staff</span></span>
    
7. <span data-ttu-id="e1cd5-140">Tenere aperta la scheda del portale di Azure nel browser.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-140">Keep the Azure portal tab in your browser open.</span></span>
    
<span data-ttu-id="e1cd5-141">Successivamente, si configurano le licenze automatiche in modo che ai membri dei gruppi vengano automaticamente assegnate le licenze per le sottoscrizioni di Office 365 ed EMS.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-141">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="e1cd5-142">Nel portale di Azure fare clic su **Azure Active Directory > Licenze > Tutti i prodotti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-142">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="e1cd5-143">Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-143">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="e1cd5-144">Nel pannello **Assegnare licenza** fare clic su **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-144">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="e1cd5-145">Nell'elenco dei gruppi selezionare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-145">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="e1cd5-146">C-Suite</span><span class="sxs-lookup"><span data-stu-id="e1cd5-146">C-Suite</span></span>
    
  - <span data-ttu-id="e1cd5-147">IT staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-147">IT staff</span></span>
    
  - <span data-ttu-id="e1cd5-148">Research staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-148">Research staff</span></span>
    
  - <span data-ttu-id="e1cd5-149">Regular staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-149">Regular staff</span></span>
    
  - <span data-ttu-id="e1cd5-150">Marketing staff</span><span class="sxs-lookup"><span data-stu-id="e1cd5-150">Marketing staff</span></span>
    
  - <span data-ttu-id="e1cd5-151">Personale addetto alle vendite</span><span class="sxs-lookup"><span data-stu-id="e1cd5-151">Sales staff</span></span>
    
5. <span data-ttu-id="e1cd5-152">Fare clic su **Seleziona**, quindi su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-152">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="e1cd5-153">Chiudere la scheda del portale di Azure nel browser.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-153">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="e1cd5-154">Successivamente, [Connettersi con il modulo di Azure Active Directory PowerShell per Graph ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-154">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e1cd5-155">Inserire il nome dell'organizzazione, la posizione e una password comune; eseguire quindi questi comandi dal prompt dei comandi di PowerShell o Integrated Script Environment (ISE) per creare account utente e aggiungerli ai rispettivi gruppi:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-155">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="e1cd5-156">L'uso di una password comune qui consente l'automazione e agevola la configurazione per un ambiente di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-156">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="e1cd5-157">Ovviamente, questo approccio è sconsigliato per le sottoscrizioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-157">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="e1cd5-158">Seguire questi passaggi per verificare che le licenze basate su gruppo funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-158">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="e1cd5-159">Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-159">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="e1cd5-160">Dalla nuova scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-160">From the new **Office Admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="e1cd5-161">Fare clic su **CEO** nell'elenco degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-161">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="e1cd5-162">Nel riquadro in cui sono elencate le proprietà dell'account utente **CEO** verificare che all'account siano state assegnate le licenze **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** (nell'elenco delle **licenze del prodotto**).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-162">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="e1cd5-163">Fase 3: Creare le etichette di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="e1cd5-163">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="e1cd5-164">In questa fase vengono create le etichette di conservazione per i diversi livelli di sicurezza per cartelle di documenti dei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-164">In this phase, you create the retention labels for the different levels of security for SharePoint Online team site documents folders.</span></span>


1. <span data-ttu-id="e1cd5-165">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="e1cd5-166">Dalla scheda **Home: Conformità Microsoft 365** del browser fare clic su **Classificazioni > Etichette**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-166">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="e1cd5-167">Fare clic su **Etichette di conservazione > Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-167">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="e1cd5-168">Nel riquadro **Assegnare un nome all'etichetta** digitare \*\*Internal Public\*\*\*\*\*\* e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-168">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="e1cd5-169">Nel riquadro **Descrittori del piano di archiviazione** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-169">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="e1cd5-170">Nel riquadro **Impostazioni etichetta** impostare **Conservazione** su **Sì**, se necessario, e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-170">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e1cd5-171">Nel riquadro **Rivedere le impostazioni** fare clic su **Crea etichetta**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-171">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="e1cd5-172">Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-172">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="e1cd5-173">Private</span><span class="sxs-lookup"><span data-stu-id="e1cd5-173">Private</span></span>
    
  - <span data-ttu-id="e1cd5-174">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="e1cd5-174">Sensitive</span></span>
    
  - <span data-ttu-id="e1cd5-175">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="e1cd5-175">Highly Confidential</span></span>
  
9. <span data-ttu-id="e1cd5-176">Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-176">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="e1cd5-177">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-177">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="e1cd5-178">Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-178">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="e1cd5-179">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-179">Click **Done**.</span></span>
    
13. <span data-ttu-id="e1cd5-180">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-180">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="e1cd5-181">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-181">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="e1cd5-182">Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-182">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="e1cd5-183">Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-183">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="e1cd5-184">Fase 4: creare i siti del team di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e1cd5-184">Phase 4: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="e1cd5-185">In questa fase vengono creati e configurati i quattro tipi di siti del team di SharePoint Online per l'organizzazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-185">In this phase, you create and configure the four types of SharePoint Online team sites for your example organization.</span></span>
  
### <a name="organization-wide-team-site"></a><span data-ttu-id="e1cd5-186">Sito del team per l'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="e1cd5-186">Organization wide team site</span></span>

<span data-ttu-id="e1cd5-187">Per creare un sito pubblico iniziale per il team di SharePoint Online, eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-187">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="e1cd5-188">Se necessario, accedere al [portale di Office 365](https://portal.office.com) con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-188">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="e1cd5-189">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-189">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e1cd5-190">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-190">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="e1cd5-191">Nella pagina **Crea un sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-191">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e1cd5-192">In **Nome sito** digitare **Organization wide**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-192">In **Site name**, type **Organization wide**.</span></span> 
    
6. <span data-ttu-id="e1cd5-193">Come **descrizione del sito del team** digitare **Sito SharePoint per l'intera organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-193">In **Team site description**, type **SharePoint site for the entire organization**.</span></span>
    
7. <span data-ttu-id="e1cd5-194">In **Impostazioni privacy** selezionare **Public – anyone in the organization can access this site** (Pubblico: qualsiasi persona dell'organizzazione può accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-194">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e1cd5-195">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-195">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="e1cd5-196">Configurare quindi la cartella dei documenti del sito del team dell'intera organizzazione per l'etichetta Internal Public.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-196">Next, configure the documents folder of the Organization wide team site for the Internal Public label.</span></span>
  
1. <span data-ttu-id="e1cd5-197">Nella scheda **Organization wide - Home** (A livello di organizzazione - Home) del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-197">In the **Organization wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="e1cd5-198">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-198">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="e1cd5-199">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="e1cd5-200">In **Impostazioni: Applica etichetta** selezionare **Internal Public**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-200">In **Settings-Apply Label**, select **Internal Public**, and then click **Save**.</span></span>
    
### <a name="project-1-team-site"></a><span data-ttu-id="e1cd5-201">Sito del team Project 1</span><span class="sxs-lookup"><span data-stu-id="e1cd5-201">Project 1 team site</span></span>

<span data-ttu-id="e1cd5-202">Per creare un sito del team SharePoint Online privato iniziale per un progetto all'interno dell'organizzazione, eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-202">To create a baseline private SharePoint Online team site for a project within the organization, do the following:</span></span>
  
1. <span data-ttu-id="e1cd5-203">Se necessario, accedere al [portale di Office 365](https://portal.office.com) con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-203">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="e1cd5-204">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e1cd5-205">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-205">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="e1cd5-206">Nella pagina **Crea un sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-206">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e1cd5-207">In **Nome del sito** digitare **Project 1**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-207">In **Site name**, type **Project 1**.</span></span> 
    
6. <span data-ttu-id="e1cd5-208">Come **descrizione del sito del team** digitare **Sito SharePoint per Project 1**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-208">In **Team site description,** type **SharePoint site for Project 1**.</span></span>
    
7. <span data-ttu-id="e1cd5-209">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-209">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e1cd5-210">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-210">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="e1cd5-211">Configurare quindi la cartella dei documenti del sito del team Project 1 per l'etichetta Private.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-211">Next, configure the documents folder of the Project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="e1cd5-212">Nella scheda **Project 1: Home** del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-212">In the **Project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="e1cd5-213">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-213">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="e1cd5-214">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-214">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="e1cd5-215">In **Impostazioni - Applica etichetta**, selezionare **Privato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-215">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="marketing-campaigns-team-site"></a><span data-ttu-id="e1cd5-216">Sito del team Campagne marketing</span><span class="sxs-lookup"><span data-stu-id="e1cd5-216">Marketing campaigns team site</span></span>

<span data-ttu-id="e1cd5-217">Per creare un sito del team di SharePoint Online isolato per i dati sensibili delle risorse della campagna di marketing, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-217">To create a sensitive-level isolated SharePoint Online team site for marketing campaign resources, do the following:</span></span>

 
1. <span data-ttu-id="e1cd5-218">Se necessario, accedere al [portale di Office 365](https://portal.office.com) con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-218">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="e1cd5-219">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-219">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e1cd5-220">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-220">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="e1cd5-221">Nella pagina **Crea un sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-221">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e1cd5-222">Come **nome del sito del team** digitare **Marketing campaigns**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-222">In **Team site name**, type **Marketing campaigns**.</span></span>
    
6. <span data-ttu-id="e1cd5-223">Come **descrizione del sito del team** digitare **SharePoint site for marketing campaign resources (sensitive)** (Sito SharePoint per le risorse delle campagne marketing - dati sensibili).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-223">In **Team site description**, type **SharePoint site for marketing campaign resources (sensitive)**.</span></span>
    
7.  <span data-ttu-id="e1cd5-224">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-224">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e1cd5-225">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-225">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="e1cd5-226">Nella nuova scheda **Campagne marketing** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-226">On the new **Marketing campaigns** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="e1cd5-227">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-227">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="e1cd5-228">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-228">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="e1cd5-229">Nella finestra di dialogo **Impostazioni richieste di accesso** deselezionare le caselle di controllo **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito**; digitare **ITAdmin1@**\<nome dell'organizzazione>**.onmicrosoft.com** in **Invia tutte le richieste di accesso**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-229">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="e1cd5-230">Fare clic su **Marketing campaigns - Members** (Campagne di marketing - Membri) nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-230">Click **Marketing campaigns Members** in the list.</span></span>
    
14. <span data-ttu-id="e1cd5-231">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-231">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="e1cd5-232">Nella finestra di dialogo **Condividi** digitare **Personale addetto al marketing**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-232">In the **Share** dialog box, type **Marketing staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="e1cd5-233">Ripetere i passaggi 14 e 15 per l'account utente **Researcher1**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-233">Repeat steps 14 and 15 for the **Researcher1** user account.</span></span>
    
17. <span data-ttu-id="e1cd5-234">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-234">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="e1cd5-235">Fare clic su **Marketing campaigns - Owners** (Campagne di marketing - Proprietari) nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-235">Click **Marketing campaigns Owners** in the list.</span></span>
    
19. <span data-ttu-id="e1cd5-236">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-236">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="e1cd5-237">Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-237">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="e1cd5-238">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-238">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="e1cd5-239">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Marketing campaigns-Home** (Campagne di marketing - Home), quindi chiudere il riquadro **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-239">Close the **People and Groups** tab in your browser, click the **Marketing campaigns-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="e1cd5-240">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-240">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="e1cd5-241">Il gruppo **Marketing campaigns - Members** (Campagne di marketing - Membri) di SharePoint contiene solo il gruppo **Marketing campaigns**, che contiene l'account utente amministratore globale, il gruppo **Marketing staff**, che contiene gli account utente Marketing1 e Marketing2, e l'account utente **Researcher1**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-241">The **Marketing campaigns-Members** SharePoint group contains only the **Marketing campaigns** group (which contains the global administrator user account), the **Marketing staff** group (which contains the Marketing1 and Marketing2 user accounts), and the **Researcher1** user account.</span></span>
    
- <span data-ttu-id="e1cd5-242">Il gruppo **Marketing campaigns - Owners** (Campagne di marketing - Proprietari) di SharePoint contiene solo il gruppo **IT staff**, che a sua volta contiene solo gli account utente ITAdmin1 e ITAdmin2.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-242">The **Marketing campaigns-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="e1cd5-243">Il gruppo **Marketing campaigns - Visitors** (Campagne di marketing - Visitatori) di SharePoint non contiene gruppi né account utente.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-243">The **Marketing campaigns-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="e1cd5-244">I membri non possono modificare le autorizzazioni a livello di sito, operazione che può essere eseguita solo dai membri del gruppo **Marketing campaigns - Owners**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-244">Members cannot modify site-level permissions (this can only be done by members of the **Marketing campaigns-Owners** group).</span></span>
    
- <span data-ttu-id="e1cd5-245">Altri account utente non possono accedere al sito o alle sue risorse, ma possono richiedere l'accesso al sito, che invierà un'e-mail alla cassetta postale dell'account utente ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-245">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="e1cd5-246">Successivamente, configurare la cartella dei documenti del sito del team Campagne marketing per l'etichetta Riservato.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-246">Next, configure the documents folder of the Marketing campaigns team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="e1cd5-247">Nella scheda **Marketing campaigns - Home** (Campagne di marketing - Home) del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-247">In the **Marketing campaigns-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="e1cd5-248">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-248">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="e1cd5-249">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-249">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="e1cd5-250">In **Impostazioni - Applica etichetta** selezionare **Riservato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-250">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="e1cd5-251">Configurare quindi un criterio di prevenzione della perdita di dati che informa gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Sensitive, incluso il sito Marketing campaigns, all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-251">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label, which includes the Marketing campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="e1cd5-252">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com/) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-252">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="e1cd5-253">Nella nuova scheda **Sicurezza Microsoft 365** del browser fare clic su **Criteri > Prevenzione della perdita dei dati**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-253">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="e1cd5-254">Nel riquadro **Home > Prevenzione della perdita dei dati** fare clic su **Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-254">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="e1cd5-255">Nel riquadro **Iniziare con un modello o creare un criterio personalizzato** fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-255">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="e1cd5-256">Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Riservato** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-256">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="e1cd5-257">Nel riquadro **Scegli posizioni** fare clic su **Consenti di scegliere posizioni specifiche** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-257">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e1cd5-258">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange**, **Account di OneDrive** e **Messaggi di chat e canali di Teams**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-258">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e1cd5-259">Nel riquadro **Personalizzare il tipo di contenuti da proteggere**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-259">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="e1cd5-260">Nel riquadro **Scegliere i tipi di contenuto da proteggere**,fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-260">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="e1cd5-261">Nel riquadro **Etichette di conservazione** fare clic su **Aggiungi**, selezionare l'etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-261">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="e1cd5-262">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-262">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="e1cd5-263">Nel riquadro **Personalizzare i tipi di informazioni da proteggere**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-263">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="e1cd5-264">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-264">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="e1cd5-265">Nel riquadro **Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica** fare clic su **Personalizza il testo del suggerimento per i criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-265">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="e1cd5-266">Nella casella di testo digitare o incollare uno dei suggerimenti riportati di seguito, a seconda se è stata implementato Azure Information Protection per proteggere i file estremamente riservati:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-266">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="e1cd5-p104">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="e1cd5-270">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-270">Click **OK**.</span></span>
    
17. <span data-ttu-id="e1cd5-271">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-271">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="e1cd5-272">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-272">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="e1cd5-273">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-273">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="e1cd5-274">Sito del team di strategia aziendale</span><span class="sxs-lookup"><span data-stu-id="e1cd5-274">Company strategy team site</span></span>

<span data-ttu-id="e1cd5-275">Per creare un sito del team di SharePoint Online isolato per i dati altamente riservati delle risorse aziendali strategiche dei dirigenti dell'organizzazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-275">To create an isolated SharePoint Online team site at the highly confidential level for strategic company resources of the chief executives of the organization, do the following:</span></span>
  
1. <span data-ttu-id="e1cd5-276">Se necessario, accedere al [portale di Office 365](https://portal.office.com) con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-276">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="e1cd5-277">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-277">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e1cd5-278">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-278">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="e1cd5-279">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-279">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e1cd5-280">Come **nome del sito del team** digitare **Company strategy** (Strategia aziendale).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-280">In **Team site name**, type **Company strategy**.</span></span>
    
6. <span data-ttu-id="e1cd5-281">Come **descrizione del sito del team** digitare **Sito di SharePoint per la strategia aziendale - Informazioni altamente riservate**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-281">In **Team site description**, type **SharePoint site for company strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="e1cd5-282">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-282">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e1cd5-283">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-283">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="e1cd5-284">Nella nuova scheda **Strategia aziendale** visualizzata nel browser fare clic sull'icona delle impostazioni nella barra degli strumenti, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-284">On the new **Company strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="e1cd5-285">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-285">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="e1cd5-286">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-286">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="e1cd5-287">Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-287">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="e1cd5-288">Fare clic su **Membri strategia aziendale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-288">Click **Company strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="e1cd5-289">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-289">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="e1cd5-290">Nella finestra di dialogo **Condividi** digitare **C-Suite**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-290">In the **Share** dialog box, type **C-Suite**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="e1cd5-291">Fare clic su **Proprietari strategia aziendale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-291">Click **Company strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="e1cd5-292">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-292">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="e1cd5-293">Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-293">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="e1cd5-294">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-294">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="e1cd5-295">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Strategia aziendale-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-295">Close the **People and Groups** tab in your browser, click the **Company strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="e1cd5-296">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-296">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="e1cd5-297">Il gruppo **Company strategy - Members** (Strategia aziendale - Membri) di SharePoint contiene solo il gruppo **C-Suite**, che contiene solo gli account utente CEO, CFO e CIO, e il gruppo **Company strategy**, che contiene solo l'account utente amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-297">The **Company strategy-Members** SharePoint group contains only the **C-Suite** group (which contains only the CEO, CFO, and CIO user accounts) and the **Company strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="e1cd5-298">Il gruppo **Strategia aziendale - Proprietari** di SharePoint contiene solo il gruppo **IT staff**, che a sua volta contiene solo gli account utente ITAdmin1 e ITAdmin2.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-298">The **Company strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="e1cd5-299">Il gruppo **Strategia aziendale - Visitatori** di SharePoint non contiene gruppi né account utente.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-299">The **Company strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="e1cd5-300">I membri non possono modificare le autorizzazioni a livello di sito, operazione che può essere eseguita solo dai membri del gruppo **Company strategy - Owners**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-300">Members cannot modify site-level permissions (this can only be done by members of the **Company strategy-Owners** group).</span></span>
    
- <span data-ttu-id="e1cd5-p105">Gli altri account utente non possono accedere al sito o alle relative risorse né richiedere l'accesso al sito. Le autorizzazioni aggiuntive per il sito devono essere eseguite dall'amministratore globale o da un membro del gruppo **Company strategy - Owners**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Company strategy-Owners** group.</span></span>
    
<span data-ttu-id="e1cd5-303">Successivamente, configurare la cartella dei documenti del sito del team Strategia aziendale per l'etichetta Estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-303">Next, configure the documents folder of the Company strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="e1cd5-304">Nella scheda **Strategia aziendale - Home** del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-304">In the **Company strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="e1cd5-305">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-305">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="e1cd5-306">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-306">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="e1cd5-307">In **Impostazioni - Applica etichetta**, selezionare **Estremamente riservato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-307">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="e1cd5-308">Configurare un criterio di prevenzione della perdita di dati che blocchi gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Highly Confidential, incluso il sito Company strategy, all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-308">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label, which includes the Company strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="e1cd5-309">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com/) con un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-309">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="e1cd5-310">Nella nuova scheda **Sicurezza Microsoft 365** del browser fare clic su **Criteri > Prevenzione della perdita dei dati**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-310">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="e1cd5-311">Nel riquadro **Home > Prevenzione della perdita dei dati** fare clic su **Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-311">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="e1cd5-312">Nel riquadro **Iniziare con un modello o creare un criterio personalizzato** fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-312">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="e1cd5-313">Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Estremamente riservato** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-313">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="e1cd5-314">Nel riquadro **Scegli posizioni** fare clic su **Consenti di scegliere posizioni specifiche** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-314">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e1cd5-315">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange**, **Account di OneDrive** e **Messaggi di chat e canali di Teams**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-315">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e1cd5-316">Nel riquadro **Personalizzare il tipo di contenuti da proteggere**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-316">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="e1cd5-317">Nel riquadro **Scegliere i tipi di contenuto da proteggere**,fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-317">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="e1cd5-318">Nel riquadro **Etichette** fare clic su **Aggiungi**, selezionare l'etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-318">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="e1cd5-319">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-319">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="e1cd5-320">Nel riquadro **Personalizzare i tipi di informazioni da proteggere**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-320">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="e1cd5-321">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-321">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="e1cd5-322">Nel riquadro **Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica** fare clic su **Personalizza il testo del suggerimento per i criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-322">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="e1cd5-323">Nella casella di testo digitare o incollare uno dei suggerimenti riportati di seguito, a seconda se è stata implementato Azure Information Protection per proteggere i file estremamente riservati:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-323">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="e1cd5-p106">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="e1cd5-327">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-327">Click **OK**.</span></span>
    
17. <span data-ttu-id="e1cd5-328">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-328">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="e1cd5-329">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-329">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="e1cd5-330">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-330">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
   
    
<span data-ttu-id="e1cd5-331">Seguire quindi le istruzioni in [Attivare Azure RMS dall'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-331">Next, follow the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="e1cd5-332">Successivamente, configurare Azure Information Protection con nuovi criteri e un'etichetta secondaria con ambito per il gruppo C-Suite per la protezione e le autorizzazioni con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e1cd5-332">Next, configure Azure Information Protection with a new policy and sub-label scoped for the C-Suite group for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="e1cd5-333">Se necessario, accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-333">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="e1cd5-334">In un'altra scheda del browser, accedere al portale di Azure ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-334">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="e1cd5-335">Se è la prima volta che viene configurato Azure Information Protection, consultare queste [istruzioni](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span><span class="sxs-lookup"><span data-stu-id="e1cd5-335">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>
    
4. <span data-ttu-id="e1cd5-336">Nel riquadro dell'elenco, fare clic su **Ulteriori servizi**, digitare **Informazioni**, quindi fare clic su **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-336">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="e1cd5-337">Fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-337">Click **Labels**.</span></span>
    
6. <span data-ttu-id="e1cd5-338">Fare clic con il pulsante destro del mouse sull'etichetta **Estremamente riservato**, quindi su **Aggiungi un'etichetta secondaria**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-338">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="e1cd5-339">Digitare **Membri C-Suite** in **Nome** e **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-339">Type **C-Suite members** in **Name** and **Description**.</span></span>
    
8. <span data-ttu-id="e1cd5-340">In **Configurare le autorizzazioni per documenti e messaggi di posta elettronica contenenti questa etichetta** fare clic su **Proteggi**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-340">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="e1cd5-341">Nella sezione **Protezione** fare clic su **Azure (chiave cloud)**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-341">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="e1cd5-342">Nel pannello **Protezione** fare clic su **+ Aggiungi autorizzazioni** in **Impostazioni di protezione**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-342">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="e1cd5-343">Nel pannello **Aggiungi autorizzazioni**, in **Specifica utenti e gruppi** fare clic su **+ Sfoglia la directory**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-343">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="e1cd5-344">Nel riquadro **Utenti e gruppi di AAD** selezionare **C-Suite** e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-344">On the **AAD Users and Groups** pane, select **C-Suite**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="e1cd5-345">In **Scegliere le autorizzazioni dal set di impostazioni o imposta personalizzato** fare clic su **Personalizza**, quindi sulla casella **Visualizza diritti**, **Modifica contenuto**, \*\* Salva\*\*, **Rispondi** e **Rispondi a tutti**</span><span class="sxs-lookup"><span data-stu-id="e1cd5-345">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="e1cd5-346">Fare due volte clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-346">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="e1cd5-347">Nel pannello **Etichetta secondaria** fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-347">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="e1cd5-348">Nel pannello **Azure Information Protection** fare clic su **Criteri > + Aggiungi un nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-348">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="e1cd5-349">Digitare **CompanyStrategy** in **Nome criterio** e **Documenti nel sito del team di strategia aziendale** in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-349">Type **CompanyStrategy** in **Policy name** and **Documents in the Company strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="e1cd5-350">Fare clic su **Selezionare gli utenti o i gruppi a cui viene applicato il criterio > Utenti/Gruppi**, quindi selezionare **C-Suite**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-350">Click **Select which users or groups get this policy > User/Groups**, and then select **C-Suite**.</span></span>
    
19. <span data-ttu-id="e1cd5-351">Fare clic su **Seleziona > OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-351">Click **Select > OK**.</span></span>

20. <span data-ttu-id="e1cd5-p107">Fare clic su **Aggiungi o rimuovi etichette**. Nel riquadro **Criteri: Aggiungere o rimuovere etichette** fare clic su **C-Suite**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-p107">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **C-Suite**, and then click **OK**.</span></span>   

21. <span data-ttu-id="e1cd5-354">Fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-354">Click **Save**, and then click **OK**.</span></span>
    
<span data-ttu-id="e1cd5-355">Per proteggere un documento con Azure Information Protection e la nuova etichetta, è necessario [installare il client di Azure Information Protection in un computer di test](https://docs.microsoft.com/information-protection/rms-client/install-client-app), installare Office dall'interfaccia di amministrazione e quindi accedere da Microsoft Word con un account del gruppo **C-Suite** dell'abbonamento di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-355">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **C-Suite** group of your trial subscription.</span></span>
  
<span data-ttu-id="e1cd5-356">A questo punto si è pronti a creare documenti in questi quattro siti e a testare l'accesso ai siti usando diversi account utente della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-356">You are now ready to create documents in these four sites and test access to them with various user accounts in your trial subscription.</span></span>
  
<span data-ttu-id="e1cd5-357">Di seguito è riportata la configurazione completa per tutti i quattro siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-357">Here is the overall configuration for all four SharePoint Online team sites.</span></span>
  
![Tutti i quattro siti del team nell’ambiente di sviluppo/test protetto di SharePoint Online.](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a><span data-ttu-id="e1cd5-359">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e1cd5-359">Next step</span></span>

<span data-ttu-id="e1cd5-360">Quando si è pronti per la distribuzione di produzione dei siti di SharePoint Online protetti, vedere [Proteggere siti e file di SharePoint Online](secure-sharepoint-online-sites-and-files.md) per informazioni dettagliate e collegamenti ad articoli relativi alle procedure di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e1cd5-360">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1cd5-361">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1cd5-361">See Also</span></span>

[<span data-ttu-id="e1cd5-362">Protezione di file e siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e1cd5-362">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="e1cd5-363">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="e1cd5-363">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="e1cd5-364">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili</span><span class="sxs-lookup"><span data-stu-id="e1cd5-364">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




