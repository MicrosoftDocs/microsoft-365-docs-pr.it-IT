---
title: Panoramica dell'installazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni sulla procedura di configurazione per Microsoft 365 Business Premium, dalla sottoscrizione, all'aggiunta di un dominio e utenti, alla configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: 46370166a9d5e8c9308b8947513e631c159f0b86
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842131"
---
# <a name="overview-of-setup"></a><span data-ttu-id="00cf4-103">Panoramica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="00cf4-103">Overview of setup</span></span>

<span data-ttu-id="00cf4-104">Guardare un breve video sulla configurazione di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="00cf4-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="00cf4-105">Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="00cf4-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="00cf4-106">La maggior parte dei passaggi di configurazione può essere eseguita nella configurazione guidata, ma sono elencate anche le altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="00cf4-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="00cf4-107">Passaggio 1: Aggiungere il dominio e gli utenti</span><span class="sxs-lookup"><span data-stu-id="00cf4-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="00cf4-108">**[Aggiungere il dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (se è stato acquistato il dominio durante l'iscrizione, questo passaggio è già stato eseguito). [](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="00cf4-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="00cf4-109">**Aggiungere utenti.**</span><span class="sxs-lookup"><span data-stu-id="00cf4-109">**Add users**.</span></span> <span data-ttu-id="00cf4-110">È possibile aggiungere utenti in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="00cf4-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="00cf4-111">Nella configurazione [guidata.](set-up.md#add-users-in-the-wizard)</span><span class="sxs-lookup"><span data-stu-id="00cf4-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="00cf4-112">Usare la sincronizzazione della directory [per aggiungere utenti tramite Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) se si dispone di una active directory locale.</span><span class="sxs-lookup"><span data-stu-id="00cf4-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="00cf4-113">È inoltre possibile [aggiungere utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="00cf4-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="00cf4-114">Passaggio 2: configurare i criteri di sicurezza e i dispositivi</span><span class="sxs-lookup"><span data-stu-id="00cf4-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="00cf4-115">Usa la [configurazione guidata per](set-up.md#protect-your-organization) configurare i criteri dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="00cf4-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="00cf4-116">Puoi anche aggiungerne altri o modificarli in un secondo momento nell'interfaccia [di amministrazione](view-policies-and-devices.md) e nel portale [di Intune.](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)</span><span class="sxs-lookup"><span data-stu-id="00cf4-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="00cf4-117">La configurazione guidata configura anche le impostazioni di base per la protezione dalle minacce e la prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="00cf4-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="00cf4-118">Oltre alle impostazioni di sicurezza dell'installazione guidata, è possibile aumentare la sicurezza aggiungendo le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00cf4-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="00cf4-119">**Protezione antimalware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="00cf4-119">**Email malware protection**</span></span>
- <span data-ttu-id="00cf4-120">**Anti-phishing in Defender per Office 365**</span><span class="sxs-lookup"><span data-stu-id="00cf4-120">**Anti-phishing in Defender for Office 365**</span></span>
- <span data-ttu-id="00cf4-121">**Archiviazione Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="00cf4-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="00cf4-122">**Azure Information Protection (Piano 1)**</span><span class="sxs-lookup"><span data-stu-id="00cf4-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="00cf4-123">Per iniziare, vedere aumentare [la protezione dalle minacce](increase-threat-protection.md) e configurare le funzionalità di [conformità.](set-up-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="00cf4-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="00cf4-124">Vedere anche i 10 modi principali per proteggere [Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) per una mappa delle procedure consigliate per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="00cf4-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="00cf4-125">Passaggio 3: Configurare e gestire i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="00cf4-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="00cf4-126">Dopo aver completato la configurazione guidata, è necessario proteggere tutti i computer Windows 10 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="00cf4-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="00cf4-127">Windows 10 Pro è un [prerequisito](pre-requisites-for-data-protection.md) per Microsoft 365 Business Premium, ma se hai Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, l'abbonamento ti dà diritto a un aggiornamento a [Windows 10 Pro.](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)</span><span class="sxs-lookup"><span data-stu-id="00cf4-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="00cf4-128">Segui i passaggi in [PC Windows 10 sicuri per](secure-win-10-pcs.md) configurare i criteri per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="00cf4-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="00cf4-129">Quando si aggiunge un dispositivo Windows 10 ad Azure AD, vengono applicati i criteri impostati per i computer Windows 10.</span><span class="sxs-lookup"><span data-stu-id="00cf4-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="00cf4-130">Per altre informazioni, vedere [Configurare i dispositivi Windows per gli utenti di Microsoft 365.](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="00cf4-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="00cf4-131">Passaggio 4: Installare Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="00cf4-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="00cf4-132">È possibile installare automaticamente Office nei dispositivi Windows utilizzando la [configurazione guidata.](set-up.md#deploy-office-365-client-apps)</span><span class="sxs-lookup"><span data-stu-id="00cf4-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="00cf4-133">Consentire agli [utenti di installare le app di Office](https://docs.microsoft.com/office365/admin/setup/install-applications) per Windows e i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="00cf4-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="00cf4-134">Impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="00cf4-134">Advanced</span></span>
- <span data-ttu-id="00cf4-135">**Usare Autopilot per configurare nuovi dispositivi**</span><span class="sxs-lookup"><span data-stu-id="00cf4-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="00cf4-136">Puoi usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per pre-configurare automaticamente i nuovi dispositivi **Windows** 10 per un utente, ma potrebbe essere più semplice ottenere un [partner](https://www.microsoft.com/solution-providers/search) in grado di farlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="00cf4-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="00cf4-137">Puoi anche accedere a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati.</span><span class="sxs-lookup"><span data-stu-id="00cf4-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="00cf4-138">**Accedere alle risorse locali**</span><span class="sxs-lookup"><span data-stu-id="00cf4-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="00cf4-139">Se l'organizzazione usa Windows Server Active Directory in locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="00cf4-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="00cf4-140">Seguire i passaggi descritti in Abilitare i dispositivi Windows 10 aggiunti a un dominio a essere gestiti da [Microsoft 365 Business Premium](manage-windows-devices.md) per configurare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="00cf4-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="00cf4-141">Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi aggiunti ad Azure AD ibrido.</span><span class="sxs-lookup"><span data-stu-id="00cf4-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="00cf4-142">Se l'azienda dispone di un'istanza locale di Active Directory che contiene alcune risorse locali (ad esempio condivisioni file e stampanti), è possibile concedere ai dispositivi aggiunti ad Azure AD l'accesso a queste risorse seguendo la procedura seguente: Accedere alle risorse locali da un dispositivo aggiunto ad [Azure AD in Microsoft 365 Business Premium.](access-resources.md)</span><span class="sxs-lookup"><span data-stu-id="00cf4-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00cf4-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00cf4-143">See also</span></span>

[<span data-ttu-id="00cf4-144">Video di formazione su Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="00cf4-144">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
