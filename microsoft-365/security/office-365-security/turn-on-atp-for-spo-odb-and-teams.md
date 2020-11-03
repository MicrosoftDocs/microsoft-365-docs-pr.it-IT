---
title: Attiva Microsoft Defender per Office 365-SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Informazioni su come abilitare ATP per SharePoint, OneDrive e teams, inclusa la procedura per impostare gli avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69cb7ffcfb06d5ccda915004a512e7eefc6eb56e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844273"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4ac6b-103">Attivare ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac6b-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4ac6b-104">Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dalla condivisione involontaria di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-104">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="4ac6b-105">Per ulteriori informazioni, vedere [ATP for SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4ac6b-106">In questo articolo sono riportati i passaggi per l'abilitazione e la configurazione di ATP per SharePoint, OneDrive e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4ac6b-107">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="4ac6b-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4ac6b-108">Aprire il Centro sicurezza e conformità in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="4ac6b-109">Per passare direttamente alla pagina degli **allegati sicuri di ATP** , Apri <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="4ac6b-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="4ac6b-110">Per abilitare ATP per SharePoint, OneDrive e Microsoft teams, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="4ac6b-111">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4ac6b-112">Per utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi, è necessario essere membri dell' [amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o dei ruoli di [amministratore di SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure ad.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="4ac6b-113">Verificare che la registrazione di controllo sia abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="4ac6b-114">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="4ac6b-115">Consenti fino a 30 minuti per rendere effettive le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4ac6b-116">Passaggio 1: utilizzare il Centro sicurezza & conformità per abilitare ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac6b-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="4ac6b-117">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP** e fare clic su **Impostazioni globali**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , and click **Global settings**.</span></span>

2. <span data-ttu-id="4ac6b-118">Nelle **Impostazioni globali** volare che viene visualizzato, passare all'impostazione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="4ac6b-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="4ac6b-119">Spostare l'interruttore verso destra per ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) attivare ATP per SharePoint, OneDrive e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="4ac6b-120">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4ac6b-121">Utilizzo di PowerShell di Exchange Online per abilitare ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac6b-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="4ac6b-122">Se si preferisce utilizzare PowerShell per abilitare ATP per SharePoint, OneDrive e Microsoft teams, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="4ac6b-123">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="4ac6b-124">Passaggio 2: (scelta consigliata) utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi</span><span class="sxs-lookup"><span data-stu-id="4ac6b-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="4ac6b-125">Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati da ATP.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="4ac6b-126">Tuttavia, è possibile eliminare e scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="4ac6b-127">Per impedire agli utenti di scaricare file dannosi, [connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="4ac6b-128">**Note** :</span><span class="sxs-lookup"><span data-stu-id="4ac6b-128">**Notes** :</span></span>

- <span data-ttu-id="4ac6b-129">Questa impostazione interessa sia gli utenti che gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="4ac6b-130">Gli utenti possono comunque eliminare i file dannosi.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-130">People can still delete malicious files.</span></span>

<span data-ttu-id="4ac6b-131">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="4ac6b-132">Passaggio 3 (scelta consigliata) utilizzare il Centro sicurezza & conformità per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="4ac6b-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="4ac6b-133">È possibile creare un criterio di avviso che informa l'utente e gli altri amministratori quando ATP per SharePoint, OneDrive e Microsoft teams rileva un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="4ac6b-134">Per ulteriori informazioni sugli avvisi, vedere [creare avvisi di attività nel centro sicurezza & Compliance](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="4ac6b-135">Nel [Centro sicurezza & conformità](https://protection.office.com), accedere a criteri **Alerts** di \> **avviso** avvisi o Apri <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="4ac6b-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="4ac6b-136">Nella pagina **criteri di avviso** fare clic su **nuovi criteri di avviso**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="4ac6b-137">La procedura guidata **nuovo criterio di avviso** viene aperta in un volo. Nella pagina **nome messaggio di avviso** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="4ac6b-138">**Nome** : digitare un nome univoco e descrittivo.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-138">**Name** : Type a unique and descriptive name.</span></span> <span data-ttu-id="4ac6b-139">Ad esempio, i file dannosi nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="4ac6b-140">**Descrizione** : digitare una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-140">**Description** : Type an optional description.</span></span> <span data-ttu-id="4ac6b-141">Ad esempio, avvisa gli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="4ac6b-142">**Severity** : lasciare il valore predefinito **basso** selezionato oppure selezionare **medio** o **elevato**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-142">**Severity** : Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="4ac6b-143">**Selezionare una categoria** : selezionare **gestione minacce**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-143">**Select a category** : Select **Threat management**.</span></span>

   <span data-ttu-id="4ac6b-144">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4ac6b-145">Nella pagina **Crea impostazioni di avviso** configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="4ac6b-146">**Che cosa si desidera avvisare?: attività è** : selezionare **rilevato malware nel file**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-146">**What do you want to alert on?: Activity is** : Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="4ac6b-147">**Come si desidera che venga attivato l'avviso?** : lasciare il valore predefinito **ogni volta che un'attività corrisponde alla regola** selezionata.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-147">**How do you want the alert to be triggered?** : Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="4ac6b-148">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4ac6b-149">Nella pagina **imposta i destinatari** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="4ac6b-150">**Invia notifiche tramite posta elettronica** : verificare che questa impostazione sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-150">**Send email notifications** : Verify this setting is selected.</span></span> <span data-ttu-id="4ac6b-151">Nella casella **destinatari di posta elettronica** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che dovrebbero ricevere una notifica quando viene rilevato un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="4ac6b-152">**Limite di notifica giornaliero** : lasciare il valore predefinito **Nessun limite** selezionato.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-152">**Daily notification limit** : Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="4ac6b-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="4ac6b-154">Nella pagina **Verifica le impostazioni** , esaminare le impostazioni, quindi fare clic su **modifica** in una delle sezioni per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="4ac6b-155">Nel caso in **cui si desidera trasformare il criterio immediatamente?** , lasciare il valore predefinito **Sì, attivarlo immediatamente** .</span><span class="sxs-lookup"><span data-stu-id="4ac6b-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="4ac6b-156">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="4ac6b-157">Utilizzare la sicurezza & conformità PowerShell per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="4ac6b-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="4ac6b-158">Se si preferisce utilizzare PowerShell per creare gli stessi criteri di avviso descritti nella sezione precedente, [connettersi al centro di sicurezza & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="4ac6b-159">**Nota** : il valore di _gravità_ predefinito è basso.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-159">**Note** : The default _Severity_ value is Low.</span></span> <span data-ttu-id="4ac6b-160">Per specificare medio o alto, includere il parametro _Severity_ e il valore nel comando.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="4ac6b-161">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4ac6b-162">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="4ac6b-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="4ac6b-163">Per verificare di aver correttamente attivato ATP per SharePoint, OneDrive e Microsoft teams, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="4ac6b-164">Nel [Centro sicurezza & conformità](https://protection.office.com), accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP** , selezionare **Impostazioni globali** e verificare il valore dell'impostazione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="4ac6b-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , select **Global settings** , and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="4ac6b-165">In Exchange Online PowerShell, eseguire il comando riportato di seguito per verificare l'impostazione della proprietà:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="4ac6b-166">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="4ac6b-167">Per verificare che le persone siano state bloccate correttamente dal Download di file dannosi, aprire PowerShell di SharePoint Online ed eseguire il comando seguente per verificare il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="4ac6b-168">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="4ac6b-169">Per verificare la corretta configurazione di un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="4ac6b-170">Nel centro sicurezza & conformità, accedere a **Alerts** \> **criteri di avviso** avvisi \> selezionare il criterio di avviso e verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="4ac6b-171">In PowerShell Centro sicurezza & conformità, sostituire \<AlertPolicyName\> con il nome del criterio di avviso, eseguire il comando riportato di seguito e verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="4ac6b-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="4ac6b-172">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="4ac6b-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="4ac6b-173">Utilizzare il [rapporto sullo stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report) per visualizzare le informazioni sui file rilevati in SharePoint, OneDrive e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4ac6b-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="4ac6b-174">In particolare, è possibile utilizzare la visualizzazione **dati di visualizzazione per: contenuto \> antimalware** .</span><span class="sxs-lookup"><span data-stu-id="4ac6b-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
