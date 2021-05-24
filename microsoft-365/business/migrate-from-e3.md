---
title: Eseguire la migrazione a Microsoft 365 Business da Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Se hai un abbonamento Office 365 E3 ma non hai più di 300 dipendenti, valuta la possibilità di passare a Microsoft 365 Business Premium.
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623606"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="8530f-103">Migrazione da Office 365 E3 a Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8530f-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="8530f-104">Microsoft 365 Business Premium ha tutto il necessario per la tua piccola azienda, combinando le migliori app di produttività basate sul cloud con semplici funzionalità di gestione e sicurezza dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8530f-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="8530f-105">Se attualmente si dispone di una sottoscrizione Office 365 E3, ma non si hanno più di 300 dipendenti, è consigliabile passare a Microsoft 365 Business Premium per aggiungere funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8530f-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="8530f-106">La migrazione è semplice: prima di tutto si cambia licenza e vengono mantenuti tutti i dati e le informazioni utente nell'abbonamento corrente.</span><span class="sxs-lookup"><span data-stu-id="8530f-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="8530f-107">Dopo la migrazione, è necessario configurare le funzionalità aggiunte in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8530f-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="8530f-108">Differenze tra Office 365 E3 e Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8530f-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="8530f-109">Questa tabella mostra le differenze tra Microsoft 365 Business Premium e Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="8530f-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="8530f-110">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="8530f-110">Feature</span></span>    | <span data-ttu-id="8530f-111">Supporto in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8530f-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="8530f-112">Supporto in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="8530f-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="8530f-113">**Locale**</span><span class="sxs-lookup"><span data-stu-id="8530f-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="8530f-114">Office app<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8530f-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="8530f-115">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="8530f-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="8530f-116">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="8530f-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="8530f-117">**App per la produttività cloud**</span><span class="sxs-lookup"><span data-stu-id="8530f-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="8530f-118">Exchange Online e Outlook</span><span class="sxs-lookup"><span data-stu-id="8530f-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="8530f-119">Limite di archiviazione di 50 GB per cassetta postale e limite Archiviazione Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8530f-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="8530f-120">Limite di archiviazione di 100 GB per cassetta postale e limite Archiviazione Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8530f-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="8530f-121">Teams</span><span class="sxs-lookup"><span data-stu-id="8530f-121">Teams</span></span>    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="8530f-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="8530f-124">OneDrive for Business</span></span>    | <span data-ttu-id="8530f-125">Limite di archiviazione di 1 TB per utente</span><span class="sxs-lookup"><span data-stu-id="8530f-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="8530f-126">Illimitati</span><span class="sxs-lookup"><span data-stu-id="8530f-126">Unlimited</span></span> | 
| <span data-ttu-id="8530f-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="8530f-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="8530f-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="8530f-130">StaffHub</span></span>    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) |
| <span data-ttu-id="8530f-133">**Threat Protection**</span><span class="sxs-lookup"><span data-stu-id="8530f-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="8530f-134">Defender per Office 365 Piano 1</span><span class="sxs-lookup"><span data-stu-id="8530f-134">Defender for Office 365 Plan 1</span></span> | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="8530f-136">Non incluso, ma può essere aggiunto in</span><span class="sxs-lookup"><span data-stu-id="8530f-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="8530f-137">**Gestione delle identità**</span><span class="sxs-lookup"><span data-stu-id="8530f-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="8530f-138">Reimpostazione della password self-service per account Azure Active Directory (Azure AD), Autenticazione a più fattori (MFA) di Azure AD, Accesso condizionale, writeback delle password per le identità locali</span><span class="sxs-lookup"><span data-stu-id="8530f-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="8530f-140">**Gestione di dispositivi e app**</span><span class="sxs-lookup"><span data-stu-id="8530f-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="8530f-141">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="8530f-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="8530f-143">Attivazione di computer condivisi</span><span class="sxs-lookup"><span data-stu-id="8530f-143">Shared computer activation</span></span>|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="8530f-146">Aggiornare i diritti Windows 10 Pro licenze win 7/8.1 Pro licenze</span><span class="sxs-lookup"><span data-stu-id="8530f-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    ||
| <span data-ttu-id="8530f-148">**Protezione delle informazioni**</span><span class="sxs-lookup"><span data-stu-id="8530f-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="8530f-149">Prevenzione della perdita di dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="8530f-149">Office 365 Data Loss Prevention</span></span>|    ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)|![Incluso con Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="8530f-152">Azure Information Protection Piano 1, BitLocker sicurezza</span><span class="sxs-lookup"><span data-stu-id="8530f-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="8530f-154">Azure Information Protection Piano 1, etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="8530f-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="8530f-156">**Licenza Accesso client (diritti CAL)**</span><span class="sxs-lookup"><span data-stu-id="8530f-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="8530f-157">Enterprise Cal Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="8530f-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluso con Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="8530f-159"><sup>1</sup> La Microsoft 365 Business Premium delle app Office non include l'attivazione di contratti multilicenza tramite Criteri di gruppo, telemetria delle app, controlli di aggiornamento, confronto e richiesta di informazioni sui fogli di calcolo o business intelligence.</span><span class="sxs-lookup"><span data-stu-id="8530f-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="8530f-160">Migrazione</span><span class="sxs-lookup"><span data-stu-id="8530f-160">Migration</span></span>

