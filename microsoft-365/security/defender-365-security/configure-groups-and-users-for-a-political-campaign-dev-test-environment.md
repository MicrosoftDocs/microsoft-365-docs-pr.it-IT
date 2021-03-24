---
title: Configurare gruppi e utenti - Ambiente di sviluppo/test per la campagna politica
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Riepilogo: creare sottoscrizioni di valutazione di Office 365 ed Enterprise Mobility + Security (EMS) con utenti e gruppi per un ambiente di sviluppo/test di una campagna politica.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e21cdfb0aabbdb10397d6d16c879756449a498e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065378"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="0d9b9-103">Configurare gruppi e utenti per un ambiente di sviluppo/test per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="0d9b9-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d9b9-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="0d9b9-104">**Applies to**</span></span>
- [<span data-ttu-id="0d9b9-105">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="0d9b9-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="0d9b9-106">**Riepilogo:** creare sottoscrizioni di valutazione di Office 365 ed Enterprise Mobility + Security (EMS) con utenti e gruppi per un ambiente di sviluppo/test di una campagna politica.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="0d9b9-107">Attenersi alle istruzioni in questo articolo per creare un ambiente di sviluppo/test che include account utente e gruppi semplificati per la soluzione [Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="0d9b9-108">Fase 1: creare l'ambiente di sviluppo/test di Office 365</span><span class="sxs-lookup"><span data-stu-id="0d9b9-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="0d9b9-109">In questa fase si ottengono le sottoscrizioni di valutazione per Office 365 E5 ed Enterprise Mobility + Security (EMS) E5 per un'organizzazione fittizia che rappresenta una campagna politica.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="0d9b9-110">Per prima cosa, seguire le istruzioni in **Fase 2** di [Configurazione di base semplificata](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="0d9b9-111">Iscriversi quindi per l’abbonamento di prova di EMS E5 e aggiungerlo alla stessa organizzazione come abbonamento di prova.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="0d9b9-112">Se necessario, accedere all'interfaccia di amministrazione con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="0d9b9-113">Per informazioni, vedere [Dove accedere](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="0d9b9-114">Scegliere il riquadro **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="0d9b9-115">Nella scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Fatturazione > Servizi di acquisto** nella barra di spostamento sinistra.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="0d9b9-p102">Nella pagina **Acquisto di servizi**, individuare la voce **Enterprise Mobility + Security E5**. Posizionare il puntatore del mouse su di essa e fare clic su **Avvia la versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="0d9b9-118">Nella pagina **Conferma l'ordine**, fare clic su **Prova adesso**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="0d9b9-119">Nella pagina **Ricevuta ordine**, fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="0d9b9-120">Abilitare quindi la licenza EMS E5 per l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="0d9b9-121">Nella scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Utenti > Utenti attivi** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="0d9b9-122">Fare clic sull'account amministratore globale e quindi su **Modifica** per le **licenze del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="0d9b9-123">Nel riquadro **Licenze per i prodotti**, impostare la licenza per i prodotti di **Enterprise Mobility + Security E5** su **Attiva**, fare clic su **Salva** e quindi fare doppio clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="0d9b9-124">Fase 2: creare e configurare i gruppi di Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="0d9b9-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="0d9b9-125">In questa fase, vengono creati e configurati i gruppi di Azure AD per la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="0d9b9-126">Innanzitutto, creare un set di gruppi per una campagna politica tipica con il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="0d9b9-127">In un'altra scheda del browser, accedere al portale di Azure <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="0d9b9-128">Se necessario, accedere con le credenziali dell'account amministratore globale della sottoscrizione di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="0d9b9-129">Nel portale di Azure fare clic su **Azure Active Directory > Utenti e gruppi > Tutti i gruppi**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="0d9b9-130">Eseguire la procedura seguente per ciascun nome del gruppo nell'elenco riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0d9b9-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="0d9b9-131">Personale senior e strategico</span><span class="sxs-lookup"><span data-stu-id="0d9b9-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="0d9b9-132">IT staff</span><span class="sxs-lookup"><span data-stu-id="0d9b9-132">IT staff</span></span>

   - <span data-ttu-id="0d9b9-133">Personale di analisi</span><span class="sxs-lookup"><span data-stu-id="0d9b9-133">Analytics staff</span></span>

   - <span data-ttu-id="0d9b9-134">Personale di base regolare</span><span class="sxs-lookup"><span data-stu-id="0d9b9-134">Regular core staff</span></span>

   - <span data-ttu-id="0d9b9-135">Personale delle operazioni</span><span class="sxs-lookup"><span data-stu-id="0d9b9-135">Operations staff</span></span>

   - <span data-ttu-id="0d9b9-136">Personale di campo</span><span class="sxs-lookup"><span data-stu-id="0d9b9-136">Field staff</span></span>

1. <span data-ttu-id="0d9b9-137">Nel pannello **Tutti i gruppi** fare clic su **+ Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="0d9b9-138">Digitare il nome del gruppo dall'elenco in **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="0d9b9-139">Selezionare **Utente dinamico** in **Appartenenza**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="0d9b9-140">Selezionare **Sì** per **Abilitare le funzionalità di Office**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="0d9b9-141">Fare clic su **Aggiungere query dinamica**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="0d9b9-142">Selezionare **Reparto** in **Dove aggiungere utenti**</span><span class="sxs-lookup"><span data-stu-id="0d9b9-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="0d9b9-143">Nel campo successivo, selezionare **Uguale a**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="0d9b9-144">Nel campo successivo, digitare il nome del gruppo dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="0d9b9-145">Fare clic su **Aggiungi query** e quindi su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="0d9b9-146">Fare clic su **Utenti e gruppi - Tutti i gruppi**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="0d9b9-147">Quindi, configurare i gruppi in modo che ai membri vengano automaticamente assegnate licenze di Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="0d9b9-148">Nel portale di Azure fare clic su **Azure Active Directory > Licenze > Tutti i prodotti**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="0d9b9-149">Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="0d9b9-150">Nel pannello **Assegnare licenza** fare clic su **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="0d9b9-151">Nell'elenco dei gruppi, selezionare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0d9b9-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="0d9b9-152">Personale di analisi</span><span class="sxs-lookup"><span data-stu-id="0d9b9-152">Analytics staff</span></span>

   - <span data-ttu-id="0d9b9-153">Personale di campo</span><span class="sxs-lookup"><span data-stu-id="0d9b9-153">Field staff</span></span>

   - <span data-ttu-id="0d9b9-154">Personale IT</span><span class="sxs-lookup"><span data-stu-id="0d9b9-154">IT staff</span></span>

   - <span data-ttu-id="0d9b9-155">Personale delle operazioni</span><span class="sxs-lookup"><span data-stu-id="0d9b9-155">Operations staff</span></span>

   - <span data-ttu-id="0d9b9-156">Personale di base regolare</span><span class="sxs-lookup"><span data-stu-id="0d9b9-156">Regular core staff</span></span>

   - <span data-ttu-id="0d9b9-157">Personale senior e strategico</span><span class="sxs-lookup"><span data-stu-id="0d9b9-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="0d9b9-158">Fare clic su **Seleziona**, quindi su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="0d9b9-159">Chiudere la scheda del portale di Azure nel browser.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="0d9b9-160">Fase 3: Aggiungere gli account utente</span><span class="sxs-lookup"><span data-stu-id="0d9b9-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="0d9b9-161">In questa fase, si aggiungono gli account utente di esempio per la campagna politica.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="0d9b9-162">Successivamente, [connettersi con il modulo di Azure Active Directory PowerShell for Graph](../../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="0d9b9-163">Successivamente, inserire il nome dell'organizzazione, la posizione e una password comune; eseguire quindi questi comandi dal prompt dei comandi di PowerShell o Integrated Script Environment (ISE):</span><span class="sxs-lookup"><span data-stu-id="0d9b9-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="0d9b9-p104">L'utilizzo di una password comune in questo caso è per rendere automatica e facile la configurazione per un ambiente di sviluppo/test. Non è una scelta consigliata per sottoscrizioni di produzione. Effettuando l'accesso con ognuno di questi nuovi account utente, verrà richiesto di modificare la password.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="0d9b9-167">Seguire questi passaggi per verificare che l'appartenenza ai gruppi dinamici e le licenze basate su gruppi funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="0d9b9-168">Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="0d9b9-169">Dalla nuova scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="0d9b9-170">Nell'elenco di utenti, fare clic su **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="0d9b9-171">Nel riquadro che elenca le proprietà dell'account utente **Candidato**, verificare che:</span><span class="sxs-lookup"><span data-stu-id="0d9b9-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="0d9b9-172">È un membro del gruppo **Personale senior e strategico** (in **Appartenenze a gruppi**).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="0d9b9-173">Dispone delle licenze **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** (in **Licenze per i prodotti**).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="0d9b9-174">Chiudere il riquadro dell'account utente **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="0d9b9-175">Registrare i valori per consultarli in futuro</span><span class="sxs-lookup"><span data-stu-id="0d9b9-175">Record values for future reference</span></span>

<span data-ttu-id="0d9b9-176">Registrare questi valori per utilizzarli con le sottoscrizioni di valutazione di Office 365 ed EMS per questo ambiente di sviluppo/test:</span><span class="sxs-lookup"><span data-stu-id="0d9b9-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="0d9b9-177">Nome dell'organizzazione della sottoscrizione di valutazione:</span><span class="sxs-lookup"><span data-stu-id="0d9b9-177">Your trial subscription organization name:</span></span> ![Sottolineato](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="0d9b9-179">Ad esempio, per il nome di dominio della sottoscrizione di valutazione di contoso.onmicrosoft.com, il nome dell'azienda è "contoso".</span><span class="sxs-lookup"><span data-stu-id="0d9b9-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="0d9b9-180">Nome amministratore globale:</span><span class="sxs-lookup"><span data-stu-id="0d9b9-180">The global administrator name:</span></span> ![Sottolineato](../../media/Common-Images/TableLine.png)<span data-ttu-id="0d9b9-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0d9b9-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="0d9b9-183">Registrare la password per l'account e la password iniziale comune per gli altri account utente in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="0d9b9-184">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0d9b9-184">Next step</span></span>

<span data-ttu-id="0d9b9-185">Creare quattro tipi diversi di siti del team di SharePoint Online nell’ambiente di sviluppo/test con [Creare siti del team in un ambiente di sviluppo/test per la campagna politica](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d9b9-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d9b9-186">See also</span></span>

[<span data-ttu-id="0d9b9-187">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili</span><span class="sxs-lookup"><span data-stu-id="0d9b9-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="0d9b9-188">Creare siti del team in un ambiente di sviluppo/test per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="0d9b9-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="0d9b9-189">Guida al lab test (TLG) per adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="0d9b9-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="0d9b9-190">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="0d9b9-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)