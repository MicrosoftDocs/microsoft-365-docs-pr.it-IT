---
title: Accedere alle risorse locali da un dispositivo aggiunto ad Azure AD in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informazioni su come accedere a risorse locali, come le app line-of-business, le condivisioni file e le stampanti, da un dispositivo Windows 10 aggiunto ad Azure Active Directory.
ms.openlocfilehash: 72b3c5ae538cad24fc12e25717dedccb2fdc9017
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843323"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="1d43a-103">Accedere alle risorse locali da un dispositivo aggiunto ad Azure AD in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1d43a-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="1d43a-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1d43a-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="1d43a-105">Qualsiasi Windows 10 aggiunto Azure Active Directory ha accesso a tutte le risorse basate sul cloud, ad esempio le app Microsoft 365, e può essere protetto da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1d43a-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="1d43a-106">È anche possibile consentire l'accesso a risorse locali come le app line-of-business (LOB), le condivisioni file e le stampanti.</span><span class="sxs-lookup"><span data-stu-id="1d43a-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="1d43a-107">Per consentire l'accesso, utilizzare [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) per sincronizzare Active Directory locale con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d43a-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span>

<span data-ttu-id="1d43a-108">Per altre informazioni, vedere [Introduzione alla gestione dei dispositivi in Azure Active Directory](/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="1d43a-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="1d43a-109">Le procedure sono riepilogate anche nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1d43a-109">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="1d43a-110">Eseguire Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1d43a-110">Run Azure AD Connect</span></span>

<span data-ttu-id="1d43a-111">Completare la procedura seguente per consentire ai dispositivi dell'organizzazione aggiunti ad Azure AD di accedere alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="1d43a-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>

1. <span data-ttu-id="1d43a-112">Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, eseguire la procedura guidata di sincronizzazione della directory e Azure AD Connect come descritto in [Configurare la sincronizzazione della directory per Office 365](../enterprise/set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="1d43a-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>

2. <span data-ttu-id="1d43a-113">Una volta completata la sincronizzazione della directory, accertarsi che i dispositivi Windows 10 dell'organizzazione siano associati ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1d43a-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="1d43a-114">Questa fase viene eseguita singolarmente in ogni dispositivo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1d43a-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="1d43a-115">Per [informazioni dettagliate, vedi](set-up-windows-devices.md) Configurare Windows dispositivi Microsoft 365 Business Premium utenti.</span><span class="sxs-lookup"><span data-stu-id="1d43a-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span>

3. <span data-ttu-id="1d43a-116">Dopo aver aggiunto Windows 10 dispositivi di Azure AD, ogni utente deve riavviare i dispositivi e accedere con le Microsoft 365 Business Premium credenziali.</span><span class="sxs-lookup"><span data-stu-id="1d43a-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="1d43a-117">Tutti i dispositivi hanno ora accesso alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="1d43a-117">All devices now have access to on-premises resources as well.</span></span>

<span data-ttu-id="1d43a-118">Non ci sono ulteriori fasi per accedere alle risorse locali per i dispositivi aggiunti ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1d43a-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="1d43a-119">Questa funzionalità è integrata in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1d43a-119">This functionality is built into Windows 10.</span></span>

<span data-ttu-id="1d43a-120">Se hai intenzione di accedere al dispositivo AADJ diverso dal metodo password Come PIN/Bio-metrica tramite l'accesso alle credenziali WHFB e quindi accedere alle risorse locali (condivisioni, stampanti e così via), segui questo [articolo.](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)</span><span class="sxs-lookup"><span data-stu-id="1d43a-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares, printers, etc.), please follow [this article](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base).</span></span>

<span data-ttu-id="1d43a-121">Se l'organizzazione non è pronta per la distribuzione nella configurazione di un dispositivo aggiunto ad Azure AD descritta in precedenza, è consigliabile impostare la [configurazione di un dispositivo aggiunto ad Azure AD ibrido](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="1d43a-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="1d43a-122">Considerazioni sull'aggiunta di un dispositivo Windows ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="1d43a-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="1d43a-123">Se il dispositivo Windows aggiunto ad Azure AD è già stato associato al dominio o a un gruppo di lavoro, prendere in considerazione le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d43a-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>

- <span data-ttu-id="1d43a-124">Quando un dispositivo viene aggiunto ad Azure AD, viene creato un nuovo utente che non fa riferimento a un profilo esistente.</span><span class="sxs-lookup"><span data-stu-id="1d43a-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="1d43a-125">I profili devono essere migrati manualmente.</span><span class="sxs-lookup"><span data-stu-id="1d43a-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="1d43a-126">Un profilo utente include informazioni come preferiti, file locali, impostazioni del browser e impostazioni del menu Avvio.</span><span class="sxs-lookup"><span data-stu-id="1d43a-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="1d43a-127">Il migliore approccio consiste nel trovare uno strumento di terze parti per eseguire il mapping dei file e delle impostazioni esistenti al nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="1d43a-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="1d43a-128">Se il dispositivo utilizza Oggetti Criteri di gruppo (GPO), alcuni di questi potrebbero non avere un [provider di servizi di configurazione](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) confrontabile in Intune.</span><span class="sxs-lookup"><span data-stu-id="1d43a-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="1d43a-129">Eseguire lo [strumento MMAT](https://www.microsoft.com/download/details.aspx?id=45520) per trovare un CSP confrontabile per gli Oggetti Criteri di gruppo esistenti.</span><span class="sxs-lookup"><span data-stu-id="1d43a-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="1d43a-130">Gli utenti potrebbero non essere in grado di eseguire l'autenticazione in applicazioni che dipendono dall'autenticazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d43a-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="1d43a-131">Valutare l'applicazione legacy e prendere in considerazione l'aggiornamento a un'applicazione che utilizzi l'autenticazione moderna, se possibile.</span><span class="sxs-lookup"><span data-stu-id="1d43a-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="1d43a-132">L'individuazione della stampante Active Directory non funziona.</span><span class="sxs-lookup"><span data-stu-id="1d43a-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="1d43a-133">È possibile fornire percorsi di stampa diretti per tutti gli utenti o utilizzare [Universal Print.](/universal-print/)</span><span class="sxs-lookup"><span data-stu-id="1d43a-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>

### <a name="related-articles"></a><span data-ttu-id="1d43a-134">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="1d43a-134">Related Articles</span></span>

[<span data-ttu-id="1d43a-135">Prerequisiti per Azure AD Connessione</span><span class="sxs-lookup"><span data-stu-id="1d43a-135">Prerequisites for Azure AD Connect</span></span>](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
