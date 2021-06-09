---
title: Identità ibrida e sincronizzazione della directory per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Descrive la sincronizzazione della directory Microsoft 365, la pulizia di Servizi di dominio Active Directory e lo strumento Azure Active Directory Connessione directory.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927545"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="74fb8-103">Identità ibrida e sincronizzazione della directory per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74fb8-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="74fb8-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="74fb8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="74fb8-105">A seconda delle esigenze aziendali e dei requisiti tecnici, il modello di identità ibrido e la sincronizzazione della directory sono la scelta più comune per i clienti aziendali che adottano Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74fb8-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="74fb8-106">La sincronizzazione della directory consente di gestire le identità in Servizi di dominio Active Directory e tutti gli aggiornamenti agli account utente, ai gruppi e ai contatti vengono sincronizzati con il tenant di Azure Active Directory (Azure AD) della sottoscrizione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74fb8-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="74fb8-107">Quando gli account utente di Servizi di dominio Active Directory vengono sincronizzati per la prima volta, non vengono assegnati automaticamente a una licenza Microsoft 365 e non possono accedere ai servizi Microsoft 365, ad esempio la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74fb8-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="74fb8-108">È innanzitutto necessario assegnare loro una posizione di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="74fb8-108">You must first assign them a usage location.</span></span> <span data-ttu-id="74fb8-109">Assegnare quindi una licenza a questi account utente, singolarmente o dinamicamente tramite l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="74fb8-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="74fb8-110">Autenticazione per l'identità ibrida</span><span class="sxs-lookup"><span data-stu-id="74fb8-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="74fb8-111">Quando si utilizza il modello di identità ibrido, esistono due tipi di autenticazione:</span><span class="sxs-lookup"><span data-stu-id="74fb8-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="74fb8-112">Autenticazione gestita</span><span class="sxs-lookup"><span data-stu-id="74fb8-112">Managed authentication</span></span>

  <span data-ttu-id="74fb8-113">Azure AD gestisce il processo di autenticazione utilizzando una versione con hash archiviata localmente della password o invia le credenziali a un agente software locale per essere autenticato da Servizi di dominio Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="74fb8-114">Autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="74fb8-114">Federated authentication</span></span>

  <span data-ttu-id="74fb8-115">Azure AD reindirizza il computer client che richiede l'autenticazione a un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="74fb8-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="74fb8-116">Autenticazione gestita</span><span class="sxs-lookup"><span data-stu-id="74fb8-116">Managed authentication</span></span>

