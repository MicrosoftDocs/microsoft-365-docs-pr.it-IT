---
title: Eseguire la migrazione a Microsoft 365 business da Office 365 E3
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Informazioni su come spostare la propria azienda in Microsoft 365 business da Office 365 E3.
ms.openlocfilehash: f624ee7ef7c00ac4d1fe413500d0cd081a156748
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640577"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="fa89b-103">Migrazione da Office 365 E3 a Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="fa89b-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="fa89b-104">Microsoft 365 business offre tutto il necessario per le piccole aziende, combinando le app di produttività basate su cloud di Best-in-Class con la gestione e la sicurezza dei dispositivi semplici.</span><span class="sxs-lookup"><span data-stu-id="fa89b-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="fa89b-105">Se attualmente si dispone di un abbonamento a Office 365 E3, ma non si dispone di più di 300 dipendenti, valutare la possibilità di passare a Microsoft 365 business per aggiungere funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fa89b-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="fa89b-106">La migrazione è semplice: prima di tutto si cambia la licenza e tutti i dati e le informazioni degli utenti nell'abbonamento corrente vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="fa89b-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="fa89b-107">Dopo la migrazione, sarà necessario configurare le caratteristiche aggiunte in Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="fa89b-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="fa89b-108">Differenze tra Office 365 E3 e Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="fa89b-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="fa89b-109">In questa tabella vengono illustrate le differenze tra Microsoft 365 business e Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="fa89b-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="fa89b-110">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="fa89b-110">Feature</span></span>   | <span data-ttu-id="fa89b-111">Supporto in Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="fa89b-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="fa89b-112">Supporto in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="fa89b-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="fa89b-113">**Locale**</span><span class="sxs-lookup"><span data-stu-id="fa89b-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="fa89b-114">App di Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fa89b-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="fa89b-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="fa89b-115">Office 365 Business</span></span>   | <span data-ttu-id="fa89b-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="fa89b-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="fa89b-117">**App per la produttività del cloud**</span><span class="sxs-lookup"><span data-stu-id="fa89b-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="fa89b-118">Exchange Online e Outlook</span><span class="sxs-lookup"><span data-stu-id="fa89b-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="fa89b-119">50 GB di spazio di archiviazione per cassetta postale e archiviazione Exchange Online illimitata</span><span class="sxs-lookup"><span data-stu-id="fa89b-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>   | <span data-ttu-id="fa89b-120">100 GB di spazio di archiviazione per cassetta postale e archiviazione Exchange Online illimitata</span><span class="sxs-lookup"><span data-stu-id="fa89b-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="fa89b-121">Teams</span><span class="sxs-lookup"><span data-stu-id="fa89b-121">Teams</span></span> | ![Incluso in Microsoft 365 business](./media/check-mark.png)   | ![Incluso con Office 365 E3](./media/check-mark.png) | 
| <span data-ttu-id="fa89b-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="fa89b-124">OneDrive for Business</span></span> | <span data-ttu-id="fa89b-125">limite di archiviazione di 1 TB per utente</span><span class="sxs-lookup"><span data-stu-id="fa89b-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="fa89b-126">Illimitata</span><span class="sxs-lookup"><span data-stu-id="fa89b-126">Unlimited</span></span> | 
| <span data-ttu-id="fa89b-127">Yammer, SharePoint Online, planner, Stream</span><span class="sxs-lookup"><span data-stu-id="fa89b-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluso in Microsoft 365 business](./media/check-mark.png)   | ![Incluso con Office 365 E3](./media/check-mark.png) | 
| <span data-ttu-id="fa89b-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="fa89b-130">StaffHub</span></span>  | ![Incluso in Microsoft 365 business](./media/check-mark.png)   | ![Incluso con Office 365 E3](./media/check-mark.png) | 
| <span data-ttu-id="fa89b-133">Gestione clienti di Outlook, MileIQ</span><span class="sxs-lookup"><span data-stu-id="fa89b-133">Outlook Customer Manager, MileIQ</span></span>  | ![Incluso in Microsoft 365 business](./media/check-mark.png)   | | 
| <span data-ttu-id="fa89b-135">**Protezione dalle minacce**</span><span class="sxs-lookup"><span data-stu-id="fa89b-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="fa89b-136">Piano 1 di Office 365 Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="fa89b-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Incluso in Microsoft 365 business](./media/check-mark.png)  | <span data-ttu-id="fa89b-138">Non incluso, ma può essere aggiunto</span><span class="sxs-lookup"><span data-stu-id="fa89b-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="fa89b-139">**Gestione delle identità**</span><span class="sxs-lookup"><span data-stu-id="fa89b-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="fa89b-140">Reimpostazione della password in modalità self-service per gli account di Azure Active Directory (Azure AD), l'autenticazione a più fattori di Azure (AMF), l'accesso condizionale, il writeback delle password per le identità locali</span><span class="sxs-lookup"><span data-stu-id="fa89b-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Incluso in Microsoft 365 business](./media/check-mark.png) |  | 
| <span data-ttu-id="fa89b-142">**Gestione di dispositivi e app**</span><span class="sxs-lookup"><span data-stu-id="fa89b-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="fa89b-143">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="fa89b-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Incluso in Microsoft 365 business](./media/check-mark.png) |  |
| <span data-ttu-id="fa89b-145">Attivazione di computer condivisi</span><span class="sxs-lookup"><span data-stu-id="fa89b-145">Shared computer activation</span></span>|   ![Incluso in Microsoft 365 business](./media/check-mark.png) | ![Incluso con Office 365 E3](./media/check-mark.png)| 
| <span data-ttu-id="fa89b-148">Diritti di aggiornamento a Windows 10 Pro dalle licenze Win 7/8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="fa89b-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Incluso in Microsoft 365 business](./media/check-mark.png) || 
| <span data-ttu-id="fa89b-150">**Protezione delle informazioni**</span><span class="sxs-lookup"><span data-stu-id="fa89b-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="fa89b-151">Prevenzione della perdita dei dati di Office 365</span><span class="sxs-lookup"><span data-stu-id="fa89b-151">Office 365 Data Loss Prevention</span></span>|   ![Incluso in Microsoft 365 business](./media/check-mark.png)|![Incluso con Office 365 E3](./media/check-mark.png)|
|<span data-ttu-id="fa89b-154">Azure Information Protection piano 1, applicazione di BitLocker</span><span class="sxs-lookup"><span data-stu-id="fa89b-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Incluso in Microsoft 365 business](./media/check-mark.png)||
|<span data-ttu-id="fa89b-156">Piano di protezione delle informazioni di Azure 1, etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="fa89b-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Incluso in Microsoft 365 business](./media/check-mark.png)||
|<span data-ttu-id="fa89b-158">**Licenza di accesso client (CAL Rights)**</span><span class="sxs-lookup"><span data-stu-id="fa89b-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="fa89b-159">Famiglia di prodotti Enterprise CAL (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="fa89b-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluso con Office 365 E3](./media/check-mark.png)|

