---
title: Configurare team con la protezione di base
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Come distribuire team con un livello di protezione di base.
ms.openlocfilehash: cd5a88069b9947bd4dcb01f6ca76620bb8ed9a52
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200294"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="fc01a-103">Configurare team con la protezione di base</span><span class="sxs-lookup"><span data-stu-id="fc01a-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="fc01a-104">Questo articolo spiega come distribuire team con un livello di protezione di base.</span><span class="sxs-lookup"><span data-stu-id="fc01a-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="fc01a-105">Questo livello offre agli utenti un'ampia gamma di opzioni per la collaborazione, migliorando la gestione delle autorizzazioni e fornendo una protezione di base dalla condivisione eccessiva.</span><span class="sxs-lookup"><span data-stu-id="fc01a-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="fc01a-106">Le protezioni consigliate per questo livello includono criteri di accesso alle identità e ai dispositivi e protezione dal malware.</span><span class="sxs-lookup"><span data-stu-id="fc01a-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="fc01a-107">Inoltre, è possibile applicare criteri di accesso condizionale e funzionalità di prevenzione della perdita dei dati come necessario.</span><span class="sxs-lookup"><span data-stu-id="fc01a-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="fc01a-108">Protezioni iniziali</span><span class="sxs-lookup"><span data-stu-id="fc01a-108">Initial protections</span></span>

