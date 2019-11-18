---
title: Configurazione di base
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Utilizzare questa guida al lab di test per creare un ambiente di testing semplificato per testare Microsoft 365 Enterprise.
ms.openlocfilehash: c654dc80620b98d09cf508e309d4410d9cf4a4dc
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639916"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="0920e-103">La configurazione di base</span><span class="sxs-lookup"><span data-stu-id="0920e-103">The lightweight base configuration</span></span>

<span data-ttu-id="0920e-104">Questo articolo fornisce istruzioni dettagliate su come creare un ambiente semplificato con un abbonamento Microsoft 365 E5 e un computer che esegue Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0920e-104">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![Ambiente di testing semplificato di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="0920e-106">Utilizzare l'ambiente risultante per testare le funzionalità di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="0920e-106">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="0920e-108">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0920e-108">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="0920e-109">Fase 1: creare la sottoscrizione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="0920e-109">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="0920e-110">Si inizia con un abbonamento di valutazione a Office 365 E5 e quindi si aggiunge l'abbonamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-110">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="0920e-111">Per avviare la sottoscrizione di valutazione di Office 365 E5, è necessario innanzitutto un nome di società fittizia e un nuovo account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0920e-111">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="0920e-p101">Si consiglia di utilizzare una variante del nome aziendale Contoso per il nome dell'azienda, che è un nome aziendale fittizio utilizzato nel contenuto di esempio di Microsoft, ma non è obbligatorio. Registrare il nome della società fittizia qui: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="0920e-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="0920e-p102">Per registrare un nuovo account Microsoft, andare su [https://outlook.com](https://outlook.com) e creare un account con un nuovo account di posta elettronica e indirizzo. Utilizzare questo account per iscriversi a Office 365.</span><span class="sxs-lookup"><span data-stu-id="0920e-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="0920e-116">Registrare il nome e cognome del nuovo account qui: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="0920e-116">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="0920e-117">Registrare l'indirizzo e-mail del nuovo account qui: ![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="0920e-117">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="0920e-118">Registrare una sottoscrizione di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="0920e-118">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="0920e-119">Aprire il browser Internet nel computer e passare a [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="0920e-119">For the lightweight Office 365 dev/test environment, open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="0920e-120">Nella pagina **Benvenuto, vogliamo conoscerti meglio**, specificare:</span><span class="sxs-lookup"><span data-stu-id="0920e-120">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="0920e-121">La posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="0920e-121">Your physical location</span></span>
    
  - <span data-ttu-id="0920e-122">Nome e cognome del nuovo account Microsoft</span><span class="sxs-lookup"><span data-stu-id="0920e-122">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="0920e-123">Il nuovo indirizzo di account di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0920e-123">Your new email account address</span></span>
    
  - <span data-ttu-id="0920e-124">Un numero di telefono dell'ufficio</span><span class="sxs-lookup"><span data-stu-id="0920e-124">A business phone number</span></span>
    
  - <span data-ttu-id="0920e-125">Il nome dell'azienda fittizia</span><span class="sxs-lookup"><span data-stu-id="0920e-125">Your fictional company name</span></span>
    
  - <span data-ttu-id="0920e-126">Dimensioni dell'organizzazione comprese tra 250-999 persone</span><span class="sxs-lookup"><span data-stu-id="0920e-126">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="0920e-127">Fare clic su **Ultimo passaggio**.</span><span class="sxs-lookup"><span data-stu-id="0920e-127">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="0920e-128">Nella pagina **Crea ID utente**, digitare un nome utente in base al nuovo indirizzo di posta elettronica, il nome della società fittizia dopo il segno @ (rimuovere tutti gli spazi nel nome), quindi una password (due volte) del nuovo account di Office 365. </span><span class="sxs-lookup"><span data-stu-id="0920e-128">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="0920e-129">Annotare la password in un posto sicuro.</span><span class="sxs-lookup"><span data-stu-id="0920e-129">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="0920e-130">Registrare il nome della società fittizia, a cui fare riferimento con **nome dell'organizzazione**, qui: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="0920e-130">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="0920e-131">Fare clic su **Crea account**.</span><span class="sxs-lookup"><span data-stu-id="0920e-131">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="0920e-p103">Nella pagina **Dimostra che non sei un robot**, digitare il numero di telefono di un telefono che riceve SMS, quindi fare clic su **Inviami un SMS**.</span><span class="sxs-lookup"><span data-stu-id="0920e-p103">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="0920e-134">Immettere il codice di verifica del messaggio di testo ricevuto, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0920e-134">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0920e-135">Registrare l'URL della pagina di accesso qui (selezionare e copiare): ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="0920e-135">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="0920e-136">Registrare l'ID utente qui (selezionare e copiare): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0920e-136">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="0920e-137">Questo valore verrà denominato **Nome amministratore globale di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="0920e-137">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="0920e-138">Quando viene visualizzato **Sei pronto per partire**, selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="0920e-138">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="0920e-139">Nella pagina successiva, attendere che Office 365 completi la configurazione e che siano disponibili tutti i riquadri.</span><span class="sxs-lookup"><span data-stu-id="0920e-139">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="0920e-140">Dovrebbe essere visualizzata la pagina principale del portale di Office 365 dalla quale è possibile accedere ai servizi di Office e all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0920e-140">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="0920e-141">È stato creato un abbonamento di valutazione a Office 365 in modo che l'ambiente di sviluppo/test includa un tenant di Azure AD diverso da quelli a pagamento attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="0920e-141">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="0920e-142">Questa separazione indica che è possibile aggiungere e rimuovere utenti e gruppi nel tenant di test senza influire sugli abbonamenti di produzione.</span><span class="sxs-lookup"><span data-stu-id="0920e-142">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="0920e-143">Fase 2: configurare l'abbonamento di valutazione a Office 365</span><span class="sxs-lookup"><span data-stu-id="0920e-143">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="0920e-144">In questa fase è possibile configurare l'abbonamento a Office 365 con altri utenti e assegnare loro le licenze di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-144">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="0920e-145">Seguire le istruzioni in [Connettersi a Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) per connettersi all'abbonamento a Office 365 con il modulo Azure Active Directory PowerShell for Graph dal proprio computer.</span><span class="sxs-lookup"><span data-stu-id="0920e-145">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="0920e-146">Nella finestra di dialogo Richiesta credenziali di Windows PowerShell, digitare il nome dell'amministratore globale Office 365 (ad esempio: jdoe@contosotoycompany.onmicrosoft.com) e la password.</span><span class="sxs-lookup"><span data-stu-id="0920e-146">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="0920e-147">Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri, una password comune di account e quindi eseguire i comandi seguenti dal prompt di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0920e-147">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="0920e-148">L'uso di una password comune qui consente l'automazione e agevola la configurazione per un ambiente di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="0920e-148">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="0920e-149">Ovviamente, questo approccio è sconsigliato per le sottoscrizioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="0920e-149">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="0920e-150">Registrare informazioni chiave per riferimenti futuri</span><span class="sxs-lookup"><span data-stu-id="0920e-150">Record key information for future reference</span></span>

