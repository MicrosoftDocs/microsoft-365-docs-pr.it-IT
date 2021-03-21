---
title: Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Gli amministratori possono imparare ad attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams, incluso come impostare avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 300cb3e004010e8ff22de7393d3f3e039bf8cfdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921145"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e16d3-103">Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e16d3-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e16d3-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="e16d3-104">**Applies to**</span></span>
- [<span data-ttu-id="e16d3-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="e16d3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e16d3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e16d3-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e16d3-107">Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="e16d3-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="e16d3-108">Per ulteriori informazioni, vedere [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e16d3-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="e16d3-109">Questo articolo contiene i passaggi per abilitare e configurare allegati sicuri per SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e16d3-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e16d3-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e16d3-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e16d3-111">Aprire il Centro sicurezza e conformità in<https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e16d3-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="e16d3-112">Per passare direttamente alla pagina Allegati sicuri **ATP,** aprire <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="e16d3-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="e16d3-113">Per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams,  è necessario  essere membri dei gruppi di ruoli Gestione organizzazione o Amministratore sicurezza nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e16d3-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="e16d3-114">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e16d3-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e16d3-115">Per usare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi, è necessario essere membri dei ruoli [Amministratore](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) globale o Amministratore [di SharePoint](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e16d3-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="e16d3-116">Verificare che la registrazione di controllo sia abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e16d3-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="e16d3-117">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="e16d3-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="e16d3-118">Consentire fino a 30 minuti per l'applicazione delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e16d3-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e16d3-119">Passaggio 1: Usare il Centro sicurezza & conformità per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e16d3-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="e16d3-120">Nel Centro sicurezza & conformità passare **a** Criteri di gestione delle minacce Allegati sicuri \>  \> **ATP** e fare clic su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="e16d3-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="e16d3-121">Nel **riquadro a comparsa** Impostazioni globali visualizzato passare all'impostazione Attiva **Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="e16d3-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="e16d3-122">Spostare l'interruttore sull'interruttore a destra attiva per attivare Allegati sicuri ![ ](../../media/scc-toggle-on.png) per SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e16d3-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="e16d3-123">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e16d3-124">Usare PowerShell di Exchange Online per attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e16d3-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e16d3-125">Se si preferisce usare PowerShell per attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams, connettersi a [PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e16d3-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="e16d3-126">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="e16d3-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="e16d3-127">Passaggio 2: (scelta consigliata) Utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi</span><span class="sxs-lookup"><span data-stu-id="e16d3-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="e16d3-128">Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati da ATP.</span><span class="sxs-lookup"><span data-stu-id="e16d3-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="e16d3-129">Tuttavia, possono eliminare e scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="e16d3-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="e16d3-130">Per impedire agli utenti di scaricare file dannosi, [connettersi a PowerShell di SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e16d3-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="e16d3-131">**Note**:</span><span class="sxs-lookup"><span data-stu-id="e16d3-131">**Notes**:</span></span>

- <span data-ttu-id="e16d3-132">Questa impostazione influisce sia sugli utenti che sugli amministratori.</span><span class="sxs-lookup"><span data-stu-id="e16d3-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="e16d3-133">Gli utenti possono comunque eliminare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="e16d3-133">People can still delete malicious files.</span></span>

<span data-ttu-id="e16d3-134">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="e16d3-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="e16d3-135">Passaggio 3 (consigliato) Usare il Centro sicurezza & conformità per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="e16d3-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="e16d3-136">È possibile creare un criterio di avviso che informa l'utente e altri amministratori quando allegati sicuri per SharePoint, OneDrive e Microsoft Teams rilevano un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="e16d3-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="e16d3-137">Per ulteriori informazioni sugli avvisi, vedere [Create activity alerts in the Security & Compliance Center.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e16d3-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="e16d3-138">Nel Centro [sicurezza & conformità](https://protection.office.com)passare a **Avvisi** Criteri \> **di avviso** o aprire <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="e16d3-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="e16d3-139">Nella pagina **Criteri avviso** fare clic su Nuovo criterio **di avviso.**</span><span class="sxs-lookup"><span data-stu-id="e16d3-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="e16d3-140">La **procedura guidata Nuovo criterio** di avviso viene aperta in un riquadro a comparsa. Nella pagina **Assegnare un nome all'avviso** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e16d3-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="e16d3-141">**Nome**: digitare un nome univoco e descrittivo.</span><span class="sxs-lookup"><span data-stu-id="e16d3-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="e16d3-142">Ad esempio, File dannosi nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="e16d3-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="e16d3-143">**Descrizione:** digitare una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e16d3-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="e16d3-144">Ad esempio, notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e16d3-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="e16d3-145">**Gravità:** lasciare selezionato il valore predefinito **Basso** oppure **selezionare Medio** o **Alto.**</span><span class="sxs-lookup"><span data-stu-id="e16d3-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="e16d3-146">**Selezionare una categoria:** selezionare **Gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="e16d3-147">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e16d3-148">Nella pagina **Crea impostazioni avviso** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e16d3-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="e16d3-149">**Cosa si desidera avvisare?: Attività è**: Selezionare **Malware rilevato nel file**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="e16d3-150">**Come si desidera attivare l'avviso?**: Lasciare selezionato il valore predefinito Ogni volta che **un'attività corrisponde alla** regola.</span><span class="sxs-lookup"><span data-stu-id="e16d3-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="e16d3-151">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e16d3-152">Nella pagina **Imposta i destinatari** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e16d3-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="e16d3-153">**Invia notifiche tramite posta** elettronica : verificare che questa impostazione sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="e16d3-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="e16d3-154">Nella casella **Destinatari di posta elettronica** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="e16d3-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="e16d3-155">**Limite notifiche giornaliere**: lasciare selezionato il valore **predefinito Nessun** limite.</span><span class="sxs-lookup"><span data-stu-id="e16d3-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="e16d3-156">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e16d3-157">Nella pagina **Rivedere le impostazioni** esaminare le impostazioni e fare clic su Modifica in una delle sezioni per apportare modifiche. </span><span class="sxs-lookup"><span data-stu-id="e16d3-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="e16d3-158">Nella sezione Vuoi attivare subito il **criterio?** lascia selezionato il valore predefinito **Sì, attivalo subito.**</span><span class="sxs-lookup"><span data-stu-id="e16d3-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="e16d3-159">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e16d3-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="e16d3-160">Usare PowerShell & sicurezza per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="e16d3-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="e16d3-161">Se si preferisce usare PowerShell per creare lo stesso criterio di avviso descritto nella sezione precedente, connettersi & Centro sicurezza e conformità [PowerShell](/powershell/exchange/connect-to-scc-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e16d3-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="e16d3-162">**Nota:** il valore _di gravità_ predefinito è Low.</span><span class="sxs-lookup"><span data-stu-id="e16d3-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="e16d3-163">Per specificare Medium o High, includere il _parametro Severity_ e il valore nel comando.</span><span class="sxs-lookup"><span data-stu-id="e16d3-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="e16d3-164">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="e16d3-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e16d3-165">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="e16d3-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="e16d3-166">Per verificare di aver attivato correttamente allegati sicuri per SharePoint, OneDrive e Microsoft Teams, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e16d3-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="e16d3-167">Nel Centro sicurezza & conformità passare  [a](https://protection.office.com)Criteri di gestione delle minacce Allegati sicuri ATP, selezionare Impostazioni globali e verificare il valore dell'impostazione Attiva \>  \> Defender per **Office 365 per SharePoint, OneDrive** e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e16d3-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="e16d3-168">In PowerShell di Exchange Online, eseguire il comando seguente per verificare l'impostazione della proprietà:</span><span class="sxs-lookup"><span data-stu-id="e16d3-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="e16d3-169">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="e16d3-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="e16d3-170">Per verificare di aver bloccato correttamente il download di file dannosi, aprire PowerShell di SharePoint Online ed eseguire il comando seguente per verificare il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="e16d3-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="e16d3-171">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="e16d3-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="e16d3-172">Per verificare di aver configurato correttamente un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e16d3-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="e16d3-173">Nel Centro sicurezza & conformità passare **a** Avvisi Criteri di avviso selezionare i criteri di \>  \> avviso e verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e16d3-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="e16d3-174">In PowerShell & Centro sicurezza e conformità sostituire con il nome del criterio di avviso, eseguire il \<AlertPolicyName\> comando seguente e verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="e16d3-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="e16d3-175">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="e16d3-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="e16d3-176">Utilizzare il [rapporto sullo stato di Protezione](view-email-security-reports.md#threat-protection-status-report) dalle minacce per visualizzare informazioni sui file rilevati in SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e16d3-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="e16d3-177">In particolare, puoi usare la **visualizzazione Visualizza dati per: Malware contenuto. \>**</span><span class="sxs-lookup"><span data-stu-id="e16d3-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>