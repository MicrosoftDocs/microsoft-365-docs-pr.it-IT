---
title: Panoramica della configurazione
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Panoramica dei passaggi di configurazione per Microsoft 365 business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074406"
---
# <a name="overview-of-setup"></a><span data-ttu-id="0faac-103">Panoramica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="0faac-103">Overview of setup</span></span>

<span data-ttu-id="0faac-104">La maggior parte dei passaggi di configurazione può essere effettuata nell'installazione guidata, ma anche le altre opzioni sono elencate.</span><span class="sxs-lookup"><span data-stu-id="0faac-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="0faac-105">Passaggio 1: aggiungere il dominio e gli utenti</span><span class="sxs-lookup"><span data-stu-id="0faac-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="0faac-106">**[Aggiungere il dominio](set-up.md#add-your-domain-to-personalize-sign-in)** Se il dominio è stato acquistato durante l' [iscrizione](sign-up.md), questo passaggio è già stato fatto.</span><span class="sxs-lookup"><span data-stu-id="0faac-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="0faac-107">**Aggiungere utenti**.</span><span class="sxs-lookup"><span data-stu-id="0faac-107">**Add users**.</span></span> <span data-ttu-id="0faac-108">È possibile eseguire questa operazione in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0faac-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="0faac-109">Nella [procedura guidata](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="0faac-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="0faac-110">Utilizzare la sincronizzazione della directory per [aggiungere utenti utilizzando Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) se si dispone di Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="0faac-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="0faac-111">È inoltre possibile [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0faac-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="0faac-112">Passaggio 2: impostare i criteri di sicurezza e configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="0faac-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="0faac-113">Utilizzare l' [installazione guidata](set-up.md#set-up-security-policies-and-device-configurations) per configurare i criteri di sicurezza e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0faac-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="0faac-114">È inoltre possibile aggiungerne altri o modificarli in un secondo momento nell'interfaccia di [Amministrazione](view-policies-and-devices.md) e nel [portale di Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="0faac-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="0faac-115">Oltre alle impostazioni di sicurezza nell'installazione guidata, è possibile aumentare la sicurezza aggiungendo le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="0faac-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="0faac-116">**Protezione antimalware per la posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="0faac-116">**Email malware protection**</span></span>
      - <span data-ttu-id="0faac-117">**Collegamenti sicuri di Advanced Threat Protection (ATP)**</span><span class="sxs-lookup"><span data-stu-id="0faac-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="0faac-118">**Allegati sicuri di ATP**</span><span class="sxs-lookup"><span data-stu-id="0faac-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="0faac-119">**Anti-phishing ATP**</span><span class="sxs-lookup"><span data-stu-id="0faac-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="0faac-120">**Archiviazione Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="0faac-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="0faac-121">**prevenzione della perdita di dati (DLP)**</span><span class="sxs-lookup"><span data-stu-id="0faac-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="0faac-122">**Protezione delle informazioni di Azure (PLAN1**)</span><span class="sxs-lookup"><span data-stu-id="0faac-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="0faac-123">Per iniziare, vedere, [impostare i criteri di sicurezza avanzati](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="0faac-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="0faac-124">Vedere anche [i primi 10 modi per proteggere l'azienda Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) per una roadmap delle migliori procedure di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0faac-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="0faac-125">Passaggio 3: configurare e gestire i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="0faac-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="0faac-126">Quando si aggiunge un dispositivo Windows 10 ad Azure AD, i criteri impostati nel [passaggio 2](#step-2-set-up-security-policies-and-configure-devices) vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="0faac-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="0faac-127">Windows 10 Pro è un [requisito indispensabile](pre-requisites-for-data-protection.md) per Microsoft 365 business, ma se si dispone di Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, l'abbonamento dà diritto a un [aggiornamento a Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="0faac-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="0faac-128">Utilizzare l' [installazione guidata](set-up.md#set-up-security-policies-and-device-configurations) per configurare i criteri per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0faac-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="0faac-129">Stes 4: installare Office 365 business</span><span class="sxs-lookup"><span data-stu-id="0faac-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="0faac-130">È possibile installare automaticamente Office nei dispositivi Windows utilizzando l' [installazione guidata](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="0faac-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="0faac-131">[Installare automaticamente Office](auto-install-or-uninstall-office.md) dall'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0faac-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="0faac-132">Consente agli utenti di [installare le app di Office](https://docs.microsoft.com/office365/admin/setup/install-applications) per Windows e i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0faac-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="0faac-133">Impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="0faac-133">Advanced</span></span>
- <span data-ttu-id="0faac-134">**Utilizzare Autopilot per configurare nuovi dispositivi**</span><span class="sxs-lookup"><span data-stu-id="0faac-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="0faac-135">È possibile usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per preconfigurare automaticamente i **nuovi** dispositivi Windows 10 per un utente, ma potrebbe essere più facile ottenere un [partner](https://www.microsoft.com/solution-providers/search) che può eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0faac-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="0faac-136">È inoltre possibile accedere a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0faac-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="0faac-137">**Accedere alle risorse locali**</span><span class="sxs-lookup"><span data-stu-id="0faac-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="0faac-138">Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="0faac-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="0faac-139">Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 business](manage-windows-devices.md) to set this up.</span><span class="sxs-lookup"><span data-stu-id="0faac-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="0faac-140">Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi ibridi di Azure AD Uniti.</span><span class="sxs-lookup"><span data-stu-id="0faac-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="0faac-141">Se l'azienda dispone di un Active Directory locale che contiene alcune risorse locali, ad esempio condivisioni di file e stampanti, è possibile consentire ai dispositivi di Azure AD-join di accedere a tali risorse attenendosi alla procedura seguente: [accesso alle risorse locali da un Dispositivo di Azure AD-joined in Microsoft 365 business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="0faac-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  