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
description: Gli amministratori possono informazioni su come attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, incluso come impostare gli avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083093"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1295b-103">Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1295b-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1295b-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="1295b-104">**Applies to**</span></span>
- [<span data-ttu-id="1295b-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="1295b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1295b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1295b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1295b-107">Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="1295b-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="1295b-108">Per ulteriori informazioni, vedere [Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1295b-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1295b-109">In questo articolo vengono descritti i passaggi per abilitare e configurare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1295b-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1295b-110">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="1295b-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1295b-111">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="1295b-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="1295b-112">Per passare direttamente alla pagina **Cassaforte allegati,** aprire <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="1295b-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="1295b-113">Per attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, è necessario essere membri dei gruppi di  ruoli  Gestione organizzazione o Amministratore sicurezza nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1295b-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="1295b-114">Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="1295b-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="1295b-115">Per usare SharePoint PowerShell online per impedire agli utenti di scaricare file dannosi, [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) è necessario essere membri dei ruoli [Amministratore](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) globale o Amministratore SharePoint in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1295b-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="1295b-116">Verificare che la registrazione di controllo sia abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1295b-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="1295b-117">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="1295b-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="1295b-118">Consentire fino a 30 minuti per l'applicazione delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1295b-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1295b-119">Passaggio 1: usare il portale Microsoft 365 Defender per attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1295b-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="1295b-120">Nel portale Microsoft 365 Defender, passare alla sezione **Criteri & criteri** di minaccia Cassaforte \>  \>  \> **allegati**.</span><span class="sxs-lookup"><span data-stu-id="1295b-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1295b-121">Nella pagina **Cassaforte allegati** fare clic su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="1295b-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="1295b-122">Nel **riquadro a comparsa** Impostazioni globali visualizzato passare alla sezione Proteggi **file in SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="1295b-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="1295b-123">Sposta l'interruttore Attiva Defender per Office 365 per **SharePoint, OneDrive** e Microsoft Teams verso destra Attiva per attivare gli allegati Cassaforte per SharePoint, OneDrive e ![ ](../../media/scc-toggle-on.png) Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1295b-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="1295b-124">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1295b-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1295b-125">Usare Exchange Online PowerShell per attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1295b-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1295b-126">Se si preferisce utilizzare PowerShell per attivare Cassaforte Attachments per SharePoint, OneDrive e Microsoft Teams, connettersi [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1295b-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="1295b-127">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="1295b-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="1295b-128">Passaggio 2: (scelta consigliata) Utilizzare SharePoint PowerShell online per impedire agli utenti di scaricare file dannosi</span><span class="sxs-lookup"><span data-stu-id="1295b-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="1295b-129">Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati dagli allegati di Cassaforte per <sup>\*</sup> SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1295b-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="1295b-130">Tuttavia, possono eliminare e scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="1295b-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="1295b-131"><sup>\*</sup> Se gli utenti passano **a Gestisci accesso,** **l'opzione** Condividi è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="1295b-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="1295b-132">Per impedire agli utenti di scaricare file dannosi, [connettersi SharePoint PowerShell online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1295b-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="1295b-133">**Note**:</span><span class="sxs-lookup"><span data-stu-id="1295b-133">**Notes**:</span></span>

- <span data-ttu-id="1295b-134">Questa impostazione influisce sia sugli utenti che sugli amministratori.</span><span class="sxs-lookup"><span data-stu-id="1295b-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="1295b-135">Gli utenti possono comunque eliminare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="1295b-135">People can still delete malicious files.</span></span>

<span data-ttu-id="1295b-136">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="1295b-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="1295b-137">Passaggio 3 (consigliato) Usare il portale Microsoft 365 Defender per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="1295b-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="1295b-138">È possibile creare un criterio di avviso che notifica all'utente e ad altri amministratori quando Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams rileva un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="1295b-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="1295b-139">Per ulteriori informazioni sugli avvisi, vedere [Create activity alerts in the Microsoft 365 Defender portal.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1295b-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="1295b-140">Nel portale Microsoft 365 Defender, passare a Criteri **& criteri** \> **di avviso** o aprire <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="1295b-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="1295b-141">Nella pagina **Criterio avviso** fare clic su Nuovo criterio **di avviso.**</span><span class="sxs-lookup"><span data-stu-id="1295b-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="1295b-142">La **procedura guidata Nuovo criterio** di avviso viene aperta in un riquadro a comparsa. Nella pagina **Assegnare un nome all'avviso** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1295b-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="1295b-143">**Nome**: digitare un nome univoco e descrittivo.</span><span class="sxs-lookup"><span data-stu-id="1295b-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="1295b-144">Ad esempio, File dannosi nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="1295b-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="1295b-145">**Descrizione:** digitare una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1295b-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="1295b-146">Ad esempio, notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1295b-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="1295b-147">**Gravità:** selezionare **Bassa,** **Media** o **Alta** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1295b-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="1295b-148">**Categoria**: selezionare **Gestione delle minacce** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1295b-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="1295b-149">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1295b-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1295b-150">Nella pagina **Crea impostazioni avviso** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1295b-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="1295b-151">**Cosa si desidera avvisare?** sezione \> **Attività è** \> Seleziona malware rilevato nel **file** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1295b-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="1295b-152">**Come si desidera attivare l'avviso?** sezione: lasciare selezionato il valore predefinito **Ogni volta che un'attività corrisponde alla regola.**</span><span class="sxs-lookup"><span data-stu-id="1295b-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="1295b-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1295b-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1295b-154">Nella pagina **Imposta i destinatari** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1295b-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="1295b-155">Verificare che **l'opzione Invia notifiche tramite posta** elettronica sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="1295b-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="1295b-156">Nella casella **Destinatari di posta elettronica** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="1295b-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="1295b-157">**Limite notifiche giornaliere**: lasciare selezionato il valore **predefinito Nessun** limite.</span><span class="sxs-lookup"><span data-stu-id="1295b-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="1295b-158">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1295b-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1295b-159">Nella pagina **Rivedere le impostazioni** esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1295b-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="1295b-160">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="1295b-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="1295b-161">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1295b-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="1295b-162">Nella sezione Vuoi attivare subito il **criterio?** lascia selezionato il valore predefinito **Sì, attivalo subito.**</span><span class="sxs-lookup"><span data-stu-id="1295b-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="1295b-163">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="1295b-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="1295b-164">Usare PowerShell & sicurezza per creare un criterio di avviso per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="1295b-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="1295b-165">Se si preferisce usare PowerShell per creare lo stesso criterio di avviso descritto nella sezione precedente, connettersi & Centro sicurezza e conformità [PowerShell](/powershell/exchange/connect-to-scc-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1295b-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="1295b-166">**Nota:** il valore _di gravità_ predefinito è Low.</span><span class="sxs-lookup"><span data-stu-id="1295b-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="1295b-167">Per specificare Medium o High, includere il _parametro Severity_ e il valore nel comando.</span><span class="sxs-lookup"><span data-stu-id="1295b-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="1295b-168">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="1295b-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1295b-169">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="1295b-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="1295b-170">Per verificare di aver attivato correttamente Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1295b-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="1295b-171">Nel portale di Microsoft 365 Defender passare **alla** sezione Criteri & regole criteri di minaccia Cassaforte Allegati, selezionare Impostazioni globali e verificare il valore dell'impostazione Attiva Defender per Office 365 per \>  \>  \>  **SharePoint, OneDrive e Microsoft Teams.** </span><span class="sxs-lookup"><span data-stu-id="1295b-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="1295b-172">In Exchange Online PowerShell, eseguire il comando seguente per verificare l'impostazione della proprietà:</span><span class="sxs-lookup"><span data-stu-id="1295b-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="1295b-173">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="1295b-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="1295b-174">Per verificare di aver bloccato correttamente il download di file dannosi, aprire SharePoint PowerShell online ed eseguire il comando seguente per verificare il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="1295b-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="1295b-175">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="1295b-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="1295b-176">Per verificare di aver configurato correttamente un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1295b-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="1295b-177">Nel portale Microsoft 365 Defender, andare a Criteri **& criteri** di avviso Selezionare il criterio di avviso e verificare \>  \> le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1295b-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="1295b-178">In Microsoft 365 Defender PowerShell del portale, sostituire con il nome del criterio di avviso, eseguire il \<AlertPolicyName\> comando seguente e verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="1295b-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="1295b-179">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="1295b-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="1295b-180">Usa il [rapporto sullo stato di Threat Protection](view-email-security-reports.md#threat-protection-status-report) per visualizzare le informazioni sui file rilevati in SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1295b-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="1295b-181">In particolare, puoi usare la **visualizzazione Visualizza dati per: Malware contenuto. \>**</span><span class="sxs-lookup"><span data-stu-id="1295b-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