<span data-ttu-id="0920e-151">Si consiglia di stampare questo articolo per registrare le informazioni specifiche necessarie per questo ambiente nei 30 giorni dell'abbonamento di valutazione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="0920e-151">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription. You can easily extend the trail subscription for another 30 days. For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span> <span data-ttu-id="0920e-152">È possibile estendere l'abbonamento di prova per altri 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0920e-152">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="0920e-153">Per un ambiente di sviluppo/test permanente, creare un nuovo abbonamento a pagamento con un tenant di Azure AD separato e un numero limitato di licenze.</span><span class="sxs-lookup"><span data-stu-id="0920e-153">For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span>

<span data-ttu-id="0920e-154">Registrare questi valori:</span><span class="sxs-lookup"><span data-stu-id="0920e-154">Record these values:</span></span>
  
- <span data-ttu-id="0920e-155">Nome amministratore globale di Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (dal passaggio 9 della fase 2)</span><span class="sxs-lookup"><span data-stu-id="0920e-155">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="0920e-156">Annotare anche la password dell'account in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="0920e-156">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="0920e-157">Nome dell'organizzazione della sottoscrizione di valutazione: ![](./media/Common-Images/TableLine.png) onmicrosoft.com (dal passaggio 4 della fase 2)</span><span class="sxs-lookup"><span data-stu-id="0920e-157">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="0920e-158">Per elencare gli account di User 2, User 3, User 4, e User 5, eseguire i comandi seguenti dal modulo di Microsoft Azure Active Directory per il prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0920e-158">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="0920e-159">Registrare i nomi degli account qui:</span><span class="sxs-lookup"><span data-stu-id="0920e-159">Record the account names here:</span></span>
    
  - <span data-ttu-id="0920e-160">Nome account utente User 2: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0920e-160">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="0920e-161">Nome account utente User 3: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0920e-161">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="0920e-162">Nome account utente User 4: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0920e-162">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="0920e-163">Nome account utente User 5: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0920e-163">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="0920e-164">Registrare anche la password comune degli account in un posto sicuro.</span><span class="sxs-lookup"><span data-stu-id="0920e-164">Also record the passwords for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-devtest-environment"></a><span data-ttu-id="0920e-165">Uso di un ambiente di sviluppo/test di Office 365</span><span class="sxs-lookup"><span data-stu-id="0920e-165">Phase 1: Create an Office 365 dev/test environment</span></span>

