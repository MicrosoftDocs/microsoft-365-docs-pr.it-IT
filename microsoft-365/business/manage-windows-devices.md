---
title: Consentire ai dispositivi Windows 10 aggiunto al dominio da gestire da Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come abilitare 365 Microsoft proteggere i dispositivi Windows 10 aggiunto al Active Directory locale.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868428"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="7a0b7-103">Consentire ai dispositivi Windows 10 aggiunto al dominio da gestire da Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7a0b7-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="7a0b7-p101">Se l'organizzazione utilizza Windows Server Active Directory locale, è possibile impostare Microsoft 365 Business per proteggere i dispositivi Windows 10, mantenendo l'accesso alle risorse locali che richiedono l'autenticazione locale. È possibile impostare questo grazie alla prima sincronizzazione di Active Directory con Azure Active Directory, seguita registrando i dispositivi Windows 10 con Azure Active Directory e li la registrazione per la gestione dei dispositivi mobili da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="7a0b7-106">Configurare i dispositivi aggiunti al dominio da gestire da Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7a0b7-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="7a0b7-p102">Per impostare i dispositivi aggiunti al dominio dell'organizzazione per usufruire delle funzionalità fornite da Azure Active Directory oltre a Active Directory locale, è possibile implementare **ibrida Azure Active Directory appartenente dispositivi**. Si tratta di dispositivi che vengono aggiunti sia di Active Directory locale e Azure Active Directory. Ibrida Azure Active Directory appartenente dispositivi possono essere protetti e gestiti da Microsoft 365 Business..</span><span class="sxs-lookup"><span data-stu-id="7a0b7-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="7a0b7-110">Completare la procedura seguente per verificare i dispositivi di 10 Windows Azure Active Directory aggiunto e gestito da Microsoft 365 Business ibrida.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="7a0b7-111">Per sincronizzare gli utenti, gruppi e contatti da Active Directory locale in Azure Active Directory, eseguire la procedura guidata di sincronizzazione della Directory e Azure Active Directory la connessione come descritto in [configurare la sincronizzazione delle directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="7a0b7-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7a0b7-112">I passaggi sono esattamente gli stessi per Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="7a0b7-113">Prima di completare il passaggio 3 per consentire ai dispositivi Windows 10 da ibrida Azure Active Directory aggiunti, è necessario assicurarsi che siano soddisfatti i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a0b7-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="7a0b7-114">Si esegue la versione più recente di Azure Active Directory la connessione.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="7a0b7-p103">La connessione di Azure Active Directory è sincronizzato tutti gli oggetti computer dei dispositivi che si desidera essere ibrida Azure Active Directory aggiunti. Connettere anche se gli oggetti computer appartengono a specifiche unità organizzative (OU), quindi verificare che siano impostate le unità organizzative per la sincronizzazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="7a0b7-117">Registrare dominio Windows 10 dispositivi esistenti per ibrida Joined Azure Active Directory e li registrare per la gestione dei dispositivi mobili da Intune (Microsoft Business 365):</span><span class="sxs-lookup"><span data-stu-id="7a0b7-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="7a0b7-p104">Seguire le istruzioni dettagliate su [come configurare i dispositivi di Azure Active Directory appartenente ibrida](https://go.microsoft.com/fwlink/p/?linkid=872870). In questo modo la sincronizzazione di Active Directory locale aggiunto al computer Windows 10 e renderli cloud ready.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="7a0b7-p105">Per registrare un dispositivo Windows 10 per la gestione dei dispositivi mobili, vedere [registrazione un dispositivo Windows 10 con Intune utilizzando criteri di gruppo](https://go.microsoft.com/fwlink/p/?linkid=872871) per le istruzioni. È possibile impostare i criteri di gruppo in un computer locale livello o per le operazioni in blocco, è possibile creare questa impostazione di criteri di gruppo nel server di controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="7a0b7-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

