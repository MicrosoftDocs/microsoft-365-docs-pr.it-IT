---
title: Accesso locale risorse da un dispositivo Azure Active Directory aggiunti in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informazioni su come accedere a risorse locali come in applicazioni Line-Of-Business, condivisioni file e stampanti da un Azure Active Directory appartenente dispositivo Windows 10.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868306"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="727cd-103">Accesso locale risorse da un dispositivo Azure Active Directory aggiunti in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="727cd-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="727cd-p101">Eventuali dispositivi 10 Windows Azure Active Directory appartenente potranno accedere a tutte le risorse basate su cloud, ad esempio le applicazioni di Office 365 e possono essere protetti da Microsoft 365 Business. Per consentire l'accesso alle risorse locali come applicazioni Line Of Business (LOB), condivisioni file e stampanti anche, è necessario sincronizzare Active Directory locale con Azure Active Directory utilizzando [Connetti Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). [Introduzione alla gestione dei dispositivi in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) per ulteriori informazioni, vedere.</span><span class="sxs-lookup"><span data-stu-id="727cd-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="727cd-107">Connettere Esegui Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="727cd-107">Run Azure AD Connect</span></span>

<span data-ttu-id="727cd-108">Completare la procedura seguente per consentire ai dispositivi dell'organizzazione Azure Active Directory appartenente accedere alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="727cd-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="727cd-109">Per sincronizzare gli utenti, gruppi e contatti da Active Directory locale in Azure Active Directory, eseguire la procedura guidata sincronizzazione della Directory e Azure Active Directory Connetti come descritto in [configurare la sincronizzazione delle directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="727cd-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="727cd-p102">Dopo aver completato la sincronizzazione della directory, verificare che i dispositivi dell'organizzazione Windows 10 siano Azure Active Directory aggiunti. Questo passaggio viene eseguito singolarmente ogni dispositivo Windows 10. Per informazioni dettagliate, vedere [configurare i dispositivi di Windows per utenti Business 365 Microsoft](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="727cd-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="727cd-p103">Dopo aver installato i dispositivi 10 Windows Azure Active Directory appartenente, ogni utente deve riavviare i dispositivi e account di accesso con le proprie credenziali aziendali 365 Microsoft. Tutti i dispositivi verranno concesso l'accesso alle risorse locali anche.</span><span class="sxs-lookup"><span data-stu-id="727cd-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="727cd-p104">Nessun passaggi aggiuntivi sono necessari per accedere alle risorse per Azure Active Directory appartenente dispositivi in locale. Questo è disponibile in Windows 10 funzionalità incorporate.</span><span class="sxs-lookup"><span data-stu-id="727cd-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="727cd-117">Se l'organizzazione non è possibile distribuire in Azure Active Directory appartenente dispositivo configurazione descritta in precedenza, è consigliabile configurare [Configurazione dispositivo ibrida Azure Active Directory Joined](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="727cd-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="727cd-118">Considerazioni per la partecipazione i dispositivi di Windows per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="727cd-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="727cd-119">In caso di Azure AD accesso a un dispositivo Windows che in precedenza è stato aggiunto al dominio o un gruppo di lavoro, è necessario prendere in considerazione le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="727cd-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="727cd-p105">Quando si unisce a un dispositivo di Azure Active Directory, viene creato un nuovo utente senza fare riferimento a un profilo esistente. Per risolvere questo problema, è necessario eseguire manualmente la migrazione profili. Un profilo utente contiene informazioni come Preferiti, file locali, le impostazioni del browser, le impostazioni del menu di avvio e così via. È un approccio più adatto per individuare uno strumento di terze parti per mappare i file esistenti e le impostazioni per il nuovo profilo</span><span class="sxs-lookup"><span data-stu-id="727cd-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="727cd-p106">Se il dispositivo utilizza gli oggetti Criteri di gruppo (GPO), alcuni oggetti Criteri di gruppo che non sia un paragonabili [Provider di servizi di configurazione](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) Intune. Eseguire lo [strumento MMAT](https://www.microsoft.com/download/details.aspx?id=45520) per individuare CSP paragonabili di oggetti Criteri di gruppo esistenti.</span><span class="sxs-lookup"><span data-stu-id="727cd-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="727cd-p107">Gli utenti non saranno in grado di eseguire l'autenticazione per le applicazioni che dipendono da autenticazione di Active Directory. Per gestire questo valutare utilizzando un'app legacy e prendere in considerazione l'aggiornamento a un'applicazione che utilizza autenticazione moderno se possibile.</span><span class="sxs-lookup"><span data-stu-id="727cd-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="727cd-p108">Rilevamento della stampante di Active Directory non funzionerà. Per risolvere questo problema, inserire percorsi di stampante diretto per tutti gli utenti o sfruttare [Ibrida Cloud stampa](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="727cd-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