<span data-ttu-id="0920e-166">Se tutto ciò che serve è un ambiente di sviluppo/test di Office 365, è possibile fermarsi qui.</span><span class="sxs-lookup"><span data-stu-id="0920e-166">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="0920e-167">Per altre guide al lab di test valide sia per Office 365 che per Microsoft 365, vedere [Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="0920e-167">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="0920e-168">Fase 3: aggiungere un abbonamento di valutazione a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0920e-168">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="0920e-169">In questa fase è possibile sottoscrivere un abbonamento di valutazione a Microsoft 365 E5 e aggiungerlo alla stessa organizzazione dell'abbonamento di valutazione a Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-169">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="0920e-170">Aggiungere prima l'abbonamento di valutazione a Microsoft 365 E5 e assegnare una licenza di Microsoft 365 all'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0920e-170">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="0920e-171">Con un'istanza privata di un browser Internet, accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0920e-171">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="0920e-172">Nella pagina dell'**interfaccia di amministrazione di Microsoft 365** fare clic su **Fatturazione > Acquisto di servizi** nella barra di spostamento sinistra.</span><span class="sxs-lookup"><span data-stu-id="0920e-172">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="0920e-173">Nella pagina **Acquisto di servizi** individuare la voce **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="0920e-173">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="0920e-174">Posizionare il puntatore del mouse su di essa e fare clic su **Avvia valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="0920e-174">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="0920e-175">Nella pagina **Valutazione di Microsoft 365 E5** scegliere di ricevere una chiamata o un SMS, immettere il numero di telefono, quindi fare clic su **Inviami un SMS** o **Chiamami**.</span><span class="sxs-lookup"><span data-stu-id="0920e-175">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="0920e-176">Nella pagina **Conferma l'ordine**, fare clic su **Prova adesso**.</span><span class="sxs-lookup"><span data-stu-id="0920e-176">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="0920e-177">Nella pagina **Ricevuta ordine**, fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="0920e-177">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="0920e-178">Nell'interfaccia di amministrazione di Microsoft 365 fare clic su **Utenti attivi**, quindi sull'account dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="0920e-178">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="0920e-179">Per **Licenze di prodotti** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0920e-179">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="0920e-180">Disattivare la licenza per Office 365 Enterprise E5 e attivare la licenza per Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-180">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="0920e-181">Fare clic su **Salva > Chiudi > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0920e-181">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="0920e-182">Successivamente, ripetere i passaggi da 8 a 11 della procedura precedente per tutti gli altri account (Utente 2, Utente 3, Utente 4 e Utente 5).</span><span class="sxs-lookup"><span data-stu-id="0920e-182">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0920e-183">L'abbonamento di valutazione a Microsoft 365 E5 dura 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0920e-183">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="0920e-184">Per un ambiente di test permanente, convertire questo abbonamento di valutazione in uno a pagamento con un numero limitato di licenze.</span><span class="sxs-lookup"><span data-stu-id="0920e-184">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="0920e-185">A questo punto, l'ambiente di test include:</span><span class="sxs-lookup"><span data-stu-id="0920e-185">Your test environment now has:</span></span>
  
- <span data-ttu-id="0920e-186">Un abbonamento di valutazione a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-186">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="0920e-187">Tutti gli account utente appropriati (solo l'amministratore globale o tutti e cinque gli account utente) sono abilitati per l'uso di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-187">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="0920e-188">Di seguito è riportata la configurazione risultante che consente di aggiungere Microsoft 365 E5 e include sia Office 365 che Enterprise Security + Management (EMS).</span><span class="sxs-lookup"><span data-stu-id="0920e-188">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Fase 2 dell'ambiente di testing di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="0920e-190">Fase 4: creare un computer con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0920e-190">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="0920e-191">In questa fase è necessario creare un computer autonomo con sistema operativo Windows 10 Enterprise, come un computer fisico, una macchina virtuale o una macchina virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="0920e-191">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="0920e-192">Computer fisico</span><span class="sxs-lookup"><span data-stu-id="0920e-192">Physical computer</span></span>

<span data-ttu-id="0920e-p109">Procurarsi un personal computer e installarvi Windows 10 Enterprise. È possibile scaricare la versione di valutazione di Windows 10 Enterprise [qui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="0920e-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="0920e-195">Macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="0920e-195">Virtual machine</span></span>

<span data-ttu-id="0920e-p110">Creare una macchina virtuale utilizzando l'hypervisor scelto e installarvi Windows 10 Enterprise. È possibile scaricare la versione di valutazione di Windows 10 Enterprise [qui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="0920e-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="0920e-198">Macchina virtuale in Azure</span><span class="sxs-lookup"><span data-stu-id="0920e-198">Virtual machine in Azure</span></span>

<span data-ttu-id="0920e-p111">Per creare una macchina virtuale con Windows 10 in Microsoft Azure, ***è necessario disporre di una sottoscrizione basata su Visual Studio***, che abbia accesso all'immagine per Windows 10 Enterprise. Altri tipi di sottoscrizioni di Azure, ad esempio le sottoscrizioni di valutazione e quelle a pagamento, non hanno accesso a tale immagine. Per le informazioni più aggiornate, vedere [Utilizzare un client Windows in Azure per gli scenari di sviluppo/test](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="0920e-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0920e-p112">I seguenti comandi consentono di utilizzare la versione più recente di Azure PowerShell. Vedere [Panoramica dei cmdlet di Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Questi set di comandi creano una macchina virtuale con Windows 10 Enterprise denominata WIN10 e tutte le infrastrutture relative necessarie, tra cui un gruppo di risorse, un account di archiviazione e una rete virtuale. Se si ha già familiarità con i servizi di infrastruttura di Azure, si consiglia di adattare queste istruzioni all’infrastruttura attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="0920e-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="0920e-206">Innanzitutto, avviare un prompt di Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0920e-206">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="0920e-207">Accedere al proprio account Azure con il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="0920e-207">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="0920e-208">Ottenere il nome della sottoscrizione utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="0920e-208">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="0920e-p113">Impostare la sottoscrizione di Azure. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri \< e >, con il nome corretto.</span><span class="sxs-lookup"><span data-stu-id="0920e-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="0920e-p114">Quindi, creare un nuovo gruppo di risorse. Per definire un nome del gruppo di risorse univoco, utilizzare questo comando per creare un elenco di gruppi di risorse esistenti.</span><span class="sxs-lookup"><span data-stu-id="0920e-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="0920e-p115">Creare il nuovo gruppo di risorse con questi comandi. Sostituire tutto il testo racchiuso tra virgolette, compresi i caratteri \< e >, con i nomi corretti.</span><span class="sxs-lookup"><span data-stu-id="0920e-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="0920e-p116">Successivamente, creare una nuova rete virtuale e la macchina virtuale con WIN10 con questi comandi. Quando richiesto, fornire il nome e la password dell'account Administrator locale per WIN10 e archiviare questi elementi in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="0920e-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="0920e-217">Fase 5: aggiungere il proprio computer con Windows 10 ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="0920e-217">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="0920e-218">Dopo che la macchina virtuale o fisica con Windows 10 Enterprise è stata creata, accedere con un account amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="0920e-218">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0920e-219">Per una macchina virtuale in Azure, connettersi seguendo [queste istruzioni](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="0920e-219">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="0920e-220">Successivamente, aggiungere il computer WIN10 al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-220">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="0920e-221">Nel desktop del computer WIN10, fare clic su **Start > Impostazioni > Account > Accedi all'azienda o all'istituto di istruzione > Connetti**.</span><span class="sxs-lookup"><span data-stu-id="0920e-221">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="0920e-222">Nella finestra di dialogo **Configura un account aziendale o dell'istituto di istruzione**, fare clic su **Aggiungi il dispositivo ad Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0920e-222">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="0920e-223">In **Account aziendale o dell'istituto di istruzione** digitare il nome dell'account di amministratore globale dell'abbonamento a Microsoft 365, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0920e-223">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="0920e-224">In **Immettere la password**, digitare la password dell’account Administrator locale, quindi fare clic su **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0920e-224">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="0920e-225">Quando viene richiesto di verificare che l’organizzazione sia la propria, fare clic su **Aggiungi**, quindi fare clic su **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="0920e-225">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="0920e-226">Chiudere la finestra delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0920e-226">Close the settings window.</span></span>
    
<span data-ttu-id="0920e-227">Successivamente, installare Office 365 ProPlus nel computer WIN10</span><span class="sxs-lookup"><span data-stu-id="0920e-227">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="0920e-228">Aprire il browser Microsoft Edge e accedere al portale di Office con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0920e-228">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="0920e-229">Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0920e-229">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="0920e-230">Nella scheda **Microsoft Office Home** fare clic su **Installa Office**.</span><span class="sxs-lookup"><span data-stu-id="0920e-230">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="0920e-231">Quando viene richiesto di eseguire operazioni, fare clic su **Esegui**, quindi fare clic su **Sì** per **Controllo dell'account utente**.</span><span class="sxs-lookup"><span data-stu-id="0920e-231">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="0920e-p118">Attendere che l’installazione di Office venga completata. Quando viene visualizzato **La configurazione è completata**, fare clic su **Chiudi** due volte.</span><span class="sxs-lookup"><span data-stu-id="0920e-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="0920e-234">Di seguito è riportato l'ambiente risultante.</span><span class="sxs-lookup"><span data-stu-id="0920e-234">Here is your resulting configuration.</span></span>

![Fase 5 dell'ambiente di testing di Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="0920e-236">Comprende il computer WIN10 che:</span><span class="sxs-lookup"><span data-stu-id="0920e-236">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="0920e-237">È stato aggiunto al tenant di Azure AD dell'abbonamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0920e-237">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="0920e-238">È stato registrato come dispositivo Azure AD in Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="0920e-238">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="0920e-239">Include l'installazione di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="0920e-239">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="0920e-240">A questo punto è possibile sperimentare le funzionalità aggiuntive di [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="0920e-240">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0920e-241">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0920e-241">Next steps</span></span>

<span data-ttu-id="0920e-242">Esplorare questi altri insiemi di guide al lab test:</span><span class="sxs-lookup"><span data-stu-id="0920e-242">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="0920e-243">Identità</span><span class="sxs-lookup"><span data-stu-id="0920e-243">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="0920e-244">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="0920e-244">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="0920e-245">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="0920e-245">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="0920e-246">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0920e-246">See also</span></span>

[<span data-ttu-id="0920e-247">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0920e-247">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0920e-248">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0920e-248">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0920e-249">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0920e-249">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
