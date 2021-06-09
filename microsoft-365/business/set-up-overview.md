---
title: Panoramica dell'installazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Informazioni sui passaggi di configurazione Microsoft 365 Business Premium, dalla sottoscrizione, all'aggiunta di un dominio e di utenti, alla configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: 008a5c51698589667acc0d01649f67dab33b4c58
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245065"
---
# <a name="overview-of-setup"></a><span data-ttu-id="df02c-103">Panoramica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="df02c-103">Overview of setup</span></span>

<span data-ttu-id="df02c-104">Guarda un breve video sull'Microsoft 365 Business Premium configurazione.</span><span class="sxs-lookup"><span data-stu-id="df02c-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="df02c-105">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="df02c-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>

<span data-ttu-id="df02c-106">La maggior parte dei passaggi di configurazione può essere eseguita nella configurazione guidata, ma sono elencate anche le altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="df02c-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="df02c-107">Passaggio 1: Aggiungere il dominio e gli utenti</span><span class="sxs-lookup"><span data-stu-id="df02c-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="df02c-108">**[Aggiungi il dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (se hai acquistato il dominio durante l'iscrizione, questo passaggio è già stato eseguito). [](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="df02c-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="df02c-109">**Aggiungere utenti**.</span><span class="sxs-lookup"><span data-stu-id="df02c-109">**Add users**.</span></span> <span data-ttu-id="df02c-110">È possibile aggiungere utenti in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="df02c-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="df02c-111">Nella configurazione [guidata](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="df02c-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="df02c-112">Usare la sincronizzazione della directory [per aggiungere utenti tramite Azure AD Connessione](../enterprise/set-up-directory-synchronization.md) se si dispone di una active directory locale.</span><span class="sxs-lookup"><span data-stu-id="df02c-112">Use directory synchronization to [add users by using Azure AD Connect](../enterprise/set-up-directory-synchronization.md) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="df02c-113">È inoltre possibile [aggiungere utenti in un secondo momento](../admin/add-users/add-users.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="df02c-113">You can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="df02c-114">Passaggio 2: Configurare i criteri di sicurezza e configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="df02c-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="df02c-115">Usa la [configurazione guidata per](set-up.md#protect-your-organization) configurare i criteri dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="df02c-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="df02c-116">Puoi anche aggiungerne altri o modificarli in un secondo momento [nell'interfaccia di amministrazione](view-policies-and-devices.md) e nel portale di [Intune.](/intune/tutorial-walkthrough-intune-portal)</span><span class="sxs-lookup"><span data-stu-id="df02c-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="df02c-117">L'installazione guidata configura anche le impostazioni di base per la protezione dalle minacce e la prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="df02c-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="df02c-118">Oltre alle impostazioni di sicurezza dell'installazione guidata, è possibile aumentare la sicurezza aggiungendo le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df02c-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="df02c-119">**Protezione antimalware della posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="df02c-119">**Email malware protection**</span></span>
- <span data-ttu-id="df02c-120">**Anti-phishing in Defender per Office 365**</span><span class="sxs-lookup"><span data-stu-id="df02c-120">**Anti-phishing in Defender for Office 365**</span></span>
- <span data-ttu-id="df02c-121">**Archiviazione Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="df02c-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="df02c-122">**Azure Information Protection (Piano1)**</span><span class="sxs-lookup"><span data-stu-id="df02c-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="df02c-123">Per iniziare, vedi Aumentare [la protezione dalle minacce](increase-threat-protection.md) e configurare le funzionalità di [conformità.](set-up-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="df02c-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="df02c-124">Vedi anche [i 10](/office365/admin/security-and-compliance/secure-your-business-data) modi principali per proteggere il Microsoft 365 Business Premium per una road map delle procedure consigliate per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="df02c-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="df02c-125">Passaggio 3: Configurare e gestire Windows 10 dispositivi</span><span class="sxs-lookup"><span data-stu-id="df02c-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="df02c-126">Dopo aver completato la configurazione guidata, è necessario proteggere tutti i Windows 10 computer dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df02c-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="df02c-127">Windows 10 Pro è un [prerequisito](pre-requisites-for-data-protection.md) per Microsoft 365 Business Premium, ma se si dispone di Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, l'abbonamento consente di eseguire un aggiornamento a [Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="df02c-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).</span></span>
- <span data-ttu-id="df02c-128">Seguire i passaggi descritti in [Proteggere Windows 10 PC per](secure-win-10-pcs.md) configurare i criteri per Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="df02c-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="df02c-129">Quando si aggiunge un dispositivo Windows 10 ad Azure AD, i criteri impostati per Windows 10 computer vengono applicati ad esso.</span><span class="sxs-lookup"><span data-stu-id="df02c-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="df02c-130">Per ulteriori informazioni, vedere [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="df02c-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="df02c-131">Passaggio 4: installare Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="df02c-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="df02c-132">È possibile installare automaticamente Office nei dispositivi Windows utilizzando [l'installazione guidata.](set-up.md#deploy-office-365-client-apps)</span><span class="sxs-lookup"><span data-stu-id="df02c-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="df02c-133">Consenti agli [utenti Office app per](/office365/admin/setup/install-applications) Windows e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="df02c-133">Let users [install Office apps](/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="df02c-134">Impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="df02c-134">Advanced</span></span>
- <span data-ttu-id="df02c-135">**Usare Autopilot per configurare nuovi dispositivi**</span><span class="sxs-lookup"><span data-stu-id="df02c-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="df02c-136">Puoi usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per pre-configurare automaticamente i nuovi dispositivi **Windows 10** per un utente, ma potrebbe essere più facile ottenere un [partner](https://www.microsoft.com/solution-providers/search) che possa farlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="df02c-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="df02c-137">Puoi anche andare a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati.</span><span class="sxs-lookup"><span data-stu-id="df02c-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="df02c-138">**Accedere alle risorse locali**</span><span class="sxs-lookup"><span data-stu-id="df02c-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="df02c-139">Se l'organizzazione usa Windows Server Active Directory locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="df02c-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="df02c-140">Segui i passaggi descritti in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span><span class="sxs-lookup"><span data-stu-id="df02c-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="df02c-141">Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi aggiunti ad Azure AD ibridi.</span><span class="sxs-lookup"><span data-stu-id="df02c-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="df02c-142">Se l'azienda ha un Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni file e stampanti), è possibile concedere ai dispositivi aggiunti ad Azure AD l'accesso a queste risorse seguendo la procedura seguente: Accedere alle risorse locali da un dispositivo aggiunto ad [Azure AD in Microsoft 365 Business Premium](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="df02c-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="df02c-143">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="df02c-143">Related content</span></span>

<span data-ttu-id="df02c-144">[video Microsoft 365 formazione su Microsoft 365](../business-video/index.yml) per le aziende (pagina dei collegamenti)</span><span class="sxs-lookup"><span data-stu-id="df02c-144">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>