<span data-ttu-id="fa89b-161"><sup>1</sup> la versione Microsoft 365 business delle app di Office non include l'attivazione di contratti multilicenza tramite criteri di gruppo, la telemetria delle app, i controlli di aggiornamento, il confronto dei fogli di calcolo e la richiesta o la Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="fa89b-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="fa89b-162">Migrazione</span><span class="sxs-lookup"><span data-stu-id="fa89b-162">Migration</span></span>

<span data-ttu-id="fa89b-163">Per eseguire la migrazione della sottoscrizione, vedere [passare a un piano diverso manualmente](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) per istruzioni se si desidera spostare solo poche persone a Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="fa89b-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="fa89b-164">È inoltre possibile [aggiornare automaticamente tutti gli utenti](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)o collaborare con il partner per spostare la sottoscrizione E3 e le licenze a un abbonamento a Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="fa89b-164">You can also [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="fa89b-165">Nelle sezioni seguenti vengono descritte le modifiche che è necessario apportare, se presenti, e le operazioni che è possibile eseguire dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="fa89b-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="fa89b-166">Configurazione e dati dell'abbonamento a Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="fa89b-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="fa89b-167">Non è necessario apportare modifiche alla sottoscrizione corrente o ai dati prima di eseguire la migrazione, che include:</span><span class="sxs-lookup"><span data-stu-id="fa89b-167">You don’t need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="fa89b-168">Configurazione della sottoscrizione, ad esempio i record DNS e i nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="fa89b-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="fa89b-169">Gli account utente e di gruppo e le impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="fa89b-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="fa89b-170">Configurazioni dei servizi di produttività e relativi dati, ad esempio Team, cassette postali di Exchange Online, siti di SharePoint Online, cartelle di OneDrive for business e blocchi appunti di OneNote.</span><span class="sxs-lookup"><span data-stu-id="fa89b-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="fa89b-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa89b-171">Windows 10</span></span>

