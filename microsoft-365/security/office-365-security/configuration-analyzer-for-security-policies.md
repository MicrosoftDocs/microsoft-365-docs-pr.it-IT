---
title: Analizzatore della configurazione per i criteri di sicurezza
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a usare l'analizzatore della configurazione per trovare e correggere i criteri di sicurezza che si trovano al di sotto dei criteri di sicurezza standard e di protezione rigida preimpostati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a78452cb3a7e4cb65c72d98b9322f217309a6d6f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165908"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="a1879-103">Analizzatore della configurazione per i criteri di protezione in EOP e Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a1879-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a1879-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a1879-104">**Applies to**</span></span>
- [<span data-ttu-id="a1879-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1879-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="a1879-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a1879-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="a1879-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1879-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a1879-108">L'analizzatore della configurazione nel Centro sicurezza & conformità fornisce una posizione centrale per trovare e correggere i criteri di sicurezza in cui le impostazioni si trovano al di sotto delle impostazioni del profilo di protezione Standard e Strict nei criteri di sicurezza [preimpostati.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a1879-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="a1879-109">I tipi di criteri seguenti vengono analizzati dall'analizzatore della configurazione:</span><span class="sxs-lookup"><span data-stu-id="a1879-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="a1879-110">**Criteri di Exchange Online Protection (EOP):** sono incluse le organizzazioni di Microsoft 365 con cassette postali di Exchange Online e le organizzazioni EOP autonome senza cassette postali di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a1879-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="a1879-111">[Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1879-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="a1879-112">[Criteri antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1879-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="a1879-113">[Criteri anti-phishing EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="a1879-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="a1879-114">**Criteri di Microsoft Defender per Office 365**: sono incluse le organizzazioni con abbonamenti ai componenti aggiuntivi di Microsoft 365 E5 o Defender per Office 365:</span><span class="sxs-lookup"><span data-stu-id="a1879-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="a1879-115">Criteri anti-phishing in Microsoft Defender per Office 365, che includono:</span><span class="sxs-lookup"><span data-stu-id="a1879-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="a1879-116">Le stesse [impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) disponibili nei criteri anti-phishing di EOP.</span><span class="sxs-lookup"><span data-stu-id="a1879-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="a1879-117">Impostazioni di rappresentazione</span><span class="sxs-lookup"><span data-stu-id="a1879-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="a1879-118">Soglie di phishing avanzate</span><span class="sxs-lookup"><span data-stu-id="a1879-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="a1879-119">[Criteri collegamenti sicuri.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a1879-119">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="a1879-120">[Criteri allegati sicuri.](set-up-atp-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a1879-120">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="a1879-121">I **valori delle** impostazioni dei criteri Standard e **Strict** utilizzati come linee di base sono descritti in Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di [Office 365.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="a1879-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1879-122">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a1879-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1879-123">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a1879-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a1879-124">Per passare direttamente alla pagina **dell'analizzatore della** configurazione, utilizzare <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="a1879-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="a1879-125">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a1879-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a1879-126">È necessario disporre delle autorizzazioni nel Centro sicurezza e conformità per poter eseguire le procedure contenute in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="a1879-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a1879-127">Per utilizzare l'analizzatore della **configurazione** e apportare aggiornamenti ai criteri di sicurezza, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a1879-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a1879-128">Per l'accesso in sola lettura all'analizzatore della  configurazione, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore **di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a1879-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a1879-129">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a1879-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="a1879-130">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1879-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a1879-131">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a1879-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="a1879-132">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a1879-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="a1879-133">Usare l'analizzatore della configurazione nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="a1879-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="a1879-134">Nel Centro sicurezza & conformità passare a **Analizzatore** configurazione criteri di gestione \>  \> **delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="a1879-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analizzatore della configurazione nella pagina Criteri \> di gestione delle minacce](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="a1879-136">L'analizzatore della configurazione ha due schede principali:</span><span class="sxs-lookup"><span data-stu-id="a1879-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="a1879-137">**Impostazioni e suggerimenti:** è possibile selezionare Standard o Strict e confrontare tali impostazioni con i criteri di sicurezza esistenti.</span><span class="sxs-lookup"><span data-stu-id="a1879-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="a1879-138">Nei risultati puoi modificare i valori delle impostazioni per portarli allo stesso livello di Standard o Strict.</span><span class="sxs-lookup"><span data-stu-id="a1879-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="a1879-139">**Analisi e cronologia della deriva della configurazione:** questa visualizzazione consente di tenere traccia delle modifiche apportate ai criteri nel tempo.</span><span class="sxs-lookup"><span data-stu-id="a1879-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="a1879-140">Scheda Impostazioni e suggerimenti nell'analizzatore della configurazione</span><span class="sxs-lookup"><span data-stu-id="a1879-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="a1879-141">Per impostazione predefinita, la scheda viene aperta nel confronto con il profilo di protezione Standard.</span><span class="sxs-lookup"><span data-stu-id="a1879-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="a1879-142">È possibile passare al confronto del profilo di protezione Strict facendo clic **su Visualizza elementi consigliati rigorosi.**</span><span class="sxs-lookup"><span data-stu-id="a1879-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="a1879-143">Per tornare indietro, selezionare **Visualizza suggerimenti standard.**</span><span class="sxs-lookup"><span data-stu-id="a1879-143">To switch back, select **View Standard recommendations**.</span></span>

![Visualizzazione delle impostazioni e degli elementi consigliati nell'analizzatore della configurazione](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="a1879-145">Per impostazione predefinita, la colonna Nome **gruppo/impostazione** criteri contiene una visualizzazione compressa dei diversi tipi di criteri di sicurezza e del numero di impostazioni che devono essere migliorate (se presenti).</span><span class="sxs-lookup"><span data-stu-id="a1879-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="a1879-146">I tipi di criteri sono:</span><span class="sxs-lookup"><span data-stu-id="a1879-146">The types of policies are:</span></span>

- <span data-ttu-id="a1879-147">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="a1879-147">**Anti-spam**</span></span>
- <span data-ttu-id="a1879-148">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="a1879-148">**Anti-phishing**</span></span>
- <span data-ttu-id="a1879-149">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="a1879-149">**Anti-malware**</span></span>
- <span data-ttu-id="a1879-150">**Allegati sicuri ATP** (se l'abbonamento include Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="a1879-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="a1879-151">**Collegamenti sicuri ATP** (se l'abbonamento include Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="a1879-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="a1879-152">Nella visualizzazione predefinita tutti gli elementi sono compressi.</span><span class="sxs-lookup"><span data-stu-id="a1879-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="a1879-153">Accanto a ogni criterio, è presente un riepilogo dei risultati del confronto dei criteri (che è possibile modificare) e delle impostazioni nei criteri corrispondenti per i profili di protezione Standard o Strict (che non è possibile modificare).</span><span class="sxs-lookup"><span data-stu-id="a1879-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="a1879-154">Verranno visualizzate le informazioni seguenti per il profilo di protezione con cui si sta confrontando:</span><span class="sxs-lookup"><span data-stu-id="a1879-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="a1879-155">**Verde:** tutte le impostazioni in tutti i criteri esistenti sono sicure almeno quanto il profilo di protezione.</span><span class="sxs-lookup"><span data-stu-id="a1879-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="a1879-156">**Ambra:** un numero limitato di impostazioni nei criteri esistenti non è così sicuro come il profilo di protezione.</span><span class="sxs-lookup"><span data-stu-id="a1879-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="a1879-157">**Rosso:** un numero significativo di impostazioni nei criteri esistenti non è sicuro come il profilo di protezione.</span><span class="sxs-lookup"><span data-stu-id="a1879-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="a1879-158">Potrebbe trattarsi di alcune impostazioni in molti criteri o di molte impostazioni in un criterio.</span><span class="sxs-lookup"><span data-stu-id="a1879-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="a1879-159">Per i confronti più vantaggiosi, vedrai il testo: **Tutte le impostazioni seguono i** \<**Standard** or **Strict**\> **suggerimenti.**</span><span class="sxs-lookup"><span data-stu-id="a1879-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="a1879-160">In caso contrario, verrà visualizzato il numero di impostazioni consigliate da modificare.</span><span class="sxs-lookup"><span data-stu-id="a1879-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="a1879-161">Se si espande **il nome del gruppo/impostazione** dei criteri, vengono rivelati tutti i criteri e le impostazioni associate in ogni criterio specifico che richiedono attenzione.</span><span class="sxs-lookup"><span data-stu-id="a1879-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="a1879-162">In caso contrario, è possibile espandere un tipo specifico di criteri (ad **esempio,** protezione da posta indesiderata) per visualizzare solo le impostazioni in quei tipi di criteri che richiedono attenzione.</span><span class="sxs-lookup"><span data-stu-id="a1879-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="a1879-163">Se il confronto non contiene consigli per il miglioramento (verde), l'espansione dei criteri non rivela nulla.</span><span class="sxs-lookup"><span data-stu-id="a1879-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="a1879-164">Se sono presenti diversi suggerimenti per il miglioramento (ambra o rosso), vengono visualizzate le impostazioni che richiedono attenzione e le informazioni corrispondenti vengono visualizzate nelle colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1879-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="a1879-165">Nome dell'impostazione che richiede attenzione.</span><span class="sxs-lookup"><span data-stu-id="a1879-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="a1879-166">Ad esempio, nello screenshot precedente, si tratta della soglia di posta elettronica in **blocco** in un criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a1879-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="a1879-167">**Criterio:** il nome del criterio interessato che contiene l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="a1879-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="a1879-168">**Applicato a:** numero di utenti a cui vengono applicati i criteri interessati.</span><span class="sxs-lookup"><span data-stu-id="a1879-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="a1879-169">**Configurazione corrente:** il valore corrente dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="a1879-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="a1879-170">**Ultima modifica:** data dell'ultima modifica del criterio.</span><span class="sxs-lookup"><span data-stu-id="a1879-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="a1879-171">**Suggerimenti:** valore dell'impostazione nel profilo di protezione Standard o Strict.</span><span class="sxs-lookup"><span data-stu-id="a1879-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="a1879-172">Per modificare il valore dell'impostazione nei criteri in modo che corrisponda al valore consigliato nel profilo di protezione, fare clic su **Adotta.**</span><span class="sxs-lookup"><span data-stu-id="a1879-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="a1879-173">Se la modifica ha esito positivo, verrà visualizzato il messaggio: **Suggerimenti adottati correttamente.**</span><span class="sxs-lookup"><span data-stu-id="a1879-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="a1879-174">Fare **clic su** Aggiorna per visualizzare il numero ridotto di elementi consigliati e la rimozione della riga di impostazione/criterio specifica dai risultati.</span><span class="sxs-lookup"><span data-stu-id="a1879-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="a1879-175">Scheda Analisi e cronologia della deriva della configurazione nell'analizzatore della configurazione</span><span class="sxs-lookup"><span data-stu-id="a1879-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="a1879-176">Questa scheda consente di tenere traccia delle modifiche apportate ai criteri di sicurezza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a1879-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="a1879-177">Per impostazione predefinita, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1879-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="a1879-178">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="a1879-178">**Last modified**</span></span>
- <span data-ttu-id="a1879-179">**Modificato da**</span><span class="sxs-lookup"><span data-stu-id="a1879-179">**Modified by**</span></span>
- <span data-ttu-id="a1879-180">**Nome impostazione**</span><span class="sxs-lookup"><span data-stu-id="a1879-180">**Setting Name**</span></span>
- <span data-ttu-id="a1879-181">**Criterio**</span><span class="sxs-lookup"><span data-stu-id="a1879-181">**Policy**</span></span>
- <span data-ttu-id="a1879-182">**Type**</span><span class="sxs-lookup"><span data-stu-id="a1879-182">**Type**</span></span>

<span data-ttu-id="a1879-183">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a1879-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a1879-184">Nel riquadro **a** comparsa Filtri visualizzato, è possibile selezionare uno dei filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1879-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="a1879-185">**Ora di** inizio **e ora di** fine (data)</span><span class="sxs-lookup"><span data-stu-id="a1879-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="a1879-186">**Protezione standard** o **protezione rigida**</span><span class="sxs-lookup"><span data-stu-id="a1879-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="a1879-187">Per esportare i risultati in un file CSV, fare clic su **Esporta.**</span><span class="sxs-lookup"><span data-stu-id="a1879-187">To export the results to a .csv file, click **Export**.</span></span>

![Analisi della deriva della configurazione e visualizzazione della cronologia nell'analizzatore della configurazione](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