<span data-ttu-id="8530f-161">Per eseguire la migrazione dell'abbonamento, vedere [Modificare](../commerce/subscriptions/change-plans-manually.md) i piani manualmente per istruzioni se si desidera spostare solo alcune persone Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8530f-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="8530f-162">È inoltre possibile [aggiornare automaticamente](../commerce/subscriptions/upgrade-to-different-plan.md)tutti gli utenti o collaborare con un partner per spostare la sottoscrizione e le licenze di E3 in una sottoscrizione Microsoft 365 Business Premium elettronica.</span><span class="sxs-lookup"><span data-stu-id="8530f-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="8530f-163">Nelle sezioni seguenti vengono descritte le modifiche da apportare, se presenti, e le operazioni che è possibile eseguire dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="8530f-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="8530f-164">Office 365 Dati e configurazione della sottoscrizione E3</span><span class="sxs-lookup"><span data-stu-id="8530f-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="8530f-165">Non è necessario apportare modifiche alla sottoscrizione o ai dati correnti prima di eseguire la migrazione, tra cui:</span><span class="sxs-lookup"><span data-stu-id="8530f-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="8530f-166">Configurazione della sottoscrizione, ad esempio record DNS e nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="8530f-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="8530f-167">Account utente e di gruppo e impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="8530f-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="8530f-168">Configurazioni dei servizi di produttività e relativi dati, ad esempio Teams, cassette postali Exchange Online, siti di SharePoint Online, cartelle OneDrive for Business e OneNote blocchi appunti.</span><span class="sxs-lookup"><span data-stu-id="8530f-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="8530f-169">Office le applicazioni verranno ridimensionate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8530f-169">Office applications will scale automatically.</span></span> <span data-ttu-id="8530f-170">Office 365 licenze moderne controllano l'assegnazione delle licenze dell'utente ogni 72 ore e convertono le applicazioni Office nella versione corrispondente all'abbonamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8530f-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="8530f-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8530f-171">Windows 10</span></span>