<span data-ttu-id="fa89b-172">Se le finestre non sono già presenti nell'aggiornamento di Windows Pro Creator, è possibile aggiornarle [nell'aggiornamento a Windows Pro Creators](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="fa89b-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="fa89b-173">Impostare i criteri per la protezione dei dispositivi e dei file utente</span><span class="sxs-lookup"><span data-stu-id="fa89b-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="fa89b-174">Se si configurano i criteri e i dispositivi di Office 365 MDM, tali dispositivi verranno elencati nella pagina **dispositivi** nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa89b-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fa89b-175">Tutti i criteri configurati verranno visualizzati nell'elenco dei criteri classici nel portale di [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="fa89b-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="fa89b-176">Dopo aver assegnato le licenze a Microsoft 365 business, è possibile iniziare a proteggere i dispositivi e i file degli utenti.</span><span class="sxs-lookup"><span data-stu-id="fa89b-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="fa89b-177">Se tutti gli utenti dell'organizzazione sono stati aggiornati a Microsoft 365 business, viene visualizzata l'installazione guidata nella Home page e è possibile eseguire la configurazione [guidata di microsoft 365 business nei](set-up.md) passaggi di configurazione per proteggere i file e i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="fa89b-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="fa89b-178">È inoltre possibile eseguire questi passaggi nella pagina dispositivi:</span><span class="sxs-lookup"><span data-stu-id="fa89b-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="fa89b-179">Nell'interfaccia di amministrazione, nella barra di spostamento a sinistra, passare ai **criteri**dei **dispositivi** \> .</span><span class="sxs-lookup"><span data-stu-id="fa89b-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="fa89b-180">Nella pagina **Criteri dispositivo** scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fa89b-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="fa89b-181">Nel riquadro **Aggiungi criterio** assegnare un nome al criterio e quindi scegliere un tipo di **criterio** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa89b-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="fa89b-182">È possibile configurare i criteri di applicazione per la protezione dei file su dispositivi Android e iPhone, oltre a Windows 10, ed è possibile configurare i criteri di configurazione del dispositivo per i dispositivi Windows 10 di proprietà dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="fa89b-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="fa89b-183">Per informazioni dettagliate, vedere i seguenti collegamenti:</span><span class="sxs-lookup"><span data-stu-id="fa89b-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="fa89b-184">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="fa89b-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="fa89b-185">Configurare le impostazioni di protezione delle app per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa89b-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="fa89b-186">Impostazione delle impostazioni di protezione dei dispositivi per PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa89b-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="fa89b-187">Dopo aver configurato i criteri, gli utenti e i dipendenti possono configurare i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="fa89b-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="fa89b-188">Vedere [configurare i dispositivi Windows per gli utenti di Microsoft 365 business](set-up-windows-devices.md) per i passaggi per i dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="fa89b-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="fa89b-189">Vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 business](set-up-mobile-devices.md) per i passaggi per i telefoni Android e iPhone.</span><span class="sxs-lookup"><span data-stu-id="fa89b-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="fa89b-190">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="fa89b-190">Threat protection</span></span>

<span data-ttu-id="fa89b-191">Dopo aver eseguito la migrazione a Microsoft 365 business, è necessario disporre di Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="fa89b-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="fa89b-192">Per una panoramica, vedere [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) .</span><span class="sxs-lookup"><span data-stu-id="fa89b-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="fa89b-193">Per impostare, vedere [set up ATP Safe Links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP Safe Attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)e [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="fa89b-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="fa89b-194">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="fa89b-194">Sensitivity labels</span></span>

<span data-ttu-id="fa89b-195">Per iniziare a utilizzare le etichette di riservatezza, vedere [Overview of Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) e [Create and Manage Sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="fa89b-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
