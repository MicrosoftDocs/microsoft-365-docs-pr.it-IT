---
title: Integrazione di Azure con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
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
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691504"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="6a222-103">Integrazione di Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a222-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="6a222-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6a222-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6a222-105">Microsoft 365 utilizza Azure Active Directory (Azure AD) per gestire le identità degli utenti dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="6a222-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="6a222-106">La sottoscrizione Microsoft 365 include una sottoscrizione gratuita ad Azure AD in modo che sia possibile integrare Microsoft 365 con Azure AD se si desidera sincronizzare le password o configurare Single Sign-on con l'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="6a222-106">Your Microsoft 365 subscription includes a free subscription to Azure AD so that you can integrate Microsoft 365 with Azure AD if you want to sync passwords or set up single sign-on with your on-premises environment.</span></span> <span data-ttu-id="6a222-107">È inoltre possibile acquistare funzionalità avanzate per gestire al meglio gli account.</span><span class="sxs-lookup"><span data-stu-id="6a222-107">You can also buy advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="6a222-108">Azure offre anche altre funzionalità, come la gestione delle app integrate, che è possibile utilizzare per estendere e personalizzare le sottoscrizioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a222-108">Azure also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="6a222-109">È possibile utilizzare i consulenti per la distribuzione di Azure AD per un'esperienza di installazione e configurazione guidata (è necessario essere connessi a Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="6a222-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="6a222-110">Advisor di Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="6a222-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="6a222-111">Assistente distribuzione di AD FS</span><span class="sxs-lookup"><span data-stu-id="6a222-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="6a222-112">Guida alla configurazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="6a222-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="6a222-113">Azure AD Editions e Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="6a222-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="6a222-114">Se si dispone di un abbonamento a pagamento a Microsoft 365, si dispone anche di un abbonamento gratuito ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6a222-114">If you have a paid subscription to Microsoft 365, you also have a free subscription to Azure AD.</span></span> <span data-ttu-id="6a222-115">È possibile utilizzare Azure AD per creare e gestire gli account utente e di gruppo.</span><span class="sxs-lookup"><span data-stu-id="6a222-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="6a222-116">Per attivare l'abbonamento, è necessario completare una registrazione singola.</span><span class="sxs-lookup"><span data-stu-id="6a222-116">To activate this subscription you have to complete a one-time registration.</span></span> <span data-ttu-id="6a222-117">Successivamente, è possibile accedere AD Azure AD dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a222-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="6a222-118">Per istruzioni, vedere [utilizzare la sottoscrizione di Azure ad gratuita](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span><span class="sxs-lookup"><span data-stu-id="6a222-118">For instructions, see [use your free Azure AD subscription](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span></span> <span data-ttu-id="6a222-119">Seguire le istruzioni per registrare la sottoscrizione gratuita ad Azure AD fornita con l'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a222-119">Follow the instructions to register the free Azure AD subscription that comes with your subscription to Microsoft 365.</span></span> <span data-ttu-id="6a222-120">Non andare direttamente a azure.microsoft.com per iscriversi o finire con un abbonamento di valutazione o pagato a Microsoft Azure che è separato da quello gratuito per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a222-120">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free one for Microsoft 365.</span></span> 
  
<span data-ttu-id="6a222-121">Con l'abbonamento gratuito, è possibile eseguire la sincronizzazione con le directory locali, configurare Single Sign-on e sincronizzarlo con molti software come applicazioni di servizio, ad esempio Salesforce, DropBox e molte altre.</span><span class="sxs-lookup"><span data-stu-id="6a222-121">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox and many more.</span></span>
  
<span data-ttu-id="6a222-122">Se si desidera migliorare la funzionalità di servizi di dominio Active Directory (AD DS), la sincronizzazione bi-direzionale e altre funzionalità di gestione, è possibile aggiornare l'abbonamento gratuito a un abbonamento Premium a pagamento.</span><span class="sxs-lookup"><span data-stu-id="6a222-122">If you want enhanced Active Directory Domain Services (AD DS) functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="6a222-123">Per informazioni dettagliate, vedere [edizioni di Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="6a222-123">For details see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="6a222-124">Per ulteriori informazioni su Microsoft 365 e Azure AD, vedere [Understanding microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="6a222-124">For more information about Microsoft 365 and Azure AD, see [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="6a222-125">Estendere le funzionalità del tenant di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a222-125">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="6a222-126">**Caratteristica**</span><span class="sxs-lookup"><span data-stu-id="6a222-126">**Feature**</span></span>|<span data-ttu-id="6a222-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6a222-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6a222-128">App integrate</span><span class="sxs-lookup"><span data-stu-id="6a222-128">Integrated apps</span></span>  <br/> |<span data-ttu-id="6a222-129">È possibile concedere alle singole app l'accesso ai dati di Microsoft 365, come la posta, i calendari, i contatti, gli utenti, i gruppi, i file e le cartelle.</span><span class="sxs-lookup"><span data-stu-id="6a222-129">You can grant individual apps access to your Microsoft 365 data, like mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="6a222-130">È inoltre possibile autorizzare tali applicazioni a livello di amministratore globale e renderle disponibili per l'intera società registrando le app in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6a222-130">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="6a222-131">Per informazioni dettagliate [, vedere Integrated Apps and Azure ad for Microsoft 365 Administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span><span class="sxs-lookup"><span data-stu-id="6a222-131">For details see [Integrated Apps and Azure AD for Microsoft 365 administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span></span>  <br/> <span data-ttu-id="6a222-132">Vedere anche [Single Sign-on per le applicazioni](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="6a222-132">Also see [single sign-on to applications](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="6a222-133">PowerApps</span><span class="sxs-lookup"><span data-stu-id="6a222-133">PowerApps</span></span>  <br/> | <span data-ttu-id="6a222-134">Le app di alimentazione sono applicazioni mirate per i dispositivi mobili che possono connettersi alle origini dati esistenti come gli elenchi di SharePoint e altre app di dati.</span><span class="sxs-lookup"><span data-stu-id="6a222-134">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists, and other data apps.</span></span> <span data-ttu-id="6a222-135">Per informazioni dettagliate, vedere [creare un PowerApp per un elenco in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) e [PowerApps](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="6a222-135">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
<span data-ttu-id="6a222-136">Per ulteriori informazioni, vedere [Integrated Apps and Azure ad per Microsoft 365 Administrators](integrated-apps-and-azure-ads.md) e [Azure ad Application Gallery e Single-Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="6a222-136">Learn more at [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md) and [Azure AD application gallery and single-sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a222-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a222-137">See also</span></span>

[<span data-ttu-id="6a222-138">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6a222-138">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