<span data-ttu-id="74fb8-117">Esistono due tipi di autenticazione gestita:</span><span class="sxs-lookup"><span data-stu-id="74fb8-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="74fb8-118">Sincronizzazione dell'hash delle password (PHS)</span><span class="sxs-lookup"><span data-stu-id="74fb8-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="74fb8-119">L'autenticazione viene eseguita direttamente da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74fb8-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="74fb8-120">Autenticazione pass-through (PTA)</span><span class="sxs-lookup"><span data-stu-id="74fb8-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="74fb8-121">L'autenticazione di Azure AD viene eseguita da AD DS.</span><span class="sxs-lookup"><span data-stu-id="74fb8-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="74fb8-122">Sincronizzazione dell'hash delle password (PHS)</span><span class="sxs-lookup"><span data-stu-id="74fb8-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="74fb8-123">Con PHS, sincronizzare gli account utente di Servizi di dominio Active Directory con Microsoft 365 e gestire gli utenti in locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="74fb8-124">Gli hash delle password utente vengono sincronizzati da Servizi di dominio Active Directory ad Azure AD in modo che gli utenti hanno la stessa password in locale e nel cloud.</span><span class="sxs-lookup"><span data-stu-id="74fb8-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="74fb8-125">Questo è il modo più semplice per abilitare l'autenticazione per le identità di Servizi di dominio Active Directory in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74fb8-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Sincronizzazione dell'hash delle password (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="74fb8-127">Quando le password vengono modificate o reimpostate in locale, i nuovi hash delle password vengono sincronizzati con Azure AD in modo che gli utenti possano sempre usare la stessa password per le risorse cloud e le risorse locali.</span><span class="sxs-lookup"><span data-stu-id="74fb8-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="74fb8-128">Le password utente non vengono mai inviate ad Azure AD o archiviate in Azure AD in testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="74fb8-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="74fb8-129">Alcune funzionalità premium di Azure AD, ad esempio Identity Protection, richiedono PHS indipendentemente dal metodo di autenticazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="74fb8-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="74fb8-130">Vedi [la scelta del metodo di autenticazione giusto](/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="74fb8-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="74fb8-131">Autenticazione pass-through (PTA)</span><span class="sxs-lookup"><span data-stu-id="74fb8-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="74fb8-132">PTA fornisce una semplice convalida delle password per i servizi di autenticazione di Azure AD usando un agente software in esecuzione su uno o più server locali per convalidare gli utenti direttamente con Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74fb8-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="74fb8-133">Con PTA, sincronizzare gli account utente di Servizi di dominio Active Directory con Microsoft 365 e gestire gli utenti in locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Autenticazione pass-through (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="74fb8-135">PTA consente agli utenti di accedere alle risorse e alle Microsoft 365 locali e alle applicazioni usando l'account e la password locali.</span><span class="sxs-lookup"><span data-stu-id="74fb8-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="74fb8-136">Questa configurazione convalida le password degli utenti direttamente rispetto a Servizi di dominio Active Directory locale senza archiviare gli hash delle password in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74fb8-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="74fb8-137">PTA è anche per le organizzazioni con un requisito di sicurezza per applicare immediatamente gli stati degli account utente locali, i criteri password e le ore di accesso.</span><span class="sxs-lookup"><span data-stu-id="74fb8-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="74fb8-138">Vedi [la scelta del metodo di autenticazione giusto](/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="74fb8-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="74fb8-139">Autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="74fb8-139">Federated authentication</span></span>

<span data-ttu-id="74fb8-140">L'autenticazione federata è principalmente per organizzazioni aziendali di grandi dimensioni con requisiti di autenticazione più complessi.</span><span class="sxs-lookup"><span data-stu-id="74fb8-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="74fb8-141">Le identità di Servizi di dominio Active Directory vengono sincronizzate con Microsoft 365 e gli account utente vengono gestiti in locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="74fb8-142">Con l'autenticazione federata, gli utenti hanno la stessa password in locale e nel cloud e non devono accedere di nuovo per usare Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74fb8-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="74fb8-143">L'autenticazione federata può supportare ulteriori requisiti di autenticazione, ad esempio l'autenticazione basata su smart card o un'autenticazione a più fattori di terze parti ed è in genere necessaria quando le organizzazioni hanno un requisito di autenticazione non supportato in modo nativo da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74fb8-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="74fb8-144">Vedi [la scelta del metodo di autenticazione giusto](/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="74fb8-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="74fb8-145">Provider di identità e autenticazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="74fb8-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="74fb8-146">Gli oggetti directory locali possono essere sincronizzati con Microsoft 365 e l'accesso alle risorse cloud è gestito principalmente da un provider di identità di terze parti.On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span><span class="sxs-lookup"><span data-stu-id="74fb8-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="74fb8-147">Se l'organizzazione usa una soluzione di federazione di terze parti, è possibile configurare l'accesso con tale soluzione per Microsoft 365 purché la soluzione di federazione di terze parti sia compatibile con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74fb8-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="74fb8-148">Per altre informazioni, [vedi l'elenco di compatibilità](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) della federazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74fb8-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="74fb8-149">Preparazione di Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="74fb8-149">AD DS Preparation</span></span>

<span data-ttu-id="74fb8-150">Per garantire una transizione senza problemi a Microsoft 365 tramite la sincronizzazione, è necessario preparare la foresta di Servizi di dominio Active Directory prima di iniziare la Microsoft 365 di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="74fb8-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="74fb8-151">La preparazione della directory deve concentrarsi sulle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="74fb8-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="74fb8-152">Rimuovere gli **attributi proxyAddress** e **userPrincipalName** duplicati.</span><span class="sxs-lookup"><span data-stu-id="74fb8-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="74fb8-153">Aggiornare gli attributi **userPrincipalName vuoti** e non validi con **attributi userPrincipalName** validi.</span><span class="sxs-lookup"><span data-stu-id="74fb8-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="74fb8-154">Rimuovere i caratteri non validi e discutibile negli attributi **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses,** **mailNickname** e **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="74fb8-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="74fb8-155">Per informazioni dettagliate sulla preparazione degli attributi, vedere [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span><span class="sxs-lookup"><span data-stu-id="74fb8-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="74fb8-156">Questi sono gli stessi attributi che Azure AD Connessione sincronizza.</span><span class="sxs-lookup"><span data-stu-id="74fb8-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="74fb8-157">Considerazioni sulla distribuzione a più foreste</span><span class="sxs-lookup"><span data-stu-id="74fb8-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="74fb8-158">Per più foreste e opzioni SSO, usare [un'installazione personalizzata di Azure AD Connessione](/azure/active-directory/hybrid/how-to-connect-install-custom).</span><span class="sxs-lookup"><span data-stu-id="74fb8-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="74fb8-159">Se l'organizzazione dispone di più foreste per l'autenticazione (foreste di accesso), è consigliabile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74fb8-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="74fb8-160">**Valutare la possibilità di consolidare le foreste.**</span><span class="sxs-lookup"><span data-stu-id="74fb8-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="74fb8-161">In generale, è necessario un maggiore sovraccarico per la gestione di più foreste.</span><span class="sxs-lookup"><span data-stu-id="74fb8-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="74fb8-162">A meno che l'organizzazione non abbia vincoli di sicurezza che impongono la necessità di foreste separate, è consigliabile semplificare l'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="74fb8-163">**Utilizzare solo nella foresta di accesso principale.**</span><span class="sxs-lookup"><span data-stu-id="74fb8-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="74fb8-164">Prendere in considerazione la Microsoft 365 solo nella foresta di accesso principale per l'implementazione iniziale di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74fb8-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="74fb8-165">Se non è possibile consolidare la distribuzione di Servizi di dominio Active Directory a più foreste o si utilizzano altri servizi directory per gestire le identità, è possibile sincronizzarli con l'aiuto di Microsoft o di un partner.</span><span class="sxs-lookup"><span data-stu-id="74fb8-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="74fb8-166">Per ulteriori informazioni, vedere [Topologies for Azure AD Connessione.](/azure/active-directory/hybrid/plan-connect-topologies)</span><span class="sxs-lookup"><span data-stu-id="74fb8-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="74fb8-167">Funzionalità che dipendono dalla sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="74fb8-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="74fb8-168">La sincronizzazione della directory è necessaria per le caratteristiche e le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="74fb8-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="74fb8-169">Azure AD Seamless Single Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="74fb8-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="74fb8-170">Skype coesistenza</span><span class="sxs-lookup"><span data-stu-id="74fb8-170">Skype coexistence</span></span>
- <span data-ttu-id="74fb8-171">Exchange distribuzione ibrida, tra cui:</span><span class="sxs-lookup"><span data-stu-id="74fb8-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="74fb8-172">Elenco indirizzi globale (GAL) completamente condiviso tra l'ambiente Exchange locale e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74fb8-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="74fb8-173">Sincronizzazione delle informazioni dell'elenco indirizzi globale da sistemi di posta diversi.</span><span class="sxs-lookup"><span data-stu-id="74fb8-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="74fb8-174">Possibilità di aggiungere e rimuovere utenti da Microsoft 365 offerte di servizi.</span><span class="sxs-lookup"><span data-stu-id="74fb8-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="74fb8-175">A tale scopo, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74fb8-175">This requires the following:</span></span>
  - <span data-ttu-id="74fb8-176">La sincronizzazione bidirezionale deve essere configurata durante l'installazione della sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="74fb8-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="74fb8-177">Per impostazione predefinita, gli strumenti di sincronizzazione della directory scrivono le informazioni della directory solo nel cloud.</span><span class="sxs-lookup"><span data-stu-id="74fb8-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="74fb8-178">Quando si configura la sincronizzazione bidirezionale, si abilita la funzionalità di write-back in modo che un numero limitato di attributi dell'oggetto viene copiato dal cloud e quindi li si scrive di nuovo nel Servizio di dominio Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="74fb8-179">Il write-back viene anche definito Exchange ibrida.</span><span class="sxs-lookup"><span data-stu-id="74fb8-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="74fb8-180">Una distribuzione ibrida Exchange locale</span><span class="sxs-lookup"><span data-stu-id="74fb8-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="74fb8-181">Possibilità di spostare alcune cassette postali utente in Microsoft 365 mantenendo altre cassette postali utente in locale.</span><span class="sxs-lookup"><span data-stu-id="74fb8-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="74fb8-182">I mittenti attendibili e i mittenti bloccati in locale vengono replicati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74fb8-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="74fb8-183">Delega di base e funzionalità di invio per conto di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74fb8-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="74fb8-184">Si dispone di una soluzione di autenticazione a più fattori o smart card locale integrata.</span><span class="sxs-lookup"><span data-stu-id="74fb8-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="74fb8-185">Sincronizzazione di foto, anteprime, sale riunioni e gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="74fb8-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="74fb8-186">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="74fb8-186">Next step</span></span>

<span data-ttu-id="74fb8-187">Quando si è pronti per distribuire l'identità ibrida, vedere [Prepare for directory synchronization](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="74fb8-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
