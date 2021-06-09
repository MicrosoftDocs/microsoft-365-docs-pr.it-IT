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
description: Integrare Microsoft 365 con Azure AD se si desidera la sincronizzazione delle password o single sign-on con l'ambiente locale.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905333"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="634f4-103">Integrazione di Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="634f4-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="634f4-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="634f4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="634f4-105">Microsoft 365 usa Azure Active Directory (Azure AD) per gestire le identità degli utenti dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="634f4-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="634f4-106">La sottoscrizione Microsoft 365 include una sottoscrizione ad Azure AD gratuita in modo da poter integrare Servizi di dominio Active Directory locale per sincronizzare account utente e password o configurare l'accesso Single Sign-on.</span><span class="sxs-lookup"><span data-stu-id="634f4-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="634f4-107">Puoi anche acquistare funzionalità avanzate per gestire meglio i tuoi account.</span><span class="sxs-lookup"><span data-stu-id="634f4-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="634f4-108">Azure AD offre anche altre funzionalità, come la gestione delle app integrate, che è possibile usare per estendere e personalizzare le sottoscrizioni Microsoft 365 personalizzate.</span><span class="sxs-lookup"><span data-stu-id="634f4-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="634f4-109">È possibile usare gli advisor per la distribuzione di Azure AD per un'esperienza di configurazione e configurazione guidata nell'interfaccia di amministrazione di Microsoft 365 (è necessario accedere a Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="634f4-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="634f4-110">Advisor di Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="634f4-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="634f4-111">Assistente distribuzione di AD FS</span><span class="sxs-lookup"><span data-stu-id="634f4-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="634f4-112">Guida alla configurazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="634f4-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="634f4-113">Edizioni di Azure AD e gestione Microsoft 365 delle identità</span><span class="sxs-lookup"><span data-stu-id="634f4-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="634f4-114">Se hai una sottoscrizione a pagamento per Microsoft 365, hai anche una sottoscrizione gratuita di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="634f4-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="634f4-115">È possibile usare Azure AD per creare e gestire account utente e di gruppo.</span><span class="sxs-lookup"><span data-stu-id="634f4-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="634f4-116">Per attivare questa sottoscrizione, è necessario completare una registrazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="634f4-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="634f4-117">Successivamente, è possibile accedere ad Azure AD dall'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="634f4-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="634f4-118">Per istruzioni su come registrare la sottoscrizione gratuita di Azure AD, vedi [usare la sottoscrizione gratuita di Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="634f4-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="634f4-119">Non passare direttamente a azure.microsoft.com per iscriversi o si finirà con una sottoscrizione di valutazione o a pagamento a Microsoft Azure separata dall'abbonamento gratuito ad Azure AD con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="634f4-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="634f4-120">Con l'abbonamento gratuito è possibile eseguire la sincronizzazione con le directory locali, configurare l'accesso Single #A0 e sincronizzare con molti software come applicazioni di servizio, ad esempio Salesforce, DropBox e molti altri.</span><span class="sxs-lookup"><span data-stu-id="634f4-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="634f4-121">Se si desiderano funzionalità avanzate di Servizi di dominio Active Directory, sincronizzazione bidirezionale e altre funzionalità di gestione, è possibile aggiornare la sottoscrizione gratuita a una sottoscrizione premium a pagamento.</span><span class="sxs-lookup"><span data-stu-id="634f4-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="634f4-122">Per i dettagli, vedere [Azure Active Directory edizioni](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="634f4-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="634f4-123">Per ulteriori informazioni su Microsoft 365 azure AD, vedere Microsoft 365 [identity models](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="634f4-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="634f4-124">Estendere le funzionalità del tenant Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="634f4-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="634f4-125">**Caratteristica**</span><span class="sxs-lookup"><span data-stu-id="634f4-125">**Feature**</span></span>|<span data-ttu-id="634f4-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="634f4-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="634f4-127">App integrate</span><span class="sxs-lookup"><span data-stu-id="634f4-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="634f4-128">Puoi concedere alle singole app l'accesso ai dati Microsoft 365, ad esempio posta, calendari, contatti, utenti, gruppi, file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="634f4-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="634f4-129">Puoi anche autorizzare queste app a livello di amministratore globale e renderle disponibili per l'intera azienda registrando le app in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="634f4-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="634f4-130">Per altre informazioni, vedi [App integrate e Azure AD per Microsoft 365 amministratori.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="634f4-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="634f4-131">Vedere anche [Single #A0](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="634f4-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="634f4-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="634f4-132">PowerApps</span></span>  <br/> | <span data-ttu-id="634f4-133">Le app di alimentazione sono app incentrate su dispositivi mobili che possono connettersi alle origini dati esistenti come SharePoint e altre app dati.</span><span class="sxs-lookup"><span data-stu-id="634f4-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="634f4-134">Per [informazioni dettagliate, vedere Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page.](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="634f4-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="634f4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="634f4-135">See also</span></span>

[<span data-ttu-id="634f4-136">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="634f4-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)