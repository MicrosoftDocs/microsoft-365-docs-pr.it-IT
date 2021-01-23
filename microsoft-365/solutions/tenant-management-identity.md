---
title: 'Passaggio 3: Identità per i tenant di Microsoft 365 per Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Distribuire il modello di identità corretto per i tenant di Microsoft 365 e applicare forti accesso utente.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908560"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="49342-104">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="49342-104">Step 3.</span></span> <span data-ttu-id="49342-105">Identità per i tenant di Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="49342-105">Identity for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="49342-106">Il tenant di Microsoft 365 include un tenant di Azure Active Directory (Azure AD) per la gestione delle identità e l'autenticazione per gli accessi. Ottenere l'infrastruttura di identità configurata in modo corretto è fondamentale per la gestione dell'accesso utente e delle autorizzazioni di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="49342-106">Your Microsoft 365 tenant includes an Azure Active Directory (Azure AD) tenant to manage identities and authentication for sign-ins. Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

## <a name="cloud-only-vs-hybrid"></a><span data-ttu-id="49342-107">Solo cloud vs ibrido</span><span class="sxs-lookup"><span data-stu-id="49342-107">Cloud-only vs. hybrid</span></span>

<span data-ttu-id="49342-108">Di seguito sono illustrati i due tipi di modelli di identità e i loro vantaggi e adattamenti migliori.</span><span class="sxs-lookup"><span data-stu-id="49342-108">Here are the two types of identity models and their best fit and benefits.</span></span>


| <span data-ttu-id="49342-109">Modello</span><span class="sxs-lookup"><span data-stu-id="49342-109">Model</span></span> | <span data-ttu-id="49342-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49342-110">Description</span></span> | <span data-ttu-id="49342-111">Autenticazione delle credenziali utente in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49342-111">How Microsoft 365 authenticates user credentials</span></span> | <span data-ttu-id="49342-112">Indicato per</span><span class="sxs-lookup"><span data-stu-id="49342-112">Best for</span></span> | <span data-ttu-id="49342-113">Principale vantaggio</span><span class="sxs-lookup"><span data-stu-id="49342-113">Greatest benefit</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="49342-114">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="49342-114">Cloud-only</span></span> | <span data-ttu-id="49342-115">L'account utente esiste solo nel tenant di Azure AD per il tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49342-115">User account only exists in the Azure AD tenant for your Microsoft 365 tenant.</span></span> | <span data-ttu-id="49342-116">Il tenant di Azure AD per il tenant di Microsoft 365 esegue l'autenticazione con l'account di identità cloud.</span><span class="sxs-lookup"><span data-stu-id="49342-116">The Azure AD tenant for your Microsoft 365 tenant performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="49342-117">Organizzazioni che non hanno o necessitano di un'istanza locale di AD DS.</span><span class="sxs-lookup"><span data-stu-id="49342-117">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="49342-118">Semplice da usare.</span><span class="sxs-lookup"><span data-stu-id="49342-118">Simple to use.</span></span> <span data-ttu-id="49342-119">Non richiede altri strumenti o server di directory.</span><span class="sxs-lookup"><span data-stu-id="49342-119">No extra directory tools or servers required.</span></span> |
| <span data-ttu-id="49342-120">Ibrido</span><span class="sxs-lookup"><span data-stu-id="49342-120">Hybrid</span></span> |  <span data-ttu-id="49342-121">L'account utente è presente nei servizi di dominio Active Directory locali (AD DS) e una copia è anche nel tenant di Azure AD per il tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49342-121">User account exists in your on-premises Active Directory Domain Services (AD DS) and a copy is also in the Azure AD tenant for your Microsoft 365 tenant.</span></span> <span data-ttu-id="49342-122">Azure AD Connect viene eseguito su un server locale per sincronizzare le modifiche di servizi di dominio Active Directory al tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49342-122">Azure AD Connect runs on an on-premises server to synchronize AD DS changes to your Azure AD tenant.</span></span> <span data-ttu-id="49342-123">L'account utente in Azure AD potrebbe includere anche una versione con hash della password dell'account utente di AD DS già sottoposto a hash.</span><span class="sxs-lookup"><span data-stu-id="49342-123">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> | <span data-ttu-id="49342-124">Il tenant di Azure AD per il tenant di Microsoft 365 gestisce il processo di autenticazione oppure reindirizza l'utente a un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="49342-124">The Azure AD tenant for your Microsoft 365 tenant either handles the authentication process or redirects the user to another identity provider.</span></span> | <span data-ttu-id="49342-125">Organizzazioni che usano AD DS o un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="49342-125">Organizations using AD DS or another identity provider.</span></span> | <span data-ttu-id="49342-126">Gli utenti possono usare le stesse credenziali per accedere a risorse locali o basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="49342-126">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||||

