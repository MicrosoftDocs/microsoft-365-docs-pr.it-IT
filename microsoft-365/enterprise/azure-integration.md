---
title: Integrazione di Azure con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrazione di Microsoft 365 con Azure AD se si desidera sincronizzare la password o l'accesso Single Sign-on con l'ambiente locale.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384746"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="4c3b4-103">Integrazione di Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c3b4-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="4c3b4-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4c3b4-105">Microsoft 365 utilizza Azure Active Directory (Azure AD) per gestire le identità degli utenti dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="4c3b4-106">La sottoscrizione Microsoft 365 include una sottoscrizione gratuita AD Azure AD in modo che sia possibile integrare i servizi di dominio Active Directory (AD DS) locali per sincronizzare gli account utente e le password o configurare Single Sign-on.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="4c3b4-107">È inoltre possibile acquistare funzionalità avanzate per gestire al meglio gli account.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="4c3b4-108">Azure AD offre anche altre funzionalità, come la gestione delle app integrate, che è possibile utilizzare per estendere e personalizzare le sottoscrizioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="4c3b4-109">È possibile utilizzare i consulenti per la distribuzione di Azure AD per un'esperienza di installazione e configurazione guidata nell'interfaccia di amministrazione di Microsoft 365 (è necessario essere connessi a Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="4c3b4-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="4c3b4-110">Advisor di Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="4c3b4-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="4c3b4-111">Assistente distribuzione di AD FS</span><span class="sxs-lookup"><span data-stu-id="4c3b4-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="4c3b4-112">Guida alla configurazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="4c3b4-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="4c3b4-113">Azure AD Editions e Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="4c3b4-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="4c3b4-114">Se si dispone di un abbonamento a pagamento a Microsoft 365, si dispone anche di una sottoscrizione gratuita AD Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="4c3b4-115">È possibile utilizzare Azure AD per creare e gestire gli account utente e di gruppo.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="4c3b4-116">Per attivare la sottoscrizione, è necessario completare una registrazione singola.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="4c3b4-117">Successivamente, è possibile accedere AD Azure AD dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4c3b4-118">Per istruzioni su come registrare la sottoscrizione gratuita AD Azure AD, vedere [Use Your Free Azure ad Subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4c3b4-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="4c3b4-119">Non andare direttamente a azure.microsoft.com per iscriversi o finire con un abbonamento di valutazione o pagato a Microsoft Azure che è separato dalla sottoscrizione gratuita di Azure AD con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="4c3b4-120">Con l'abbonamento gratuito è possibile eseguire la sincronizzazione con le directory locali, configurare Single Sign-on e sincronizzarlo con molti software come applicazioni di servizio, ad esempio Salesforce, DropBox e molte altre.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="4c3b4-121">Se si desidera migliorare la funzionalità di servizi di dominio Active Directory, la sincronizzazione bi-direzionale e altre funzionalità di gestione, è possibile aggiornare l'abbonamento gratuito a un abbonamento Premium a pagamento.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="4c3b4-122">Per i dettagli, vedere [edizioni di Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="4c3b4-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="4c3b4-123">Per ulteriori informazioni su Microsoft 365 e Azure AD, vedere [modelli di identità di microsoft 365](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="4c3b4-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="4c3b4-124">Estendere le funzionalità del tenant di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c3b4-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="4c3b4-125">**Caratteristica**</span><span class="sxs-lookup"><span data-stu-id="4c3b4-125">**Feature**</span></span>|<span data-ttu-id="4c3b4-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4c3b4-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c3b4-127">App integrate</span><span class="sxs-lookup"><span data-stu-id="4c3b4-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="4c3b4-128">È possibile concedere alle singole app l'accesso ai dati di Microsoft 365, ad esempio messaggi di posta elettronica, calendari, contatti, utenti, gruppi, file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="4c3b4-129">È inoltre possibile autorizzare tali applicazioni a livello di amministratore globale e renderle disponibili per l'intera società registrando le app in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="4c3b4-130">Formore informazioni, vedere [Integrated Apps and Azure ad per Microsoft 365 Administrators](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="4c3b4-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="4c3b4-131">Vedere anche [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="4c3b4-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="4c3b4-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="4c3b4-132">PowerApps</span></span>  <br/> | <span data-ttu-id="4c3b4-133">Le app Power sono applicazioni mirate per i dispositivi mobili che possono connettersi alle origini dati esistenti come gli elenchi di SharePoint e altre app di dati.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="4c3b4-134">Per informazioni dettagliate, vedere [creare un PowerApp per un elenco in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) e la [pagina PowerApps](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="4c3b4-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4c3b4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c3b4-135">See also</span></span>

[<span data-ttu-id="4c3b4-136">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4c3b4-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
