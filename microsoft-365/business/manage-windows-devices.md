---
title: Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come consentire a Microsoft 365 di proteggere gli annunci locali con i dispositivi Windows 10.
ms.openlocfilehash: 661e5bf8205a661eb4382b4bdd8fcf3a54ecc12f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660310"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="f4a31-103">Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="f4a31-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="f4a31-104">Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="f4a31-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="f4a31-105">È possibile configurarlo eseguendo prima la sincronizzazione di Active Directory con Azure Active Directory, seguito dalla registrazione dei dispositivi Windows 10 con Azure AD e dall'iscrizione per la gestione dei dispositivi mobili da parte di Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="f4a31-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="f4a31-106">Configurare i dispositivi associati a un dominio per essere gestiti da Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="f4a31-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="f4a31-107">Per configurare i dispositivi appartenenti al dominio dell'organizzazione in modo da trarre vantaggio dalle funzionalità fornite da Azure Active Directory oltre che da Active Directory locale, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**.</span><span class="sxs-lookup"><span data-stu-id="f4a31-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="f4a31-108">Si tratta di dispositivi che si uniscono sia a Active Directory locale che a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f4a31-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="f4a31-109">I dispositivi ibridi di Azure AD Uniti possono essere protetti e gestiti da Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="f4a31-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="f4a31-110">Completare i passaggi riportati di seguito per rendere i dispositivi Windows 10 ibridi di Azure AD Uniti e gestiti da Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="f4a31-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="f4a31-111">Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, eseguire la procedura guidata di sincronizzazione della directory e Azure Active Directory Connect come descritto in [configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="f4a31-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4a31-112">I passaggi sono esattamente gli stessi per Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="f4a31-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="f4a31-113">Prima di completare il passaggio 3 per consentire ai dispositivi Windows 10 di essere Uniti ad Azure ibrido, è necessario verificare che siano soddisfatti i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4a31-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="f4a31-114">Si sta eseguendo la versione più recente di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="f4a31-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="f4a31-115">Azure AD Connect ha sincronizzato tutti gli oggetti computer dei dispositivi in cui si desidera essere Uniti AD Azure ibrido.</span><span class="sxs-lookup"><span data-stu-id="f4a31-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="f4a31-116">Se gli oggetti computer appartengono a specifiche unità organizzative (OU), assicurarsi che le unità organizzative siano impostate per la sincronizzazione anche in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="f4a31-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="f4a31-117">Registrare i dispositivi Windows 10 aggiunti a un dominio esistenti per essere ibridi di Azure AD e iscriverli per la gestione dei dispositivi mobili da Intune (Microsoft 365 business):</span><span class="sxs-lookup"><span data-stu-id="f4a31-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="f4a31-118">Seguire le istruzioni dettagliate su [come configurare i dispositivi Uniti ibridi di Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="f4a31-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="f4a31-119">In questo modo, la sincronizzazione di Active Directory locale è stata aggiunta ai computer Windows 10 e li rende pronti per il cloud.</span><span class="sxs-lookup"><span data-stu-id="f4a31-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="f4a31-120">Per registrare un dispositivo Windows 10 per la gestione dei dispositivi mobili, vedere [registrazione di un dispositivo Windows 10 con Intune tramite criteri di gruppo](https://go.microsoft.com/fwlink/p/?linkid=872871) per le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f4a31-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="f4a31-121">È possibile impostare criteri di gruppo a livello di computer locale o per le operazioni in blocco, è possibile creare questa impostazione di criteri di gruppo nel server del controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="f4a31-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>