<span data-ttu-id="49342-127">Ecco i componenti di base dell'identità solo cloud.</span><span class="sxs-lookup"><span data-stu-id="49342-127">Here are the basic components of cloud-only identity.</span></span>
 
![Componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="49342-129">In questa illustrazione, gli utenti locali e remoti eseguono l'accesso con account nel tenant di Azure AD del tenant Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49342-129">In this illustration, on-premises and remote users sign in with accounts in the Azure AD tenant of their Microsoft 365 tenant.</span></span>

<span data-ttu-id="49342-130">Di seguito sono ripartiti i componenti di base dell'identità ibrida.</span><span class="sxs-lookup"><span data-stu-id="49342-130">Here are the basic components of hybrid identity.</span></span>

![Componenti di base dell'identità ibrida](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="49342-132">In questa illustrazione, gli utenti locali e remoti eseguono l'accesso al tenant Microsoft 365 con account nel tenant di Azure AD che sono stati copiati dal servizio di dominio Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="49342-132">In this illustration, on-premises and remote users sign in to their Microsoft 365 tenant with accounts in the Azure AD tenant that have been copied from their on-premises AD DS.</span></span>

## <a name="synchronizing-your-on-premises-ad-ds"></a><span data-ttu-id="49342-133">Sincronizzazione di servizi di dominio Active Directory locali</span><span class="sxs-lookup"><span data-stu-id="49342-133">Synchronizing your on-premises AD DS</span></span>

<span data-ttu-id="49342-134">A seconda delle esigenze aziendali e dei requisiti tecnici, il modello di identità ibrido e la sincronizzazione della directory rappresentano la scelta più comune per i clienti aziendali che stanno adottando Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49342-134">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="49342-135">La sincronizzazione della directory consente di gestire le identità in AD DS e tutti gli aggiornamenti per gli account utente, i gruppi e i contatti vengono sincronizzati con il tenant di Azure AD del tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49342-135">Directory synchronization allows you to manage identities in your AD DS and all updates to user accounts, groups, and contacts are synchronized to the Azure AD tenant of your Microsoft 365 tenant.</span></span>

>[!Note]
><span data-ttu-id="49342-136">Quando gli account utente di servizi di dominio Active Directory vengono sincronizzati per la prima volta, non viene assegnata automaticamente una licenza Microsoft 365 e non possono accedere ai servizi Microsoft 365, ad esempio la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="49342-136">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="49342-137">Prima di tutto, è necessario assegnare loro una posizione di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="49342-137">You must first assign them a usage location.</span></span> <span data-ttu-id="49342-138">Assegnare quindi una licenza a questi account utente, sia singolarmente che dinamicamente tramite l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="49342-138">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

<span data-ttu-id="49342-139">Di seguito sono disponibili i due tipi di autenticazione quando si utilizza il modello di identità ibrido.</span><span class="sxs-lookup"><span data-stu-id="49342-139">Here are the two types of authentication when using the hybrid identity model.</span></span>

| <span data-ttu-id="49342-140">Tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="49342-140">Authentication type</span></span> | <span data-ttu-id="49342-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49342-141">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="49342-142">Autenticazione gestita</span><span class="sxs-lookup"><span data-stu-id="49342-142">Managed authentication</span></span> | <span data-ttu-id="49342-143">Azure AD gestisce il processo di autenticazione utilizzando una versione con hash archiviati localmente della password o invia le credenziali a un agente software locale per essere autenticato da servizi di dominio Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="49342-143">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span> <br> <br>  <span data-ttu-id="49342-144">Esistono due tipi di autenticazione gestita: la sincronizzazione dell'hash delle password (pH) e l'autenticazione pass-through (PTA).</span><span class="sxs-lookup"><span data-stu-id="49342-144">There are two types of managed authentication: Password hash synchronization (PHS) and Pass-through authentication (PTA).</span></span> <span data-ttu-id="49342-145">Con pH, Azure AD esegue l'autenticazione stessa.</span><span class="sxs-lookup"><span data-stu-id="49342-145">With PHS, Azure AD performs the authentication itself.</span></span> <span data-ttu-id="49342-146">Con PTA, Azure AD ha servizi di dominio Active Directory per eseguire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="49342-146">With PTA, Azure AD has AD DS perform the authentication.</span></span> |
| <span data-ttu-id="49342-147">Autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="49342-147">Federated authentication</span></span> | <span data-ttu-id="49342-148">Azure AD reindirizza il computer client che richiede l'autenticazione a un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="49342-148">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span> |
|  |  |

<span data-ttu-id="49342-149">Per ulteriori informazioni, vedere [scelta del metodo di autenticazione appropriato](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="49342-149">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>

## <a name="enforcing-strong-sign-ins"></a><span data-ttu-id="49342-150">Applicazione di accessi sicuri</span><span class="sxs-lookup"><span data-stu-id="49342-150">Enforcing strong sign-ins</span></span>

<span data-ttu-id="49342-151">Per aumentare la sicurezza degli accessi degli utenti, utilizzare le funzionalità e le funzionalità nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="49342-151">To increase the security of user sign-ins, use the features and capabilities in the following table.</span></span>

| <span data-ttu-id="49342-152">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="49342-152">Capability</span></span> | <span data-ttu-id="49342-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49342-153">Description</span></span> | <span data-ttu-id="49342-154">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="49342-154">More information</span></span> | <span data-ttu-id="49342-155">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="49342-155">Licensing requirements</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="49342-156">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="49342-156">Windows Hello for Business</span></span> | <span data-ttu-id="49342-157">Sostituisce le password con una forte autenticazione a due fattori quando si effettua l'accesso a un dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="49342-157">Replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="49342-158">I due fattori sono un nuovo tipo di credenziale utente che è associato a un dispositivo e a una biometria o a un PIN.</span><span class="sxs-lookup"><span data-stu-id="49342-158">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span> | [<span data-ttu-id="49342-159">Panoramica di Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="49342-159">Windows Hello for Business Overview</span></span>](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | <span data-ttu-id="49342-160">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="49342-160">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="49342-161">Protezione delle password di Azure AD</span><span class="sxs-lookup"><span data-stu-id="49342-161">Azure AD Password Protection</span></span> | <span data-ttu-id="49342-162">Rileva e blocca le password deboli note e le relative varianti e può anche bloccare ulteriori termini deboli specifici per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="49342-162">Detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> | [<span data-ttu-id="49342-163">Configurare la protezione delle password di Azure AD</span><span class="sxs-lookup"><span data-stu-id="49342-163">Configure Azure AD password protection</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | <span data-ttu-id="49342-164">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="49342-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="49342-165">Usare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="49342-165">Use multi-factor authentication (MFA)</span></span> | <span data-ttu-id="49342-166">AMF richiede che gli accessi degli utenti siano soggetti a una verifica supplementare oltre la password dell'account utente, ad esempio la verifica con un'app per smartphone o un SMS inviato a uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="49342-166">MFA requires that user sign-ins be subject to an additional verification beyond the user account password, such as verification with a smartphone app or a text message sent to a smartphone.</span></span> <span data-ttu-id="49342-167">Vedere [questo video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) per istruzioni su come gli utenti configurano l'AMF.</span><span class="sxs-lookup"><span data-stu-id="49342-167">See [this video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) for instructions on how users set up MFA.</span></span> | [<span data-ttu-id="49342-168">Mae per Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="49342-168">MFA for Microsoft 365 for enterprise</span></span>](../enterprise/microsoft-365-secure-sign-in.md#mfa) | <span data-ttu-id="49342-169">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="49342-169">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="49342-170">Configurazioni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="49342-170">Identity and device access configurations</span></span> | <span data-ttu-id="49342-171">Impostazioni e criteri che consistono nelle caratteristiche prerequisite consigliate e nelle relative impostazioni, combinati con i criteri di accesso condizionale, Intune e Azure AD Identity Protection, che determinano se una determinata richiesta di accesso deve essere concessa e in quali condizioni.</span><span class="sxs-lookup"><span data-stu-id="49342-171">Settings and policies that consist of recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span>  | [<span data-ttu-id="49342-172">Configurazioni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="49342-172">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md) | <span data-ttu-id="49342-173">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="49342-173">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="49342-174">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="49342-174">Azure AD Identity Protection</span></span> | <span data-ttu-id="49342-175">Proteggersi dal compromesso delle credenziali, in cui un utente malintenzionato determina il nome e la password dell'account e l'accesso ai dati e ai servizi cloud dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="49342-175">Protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> | [<span data-ttu-id="49342-176">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="49342-176">Azure AD Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | <span data-ttu-id="49342-177">Microsoft 365 E5 o Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection</span><span class="sxs-lookup"><span data-stu-id="49342-177">Microsoft 365 E5 or Microsoft 365 E3 with the Identity & Threat Protection add-on</span></span> |
|  |  |  |



## <a name="results-of-step-3"></a><span data-ttu-id="49342-178">Risultati del Passaggio 3</span><span class="sxs-lookup"><span data-stu-id="49342-178">Results of Step 3</span></span>

<span data-ttu-id="49342-179">Per l'identità del tenant Microsoft 365, è stato determinato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="49342-179">For identity for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="49342-180">Modello di identità da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="49342-180">Which identity model to use.</span></span>
- <span data-ttu-id="49342-181">Modalità di applicazione di un utilizzo sicuro degli utenti e del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49342-181">How you will enforce strong user and device access.</span></span>

<span data-ttu-id="49342-182">Di seguito è riportato un esempio di tenant con i nuovi elementi Identity ibridi evidenziati.</span><span class="sxs-lookup"><span data-stu-id="49342-182">Here is an example a tenant with the new hybrid identity elements highlighted.</span></span>

![Esempio di identità ibrida per un tenant](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

<span data-ttu-id="49342-184">In questa figura, il tenant ha:</span><span class="sxs-lookup"><span data-stu-id="49342-184">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="49342-185">Una foresta di servizi di dominio Active Directory che viene sincronizzata con il tenant di Azure AD utilizzando un server DirSync e Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="49342-185">An AD DS forest that is being synchronized with the Azure AD tenant using a DirSync server and Azure AD Connect.</span></span>
- <span data-ttu-id="49342-186">Copia degli account utente di servizi di dominio Active Directory e di altri oggetti dalla foresta di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49342-186">A copy of the AD DS user accounts and other objects from the AD DS forest.</span></span>
- <span data-ttu-id="49342-187">Un set di criteri di accesso condizionale per applicare gli accessi e l'accesso degli utenti sicuri in base all'account utente.</span><span class="sxs-lookup"><span data-stu-id="49342-187">A set of Conditional Access policies to enforce secure user sign-ins and access based on the user account.</span></span> 

## <a name="ongoing-maintenance-for-identity"></a><span data-ttu-id="49342-188">Manutenzione continua per l'identità</span><span class="sxs-lookup"><span data-stu-id="49342-188">Ongoing maintenance for identity</span></span>

<span data-ttu-id="49342-189">Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="49342-189">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="49342-190">Aggiungere o modificare gli account utente e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="49342-190">Add or modify user accounts and groups.</span></span> <span data-ttu-id="49342-191">Per l'identità solo cloud, è possibile gestire gli utenti e i gruppi basati sul cloud con gli strumenti di Azure AD, ad esempio l'interfaccia di amministrazione di Microsoft 365 o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49342-191">For cloud-only identity, you maintain your cloud-based users and groups with Azure AD tools such as the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="49342-192">Per l'identità ibrida, è possibile gestire gli utenti e i gruppi locali con gli strumenti di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49342-192">For hybrid identity, you maintain your on-premises users and groups with AD DS tools.</span></span>
- <span data-ttu-id="49342-193">Aggiungere o modificare la configurazione dell'identità e dell'accesso ai dispositivi per applicare i requisiti di sicurezza di accesso.</span><span class="sxs-lookup"><span data-stu-id="49342-193">Add or modify your identity and device access configuration to enforce sign-in security requirements.</span></span>

## <a name="next-step"></a><span data-ttu-id="49342-194">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="49342-194">Next step</span></span>

<span data-ttu-id="49342-195">[![Passaggio 4. Migrare i dati e i server di Office locali](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span><span class="sxs-lookup"><span data-stu-id="49342-195">[![Step 4. Migrate your on-premises Office servers and data](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span></span>

<span data-ttu-id="49342-196">Continuare con la [migrazione](tenant-management-migration.md) per migrare i server di Office locali e i relativi dati a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49342-196">Continue with [migration](tenant-management-migration.md) to migrate your on-premises Office servers and their data to Microsoft 365.</span></span>