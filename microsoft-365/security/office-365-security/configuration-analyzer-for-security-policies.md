---
title: Analizzatore di configurazione per i criteri di sicurezza
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come utilizzare l'analizzatore di configurazione per individuare e correggere i criteri di sicurezza che si trovano al di sotto dei criteri di protezione standard e di protezione preimpostati.
ms.openlocfilehash: 5a57e16dcac6afee910ce546d3a40c2c9c669f2d
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616153"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="62a96-103">Analizzatore di configurazione per i criteri di protezione in EOP e Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="62a96-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="62a96-104">Le funzionalità descritte in questo argomento sono in anteprima, non sono disponibili in tutte le organizzazioni e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="62a96-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="62a96-105">Per informazioni sulla pianificazione dei rilasci, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="62a96-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="62a96-106">Analizzatore di configurazione nel centro sicurezza & conformità fornisce una posizione centrale per individuare e correggere i criteri di sicurezza in cui le impostazioni sono al di sotto delle impostazioni di protezione standard e del profilo di protezione rigido nei [criteri di sicurezza preimpostati](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="62a96-107">I seguenti tipi di criteri vengono analizzati dall'analizzatore della configurazione:</span><span class="sxs-lookup"><span data-stu-id="62a96-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="62a96-108">**Criteri di Exchange Online Protection (EOP)**: sono incluse le organizzazioni Microsoft 365 con le cassette postali di Exchange Online e le organizzazioni EOP autonome senza cassette postali di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62a96-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="62a96-109">[Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="62a96-110">[Criteri anti-malware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="62a96-111">[Criteri di anti-phishing di EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="62a96-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="62a96-112">**Microsoft Defender per i criteri di office 365**: include le organizzazioni con Microsoft 365 E5 o gli abbonamenti del componente aggiuntivo Defender per Office 365:</span><span class="sxs-lookup"><span data-stu-id="62a96-112">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="62a96-113">Criteri di anti-phishing in Microsoft Defender per Office 365, che includono:</span><span class="sxs-lookup"><span data-stu-id="62a96-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="62a96-114">Le stesse [impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) disponibili nei criteri di anti-phishing di EOP.</span><span class="sxs-lookup"><span data-stu-id="62a96-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="62a96-115">Impostazioni di rappresentazione</span><span class="sxs-lookup"><span data-stu-id="62a96-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="62a96-116">Soglie di phishing avanzate</span><span class="sxs-lookup"><span data-stu-id="62a96-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="62a96-117">[Criteri collegamenti sicuri](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="62a96-118">[Criteri allegati sicuri](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="62a96-119">I valori di impostazione dei criteri **standard** e **rigorosi** utilizzati come linee di base sono descritti in [impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62a96-120">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="62a96-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="62a96-121">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="62a96-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="62a96-122">Per passare direttamente alla pagina dell' **analizzatore** dell'utilità di configurazione, utilizzare <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="62a96-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="62a96-123">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="62a96-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="62a96-124">Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni per il Centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="62a96-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="62a96-125">Per utilizzare l'analizzatore di configurazione **e** aggiornare i criteri di sicurezza, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="62a96-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="62a96-126">Per l'accesso in sola lettura all'analizzatore di configurazione, è necessario essere membri dei gruppi di ruoli **lettore globale** o lettore di **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="62a96-126">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="62a96-127">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="62a96-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="62a96-128">**Note**:</span><span class="sxs-lookup"><span data-stu-id="62a96-128">**Notes**:</span></span>

  - <span data-ttu-id="62a96-129">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62a96-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="62a96-130">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="62a96-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="62a96-131">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="62a96-131">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="62a96-132">Utilizzare l'analizzatore di configurazione nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="62a96-132">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="62a96-133">Nel centro sicurezza & conformità, accedere a  \>  \> **analizzatore configurazione** criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="62a96-133">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget Configuration Analyzer nella pagina Criteri di gestione dei pericoli \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="62a96-135">L'analizzatore di configurazione dispone di due schede principali:</span><span class="sxs-lookup"><span data-stu-id="62a96-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="62a96-136">**Impostazioni e suggerimenti**: si seleziona standard o Strict e si confrontano tali impostazioni con i criteri di sicurezza esistenti.</span><span class="sxs-lookup"><span data-stu-id="62a96-136">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="62a96-137">Nei risultati, è possibile modificare i valori delle impostazioni per riportarli allo stesso livello di standard o Strict.</span><span class="sxs-lookup"><span data-stu-id="62a96-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="62a96-138">**Analisi della deriva di configurazione e cronologia**: questa visualizzazione consente di monitorare le modifiche dei criteri nel tempo.</span><span class="sxs-lookup"><span data-stu-id="62a96-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="62a96-139">Scheda Impostazioni e suggerimenti nell'analizzatore di configurazione</span><span class="sxs-lookup"><span data-stu-id="62a96-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="62a96-140">Per impostazione predefinita, la scheda viene visualizzata nel confronto con il profilo di protezione standard.</span><span class="sxs-lookup"><span data-stu-id="62a96-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="62a96-141">È possibile passare al confronto del profilo di protezione rigoroso facendo clic su **Visualizza suggerimenti rigorosi**.</span><span class="sxs-lookup"><span data-stu-id="62a96-141">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="62a96-142">Per tornare indietro, selezionare **Visualizza suggerimenti standard**.</span><span class="sxs-lookup"><span data-stu-id="62a96-142">To switch back, select **View Standard recommendations**.</span></span>

![Visualizzazione delle impostazioni e dei suggerimenti nell'analizzatore di configurazione](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="62a96-144">Per impostazione predefinita, la colonna **gruppo di criteri/Nome impostazione** contiene una visualizzazione compressa dei diversi tipi di criteri di sicurezza e il numero di impostazioni che devono essere migliorate (se presenti).</span><span class="sxs-lookup"><span data-stu-id="62a96-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="62a96-145">I tipi di criteri sono:</span><span class="sxs-lookup"><span data-stu-id="62a96-145">The types of policies are:</span></span>

- <span data-ttu-id="62a96-146">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="62a96-146">**Anti-spam**</span></span>
- <span data-ttu-id="62a96-147">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="62a96-147">**Anti-phishing**</span></span>
- <span data-ttu-id="62a96-148">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="62a96-148">**Anti-malware**</span></span>
- <span data-ttu-id="62a96-149">**Allegati sicuri ATP** (se l'abbonamento include Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="62a96-149">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="62a96-150">**Collegamenti sicuri ATP** (se l'abbonamento include Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="62a96-150">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="62a96-151">Nella visualizzazione predefinita, tutto è compresso.</span><span class="sxs-lookup"><span data-stu-id="62a96-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="62a96-152">Accanto a ogni criterio, è disponibile un riepilogo dei risultati del confronto tra i criteri (che è possibile modificare) e le impostazioni nei criteri corrispondenti per i profili di protezione standard o rigorosi (che non è possibile modificare).</span><span class="sxs-lookup"><span data-stu-id="62a96-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="62a96-153">Verranno visualizzate le informazioni seguenti per il profilo di protezione a cui si sta eseguendo il confronto:</span><span class="sxs-lookup"><span data-stu-id="62a96-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="62a96-154">**Verde**: tutte le impostazioni di tutti i criteri esistenti sono almeno altrettanto sicure del profilo di protezione.</span><span class="sxs-lookup"><span data-stu-id="62a96-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="62a96-155">**Ambra**: un numero limitato di impostazioni nei criteri esistenti non è più sicuro del profilo di protezione.</span><span class="sxs-lookup"><span data-stu-id="62a96-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="62a96-156">**Rosso**: un numero significativo di impostazioni nei criteri esistenti non è più sicuro del profilo di protezione.</span><span class="sxs-lookup"><span data-stu-id="62a96-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="62a96-157">Questo potrebbe essere un paio di impostazioni in molti criteri o in molte impostazioni di un criterio.</span><span class="sxs-lookup"><span data-stu-id="62a96-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="62a96-158">Per i confronti favorevoli, viene visualizzato il testo: **tutte le impostazioni seguono** i \<**Standard** or **Strict**\> **suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="62a96-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="62a96-159">In caso contrario, verrà visualizzato il numero di impostazioni consigliate da modificare.</span><span class="sxs-lookup"><span data-stu-id="62a96-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="62a96-160">Se si espande il **nome del gruppo di criteri/impostazione**, vengono rivelati tutti i criteri e le impostazioni associate in ogni criterio specifico che richiede attenzione.</span><span class="sxs-lookup"><span data-stu-id="62a96-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="62a96-161">In alternativa, è possibile espandere un tipo specifico di criteri, ad esempio la protezione da **posta indesiderata**, per visualizzare solo tali impostazioni in quei tipi di criteri che richiedono attenzione.</span><span class="sxs-lookup"><span data-stu-id="62a96-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="62a96-162">Se il confronto non ha suggerimenti per il miglioramento (verde), l'espansione del criterio non rivela nulla.</span><span class="sxs-lookup"><span data-stu-id="62a96-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="62a96-163">Se è presente un numero qualsiasi di suggerimenti per il miglioramento (ambra o rosso), vengono rivelate le impostazioni che richiedono attenzione e vengono riportate le informazioni corrispondenti nelle colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="62a96-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="62a96-164">Nome dell'impostazione che richiede attenzione.</span><span class="sxs-lookup"><span data-stu-id="62a96-164">The name of the setting that requires your attention.</span></span> <span data-ttu-id="62a96-165">Ad esempio, nella schermata precedente, è la soglia di **posta elettronica in blocco** in un criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="62a96-165">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="62a96-166">**Policy**: il nome del criterio coinvolto che contiene l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="62a96-166">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="62a96-167">**Applicato a**: il numero di utenti a cui sono applicati i criteri coinvolti.</span><span class="sxs-lookup"><span data-stu-id="62a96-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="62a96-168">**Configurazione corrente**: valore corrente dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="62a96-168">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="62a96-169">**Last modified**: la data in cui è stato modificato l'ultima volta il criterio.</span><span class="sxs-lookup"><span data-stu-id="62a96-169">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="62a96-170">**Suggerimenti**: il valore dell'impostazione nel profilo di protezione standard o rigoroso.</span><span class="sxs-lookup"><span data-stu-id="62a96-170">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="62a96-171">Per modificare il valore dell'impostazione del criterio in modo che corrisponda al valore consigliato nel profilo di protezione, fare clic su **adotta**.</span><span class="sxs-lookup"><span data-stu-id="62a96-171">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="62a96-172">Se la modifica ha esito positivo, verrà visualizzato il messaggio: **suggerimenti adottati correttamente**.</span><span class="sxs-lookup"><span data-stu-id="62a96-172">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="62a96-173">Fare clic su **Aggiorna** per visualizzare il numero ridotto di suggerimenti e la rimozione della riga specifica dell'impostazione o dei criteri dai risultati.</span><span class="sxs-lookup"><span data-stu-id="62a96-173">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="62a96-174">Scheda cronologia e analisi della deriva di configurazione nell'analizzatore di configurazione</span><span class="sxs-lookup"><span data-stu-id="62a96-174">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="62a96-175">Questa scheda consente di monitorare le modifiche apportate ai criteri di sicurezza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="62a96-175">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="62a96-176">Per impostazione predefinita, vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="62a96-176">By default, the following information is displayed:</span></span>

- <span data-ttu-id="62a96-177">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="62a96-177">**Last modified**</span></span>
- <span data-ttu-id="62a96-178">**Modificato da**</span><span class="sxs-lookup"><span data-stu-id="62a96-178">**Modified by**</span></span>
- <span data-ttu-id="62a96-179">**Nome dell'impostazione**</span><span class="sxs-lookup"><span data-stu-id="62a96-179">**Setting Name**</span></span>
- <span data-ttu-id="62a96-180">**Criterio**</span><span class="sxs-lookup"><span data-stu-id="62a96-180">**Policy**</span></span>
- <span data-ttu-id="62a96-181">**Type**</span><span class="sxs-lookup"><span data-stu-id="62a96-181">**Type**</span></span>

<span data-ttu-id="62a96-182">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="62a96-182">To filter the results, click **Filter**.</span></span> <span data-ttu-id="62a96-183">Nel riquadro a comparsa **filtri** che viene visualizzato, è possibile scegliere tra i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="62a96-183">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="62a96-184">**Ora di inizio** e **ora di fine** (Data)</span><span class="sxs-lookup"><span data-stu-id="62a96-184">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="62a96-185">**Protezione standard** o **protezione rigorosa**</span><span class="sxs-lookup"><span data-stu-id="62a96-185">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="62a96-186">Per esportare i risultati in un file CSV, fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="62a96-186">To export the results to a .csv file, click **Export**.</span></span>

![Analisi della deriva della configurazione e visualizzazione della cronologia nell'analizzatore di configurazione](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
