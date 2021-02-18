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
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286370"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7a599-103">Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a599-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7a599-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="7a599-104">**Applies to**</span></span>
- [<span data-ttu-id="7a599-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="7a599-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7a599-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a599-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7a599-107">Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="7a599-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="7a599-108">Per ulteriori informazioni, vedere [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7a599-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="7a599-109">Questo articolo contiene i passaggi per abilitare e configurare allegati sicuri per SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a599-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7a599-110">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="7a599-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7a599-111">Aprire il Centro sicurezza e conformità in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="7a599-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="7a599-112">Per passare direttamente alla pagina **Allegati sicuri di ATP,** aprire <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="7a599-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="7a599-113">Per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams,  è necessario  essere membri dei gruppi di ruoli Gestione organizzazione o Amministratore sicurezza nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="7a599-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="7a599-114">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7a599-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7a599-115">Per utilizzare PowerShell di SharePoint Online per impedire agli utenti di [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) scaricare file dannosi, è necessario essere membri dei ruoli Amministratore globale o Amministratore di [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7a599-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="7a599-116">Verificare che la registrazione di controllo sia abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7a599-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="7a599-117">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="7a599-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="7a599-118">Consentire fino a 30 minuti per l'applicazione delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7a599-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7a599-119">Passaggio 1: Usare il Centro sicurezza & conformità per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a599-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="7a599-120">Nel Centro sicurezza & conformità passare **a** Allegati sicuri dei criteri di gestione delle minacce ATP e fare clic su \>  \>  **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="7a599-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="7a599-121">Nel **riquadro a comparsa** Impostazioni globali visualizzato passare all'impostazione Attiva **Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="7a599-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="7a599-122">Spostare l'interruttore a destra per attivare Allegati sicuri ![ ](../../media/scc-toggle-on.png) per SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a599-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="7a599-123">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7a599-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7a599-124">Usare PowerShell di Exchange Online per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a599-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7a599-125">Se si preferisce usare PowerShell per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams, connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7a599-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="7a599-126">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="7a599-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="7a599-127">Passaggio 2: (scelta consigliata) Utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi</span><span class="sxs-lookup"><span data-stu-id="7a599-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="7a599-128">Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati da ATP.</span><span class="sxs-lookup"><span data-stu-id="7a599-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="7a599-129">Tuttavia, possono eliminare e scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="7a599-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="7a599-130">Per impedire agli utenti di scaricare file dannosi, [connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7a599-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="7a599-131">**Note**:</span><span class="sxs-lookup"><span data-stu-id="7a599-131">**Notes**:</span></span>

- <span data-ttu-id="7a599-132">Questa impostazione influisce sia sugli utenti che sugli amministratori.</span><span class="sxs-lookup"><span data-stu-id="7a599-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="7a599-133">Gli utenti possono comunque eliminare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="7a599-133">People can still delete malicious files.</span></span>

<span data-ttu-id="7a599-134">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="7a599-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="7a599-135">Passaggio 3 (consigliato) Usare il Centro sicurezza & conformità per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="7a599-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="7a599-136">È possibile creare un criterio di avviso che informa l'utente e altri amministratori quando Allegati sicuri per SharePoint, OneDrive e Microsoft Teams rileva un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="7a599-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="7a599-137">Per ulteriori informazioni sugli avvisi, vedere Creare avvisi [attività nel Centro sicurezza & conformità.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7a599-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="7a599-138">Nel Centro [sicurezza & conformità](https://protection.office.com)passare a Criteri **avvisi** o \>  aprire <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="7a599-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="7a599-139">Nella pagina **Criteri di avviso** fare clic su Nuovo criterio di **avviso.**</span><span class="sxs-lookup"><span data-stu-id="7a599-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="7a599-140">La **procedura guidata Nuovo criterio** di avviso si apre in un riquadro a comparsa. Nella pagina **Assegnare un nome all'avviso** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a599-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="7a599-141">**Nome**: digitare un nome univoco e descrittivo.</span><span class="sxs-lookup"><span data-stu-id="7a599-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="7a599-142">Ad esempio, File dannosi nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="7a599-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="7a599-143">**Descrizione:** digitare una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a599-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="7a599-144">Ad esempio, notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a599-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="7a599-145">**Gravità:** lasciare selezionato il valore predefinito **Basso** oppure **selezionare Medio** o **Alto.**</span><span class="sxs-lookup"><span data-stu-id="7a599-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="7a599-146">**Selezionare una categoria:** selezionare **Gestione delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="7a599-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="7a599-147">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7a599-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7a599-148">Nella pagina **Crea impostazioni avviso** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a599-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="7a599-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file.**</span><span class="sxs-lookup"><span data-stu-id="7a599-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="7a599-150">**Come si desidera attivare l'avviso?**: Lasciare il valore predefinito Ogni volta che un'attività **corrisponde alla regola** selezionata.</span><span class="sxs-lookup"><span data-stu-id="7a599-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="7a599-151">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7a599-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7a599-152">Nella pagina **Imposta destinatari** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a599-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="7a599-153">**Invia notifiche tramite posta elettronica:** verificare che questa impostazione sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="7a599-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="7a599-154">Nella casella **Destinatari di posta** elettronica selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="7a599-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="7a599-155">**Limite di notifica giornaliero:** lasciare selezionato il valore **predefinito Nessun** limite.</span><span class="sxs-lookup"><span data-stu-id="7a599-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="7a599-156">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7a599-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7a599-157">Nella pagina **Verifica le impostazioni** esaminare le impostazioni e fare clic su **Modifica** in una delle sezioni per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a599-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="7a599-158">Nella sezione Vuoi attivare il criterio **subito?** lascia selezionato il valore predefinito **Sì, attivalo subito.**</span><span class="sxs-lookup"><span data-stu-id="7a599-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="7a599-159">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7a599-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="7a599-160">Usare PowerShell & sicurezza per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="7a599-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="7a599-161">Se si preferisce usare PowerShell per creare lo stesso criterio di avviso descritto nella sezione precedente, connettersi [a PowerShell per](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Centro sicurezza & conformità ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7a599-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="7a599-162">**Nota:** il valore _di gravità_ predefinito è Basso.</span><span class="sxs-lookup"><span data-stu-id="7a599-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="7a599-163">Per specificare Medium o High, includere il _parametro Severity_ e il valore nel comando.</span><span class="sxs-lookup"><span data-stu-id="7a599-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="7a599-164">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="7a599-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7a599-165">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="7a599-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="7a599-166">Per verificare che gli allegati sicuri per SharePoint, OneDrive e Microsoft Teams siano stati attivati correttamente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a599-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="7a599-167">Nel Centro sicurezza & conformità, accedere  [a](https://protection.office.com)Allegati sicuri atp dei criteri di gestione delle minacce, selezionare Impostazioni globali e verificare il valore dell'impostazione Attiva \>  \> Defender per **Office 365 per SharePoint, OneDrive** e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a599-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="7a599-168">In PowerShell di Exchange Online, eseguire il comando seguente per verificare l'impostazione della proprietà:</span><span class="sxs-lookup"><span data-stu-id="7a599-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="7a599-169">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="7a599-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="7a599-170">Per verificare di aver bloccato correttamente il download di file dannosi, aprire PowerShell di SharePoint Online ed eseguire il comando seguente per verificare il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="7a599-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="7a599-171">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="7a599-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="7a599-172">Per verificare di aver configurato correttamente un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a599-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="7a599-173">Nel Centro sicurezza & conformità, andare a **Criteri avvisi** selezionare i criteri di avviso e verificare \>  \> le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7a599-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="7a599-174">In PowerShell & Centro sicurezza e conformità, sostituire con il nome del criterio di avviso, eseguire il comando seguente e \<AlertPolicyName\> verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="7a599-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="7a599-175">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="7a599-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="7a599-176">Usare il [report sullo stato di Protezione](view-email-security-reports.md#threat-protection-status-report) dalle minacce per visualizzare informazioni sui file rilevati in SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a599-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="7a599-177">In particolare, è possibile utilizzare la **visualizzazione dati da: visualizzazione \> Malware** contenuto.</span><span class="sxs-lookup"><span data-stu-id="7a599-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