<span data-ttu-id="fc01a-109">Come primo passaggio, è consigliabile configurare criteri di base per le identità e l'accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fc01a-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="fc01a-110">Per informazioni dettagliate, vedere [Suggerimenti sui criteri per la protezione di chat, gruppi e file di Teams](../security/office-365-security/teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fc01a-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="fc01a-111">È anche consigliabile attivare le funzionalità di base di Defender per Office 365 per prevenire malware in documenti, allegati e collegamenti.</span><span class="sxs-lookup"><span data-stu-id="fc01a-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="fc01a-112">È consigliabile attivare ognuna delle opzioni indicate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="fc01a-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="fc01a-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="fc01a-113">Option</span></span>|<span data-ttu-id="fc01a-114">Informazioni</span><span class="sxs-lookup"><span data-stu-id="fc01a-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="fc01a-115">Allegati sicuri per SPO, OneDrive e Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="fc01a-116">Allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="fc01a-116">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)<br>[<span data-ttu-id="fc01a-117">Defender per Office 365 - SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="fc01a-118">Sicurezza documenti</span><span class="sxs-lookup"><span data-stu-id="fc01a-118">Safe Documents</span></span>|[<span data-ttu-id="fc01a-119">Sicurezza documenti in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="fc01a-119">Safe Documents in Microsoft Defender for Office 365</span></span>](../security/office-365-security/safe-docs.md)|
|<span data-ttu-id="fc01a-120">Collegamenti sicuri per Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-120">Safe Links for Teams</span></span>|[<span data-ttu-id="fc01a-121">Collegamenti sicuri di Office 365 in Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-121">Office 365 Safe Links in Teams</span></span>](../security/office-365-security/safe-links.md#safe-links-settings-for-microsoft-teamssafe-links-settings-for-microsoft-teams)<br>[<span data-ttu-id="fc01a-122">Collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="fc01a-122">Safe Links</span></span>](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="fc01a-123">Condivisione con gli utenti guest in Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-123">Teams guest sharing</span></span>

<span data-ttu-id="fc01a-124">In ognuno dei livelli è possibile la condivisione con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc01a-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="fc01a-125">Per i livelli dei dati sensibili e altamente sensibili, si avrà la possibilità di disattivare la condivisione guest al livello di team usando le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="fc01a-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="fc01a-126">Tuttavia, per il funzionamento della condivisione guest in Teams è necessario attivare l'opzione a livello aziendale.</span><span class="sxs-lookup"><span data-stu-id="fc01a-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="fc01a-128">Per configurare le impostazioni di accesso guest di Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="fc01a-129">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fc01a-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="fc01a-130">Nel riquadro di spostamento sinistro fare clic su **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="fc01a-131">In **Interfacce di amministrazione** fare clic su **Teams**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="fc01a-132">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** nel riquadro di spostamento sinistro e fare clic su **Accesso guest**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="fc01a-133">Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia \*\*\*\* abilitata.</span><span class="sxs-lookup"><span data-stu-id="fc01a-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="fc01a-134">Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="fc01a-135">Dopo l'attivazione, potrebbero essere necessarie fino a 24 ore prima che le impostazioni guest di Teams diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="fc01a-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="fc01a-136">La condivisione guest è attivata per impostazione predefinita per i gruppi di Office 365 e SharePoint. Tuttavia, se in precedenza si sono modificate le impostazioni di condivisione guest per la propria organizzazione, è consigliabile rivedere [Collaborare con gli utenti guest in un team](./collaborate-as-team.md) per assicurarsi che la condivisione guest sia disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="fc01a-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](./collaborate-as-team.md) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="fc01a-137">Condivisione di siti e file</span><span class="sxs-lookup"><span data-stu-id="fc01a-137">Site and file sharing</span></span>

<span data-ttu-id="fc01a-138">Per ridurre il rischio di condivisione accidentale di file o cartelle con persone esterne all'organizzazione, è consigliabile modificare il collegamento di condivisione predefinito per SharePoint in *Solo gli utenti dell'organizzazione*.</span><span class="sxs-lookup"><span data-stu-id="fc01a-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="fc01a-139">Se gli utenti devono condividere all'esterno ed è stata abilitata la condivisione guest, potranno comunque modificare il tipo di collegamento quando condividono.</span><span class="sxs-lookup"><span data-stu-id="fc01a-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="fc01a-140">Per modificare il collegamento di condivisione predefinito</span><span class="sxs-lookup"><span data-stu-id="fc01a-140">To change the default sharing link</span></span>
1. <span data-ttu-id="fc01a-141">Aprire l'[interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="fc01a-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="fc01a-142">In **Criteri** fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="fc01a-143">In **Collegamenti di file e cartelle** selezionare **Solo gli utenti dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="fc01a-144">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-144">Click **Save**.</span></span>

<span data-ttu-id="fc01a-145">Per un'esperienza di condivisione guest ottimale, è inoltre consigliabile abilitare l'[Integrazione di SharePoint e OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span><span class="sxs-lookup"><span data-stu-id="fc01a-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="fc01a-146">Creare un team</span><span class="sxs-lookup"><span data-stu-id="fc01a-146">Create a team</span></span>

<span data-ttu-id="fc01a-147">Un'ulteriore configurazione per il livello di protezione di base va effettuata nel sito di SharePoint associato a un team.</span><span class="sxs-lookup"><span data-stu-id="fc01a-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="fc01a-148">[Creare un team pubblico o privato](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) prima di procedere alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="fc01a-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="fc01a-149">Impostazioni di condivisione del sito</span><span class="sxs-lookup"><span data-stu-id="fc01a-149">Site sharing settings</span></span>

<span data-ttu-id="fc01a-150">Per impostazione predefinita, i membri di un sito di SharePoint possono invitare altri utenti nel sito.</span><span class="sxs-lookup"><span data-stu-id="fc01a-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="fc01a-151">Quando un sito fa parte di un team, i membri del team sono inclusi come membri del sito.</span><span class="sxs-lookup"><span data-stu-id="fc01a-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="fc01a-152">Tuttavia, le persone aggiunte direttamente al sito non hanno accesso al resto del team.</span><span class="sxs-lookup"><span data-stu-id="fc01a-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="fc01a-153">Per questo motivo, è consigliabile gestire le autorizzazioni esclusivamente attraverso il team.</span><span class="sxs-lookup"><span data-stu-id="fc01a-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="fc01a-154">Per agevolare la gestione delle autorizzazioni, è consigliabile configurare il sito associato in modo da consentire solo ai proprietari di condividere il sito.</span><span class="sxs-lookup"><span data-stu-id="fc01a-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="fc01a-155">Questo semplifica la gestione delle autorizzazioni e impedisce che qualcuno possa accedere senza che il proprietario del team ne sia a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="fc01a-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="fc01a-156">Eseguire questa operazione per ogni team che richiede la protezione di base.</span><span class="sxs-lookup"><span data-stu-id="fc01a-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="fc01a-157">Per aggiornare le impostazioni di condivisione del sito</span><span class="sxs-lookup"><span data-stu-id="fc01a-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="fc01a-158">Nella barra degli strumenti per il team fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="fc01a-159">Fare clic su **Apri in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="fc01a-160">Nella barra degli strumenti del sito di SharePoint fare clic sull'icona delle impostazioni, poi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="fc01a-161">Nel riquadro **Autorizzazioni sito**, in **Condivisione sito**, fare clic su **Modifica il metodo di condivisione dei membri**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-161">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
5. <span data-ttu-id="fc01a-162">In **Autorizzazioni di condivisione** selezionare **I proprietari e i membri del sito e gli utenti con autorizzazioni di modifica possono condividere file e cartelle, ma solo i proprietari del sito possono condividere il sito**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc01a-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="fc01a-163">Protezioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fc01a-163">Additional protections</span></span>

<span data-ttu-id="fc01a-164">In Microsoft 365 sono disponibili altri metodi per proteggere i contenuti.</span><span class="sxs-lookup"><span data-stu-id="fc01a-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="fc01a-165">Valutare se le opzioni seguenti possono migliorare la sicurezza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc01a-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="fc01a-166">Fare in modo che gli utenti guest accettino le [condizioni per l'utilizzo](/azure/active-directory/conditional-access/terms-of-use).</span><span class="sxs-lookup"><span data-stu-id="fc01a-166">Have guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="fc01a-167">Configurare un [criterio di timeout della sessione](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="fc01a-167">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="fc01a-168">Creare [tipi di informazioni sensibili](../compliance/sensitive-information-type-learn-about.md) e usare la [prevenzione della perdita dei dati](../compliance/data-loss-prevention-policies.md) per impostare criteri per l'accesso alle informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="fc01a-168">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/data-loss-prevention-policies.md) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc01a-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc01a-169">See Also</span></span>

[<span data-ttu-id="fc01a-170">Gestire i criteri di riunione in Teams</span><span class="sxs-lookup"><span data-stu-id="fc01a-170">Manage meeting policies in Teams</span></span>](/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="fc01a-171">Introduzione alla gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="fc01a-171">Get started with insider risk management</span></span>](../compliance/insider-risk-management-configure.md)