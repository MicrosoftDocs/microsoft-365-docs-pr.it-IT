---
title: Protezione dalle minacce
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Gli amministratori possono acquisire informazioni sulla protezione dalle minacce in Microsoft 365 e configurare come utilizzarla per l'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 54500500095392ebfc3d93080701fa4715fc8448
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617397"
---
# <a name="protect-against-threats"></a><span data-ttu-id="a67bd-103">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="a67bd-103">Protect against threats</span></span>

<span data-ttu-id="a67bd-104">Microsoft 365 include una vasta gamma di funzionalità di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="a67bd-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="a67bd-105">Di seguito è illustrata una guida introduttiva che è possibile utilizzare come elenco di controllo per verificare che le funzionalità di protezione delle minacce siano configurate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a67bd-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="a67bd-106">Se si è nuovi per le funzionalità di protezione dalle minacce in Office 365 o si è sicuri di dove iniziare, utilizzare le linee guida seguenti come punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="a67bd-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a67bd-107">**Per ogni tipo di criterio sono incluse le impostazioni consigliate iniziali, tuttavia sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="a67bd-108">Consenti circa 30 minuti affinché i criteri o le modifiche vengano elaborati tramite il Data Center.</span><span class="sxs-lookup"><span data-stu-id="a67bd-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="a67bd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a67bd-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="a67bd-110">Sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="a67bd-110">Subscriptions</span></span>