<span data-ttu-id="8530f-172">Se il Windows non è già in Windows Pro Creator, aggiornali [a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="8530f-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="8530f-173">Configurare criteri per proteggere i dispositivi e i file degli utenti</span><span class="sxs-lookup"><span data-stu-id="8530f-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="8530f-174">Se si configurano Office 365 e dispositivi MDM, tali dispositivi  verranno elencati nella pagina Dispositivi nell'interfaccia di amministrazione Microsoft 365 aziendale.</span><span class="sxs-lookup"><span data-stu-id="8530f-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8530f-175">Tutti i criteri impostati verranno visualizzati nell'elenco dei criteri classici nel [portale di Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="8530f-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="8530f-176">Dopo aver assegnato le licenze a Microsoft 365 Business Premium, puoi iniziare a proteggere i dispositivi e i file degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8530f-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="8530f-177">Se tutti gli utenti dell'organizzazione sono stati aggiornati a Microsoft 365 Business Premium, verrà visualizzata la configurazione guidata nella home page e sarà possibile seguire la procedura di configurazione [di Microsoft 365 Business Premium](set-up.md) nella procedura di configurazione guidata per proteggere file e dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="8530f-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="8530f-178">Puoi anche completare questi passaggi nella pagina Dispositivi:</span><span class="sxs-lookup"><span data-stu-id="8530f-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="8530f-179">Nell'interfaccia di amministrazione, nel riquadro di spostamento sinistro, vai a **Criteri** \> **dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="8530f-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="8530f-180">Nella pagina **Criteri dispositivo** scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8530f-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="8530f-181">Nel riquadro **Aggiungi** criterio assegna un nome al criterio e quindi scegli un **tipo di criterio** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8530f-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="8530f-182">Puoi configurare criteri di applicazione per la protezione dei file nei dispositivi Android e iPhone, nonché Windows 10 e puoi configurare i criteri di configurazione dei dispositivi per i dispositivi Windows 10 aziendali.</span><span class="sxs-lookup"><span data-stu-id="8530f-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="8530f-183">Per informazioni dettagliate, vedere i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8530f-183">See the following links for details:</span></span>

  - [<span data-ttu-id="8530f-184">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="8530f-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="8530f-185">Configurare le impostazioni di protezione delle app per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="8530f-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="8530f-186">Impostare le impostazioni di protezione dei dispositivi Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="8530f-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="8530f-187">Dopo aver configurato i criteri, tu e i tuoi dipendenti puoi configurare i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="8530f-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="8530f-188">Vedi [Configurare i Windows per Microsoft 365 Business Premium utenti](set-up-windows-devices.md) per la procedura per Windows dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8530f-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="8530f-189">Vedi [Configurare i dispositivi mobili per Microsoft 365 Business Premium utenti per](set-up-mobile-devices.md) la procedura per telefoni Android e iPhone.</span><span class="sxs-lookup"><span data-stu-id="8530f-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="8530f-190">Dimensione cassetta postale</span><span class="sxs-lookup"><span data-stu-id="8530f-190">Mailbox Size</span></span>

<span data-ttu-id="8530f-191">Microsoft 365 Business Premium ha un limite di archiviazione di 50 GB in quanto utilizza Exchange Online Piano 1.</span><span class="sxs-lookup"><span data-stu-id="8530f-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="8530f-192">Durante la migrazione a Microsoft 365 Business Premium, se uno degli utenti supera i 50 GB di spazio di archiviazione delle cassette postali, è consigliabile assegnare a questo utente un piano 2 di Exchange Online e rimuovere il piano Exchange Online 1 poiché non è possibile assegnare entrambi.</span><span class="sxs-lookup"><span data-stu-id="8530f-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="8530f-193">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="8530f-193">Threat protection</span></span>

<span data-ttu-id="8530f-194">Dopo la migrazione a Microsoft 365 Business Premium, hai Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="8530f-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="8530f-195">Per [una panoramica, vedi Microsoft Defender Office 365](../security/office-365-security/defender-for-office-365.md) informazioni generali.</span><span class="sxs-lookup"><span data-stu-id="8530f-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="8530f-196">Per la configurazione, vedere [configurare collegamenti](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)sicuri, [configurare](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)allegati sicuri e configurare [anti-phishing in Defender per Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="8530f-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="8530f-197">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="8530f-197">Sensitivity labels</span></span>

<span data-ttu-id="8530f-198">Per iniziare a usare le etichette di riservatezza, vedi [Panoramica delle etichette di riservatezza](../compliance/sensitivity-labels.md) e video sulla creazione e gestione delle etichette [di](../business-video/create-sensitivity-labels.md) riservatezza.</span><span class="sxs-lookup"><span data-stu-id="8530f-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>

## <a name="related-content"></a><span data-ttu-id="8530f-199">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="8530f-199">Related content</span></span>

<span data-ttu-id="8530f-200">[Modificare i piani manualmente](../commerce/subscriptions/change-plans-manually.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8530f-200">[Change plans manually](../commerce/subscriptions/change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="8530f-201">[Aggiornare Windows dispositivi a Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span><span class="sxs-lookup"><span data-stu-id="8530f-201">[Upgrade Windows devices to Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span></span>\
<span data-ttu-id="8530f-202">[Configurare le impostazioni di protezione delle app per i dispositivi Android](app-protection-settings-for-android-and-ios.md) o iOS (articolo)</span><span class="sxs-lookup"><span data-stu-id="8530f-202">[Set app protection settings for Android or iOS devices](app-protection-settings-for-android-and-ios.md) (article)</span></span>\
<span data-ttu-id="8530f-203">[Impostare o modificare le impostazioni di protezione delle applicazioni Windows 10 dispositivi](protection-settings-for-windows-10-devices.md) mobili (articolo)</span><span class="sxs-lookup"><span data-stu-id="8530f-203">[Set or edit application protection settings for Windows 10 devices](protection-settings-for-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="8530f-204">[]</span><span class="sxs-lookup"><span data-stu-id="8530f-204">[]</span></span>

