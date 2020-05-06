---
title: Attivazione di Office 365 ATP-SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
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
ms.openlocfilehash: f7708697f191107176173f2bfaced576c024954c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036729"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e4627-103">Attivare ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4627-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4627-104">Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="e4627-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="e4627-105">Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="e4627-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e4627-106">[Office 365 ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) protegge l'organizzazione dalla condivisione involontaria di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="e4627-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="e4627-107">Quando viene rilevato un file dannoso, il file viene bloccato in modo che nessuno possa aprirlo, copiarlo, spostarlo o condividerlo fino a quando non vengono intraprese altre azioni da parte del team di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4627-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="e4627-108">Leggere questo articolo per abilitare ATP per SharePoint, OneDrive e teams, impostare gli avvisi per ricevere una notifica sui file rilevati e seguire i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="e4627-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="e4627-109">Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato.</span><span class="sxs-lookup"><span data-stu-id="e4627-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="e4627-110">Alcuni esempi sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="e4627-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="e4627-111">Ruolo</span><span class="sxs-lookup"><span data-stu-id="e4627-111">Role</span></span>|<span data-ttu-id="e4627-112">Dove/come assegnato</span><span class="sxs-lookup"><span data-stu-id="e4627-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="e4627-113">amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e4627-113">global administrator</span></span>|<span data-ttu-id="e4627-114">La persona che si iscrive all'acquisto di Microsoft 365 è un amministratore globale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4627-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="e4627-115">Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="e4627-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="e4627-116">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4627-116">Security Administrator</span></span>|<span data-ttu-id="e4627-117">Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()</span><span class="sxs-lookup"><span data-stu-id="e4627-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="e4627-118">Gestione organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4627-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="e4627-119">Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange ()</span><span class="sxs-lookup"><span data-stu-id="e4627-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="e4627-120">oppure</span><span class="sxs-lookup"><span data-stu-id="e4627-120">or</span></span> <br>  <span data-ttu-id="e4627-121">Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="e4627-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e4627-122">Attivare ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4627-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e4627-123">**Prima di iniziare questa procedura, verificare che la registrazione di controllo sia già attiva per l'ambiente Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="e4627-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="e4627-124">Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e4627-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="e4627-125">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="e4627-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="e4627-126">Passare a [https://protection.office.com](https://protection.office.com)e accedere con l'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="e4627-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="e4627-127">Nel riquadro di spostamento a sinistra del Centro sicurezza & conformità, in **gestione minacce**scegliere **allegati sicuri**per i **criteri** \> .</span><span class="sxs-lookup"><span data-stu-id="e4627-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Nel centro sicurezza & conformità scegliere criteri di gestione \> delle minacce](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="e4627-129">Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="e4627-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Abilitare Advanced Threat Protection per SharePoint Online, OneDrive for business e Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="e4627-131">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e4627-131">Click **Save**.</span></span>

5. <span data-ttu-id="e4627-132">Rivedere (e, a seconda dei casi, modificare) i [criteri per gli allegati sicuri](set-up-atp-safe-attachments-policies.md) dell'organizzazione e i [criteri collegamenti sicuri](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4627-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="e4627-133">Consigliato In qualità di amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro _DisallowInfectedFileDownload_ impostato su *true*.</span><span class="sxs-lookup"><span data-stu-id="e4627-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="e4627-134">L'impostazione del parametro su *true* blocca tutte le azioni (eccetto Delete) per i file rilevati.</span><span class="sxs-lookup"><span data-stu-id="e4627-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="e4627-135">Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.</span><span class="sxs-lookup"><span data-stu-id="e4627-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="e4627-136">Se si imposta il parametro su *false* , vengono bloccate tutte le azioni ad eccezione di Delete e download.</span><span class="sxs-lookup"><span data-stu-id="e4627-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="e4627-137">Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.</span><span class="sxs-lookup"><span data-stu-id="e4627-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="e4627-138">Consentono fino a 30 minuti affinché le modifiche vengano estese a tutti i datacenter di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4627-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="e4627-139">Consigliato Procedere alla configurazione degli avvisi per i file rilevati.</span><span class="sxs-lookup"><span data-stu-id="e4627-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="e4627-140">Per ulteriori informazioni sull'utilizzo di PowerShell con Microsoft 365, vedere [gestire microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4627-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="e4627-141">Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere [cosa fare quando si trova un file dannoso in SharePoint Online, OneDrive o Microsoft teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="e4627-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="e4627-142">Configurare gli avvisi per i file rilevati</span><span class="sxs-lookup"><span data-stu-id="e4627-142">Set up alerts for detected files</span></span>

<span data-ttu-id="e4627-143">Per ricevere una notifica quando un file in SharePoint Online, OneDrive for business o Microsoft teams è stato identificato come dannoso, è possibile impostare un avviso.</span><span class="sxs-lookup"><span data-stu-id="e4627-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="e4627-144">Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere **avvisi** \> **Gestione avvisi**.</span><span class="sxs-lookup"><span data-stu-id="e4627-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="e4627-145">Scegliere **nuovi criteri di avviso**.</span><span class="sxs-lookup"><span data-stu-id="e4627-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="e4627-146">Specificare un nome per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e4627-146">Specify a name for the alert.</span></span> <span data-ttu-id="e4627-147">Ad esempio, è possibile digitare file dannosi nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="e4627-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="e4627-148">Digitare una descrizione per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e4627-148">Type a description for the alert.</span></span> <span data-ttu-id="e4627-149">Ad esempio, è possibile digitare notifiche agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e4627-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="e4627-150">Nella sezione **Invia questo avviso quando...** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4627-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="e4627-151">a.</span><span class="sxs-lookup"><span data-stu-id="e4627-151">a.</span></span> <span data-ttu-id="e4627-152">Nell'elenco **attività** scegliere **rilevato malware nel file**.</span><span class="sxs-lookup"><span data-stu-id="e4627-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="e4627-153">b.</span><span class="sxs-lookup"><span data-stu-id="e4627-153">b.</span></span> <span data-ttu-id="e4627-154">Lasciare vuoto il campo **Users** .</span><span class="sxs-lookup"><span data-stu-id="e4627-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="e4627-155">Nella sezione **Invia questo avviso a...** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che dovrebbero ricevere una notifica quando viene rilevato un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="e4627-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="e4627-156">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e4627-156">Click **Save**.</span></span>

<span data-ttu-id="e4627-157">Per ulteriori informazioni sugli avvisi, vedere [creare avvisi di attività nel centro sicurezza & Compliance](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="e4627-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4627-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e4627-158">Next steps</span></span>

1. [<span data-ttu-id="e4627-159">Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4627-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="e4627-160">Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e4627-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