<span data-ttu-id="a67bd-111">Le funzionalità di protezione dalle minacce sono incluse in tutte le sottoscrizioni di Microsoft 365; Tuttavia, alcuni abbonamenti includono funzionalità più avanzate.</span><span class="sxs-lookup"><span data-stu-id="a67bd-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="a67bd-112">Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo, insieme ai requisiti minimi di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a67bd-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|||
|---|---|
|<span data-ttu-id="a67bd-113">**Tipo di protezione**</span><span class="sxs-lookup"><span data-stu-id="a67bd-113">**Protection type**</span></span>|<span data-ttu-id="a67bd-114">**Requisito di sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="a67bd-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="a67bd-115">Protezione anti-malware</span><span class="sxs-lookup"><span data-stu-id="a67bd-115">Anti-malware protection</span></span>|<span data-ttu-id="a67bd-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="a67bd-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="a67bd-117">Protezione da URL e file dannosi nei documenti di posta elettronica e di Office</span><span class="sxs-lookup"><span data-stu-id="a67bd-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="a67bd-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="a67bd-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="a67bd-119">Protezione anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a67bd-119">Anti-phishing protection</span></span>|[<span data-ttu-id="a67bd-120">EOP</span><span class="sxs-lookup"><span data-stu-id="a67bd-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a67bd-121">Protezione anti-phishing avanzata</span><span class="sxs-lookup"><span data-stu-id="a67bd-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="a67bd-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a67bd-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="a67bd-123">Protezione dalla posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a67bd-123">Anti-spam protection</span></span>|[<span data-ttu-id="a67bd-124">EOP</span><span class="sxs-lookup"><span data-stu-id="a67bd-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a67bd-125">Spurgo automatico zero-hour (per la posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="a67bd-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="a67bd-126">EOP</span><span class="sxs-lookup"><span data-stu-id="a67bd-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a67bd-127">Registrazione di controllo (utilizzata per la creazione di report)</span><span class="sxs-lookup"><span data-stu-id="a67bd-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="a67bd-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a67bd-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="a67bd-129">Ruoli e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a67bd-129">Roles and permissions</span></span>

<span data-ttu-id="a67bd-130">È necessario essere assegnati a un ruolo appropriato per configurare i criteri nel [Centro sicurezza & conformità](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="a67bd-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="a67bd-131">La tabella seguente include alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="a67bd-131">The following table includes some examples:</span></span>

|<span data-ttu-id="a67bd-132">Ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="a67bd-132">Role or role group</span></span>|<span data-ttu-id="a67bd-133">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a67bd-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="a67bd-134">amministratore globale</span><span class="sxs-lookup"><span data-stu-id="a67bd-134">global administrator</span></span>|[<span data-ttu-id="a67bd-135">Informazioni sui ruoli di amministratore di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a67bd-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="a67bd-136">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="a67bd-136">Security Administrator</span></span>|[<span data-ttu-id="a67bd-137">Autorizzazioni del ruolo di amministratore in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a67bd-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="a67bd-138">Gestione organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a67bd-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="a67bd-139">Autorizzazioni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a67bd-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="a67bd-140">e</span><span class="sxs-lookup"><span data-stu-id="a67bd-140">and</span></span><br> [<span data-ttu-id="a67bd-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a67bd-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="a67bd-142">Per ulteriori informazioni, vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="a67bd-143">Parte 1-protezione antimalware</span><span class="sxs-lookup"><span data-stu-id="a67bd-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="a67bd-144">La [protezione antimalware](anti-malware-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="a67bd-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="a67bd-145">Nel [Centro sicurezza & conformità](https://protection.office.com)scegliere **Threat management**  >  **Policy**  >  **antimalware**per criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="a67bd-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="a67bd-146">Fare doppio clic sul criterio **predefinito** e quindi scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="a67bd-147">Specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-147">Specify the following settings:</span></span>

    - <span data-ttu-id="a67bd-148">Nella sezione **risposta di rilevamento malware** mantenere l'impostazione predefinita **Nr**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="a67bd-149">Nella sezione **filtro tipi di allegati comuni** **scegliere attivato**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="a67bd-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-150">Click **Save**.</span></span>

<span data-ttu-id="a67bd-151">Per ulteriori informazioni sulle opzioni di criteri anti-malware, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="a67bd-152">Parte 2-protezione da URL e file dannosi</span><span class="sxs-lookup"><span data-stu-id="a67bd-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="a67bd-153">La protezione del tempo di clic da URL e file dannosi è disponibile in abbonamenti che includono [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) ed è configurata tramite gli [allegati sicuri di ATP](atp-safe-attachments.md) e i criteri dei [collegamenti sicuri di ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="a67bd-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="a67bd-154">Criteri per gli allegati sicuri ATP</span><span class="sxs-lookup"><span data-stu-id="a67bd-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="a67bd-155">Per configurare gli [allegati sicuri di ATP](atp-safe-attachments.md), è necessario definire almeno un criterio per gli allegati sicuri ATP.</span><span class="sxs-lookup"><span data-stu-id="a67bd-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="a67bd-156">Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere gli allegati sicuri per i criteri di **gestione delle minacce**  >  **Policy**  >  **ATP**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="a67bd-157">Selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="a67bd-158">Nella sezione **Proteggi allegati di posta elettronica** , fare clic sul segno più ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="a67bd-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="a67bd-159">Specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-159">Specify the following settings:</span></span>

   - <span data-ttu-id="a67bd-160">Nella casella **nome** Digitare `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="a67bd-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="a67bd-161">Nella sezione Response scegliere **Block**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="a67bd-162">Nella sezione **allegato di reindirizzamento** selezionare l'opzione **Abilita reindirizzamento**e quindi specificare l'indirizzo di posta elettronica per l'amministratore o l'operatore di sicurezza dell'organizzazione che rivedrà i file rilevati.</span><span class="sxs-lookup"><span data-stu-id="a67bd-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="a67bd-163">Nella sezione **applicato a** scegliere **il dominio del destinatario**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="a67bd-164">Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="a67bd-165">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-165">Click **Save**.</span></span>

6. <span data-ttu-id="a67bd-166">(**Passaggio aggiuntivo consigliato**) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro **DisallowInfectedFileDownload** impostato su *true* per l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a67bd-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="a67bd-167">In questo modo si impedisce l'apertura, lo spostamento, la copia o la condivisione di file che vengono rilevati come dannosi.</span><span class="sxs-lookup"><span data-stu-id="a67bd-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="a67bd-168">Per ulteriori informazioni, vedere [configurare i criteri per gli allegati sicuri ATP di office 365](set-up-atp-safe-attachments-policies.md) e [abilitare Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="a67bd-169">Criteri per i collegamenti sicuri ATP</span><span class="sxs-lookup"><span data-stu-id="a67bd-169">ATP Safe Links policies</span></span>

<span data-ttu-id="a67bd-170">Per configurare i [collegamenti sicuri di ATP](atp-safe-links.md), esaminare e modificare il criterio predefinito e aggiungere un criterio per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="a67bd-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="a67bd-171">Nel [Centro sicurezza & Compliance](https://protection.office.com)scegliere criteri di **gestione delle minacce**  >  **Policy**  >  **ATP collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a67bd-172">Fare doppio clic sul criterio **predefinito** .</span><span class="sxs-lookup"><span data-stu-id="a67bd-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="a67bd-173">Nella sezione **use Safe Links in** selezionare l'opzione **Microsoft 365 Apps for Enterprise, Office per iOS e Android**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="a67bd-174">Nella sezione **criteri che si applicano a destinatari specifici** fare clic sul segno più ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="a67bd-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="a67bd-175">Specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-175">Specify the following settings:</span></span>

   - <span data-ttu-id="a67bd-176">Nella casella **nome** Digitare un nome, ad esempio `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="a67bd-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="a67bd-177">Nella sezione **selezionare l'azione** scegliere **attivato.**</span><span class="sxs-lookup"><span data-stu-id="a67bd-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="a67bd-178">Selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-178">Select these options:</span></span>

     - <span data-ttu-id="a67bd-179">**Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile**</span><span class="sxs-lookup"><span data-stu-id="a67bd-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="a67bd-180">**Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="a67bd-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="a67bd-181">**Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale**</span><span class="sxs-lookup"><span data-stu-id="a67bd-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="a67bd-182">Nella sezione **applicato a** scegliere **il dominio del destinatario**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="a67bd-183">Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="a67bd-184">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-184">Click **Save**.</span></span>

<span data-ttu-id="a67bd-185">Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri in Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="a67bd-186">Parte 3-protezione anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a67bd-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="a67bd-187">[Anti-phishing]</span><span class="sxs-lookup"><span data-stu-id="a67bd-187">[Anti-phishing]</span></span>

<span data-ttu-id="a67bd-188">La [protezione anti-phishing](anti-phishing-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="a67bd-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="a67bd-189">La protezione anti-phishing avanzata è disponibile in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="a67bd-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="a67bd-190">Nella procedura seguente viene descritto come configurare un criterio anti-phishing ATP.</span><span class="sxs-lookup"><span data-stu-id="a67bd-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="a67bd-191">I passaggi sono simili per la configurazione di un criterio anti-phishing (senza ATP).</span><span class="sxs-lookup"><span data-stu-id="a67bd-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="a67bd-192">Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere criteri di **gestione delle minacce**  >  **Policy**  >  **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="a67bd-193">Fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="a67bd-194">Nella sezione **rappresentazione** fare clic su **modifica**e quindi specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a67bd-195">Nella scheda **Aggiungi utenti da proteggere** , attiva la protezione.</span><span class="sxs-lookup"><span data-stu-id="a67bd-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="a67bd-196">Aggiungere quindi gli utenti, ad esempio i membri del Consiglio dell'organizzazione, il CEO, il CFO e altri leader senior.</span><span class="sxs-lookup"><span data-stu-id="a67bd-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="a67bd-197">(È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco).</span><span class="sxs-lookup"><span data-stu-id="a67bd-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="a67bd-198">Nella scheda **Aggiungi domini da proteggere** , attiva **automaticamente Includi i domini che possiedo**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="a67bd-199">Se si dispone di domini personalizzati, aggiungere anche quelli.</span><span class="sxs-lookup"><span data-stu-id="a67bd-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="a67bd-200">Nella scheda **azioni** , selezionare **quarantena il messaggio** sia per l' **utente rappresentato** sia per le opzioni di **dominio rappresentate** .</span><span class="sxs-lookup"><span data-stu-id="a67bd-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="a67bd-201">Inoltre, attiva suggerimenti per la sicurezza della rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="a67bd-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="a67bd-202">Nella scheda **Intelligence della cassetta postale** , verificare che l'intelligence della cassetta postale sia attivata.</span><span class="sxs-lookup"><span data-stu-id="a67bd-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="a67bd-203">Inoltre, abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a67bd-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="a67bd-204">Nel caso in cui il messaggio **di posta elettronica venga inviato da un elenco di utenti rappresentati** , scegliere **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="a67bd-205">Nella scheda **Aggiungi mittenti attendibili e domini** specificare gli eventuali mittenti o domini attendibili che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="a67bd-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="a67bd-206">Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="a67bd-207">Nella sezione **spoofing** fare clic su **modifica**e quindi specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a67bd-208">Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.</span><span class="sxs-lookup"><span data-stu-id="a67bd-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="a67bd-209">Nella scheda **azioni** scegliere **quarantena il messaggio**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="a67bd-210">Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="a67bd-211">Se non sono state apportate modifiche, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="a67bd-212">Chiudere la pagina impostazioni di criteri predefinite.</span><span class="sxs-lookup"><span data-stu-id="a67bd-212">Close the default policy settings page.</span></span>

<span data-ttu-id="a67bd-213">Per ulteriori informazioni sulle opzioni di criteri anti-phishing, vedere [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="a67bd-214">Parte 4-protezione dalla posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a67bd-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="a67bd-215">La [protezione da posta indesiderata](anti-spam-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="a67bd-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="a67bd-216">Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere protezione dalla **Threat management**  >  **Policy**  >  **posta indesiderata**dei criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="a67bd-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="a67bd-217">Nella scheda **personalizzato** , attiva **impostazioni personalizzate** .</span><span class="sxs-lookup"><span data-stu-id="a67bd-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="a67bd-218">Espandere **criteri di filtro della posta indesiderata predefiniti**, fare clic su **modifica criteri**e quindi specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a67bd-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a67bd-219">Nella sezione **azioni di posta indesiderata e di massa** impostare la soglia su un valore pari a 5 o 6.</span><span class="sxs-lookup"><span data-stu-id="a67bd-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="a67bd-220">Nella sezione **Consenti elenchi** esaminare (e, se necessario, modificare) i propri mittenti e domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="a67bd-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="a67bd-221">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67bd-221">Click **Save**.</span></span>

<span data-ttu-id="a67bd-222">Per ulteriori informazioni sulle opzioni relative ai criteri di protezione da posta indesiderata, vedere [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="a67bd-223">Parte 5-impostazioni aggiuntive da configurare</span><span class="sxs-lookup"><span data-stu-id="a67bd-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="a67bd-224">Oltre alla configurazione della protezione da malware, URL e file dannosi, phishing e posta indesiderata, è consigliabile configurare le impostazioni di eliminazione automatica e registrazione di controllo di zero-hour.</span><span class="sxs-lookup"><span data-stu-id="a67bd-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="a67bd-225">Spurgo automatico zero-hour per la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a67bd-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="a67bd-226">Lo Zap ( [zero-hour auto Purge](zero-hour-auto-purge.md) ) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="a67bd-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="a67bd-227">Questa protezione è attivata per impostazione predefinita. Tuttavia, le condizioni seguenti devono essere soddisfatte affinché la protezione sia attiva:</span><span class="sxs-lookup"><span data-stu-id="a67bd-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="a67bd-228">Le azioni di posta indesiderata sono impostate in modo da **spostare messaggi nella cartella posta indesiderata** nei criteri di protezione dalla [posta](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a67bd-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="a67bd-229">Gli utenti hanno mantenuto le impostazioni predefinite per la [posta indesiderata](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e non hanno disattivato la protezione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a67bd-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="a67bd-230">Per ulteriori informazioni, vedere [zero-hour auto Purge-protezione da posta indesiderata e malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="a67bd-231">Registrazione di controllo per i report e le indagini</span><span class="sxs-lookup"><span data-stu-id="a67bd-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="a67bd-232">La registrazione di controllo è disponibile in abbonamenti che includono [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="a67bd-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="a67bd-233">Per visualizzare i dati nei rapporti di protezione dalle minacce, ad esempio il [dashboard di sicurezza](security-dashboard.md), i report sulla sicurezza della [posta elettronica](view-email-security-reports.md)e l' [esploratore](threat-explorer.md), la registrazione di controllo deve essere attivata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a67bd-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="a67bd-234">Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="a67bd-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="a67bd-235">Attività successive all'installazione</span><span class="sxs-lookup"><span data-stu-id="a67bd-235">Post-setup tasks</span></span>

<span data-ttu-id="a67bd-236">Dopo aver configurato le funzionalità di protezione dalle minacce, verificare la modalità di funzionamento di tali caratteristiche, rivedere e rivedere i criteri in base alle esigenze e guardare le nuove funzionalità e gli aggiornamenti dei servizi.</span><span class="sxs-lookup"><span data-stu-id="a67bd-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="a67bd-237">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="a67bd-237">**What to do**</span></span>|<span data-ttu-id="a67bd-238">**Risorse per approfondire**</span><span class="sxs-lookup"><span data-stu-id="a67bd-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="a67bd-239">Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report</span><span class="sxs-lookup"><span data-stu-id="a67bd-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="a67bd-240">Dashboard di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a67bd-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="a67bd-241">Rapporti di sicurezza della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a67bd-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="a67bd-242">Report per Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a67bd-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="a67bd-243">Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="a67bd-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="a67bd-244">Rivedere e rivedere periodicamente i criteri di protezione dalle minacce in base alle esigenze</span><span class="sxs-lookup"><span data-stu-id="a67bd-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="a67bd-245">Secure Score</span><span class="sxs-lookup"><span data-stu-id="a67bd-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="a67bd-246">Smart report e informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="a67bd-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="a67bd-247">Microsoft 365 analisi delle minacce e funzionalità di risposta</span><span class="sxs-lookup"><span data-stu-id="a67bd-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="a67bd-248">Controllare le nuove funzionalità e gli aggiornamenti dei servizi</span><span class="sxs-lookup"><span data-stu-id="a67bd-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="a67bd-249">Opzioni standard e di rilascio mirato</span><span class="sxs-lookup"><span data-stu-id="a67bd-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="a67bd-250">Centro messaggi</span><span class="sxs-lookup"><span data-stu-id="a67bd-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="a67bd-251">Roadmap di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a67bd-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="a67bd-252">Descrizioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="a67bd-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
