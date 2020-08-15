---
title: Microsoft 365 modelli di identità e Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 06/09/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Informazioni su come gestire il servizio di identità degli utenti di Azure AD in Microsoft 365 utilizzando modelli di identità solo cloud o ibridi.
ms.openlocfilehash: d91e14f678e487365805b024e4025e9a39db0c2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691534"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="c0c52-103">Microsoft 365 modelli di identità e Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c0c52-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="c0c52-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c0c52-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c0c52-105">Microsoft 365 utilizza Azure Active Directory (Azure AD), un servizio di autenticazione e identità utente basato sul cloud incluso nell'abbonamento a Microsoft 365, per gestire le identità e l'autenticazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="c0c52-106">Ottenere l'infrastruttura di identità configurata in modo corretto è fondamentale per la gestione dell'accesso utente e delle autorizzazioni di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0c52-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="c0c52-107">Prima di iniziare, guardare questo video che illustra i modelli di identità e l'autenticazione per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="c0c52-108">La prima scelta di pianificazione è il modello di identità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-108">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="c0c52-109">Modelli di identità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0c52-109">Microsoft 365 identity models</span></span>

<span data-ttu-id="c0c52-110">Per pianificare gli account utente, è necessario prima di tutto conoscere i due modelli di gestione delle identità disponibili in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-110">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="c0c52-111">È possibile mantenere le identità dell'organizzazione solo nel cloud. In alternativa, è possibile mantenere le identità Active Directory Domain Services (AD DS) in locale e usarle per l'autenticazione quando gli utenti accedono ai servizi cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-111">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="c0c52-112">Ecco i due tipi di identità con la descrizione dei vantaggi e dell'ambiente in cui sono più indicati.</span><span class="sxs-lookup"><span data-stu-id="c0c52-112">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="c0c52-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c0c52-113">Attribute</span></span> | <span data-ttu-id="c0c52-114">Identità solo cloud</span><span class="sxs-lookup"><span data-stu-id="c0c52-114">Cloud-only identity</span></span> | <span data-ttu-id="c0c52-115">Identità ibrida</span><span class="sxs-lookup"><span data-stu-id="c0c52-115">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="c0c52-116">**Definizione**</span><span class="sxs-lookup"><span data-stu-id="c0c52-116">**Definition**</span></span> | <span data-ttu-id="c0c52-117">L'account utente esiste solo nel tenant di Azure AD per l'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-117">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="c0c52-118">L'account utente esiste in AD DS, ma una copia si trova anche nel tenant di Azure AD per l'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-118">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="c0c52-119">L'account utente in Azure AD potrebbe includere anche una versione con hash della password dell'account utente di AD DS già sottoposto a hash.</span><span class="sxs-lookup"><span data-stu-id="c0c52-119">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="c0c52-120">**Autenticazione delle credenziali utente in Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="c0c52-120">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="c0c52-121">Per eseguire l'autenticazione, il tenant di Azure AD per l'abbonamento a Microsoft 365 usa l'account dell'identità cloud.</span><span class="sxs-lookup"><span data-stu-id="c0c52-121">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="c0c52-122">Il tenant di Azure AD per l'abbonamento a Microsoft 365 gestisce il processo di autenticazione oppure reindirizza l'utente a un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="c0c52-122">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="c0c52-123">**Indicato per**</span><span class="sxs-lookup"><span data-stu-id="c0c52-123">**Best for**</span></span> | <span data-ttu-id="c0c52-124">Organizzazioni che non hanno o necessitano di un'istanza locale di AD DS.</span><span class="sxs-lookup"><span data-stu-id="c0c52-124">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="c0c52-125">Organizzazioni che usano AD DS o un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="c0c52-125">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="c0c52-126">**Principale vantaggio**</span><span class="sxs-lookup"><span data-stu-id="c0c52-126">**Greatest benefit**</span></span> | <span data-ttu-id="c0c52-127">Semplice da usare.</span><span class="sxs-lookup"><span data-stu-id="c0c52-127">Simple to use.</span></span> <span data-ttu-id="c0c52-128">Non richiede altri strumenti o server di directory.</span><span class="sxs-lookup"><span data-stu-id="c0c52-128">No extra directory tools or servers required.</span></span> | <span data-ttu-id="c0c52-129">Gli utenti possono usare le stesse credenziali per accedere a risorse locali o basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="c0c52-129">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="c0c52-130">Identità solo cloud</span><span class="sxs-lookup"><span data-stu-id="c0c52-130">Cloud-only identity</span></span>

<span data-ttu-id="c0c52-131">Un'identità solo cloud usa solo gli account utente che esistono in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0c52-131">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="c0c52-132">Viene in genere usata da organizzazioni di piccole dimensioni che non dispongono di server locali o non usano AD DS per gestire le identità locali.</span><span class="sxs-lookup"><span data-stu-id="c0c52-132">Cloud identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="c0c52-133">Ecco i componenti di base dell'identità solo cloud.</span><span class="sxs-lookup"><span data-stu-id="c0c52-133">Here are the basic components of cloud-only identity.</span></span>
 
![Componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="c0c52-135">Sia gli utenti locali che quelli remoti (online) usano gli account utente e le password di Azure AD per accedere ai servizi cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-135">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="c0c52-136">Azure AD autentica le credenziali utente in base agli account utente e alle password archiviate.</span><span class="sxs-lookup"><span data-stu-id="c0c52-136">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="c0c52-137">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="c0c52-137">Administration</span></span>
<span data-ttu-id="c0c52-138">Poiché gli account utente sono archiviati solo in Azure Active Directory, è possibile gestire le identità cloud con strumenti quali l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) e [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c0c52-138">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://admin.microsoft.com) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="c0c52-139">Identità ibrida</span><span class="sxs-lookup"><span data-stu-id="c0c52-139">Hybrid identity</span></span>

<span data-ttu-id="c0c52-140">L'identità ibrida usa gli account che provengono da un'istanza locale di AD DS e per i quali esiste una copia nel tenant di Azure AD di un abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0c52-140">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="c0c52-141">Tuttavia, la maggior parte delle modifiche è unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="c0c52-141">However, most changes only flow one way.</span></span> <span data-ttu-id="c0c52-142">Le modifiche apportate agli account utente di AD DS vengono sincronizzate con le copie corrispondenti in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0c52-142">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="c0c52-143">Le modifiche apportate agli account basati sul cloud in Azure AD, ad esempio i nuovi account utente, non vengono invece sincronizzate con AD DS.</span><span class="sxs-lookup"><span data-stu-id="c0c52-143">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="c0c52-144">Azure AD Connect offre la sincronizzazione continua degli account.</span><span class="sxs-lookup"><span data-stu-id="c0c52-144">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="c0c52-145">Viene eseguito in un server locale, verifica la presenza di modifiche in AD DS e invia queste modifiche ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0c52-145">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="c0c52-146">Azure AD Connect consente di filtrare gli account sincronizzati e scegliere se eseguire la sincronizzazione di una versione con hash delle password utente, nota come sincronizzazione dell'hash delle password (PHS).</span><span class="sxs-lookup"><span data-stu-id="c0c52-146">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="c0c52-147">Durante l'implementazione dell'identità ibrida, l'istanza locale di AD DS costituisce l'origine autorevole delle informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="c0c52-147">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="c0c52-148">Questo significa che le attività di amministrazione vengono eseguite principalmente in locale e quindi sincronizzate con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0c52-148">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="c0c52-149">Ecco i componenti dell'identità ibrida.</span><span class="sxs-lookup"><span data-stu-id="c0c52-149">Here are the components of hybrid identity.</span></span>

![Componenti dell'identità ibrida](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="c0c52-151">Il tenant di Azure AD contiene una copia degli account di AD DS.</span><span class="sxs-lookup"><span data-stu-id="c0c52-151">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="c0c52-152">In questa configurazione sia gli utenti locali che gli utenti remoti che accedono ai servizi cloud di Microsoft 365 eseguono l'autenticazione in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0c52-152">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="c0c52-153">È sempre necessario usare Azure AD Connect per sincronizzare gli account utenti per l'identità ibrida.</span><span class="sxs-lookup"><span data-stu-id="c0c52-153">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="c0c52-154">Gli account utente sincronizzati in Azure AD sono necessari per l'assegnazione di licenze e la gestione dei gruppi, nonché per configurare le autorizzazioni e per altre attività amministrative che interessano gli account utente.</span><span class="sxs-lookup"><span data-stu-id="c0c52-154">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="c0c52-155">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="c0c52-155">Administration</span></span>

<span data-ttu-id="c0c52-156">Dal momento che gli account utente originali e autorevoli sono archiviati nell'istanza locale di AD DS, è possibile gestire le identità con gli stessi strumenti di AD DS, ad esempio lo strumento Utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c0c52-156">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as AD DS, such as the Active Directory Users and Computers tool.</span></span> 

<span data-ttu-id="c0c52-157">Non è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell per Microsoft 365 per gestire gli account utente sincronizzati in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0c52-157">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="c0c52-158">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c0c52-158">Next step</span></span>

<span data-ttu-id="c0c52-159">Se è necessario il modello di identità solo cloud, vedere [identità solo cloud](cloud-only-identities.md).</span><span class="sxs-lookup"><span data-stu-id="c0c52-159">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="c0c52-160">Se è necessario il modello di identità ibrido, vedere [Hybrid Identity](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c0c52-160">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="c0c52-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0c52-161">See also</span></span>

[<span data-ttu-id="c0c52-162">Panoramica di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0c52-162">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
