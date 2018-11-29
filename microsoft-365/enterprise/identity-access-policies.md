---
title: Identità e dispositivi comuni accedere criteri - Microsoft 365 Enterprise | Documenti di Microsoft
description: Descrive i criteri per i consigli di Microsoft su come applicare i criteri e le configurazioni relativi all'identità e all'accesso ai dispositivi.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868914"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="517d1-103">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="517d1-103">Common identity and device access policies</span></span>
<span data-ttu-id="517d1-104">In questo articolo viene comuni consigliati i criteri per la protezione dell'accesso per il cloud services, incluse le applicazioni locale pubblicate con Proxy dell'applicazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="517d1-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="517d1-p101">In questa guida viene descritto come distribuire i criteri consigliati in un ambiente di cui è appena stato eseguito il provisioning. L'impostazione di questi criteri in un ambiente lab distinto consente di comprendere e valutare i criteri consigliati prima di eseguire l'implementazione degli ambienti di pre-produzione e di produzione. L'ambiente di cui è stato eseguito il provisioning può essere solo cloud o ibrido.</span><span class="sxs-lookup"><span data-stu-id="517d1-p101">This guidance discusses how to deploy the recommended policies in a newly provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your pre-production and production environments. Your newly provisioned environment may be cloud-only or Hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="517d1-108">Set di criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-108">Policy set</span></span> 

<span data-ttu-id="517d1-p102">Nel diagramma seguente illustra il set di criteri consigliato. Viene illustrato quale livello di protezione si applica a ogni criterio e indica se i criteri si applicano a PC, telefoni e Tablet o entrambe le categorie di dispositivi. Indica inoltre cui tali criteri vengono configurati.</span><span class="sxs-lookup"><span data-stu-id="517d1-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs, phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Criteri comuni per la configurazione dell'accesso di identità e dei dispositivi](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="517d1-113">Il resto di questo articolo viene descritto come configurare questi criteri.</span><span class="sxs-lookup"><span data-stu-id="517d1-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="517d1-p103">È consigliabile utilizzare l'autenticazione a più fattori dopo aver registrato i dispositivi in Intune per verificare che il dispositivo non è in possesso dell'utente desiderato. Ed è necessario registrare dispositivi in Intune prima dell'applicazione di criteri di conformità di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="517d1-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. And you must enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="517d1-p104">Per assegnare il tempo necessario per eseguire queste attività, è consigliabile implementare criteri di base nell'ordine elencato nella tabella seguente. Tuttavia, è possibile implementare criteri MFA per la protezione riservato e altamente regolamentato in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="517d1-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="517d1-118">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="517d1-118">Protection level</span></span>|<span data-ttu-id="517d1-119">Criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-119">Policies</span></span>|<span data-ttu-id="517d1-120">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="517d1-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="517d1-121">**Protezione di base**</span><span class="sxs-lookup"><span data-stu-id="517d1-121">**Baseline**</span></span>|[<span data-ttu-id="517d1-122">È necessario MFA per i rischi di accesso impostato *su medio* o *alta*</span><span class="sxs-lookup"><span data-stu-id="517d1-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="517d1-123">Bloccare i client che non supportano l'autenticazione moderno</span><span class="sxs-lookup"><span data-stu-id="517d1-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="517d1-124">I client che non utilizzano l'autenticazione moderno possono ignorare le regole di accesso condizionale in modo che è importante bloccare queste.</span><span class="sxs-lookup"><span data-stu-id="517d1-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these.</span></span>|
|        |[<span data-ttu-id="517d1-125">Gli utenti ad alto rischio modifica della password</span><span class="sxs-lookup"><span data-stu-id="517d1-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="517d1-126">Impone agli utenti di modificare la password all'accesso se viene rilevata qualche attività ad alto rischio per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="517d1-126">Forces users to change their password when signing in if high risk activity is detected for their account.</span></span>|
|        |[<span data-ttu-id="517d1-127">Definire criteri di protezione delle app</span><span class="sxs-lookup"><span data-stu-id="517d1-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="517d1-128">Un criterio per ogni piattaforma (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="517d1-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="517d1-129">Richiedi App approvate</span><span class="sxs-lookup"><span data-stu-id="517d1-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="517d1-130">Impone la protezione di applicazioni per dispositivi mobili per telefoni e Tablet</span><span class="sxs-lookup"><span data-stu-id="517d1-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="517d1-131">Definire criteri di conformità di dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="517d1-132">Un criterio per ogni piattaforma.</span><span class="sxs-lookup"><span data-stu-id="517d1-132">One policy for each platform.</span></span>|
|        |[<span data-ttu-id="517d1-133">Richiedi PC Compatible</span><span class="sxs-lookup"><span data-stu-id="517d1-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="517d1-134">Impone la gestione Intune di PC</span><span class="sxs-lookup"><span data-stu-id="517d1-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="517d1-135">**Dati sensibili**</span><span class="sxs-lookup"><span data-stu-id="517d1-135">**Sensitive**</span></span>|[<span data-ttu-id="517d1-136">È necessario MFA per i rischi di accesso sono *bassa*, *Media* o *alta*</span><span class="sxs-lookup"><span data-stu-id="517d1-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="517d1-137">Richiedi compatibile con PC *e* dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="517d1-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="517d1-138">Impone la gestione di Intune per PC e telefono/Tablet.</span><span class="sxs-lookup"><span data-stu-id="517d1-138">Enforces Intune management for PCs and phone/tablets.</span></span>|
|<span data-ttu-id="517d1-139">**Protezione per ambienti altamente regolamentati**</span><span class="sxs-lookup"><span data-stu-id="517d1-139">**Highly regulated**</span></span>|[<span data-ttu-id="517d1-140">*Sempre* richiedono MFA</span><span class="sxs-lookup"><span data-stu-id="517d1-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="517d1-141">Assegnazione di criteri per gli utenti</span><span class="sxs-lookup"><span data-stu-id="517d1-141">Assigning policies to users</span></span>
<span data-ttu-id="517d1-p105">Prima di configurare i criteri, identificare i gruppi di Azure Active Directory in uso per ogni livello di protezione. Protezione di base in genere, si applica a tutti gli utenti nell'organizzazione. Un utente che è incluso sia previsto e la protezione sensibile avrà tutti i criteri di base applicati più criteri riservati. Protezione è cumulativa e viene applicato il criterio più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="517d1-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="517d1-p106">Una procedura consigliata consiste nel creare un gruppo di Azure Active Directory per l'esclusione di accesso condizionale. Aggiungere il gruppo a tutte le regole di accesso condizionato in "Exclude". In questo modo un metodo per fornire l'accesso a un utente durante la risoluzione dei problemi di accesso. Si consiglia di come soluzione temporanea. Monitorare questo gruppo per le modifiche e verificare che il gruppo di esclusione è utilizzato solo come previsto.</span><span class="sxs-lookup"><span data-stu-id="517d1-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="517d1-151">Nel diagramma seguente viene fornito un esempio di assegnazione utente e le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="517d1-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![Assegnazione di esempio utente e le esclusioni per le regole di MFA](../images/identity-access-policies-assignment.png)

<span data-ttu-id="517d1-p107">Nella figura "team di project segreta principali X" è stato assegnato un criterio di accesso condizionale che richiede MFA *sempre*. Essere razionale quando si applica più alti livelli di protezione per gli utenti. I membri del team di progetto deve fornire due metodi di autenticazione ogni volta che si connettono, anche se non visualizzano contenuto altamente regolamentato.</span><span class="sxs-lookup"><span data-stu-id="517d1-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly regulated content.</span></span>  

 <span data-ttu-id="517d1-p108">Tutti i gruppi di Azure Active Directory creati come parte di questi suggerimenti devono essere creati come gruppi di Office 365. Si tratta in particolare importante per la distribuzione di Azure Information Protection (AIP) durante la protezione dei documenti in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="517d1-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Acquisizione schermo per la creazione di gruppi di Office 365](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="517d1-159">Richiedi MFA basato su accesso rischio</span><span class="sxs-lookup"><span data-stu-id="517d1-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="517d1-p109">Prima di richiedere MFA, utilizzare un criterio di registrazione di MFA di protezione di identità per registrare gli utenti di MFA. Dopo che gli utenti vengono registrati è possibile applicare MFA per l'accesso. [Lavoro prerequisito](identity-access-prerequisites.md) inclusa la registrazione di tutti gli utenti con MFA.</span><span class="sxs-lookup"><span data-stu-id="517d1-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="517d1-163">Per creare nuovi criteri di accesso condizionale:</span><span class="sxs-lookup"><span data-stu-id="517d1-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="517d1-p110">Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.</span><span class="sxs-lookup"><span data-stu-id="517d1-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="517d1-166">Scegliere **Azure Active Directory** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="517d1-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="517d1-167">Nella sezione **Sicurezza** scegliere **Accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="517d1-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="517d1-168">Scegliere **nuovo criterio** , come illustrato nella figura riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="517d1-168">Choose **New policy** as shown in the screenshot below:</span></span>

![Criterio di accesso condizionale di base](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="517d1-170">Nelle tabelle seguenti vengono descritte le impostazioni di criteri di accesso condizionale per l'implementazione di questo criterio.</span><span class="sxs-lookup"><span data-stu-id="517d1-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="517d1-171">**Assegnazioni**</span><span class="sxs-lookup"><span data-stu-id="517d1-171">**Assignments**</span></span>

|<span data-ttu-id="517d1-172">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-172">Type</span></span>|<span data-ttu-id="517d1-173">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-173">Properties</span></span>|<span data-ttu-id="517d1-174">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-174">Values</span></span>|<span data-ttu-id="517d1-175">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-176">Utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="517d1-176">Users and groups</span></span>|<span data-ttu-id="517d1-177">Includi</span><span class="sxs-lookup"><span data-stu-id="517d1-177">Include</span></span>|<span data-ttu-id="517d1-178">Seleziona utenti e gruppi - Selezionare il gruppo di sicurezza specifico in cui sono contenuti gli utenti di destinazione</span><span class="sxs-lookup"><span data-stu-id="517d1-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="517d1-179">Iniziare con il gruppo di sicurezza che include utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="517d1-179">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="517d1-180">Exclude</span><span class="sxs-lookup"><span data-stu-id="517d1-180">Exclude</span></span>|<span data-ttu-id="517d1-181">Exception security group; service accounts (app identities) (Gruppo di sicurezza eccezione account del servizio (identità applicazione)</span><span class="sxs-lookup"><span data-stu-id="517d1-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="517d1-182">Appartenenza modificata su base temporanea a seconda delle necessità</span><span class="sxs-lookup"><span data-stu-id="517d1-182">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="517d1-183">App cloud</span><span class="sxs-lookup"><span data-stu-id="517d1-183">Cloud apps</span></span>|<span data-ttu-id="517d1-184">Includi</span><span class="sxs-lookup"><span data-stu-id="517d1-184">Include</span></span>|<span data-ttu-id="517d1-p111">Selezionare le applicazioni che si desidera applicare per la regola. Ad esempio, selezionare Exchange Online di Office 365</span><span class="sxs-lookup"><span data-stu-id="517d1-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="517d1-187">Condizioni</span><span class="sxs-lookup"><span data-stu-id="517d1-187">Conditions</span></span>|<span data-ttu-id="517d1-188">Configurata</span><span class="sxs-lookup"><span data-stu-id="517d1-188">Configured</span></span>|<span data-ttu-id="517d1-189">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-189">Yes</span></span>|<span data-ttu-id="517d1-190">Configurare in base all'ambiente e alle necessità specifici</span><span class="sxs-lookup"><span data-stu-id="517d1-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="517d1-191">Rischio di accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-191">Sign-in risk</span></span>|<span data-ttu-id="517d1-192">Livello di rischio</span><span class="sxs-lookup"><span data-stu-id="517d1-192">Risk level</span></span>||<span data-ttu-id="517d1-193">Vedere le informazioni aggiuntive nella tabella seguente</span><span class="sxs-lookup"><span data-stu-id="517d1-193">See the guidance in the following table</span></span>|

<span data-ttu-id="517d1-194">**Rischio di accesso**</span><span class="sxs-lookup"><span data-stu-id="517d1-194">**Sign-in risk**</span></span>

<span data-ttu-id="517d1-195">Applicare le impostazioni in base al livello di protezione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="517d1-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="517d1-196">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-196">Property</span></span>|<span data-ttu-id="517d1-197">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="517d1-197">Level of protection</span></span>|<span data-ttu-id="517d1-198">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-198">Values</span></span>|<span data-ttu-id="517d1-199">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-200">Livello di rischio</span><span class="sxs-lookup"><span data-stu-id="517d1-200">Risk level</span></span>|<span data-ttu-id="517d1-201">Protezione di base</span><span class="sxs-lookup"><span data-stu-id="517d1-201">Baseline</span></span>|<span data-ttu-id="517d1-202">Alto, medio</span><span class="sxs-lookup"><span data-stu-id="517d1-202">High, medium</span></span>|<span data-ttu-id="517d1-203">Controllare entrambi</span><span class="sxs-lookup"><span data-stu-id="517d1-203">Check both</span></span>|
| |<span data-ttu-id="517d1-204">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="517d1-204">Sensitive</span></span>|<span data-ttu-id="517d1-205">Alta, Media, bassa</span><span class="sxs-lookup"><span data-stu-id="517d1-205">High, medium, low</span></span>|<span data-ttu-id="517d1-206">Controllare tutti e tre</span><span class="sxs-lookup"><span data-stu-id="517d1-206">Check all three</span></span>|
| |<span data-ttu-id="517d1-207">Protezione per ambienti altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="517d1-207">Highly regulated</span></span>| |<span data-ttu-id="517d1-208">Lasciare deselezionata per applicare sempre MFA tutte le opzioni</span><span class="sxs-lookup"><span data-stu-id="517d1-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="517d1-209">**Controlli di accesso**</span><span class="sxs-lookup"><span data-stu-id="517d1-209">**Access controls**</span></span>

|<span data-ttu-id="517d1-210">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-210">Type</span></span>|<span data-ttu-id="517d1-211">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-211">Properties</span></span>|<span data-ttu-id="517d1-212">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-212">Values</span></span>|<span data-ttu-id="517d1-213">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-214">Concessione</span><span class="sxs-lookup"><span data-stu-id="517d1-214">Grant</span></span>|<span data-ttu-id="517d1-215">Concedi accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-215">Grant access</span></span>|<span data-ttu-id="517d1-216">True</span><span class="sxs-lookup"><span data-stu-id="517d1-216">True</span></span>|<span data-ttu-id="517d1-217">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="517d1-217">Selected</span></span>|
||<span data-ttu-id="517d1-218">Richiedi MFA</span><span class="sxs-lookup"><span data-stu-id="517d1-218">Require MFA</span></span>|<span data-ttu-id="517d1-219">True</span><span class="sxs-lookup"><span data-stu-id="517d1-219">True</span></span>|<span data-ttu-id="517d1-220">Check</span><span class="sxs-lookup"><span data-stu-id="517d1-220">Check</span></span>|
||<span data-ttu-id="517d1-221">Richiedi dispositivo deve essere contrassegnato come compatibile.</span><span class="sxs-lookup"><span data-stu-id="517d1-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="517d1-222">False</span><span class="sxs-lookup"><span data-stu-id="517d1-222">False</span></span>||
||<span data-ttu-id="517d1-223">Richiedi ibrida Azure Active Directory aggiunti al dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-223">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="517d1-224">False</span><span class="sxs-lookup"><span data-stu-id="517d1-224">False</span></span>||
||<span data-ttu-id="517d1-225">Richiedere l'applicazione client approvata</span><span class="sxs-lookup"><span data-stu-id="517d1-225">Require approved client app</span></span>|<span data-ttu-id="517d1-226">False</span><span class="sxs-lookup"><span data-stu-id="517d1-226">False</span></span>||
||<span data-ttu-id="517d1-227">Richiedi tutti i controlli selezionati</span><span class="sxs-lookup"><span data-stu-id="517d1-227">Require all the selected controls</span></span>|<span data-ttu-id="517d1-228">True</span><span class="sxs-lookup"><span data-stu-id="517d1-228">True</span></span>|<span data-ttu-id="517d1-229">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="517d1-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="517d1-p112">È necessario abilitare questi criteri, fare clic **su**. Inoltre è consigliabile utilizzare lo strumento [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare i criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-p112">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="517d1-232">Bloccare i client che non supportano l'autenticazione moderno</span><span class="sxs-lookup"><span data-stu-id="517d1-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="517d1-p113">Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.</span><span class="sxs-lookup"><span data-stu-id="517d1-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="517d1-235">Scegliere **Azure Active Directory** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="517d1-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="517d1-236">Nella sezione **Sicurezza** scegliere **Accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="517d1-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="517d1-237">Scegliere **Nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-237">Choose **New policy**.</span></span>

<span data-ttu-id="517d1-238">Nelle tabelle seguenti vengono descritte le impostazioni di criteri di accesso condizionale per l'implementazione di questo criterio.</span><span class="sxs-lookup"><span data-stu-id="517d1-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="517d1-239">**Assegnazioni**</span><span class="sxs-lookup"><span data-stu-id="517d1-239">**Assignments**</span></span>

|<span data-ttu-id="517d1-240">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-240">Type</span></span>|<span data-ttu-id="517d1-241">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-241">Properties</span></span>|<span data-ttu-id="517d1-242">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-242">Values</span></span>|<span data-ttu-id="517d1-243">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-244">Utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="517d1-244">Users and groups</span></span>|<span data-ttu-id="517d1-245">Includi</span><span class="sxs-lookup"><span data-stu-id="517d1-245">Include</span></span>|<span data-ttu-id="517d1-246">Seleziona utenti e gruppi - Selezionare il gruppo di sicurezza specifico in cui sono contenuti gli utenti di destinazione</span><span class="sxs-lookup"><span data-stu-id="517d1-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="517d1-247">Iniziare con il gruppo di sicurezza che include utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="517d1-247">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="517d1-248">Exclude</span><span class="sxs-lookup"><span data-stu-id="517d1-248">Exclude</span></span>|<span data-ttu-id="517d1-249">Exception security group; service accounts (app identities) (Gruppo di sicurezza eccezione account del servizio (identità applicazione)</span><span class="sxs-lookup"><span data-stu-id="517d1-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="517d1-250">Appartenenza modificata su base temporanea a seconda delle necessità</span><span class="sxs-lookup"><span data-stu-id="517d1-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="517d1-251">App cloud</span><span class="sxs-lookup"><span data-stu-id="517d1-251">Cloud apps</span></span>|<span data-ttu-id="517d1-252">Includi</span><span class="sxs-lookup"><span data-stu-id="517d1-252">Include</span></span>|<span data-ttu-id="517d1-p114">Selezionare le applicazioni che si desidera applicare per la regola. Ad esempio, selezionare Exchange Online di Office 365</span><span class="sxs-lookup"><span data-stu-id="517d1-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="517d1-255">Condizioni</span><span class="sxs-lookup"><span data-stu-id="517d1-255">Conditions</span></span>|<span data-ttu-id="517d1-256">Configurata</span><span class="sxs-lookup"><span data-stu-id="517d1-256">Configured</span></span>|<span data-ttu-id="517d1-257">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-257">Yes</span></span>|<span data-ttu-id="517d1-258">Configurare le applicazioni Client</span><span class="sxs-lookup"><span data-stu-id="517d1-258">Configure Client apps</span></span>|
|<span data-ttu-id="517d1-259">Applicazioni client</span><span class="sxs-lookup"><span data-stu-id="517d1-259">Client apps</span></span>|<span data-ttu-id="517d1-260">Configurata</span><span class="sxs-lookup"><span data-stu-id="517d1-260">Configured</span></span>|<span data-ttu-id="517d1-261">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-261">Yes</span></span>|<span data-ttu-id="517d1-262">App per dispositivi mobili e i client desktop, gli altri client (selezionare entrambi)</span><span class="sxs-lookup"><span data-stu-id="517d1-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="517d1-263">**Controlli di accesso**</span><span class="sxs-lookup"><span data-stu-id="517d1-263">**Access controls**</span></span>

|<span data-ttu-id="517d1-264">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-264">Type</span></span>|<span data-ttu-id="517d1-265">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-265">Properties</span></span>|<span data-ttu-id="517d1-266">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-266">Values</span></span>|<span data-ttu-id="517d1-267">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-268">Concessione</span><span class="sxs-lookup"><span data-stu-id="517d1-268">Grant</span></span>|<span data-ttu-id="517d1-269">Blocca accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-269">Block access</span></span>|<span data-ttu-id="517d1-270">True</span><span class="sxs-lookup"><span data-stu-id="517d1-270">True</span></span>|<span data-ttu-id="517d1-271">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="517d1-271">Selected</span></span>|
||<span data-ttu-id="517d1-272">Richiedi MFA</span><span class="sxs-lookup"><span data-stu-id="517d1-272">Require MFA</span></span>|<span data-ttu-id="517d1-273">False</span><span class="sxs-lookup"><span data-stu-id="517d1-273">False</span></span>||
||<span data-ttu-id="517d1-274">Richiedi dispositivo deve essere contrassegnato come compatibile.</span><span class="sxs-lookup"><span data-stu-id="517d1-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="517d1-275">False</span><span class="sxs-lookup"><span data-stu-id="517d1-275">False</span></span>||
||<span data-ttu-id="517d1-276">Richiedi ibrida Azure Active Directory aggiunti al dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-276">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="517d1-277">False</span><span class="sxs-lookup"><span data-stu-id="517d1-277">False</span></span>||
||<span data-ttu-id="517d1-278">Richiedere l'applicazione client approvata</span><span class="sxs-lookup"><span data-stu-id="517d1-278">Require approved client app</span></span>|<span data-ttu-id="517d1-279">False</span><span class="sxs-lookup"><span data-stu-id="517d1-279">False</span></span>||
||<span data-ttu-id="517d1-280">Richiedi tutti i controlli selezionati</span><span class="sxs-lookup"><span data-stu-id="517d1-280">Require all the selected controls</span></span>|<span data-ttu-id="517d1-281">True</span><span class="sxs-lookup"><span data-stu-id="517d1-281">True</span></span>|<span data-ttu-id="517d1-282">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="517d1-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="517d1-p115">È necessario abilitare questi criteri, fare clic **su**. Inoltre è consigliabile utilizzare lo strumento [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare i criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-p115">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="517d1-285">Gli utenti ad alto rischio modifica della password</span><span class="sxs-lookup"><span data-stu-id="517d1-285">High risk users must change password</span></span>
<span data-ttu-id="517d1-286">Perché tutti gli account compromessi di utenti a rischio elevato siano obbligati a modificare la password durante l'accesso, è necessario applicare i criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="517d1-286">To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="517d1-287">Eseguire l'accesso al [portale Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) con le credenziali di amministratore e quindi passare alla **Azure Active Directory Identity protezione > criteri utente rischio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="517d1-288">**Assegnazioni**</span><span class="sxs-lookup"><span data-stu-id="517d1-288">**Assignments**</span></span>

|<span data-ttu-id="517d1-289">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-289">Type</span></span>|<span data-ttu-id="517d1-290">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-290">Properties</span></span>|<span data-ttu-id="517d1-291">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-291">Values</span></span>|<span data-ttu-id="517d1-292">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-293">Users</span><span class="sxs-lookup"><span data-stu-id="517d1-293">Users</span></span>|<span data-ttu-id="517d1-294">Includi</span><span class="sxs-lookup"><span data-stu-id="517d1-294">Include</span></span>|<span data-ttu-id="517d1-295">Tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="517d1-295">All users</span></span>|<span data-ttu-id="517d1-296">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="517d1-296">Selected</span></span>|
||<span data-ttu-id="517d1-297">Exclude</span><span class="sxs-lookup"><span data-stu-id="517d1-297">Exclude</span></span>|<span data-ttu-id="517d1-298">Nessuno</span><span class="sxs-lookup"><span data-stu-id="517d1-298">None</span></span>||
|<span data-ttu-id="517d1-299">Condizioni</span><span class="sxs-lookup"><span data-stu-id="517d1-299">Conditions</span></span>|<span data-ttu-id="517d1-300">Rischio utente</span><span class="sxs-lookup"><span data-stu-id="517d1-300">User risk</span></span>|<span data-ttu-id="517d1-301">Alta</span><span class="sxs-lookup"><span data-stu-id="517d1-301">High</span></span>|<span data-ttu-id="517d1-302">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="517d1-302">Selected</span></span>|

<span data-ttu-id="517d1-303">**Controlli**</span><span class="sxs-lookup"><span data-stu-id="517d1-303">**Controls**</span></span>

| <span data-ttu-id="517d1-304">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-304">Type</span></span> | <span data-ttu-id="517d1-305">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-305">Properties</span></span> | <span data-ttu-id="517d1-306">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-306">Values</span></span>                  | <span data-ttu-id="517d1-307">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="517d1-308">Access</span><span class="sxs-lookup"><span data-stu-id="517d1-308">Access</span></span>     | <span data-ttu-id="517d1-309">Consenti l'accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-309">Allow access</span></span>            | <span data-ttu-id="517d1-310">True</span><span class="sxs-lookup"><span data-stu-id="517d1-310">True</span></span>  |
|      | <span data-ttu-id="517d1-311">Accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-311">Access</span></span>     | <span data-ttu-id="517d1-312">Richiedi modifica password</span><span class="sxs-lookup"><span data-stu-id="517d1-312">Require password change</span></span> | <span data-ttu-id="517d1-313">True</span><span class="sxs-lookup"><span data-stu-id="517d1-313">True</span></span>  |

<span data-ttu-id="517d1-314">**Revisione:** non applicabile</span><span class="sxs-lookup"><span data-stu-id="517d1-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="517d1-p116">È necessario abilitare questi criteri, fare clic **su**. Inoltre è consigliabile utilizzare lo strumento [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare i criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-p116">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="517d1-317">Definire criteri di protezione delle app</span><span class="sxs-lookup"><span data-stu-id="517d1-317">Define app protection policies</span></span>
<span data-ttu-id="517d1-p117">Definiscono criteri di protezione App quali App possono e le azioni che possa rispondere con i dati dell'organizzazione. Creare app Intune criteri di protezione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="517d1-p117">App protection policies define which apps are allowed and the actions they can take with your organization data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="517d1-320">Creare un criterio per ogni piattaforma:</span><span class="sxs-lookup"><span data-stu-id="517d1-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="517d1-321">iOS</span><span class="sxs-lookup"><span data-stu-id="517d1-321">iOS</span></span>
- <span data-ttu-id="517d1-322">Android</span><span class="sxs-lookup"><span data-stu-id="517d1-322">Android</span></span>
- <span data-ttu-id="517d1-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="517d1-323">Windows 10</span></span>

<span data-ttu-id="517d1-p118">Per creare un nuovo criterio di protezione di applicazioni, eseguire l'accesso al portale dei Microsoft Azure con le credenziali di amministrazione e quindi passare alla **App per dispositivi mobili > Criteri di protezione App**. Fare clic su **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Click **Add a policy**.</span></span>

<span data-ttu-id="517d1-p119">Esistono lievi differenze nella protezione app opzioni dei criteri tra iOS e Android. Il criterio di seguito è riportato in modo specifico per Android. Utilizzare come guida per gli altri criteri di.</span><span class="sxs-lookup"><span data-stu-id="517d1-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="517d1-329">L'elenco delle App consigliato include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="517d1-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="517d1-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="517d1-330">PowerPoint</span></span>
- <span data-ttu-id="517d1-331">Excel</span><span class="sxs-lookup"><span data-stu-id="517d1-331">Excel</span></span>
- <span data-ttu-id="517d1-332">Word</span><span class="sxs-lookup"><span data-stu-id="517d1-332">Word</span></span>
- <span data-ttu-id="517d1-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="517d1-333">Microsoft Teams</span></span>
- <span data-ttu-id="517d1-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="517d1-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="517d1-335">Visualizzatore di Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="517d1-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="517d1-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="517d1-336">OneDrive</span></span>
- <span data-ttu-id="517d1-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="517d1-337">OneNote</span></span>
- <span data-ttu-id="517d1-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="517d1-338">Outlook</span></span>

<span data-ttu-id="517d1-339">Nelle tabelle seguenti vengono descrivono le impostazioni consigliate:</span><span class="sxs-lookup"><span data-stu-id="517d1-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="517d1-340">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-340">Type</span></span>|<span data-ttu-id="517d1-341">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-341">Properties</span></span>|<span data-ttu-id="517d1-342">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-342">Values</span></span>|<span data-ttu-id="517d1-343">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-344">Rilocazione dati</span><span class="sxs-lookup"><span data-stu-id="517d1-344">Data relocation</span></span>|<span data-ttu-id="517d1-345">Impedisci backup in Android</span><span class="sxs-lookup"><span data-stu-id="517d1-345">Prevent Android backup</span></span>|<span data-ttu-id="517d1-346">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-346">Yes</span></span>|<span data-ttu-id="517d1-347">In iOS viene effettua una chiamata in iTunes e iCloud</span><span class="sxs-lookup"><span data-stu-id="517d1-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="517d1-348">Consenti all'app di trasferire i dati ad altre app</span><span class="sxs-lookup"><span data-stu-id="517d1-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="517d1-349">App gestite da criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-349">Policy managed apps</span></span>||
||<span data-ttu-id="517d1-350">Consenti all'app di ricevere i dati da altre app</span><span class="sxs-lookup"><span data-stu-id="517d1-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="517d1-351">App gestite da criteri</span><span class="sxs-lookup"><span data-stu-id="517d1-351">Policy managed apps</span></span>||
||<span data-ttu-id="517d1-352">Impedisci Salva con nome</span><span class="sxs-lookup"><span data-stu-id="517d1-352">Prevent "Save As"</span></span>|<span data-ttu-id="517d1-353">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-353">Yes</span></span>||
||<span data-ttu-id="517d1-354">Selezionare i servizi di archiviazione in cui è possibile salvare i dati aziendali</span><span class="sxs-lookup"><span data-stu-id="517d1-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="517d1-355">OneDrive for Business, SharePoint</span><span class="sxs-lookup"><span data-stu-id="517d1-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="517d1-356">Limita le operazioni taglia, copia e incolla con le altre app</span><span class="sxs-lookup"><span data-stu-id="517d1-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="517d1-357">Applicazioni gestiti da criteri con Incolla in</span><span class="sxs-lookup"><span data-stu-id="517d1-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="517d1-358">Limita il contenuto Web per la visualizzazione in Managed Browser</span><span class="sxs-lookup"><span data-stu-id="517d1-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="517d1-359">No</span><span class="sxs-lookup"><span data-stu-id="517d1-359">No</span></span>||
||<span data-ttu-id="517d1-360">Crittografa dati app</span><span class="sxs-lookup"><span data-stu-id="517d1-360">Encrypt app data</span></span>|<span data-ttu-id="517d1-361">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-361">Yes</span></span>|<span data-ttu-id="517d1-362">In iOS selezionare l'opzione Quando il dispositivo è bloccato</span><span class="sxs-lookup"><span data-stu-id="517d1-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="517d1-363">Disattivare la crittografia app quando è abilitata la periferica</span><span class="sxs-lookup"><span data-stu-id="517d1-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="517d1-364">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-364">Yes</span></span>|<span data-ttu-id="517d1-365">Disabilitare questa impostazione per evitare di crittografia doppia</span><span class="sxs-lookup"><span data-stu-id="517d1-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="517d1-366">Disabilita sincronizzazione contatti</span><span class="sxs-lookup"><span data-stu-id="517d1-366">Disable contacts sync</span></span>|<span data-ttu-id="517d1-367">No</span><span class="sxs-lookup"><span data-stu-id="517d1-367">No</span></span>||
||<span data-ttu-id="517d1-368">Disattiva la stampa</span><span class="sxs-lookup"><span data-stu-id="517d1-368">Disable printing</span></span>|<span data-ttu-id="517d1-369">No</span><span class="sxs-lookup"><span data-stu-id="517d1-369">No</span></span>||
|<span data-ttu-id="517d1-370">Accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-370">Access</span></span>|<span data-ttu-id="517d1-371">Richiedi PIN per l'accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-371">Require PIN for access</span></span>|<span data-ttu-id="517d1-372">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-372">Yes</span></span>||
||<span data-ttu-id="517d1-373">Selezionare tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-373">Select Type</span></span>|<span data-ttu-id="517d1-374">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="517d1-374">Numeric</span></span>||
||<span data-ttu-id="517d1-375">Consenti PIN semplice</span><span class="sxs-lookup"><span data-stu-id="517d1-375">Allow simple PIN</span></span>|<span data-ttu-id="517d1-376">No</span><span class="sxs-lookup"><span data-stu-id="517d1-376">No</span></span>||
||<span data-ttu-id="517d1-377">Lunghezza PIN</span><span class="sxs-lookup"><span data-stu-id="517d1-377">PIN length</span></span>|<span data-ttu-id="517d1-378">6</span><span class="sxs-lookup"><span data-stu-id="517d1-378">6</span></span>||
||<span data-ttu-id="517d1-379">Consenti impronta digitale anziché PIN</span><span class="sxs-lookup"><span data-stu-id="517d1-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="517d1-380">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-380">Yes</span></span>||
||<span data-ttu-id="517d1-381">Disattivare app PIN quando viene gestito PIN del dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="517d1-382">Sì</span><span class="sxs-lookup"><span data-stu-id="517d1-382">Yes</span></span>||
||<span data-ttu-id="517d1-383">Richiedi credenziali aziendali per l'accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-383">Require corporate credentials for access</span></span>|<span data-ttu-id="517d1-384">No</span><span class="sxs-lookup"><span data-stu-id="517d1-384">No</span></span>||
||<span data-ttu-id="517d1-385">Controlla di nuovo i requisiti di accesso dopo (minuti)</span><span class="sxs-lookup"><span data-stu-id="517d1-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="517d1-386">30</span><span class="sxs-lookup"><span data-stu-id="517d1-386">30</span></span>||
||<span data-ttu-id="517d1-387">Blocca acquisizione schermo e Assistente per Android</span><span class="sxs-lookup"><span data-stu-id="517d1-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="517d1-388">No</span><span class="sxs-lookup"><span data-stu-id="517d1-388">No</span></span>|<span data-ttu-id="517d1-389">In iOS questa opzione non è disponibile</span><span class="sxs-lookup"><span data-stu-id="517d1-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="517d1-390">Requisiti di protezione di accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-390">Sign-in security requirements</span></span>|<span data-ttu-id="517d1-391">PIN numero massimo tentativi</span><span class="sxs-lookup"><span data-stu-id="517d1-391">Max PIN attempts</span></span>|<span data-ttu-id="517d1-392">5</span><span class="sxs-lookup"><span data-stu-id="517d1-392">5</span></span>|<span data-ttu-id="517d1-393">Reimpostare il Pin</span><span class="sxs-lookup"><span data-stu-id="517d1-393">Reset Pin</span></span>|
||<span data-ttu-id="517d1-394">Periodo di prova offline</span><span class="sxs-lookup"><span data-stu-id="517d1-394">Offline grace period</span></span>|<span data-ttu-id="517d1-395">720</span><span class="sxs-lookup"><span data-stu-id="517d1-395">720</span></span>|<span data-ttu-id="517d1-396">Blocca accesso</span><span class="sxs-lookup"><span data-stu-id="517d1-396">Block access</span></span>|
||<span data-ttu-id="517d1-397">Intervallo offline (giorni) prima della cancellazione dei dati dell'app</span><span class="sxs-lookup"><span data-stu-id="517d1-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="517d1-398">90</span><span class="sxs-lookup"><span data-stu-id="517d1-398">90</span></span>|<span data-ttu-id="517d1-399">Cancellazione dati</span><span class="sxs-lookup"><span data-stu-id="517d1-399">Wipe data</span></span>|
||<span data-ttu-id="517d1-400">Dispositivi Jailbroken/radice</span><span class="sxs-lookup"><span data-stu-id="517d1-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="517d1-401">Cancellazione dati</span><span class="sxs-lookup"><span data-stu-id="517d1-401">Wipe data</span></span>|

<span data-ttu-id="517d1-p120">Al termine, ricordarsi di fare clic su "Crea". Ripetere i passaggi precedenti e sostituire la piattaforma selezionata (menu a discesa) con iOS. In questo modo vengono creati due criteri per le app, quindi dopo aver creato i criteri, assegnare i gruppi ai criteri e distribuirli.</span><span class="sxs-lookup"><span data-stu-id="517d1-p120">When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="517d1-405">Per modificare i criteri e assegnare i criteri per gli utenti, vedere [come creare e assegnare i criteri di protezione di applicazioni](https://docs.microsoft.com/intune/app-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="517d1-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="517d1-406">Richiedi App approvate</span><span class="sxs-lookup"><span data-stu-id="517d1-406">Require approved apps</span></span>
<span data-ttu-id="517d1-407">Per richiedere l'App approvate:</span><span class="sxs-lookup"><span data-stu-id="517d1-407">To require approved apps:</span></span>

1. <span data-ttu-id="517d1-p121">Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.</span><span class="sxs-lookup"><span data-stu-id="517d1-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="517d1-410">Scegliere **Azure Active Directory** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="517d1-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="517d1-411">Nella sezione **Sicurezza** scegliere **Accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="517d1-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="517d1-412">Scegliere **Nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="517d1-413">Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="517d1-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="517d1-414">Scegliere **App cloud**.</span><span class="sxs-lookup"><span data-stu-id="517d1-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="517d1-p122">Scegliere **Seleziona App**, selezionare l'App desiderata nell'elenco di **applicazioni basate su Cloud** . Ad esempio, selezionare Exchange Online di Office 365. Fare clic su **Seleziona** e **Fine**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="517d1-418">Scegliere **Concedi** nella sezione **Controlli di accesso**.</span><span class="sxs-lookup"><span data-stu-id="517d1-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="517d1-p123">Scegliere **concedere l'accesso**, selezionare **Richiedi approvato dall'applicazione client**.  Per più controlli, selezionare **Richiedi i controlli selezionati**, quindi scegliere **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p123">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="517d1-421">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="517d1-421">Click **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="517d1-422">Definire criteri di conformità di dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-422">Define device compliance policies</span></span>

<span data-ttu-id="517d1-p124">Criteri di conformità dispositivo definiscono i requisiti dei dispositivi devono rispettare per poter essere contrassegnato come compatibile. Creare criteri di conformità dall'interno del portale Azure Intune dispositivo.</span><span class="sxs-lookup"><span data-stu-id="517d1-p124">Device compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="517d1-425">Creare un criterio per ogni piattaforma:</span><span class="sxs-lookup"><span data-stu-id="517d1-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="517d1-426">Android</span><span class="sxs-lookup"><span data-stu-id="517d1-426">Android</span></span>
- <span data-ttu-id="517d1-427">Enterprise Android</span><span class="sxs-lookup"><span data-stu-id="517d1-427">Android enterprise</span></span>
- <span data-ttu-id="517d1-428">iOS</span><span class="sxs-lookup"><span data-stu-id="517d1-428">iOS</span></span>
- <span data-ttu-id="517d1-429">Mac OS</span><span class="sxs-lookup"><span data-stu-id="517d1-429">macOS</span></span>
- <span data-ttu-id="517d1-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="517d1-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="517d1-431">Windows 8.1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="517d1-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="517d1-432">Windows 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="517d1-432">Windows 10 and later</span></span>

<span data-ttu-id="517d1-p125">Per creare criteri di conformità dispositivo, eseguire l'accesso al portale dei Microsoft Azure con le credenziali di amministrazione e quindi passare alla **Intune > conformità dispositivo**. Fare clic su **Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Click **Create policy**.</span></span>

<span data-ttu-id="517d1-435">Le impostazioni riportate di seguito sono consigliate per Windows 10.</span><span class="sxs-lookup"><span data-stu-id="517d1-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="517d1-436">**Integrità dispositivo: le regole di valutazione di Windows integrità attestazione servizio**</span><span class="sxs-lookup"><span data-stu-id="517d1-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="517d1-437">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-437">Properties</span></span>|<span data-ttu-id="517d1-438">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-438">Values</span></span>|<span data-ttu-id="517d1-439">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="517d1-440">Richiedi BitLocker</span><span class="sxs-lookup"><span data-stu-id="517d1-440">Require BitLocker</span></span>|<span data-ttu-id="517d1-441">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-441">Require</span></span>||
|<span data-ttu-id="517d1-442">Richiedi avvio sicura sia abilitata nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="517d1-443">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-443">Require</span></span>||
|<span data-ttu-id="517d1-444">Richiedere l'integrità del codice</span><span class="sxs-lookup"><span data-stu-id="517d1-444">Require code integrity</span></span>|<span data-ttu-id="517d1-445">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-445">Require</span></span>||


<span data-ttu-id="517d1-446">**Proprietà del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="517d1-446">**Device properties**</span></span>

|<span data-ttu-id="517d1-447">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-447">Type</span></span>|<span data-ttu-id="517d1-448">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-448">Properties</span></span>|<span data-ttu-id="517d1-449">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-449">Values</span></span>|<span data-ttu-id="517d1-450">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-451">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="517d1-451">Operating system version</span></span>|<span data-ttu-id="517d1-452">Tutto</span><span class="sxs-lookup"><span data-stu-id="517d1-452">All</span></span>|<span data-ttu-id="517d1-453">Non configurata</span><span class="sxs-lookup"><span data-stu-id="517d1-453">Not configured</span></span>||

<span data-ttu-id="517d1-p126">Tutti i criteri descritti in precedenza vengono considerati distribuiti se assegnati a gruppi di utenti. Creare quindi criteri (al momento del salvataggio) o successivamente selezionando Gestisci distribuzione nella sezione Criteri (stesso livello di Aggiungi).</span><span class="sxs-lookup"><span data-stu-id="517d1-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).</span></span>

<span data-ttu-id="517d1-456">**Protezione del sistema**</span><span class="sxs-lookup"><span data-stu-id="517d1-456">**System security**</span></span>

|<span data-ttu-id="517d1-457">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-457">Type</span></span>|<span data-ttu-id="517d1-458">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-458">Properties</span></span>|<span data-ttu-id="517d1-459">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-459">Values</span></span>|<span data-ttu-id="517d1-460">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-461">Password</span><span class="sxs-lookup"><span data-stu-id="517d1-461">Password</span></span>|<span data-ttu-id="517d1-462">Richiedere una password per sbloccare i dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="517d1-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="517d1-463">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-463">Require</span></span>||
||<span data-ttu-id="517d1-464">Password semplice</span><span class="sxs-lookup"><span data-stu-id="517d1-464">Simple passwords</span></span>|<span data-ttu-id="517d1-465">Blocco</span><span class="sxs-lookup"><span data-stu-id="517d1-465">Block</span></span>||
||<span data-ttu-id="517d1-466">Tipo di password</span><span class="sxs-lookup"><span data-stu-id="517d1-466">Password type</span></span>|<span data-ttu-id="517d1-467">Impostazioni predefinite dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-467">Device default</span></span>||
||<span data-ttu-id="517d1-468">Lunghezza minima password</span><span class="sxs-lookup"><span data-stu-id="517d1-468">Minimum password length</span></span>|<span data-ttu-id="517d1-469">6</span><span class="sxs-lookup"><span data-stu-id="517d1-469">6</span></span>||
||<span data-ttu-id="517d1-470">Numero massimo di minuti di inattività prima che la password è obbligatoria</span><span class="sxs-lookup"><span data-stu-id="517d1-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="517d1-471">15 </span><span class="sxs-lookup"><span data-stu-id="517d1-471">15</span></span>|<span data-ttu-id="517d1-p127">Questa impostazione è supportata per le versioni Android 4.0 e versioni successive o KNOX 4.0 e versioni successive. Per i dispositivi iOS, è supportato per iOS 8.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="517d1-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above.</span></span>|
||<span data-ttu-id="517d1-474">Scadenza password (giorni)</span><span class="sxs-lookup"><span data-stu-id="517d1-474">Password expiration (days)</span></span>|<span data-ttu-id="517d1-475">41</span><span class="sxs-lookup"><span data-stu-id="517d1-475">41</span></span>||
||<span data-ttu-id="517d1-476">Numero di password precedente per impedire il riutilizzo</span><span class="sxs-lookup"><span data-stu-id="517d1-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="517d1-477">5</span><span class="sxs-lookup"><span data-stu-id="517d1-477">5</span></span>||
||<span data-ttu-id="517d1-478">Richiedi password quando dispositivo restituisce da uno stato inattivo (Mobile e Holographic)</span><span class="sxs-lookup"><span data-stu-id="517d1-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="517d1-479">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-479">Require</span></span>|<span data-ttu-id="517d1-480">Disponibile per Windows 10 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="517d1-480">Available for Windows 10 and later.</span></span>|
|<span data-ttu-id="517d1-481">Crittografia</span><span class="sxs-lookup"><span data-stu-id="517d1-481">Encryption</span></span>|<span data-ttu-id="517d1-482">Crittografia di archiviazione dei dati nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="517d1-482">Encryption of data storage on device</span></span>|<span data-ttu-id="517d1-483">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-483">Require</span></span>||
|<span data-ttu-id="517d1-484">Sicurezza dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="517d1-484">Device Security</span></span>|<span data-ttu-id="517d1-485">Firewall</span><span class="sxs-lookup"><span data-stu-id="517d1-485">Firewall</span></span>|<span data-ttu-id="517d1-486">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-486">Require</span></span>||
||<span data-ttu-id="517d1-487">Antivirus</span><span class="sxs-lookup"><span data-stu-id="517d1-487">Antivirus</span></span>|<span data-ttu-id="517d1-488">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-488">Require</span></span>||
||<span data-ttu-id="517d1-489">Antispyware</span><span class="sxs-lookup"><span data-stu-id="517d1-489">Antispyware</span></span>|<span data-ttu-id="517d1-490">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-490">Require</span></span>|<span data-ttu-id="517d1-491">Questa impostazione richiede una soluzione di Anti-Spyware registrata in Centro protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="517d1-491">This setting requires an Anti-Spyware solution registered with Windows Security Center.</span></span>|
|<span data-ttu-id="517d1-492">Defender</span><span class="sxs-lookup"><span data-stu-id="517d1-492">Defender</span></span>|<span data-ttu-id="517d1-493">Windows Defender Antimalware</span><span class="sxs-lookup"><span data-stu-id="517d1-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="517d1-494">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-494">Require</span></span>||
||<span data-ttu-id="517d1-495">Versione minima di Windows Defender Antimalware</span><span class="sxs-lookup"><span data-stu-id="517d1-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="517d1-p128">Supportata solo per Windows 10 desktop. Microsoft non consiglia di versioni più di cinque dietro dalla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="517d1-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version.</span></span>|
||<span data-ttu-id="517d1-498">Windows Defender Antimalware firma aggiornato</span><span class="sxs-lookup"><span data-stu-id="517d1-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="517d1-499">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-499">Require</span></span>||
||<span data-ttu-id="517d1-500">Protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="517d1-500">Real-time protection</span></span>|<span data-ttu-id="517d1-501">Require</span><span class="sxs-lookup"><span data-stu-id="517d1-501">Require</span></span>|<span data-ttu-id="517d1-502">Supportata solo per Windows 10 desktop.</span><span class="sxs-lookup"><span data-stu-id="517d1-502">Only supported for Windows 10 desktop.</span></span>|

<span data-ttu-id="517d1-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="517d1-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="517d1-504">Tipo</span><span class="sxs-lookup"><span data-stu-id="517d1-504">Type</span></span>|<span data-ttu-id="517d1-505">Proprietà</span><span class="sxs-lookup"><span data-stu-id="517d1-505">Properties</span></span>|<span data-ttu-id="517d1-506">Valori</span><span class="sxs-lookup"><span data-stu-id="517d1-506">Values</span></span>|<span data-ttu-id="517d1-507">Note</span><span class="sxs-lookup"><span data-stu-id="517d1-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="517d1-508">Regole di protezione di Windows Defender avanzate rischio</span><span class="sxs-lookup"><span data-stu-id="517d1-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="517d1-509">Richiedono il dispositivo sia in o sotto il punteggio di rischio automatica</span><span class="sxs-lookup"><span data-stu-id="517d1-509">Require the device to be at or under the machine risk score</span></span>|<span data-ttu-id="517d1-510">Medio</span><span class="sxs-lookup"><span data-stu-id="517d1-510">Medium</span></span>||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="517d1-511">Richiedi PC compatibile con (ma non Compatible telefoni e Tablet)</span><span class="sxs-lookup"><span data-stu-id="517d1-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="517d1-p129">Prima di aggiungere un criterio per richiedere PC compatibile, assicurarsi di registrare i dispositivi per la gestione in Intune. È consigliabile utilizzare l'autenticazione a più fattori dopo aver registrato i dispositivi in Intune per verificare che il dispositivo non è in possesso dell'utente desiderato.</span><span class="sxs-lookup"><span data-stu-id="517d1-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="517d1-514">Per richiedere PC compatibile:</span><span class="sxs-lookup"><span data-stu-id="517d1-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="517d1-p130">Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.</span><span class="sxs-lookup"><span data-stu-id="517d1-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="517d1-517">Scegliere **Azure Active Directory** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="517d1-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="517d1-518">Nella sezione **Sicurezza** scegliere **Accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="517d1-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="517d1-519">Scegliere **Nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="517d1-520">Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="517d1-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="517d1-521">Scegliere **App cloud**.</span><span class="sxs-lookup"><span data-stu-id="517d1-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="517d1-p131">Scegliere **Seleziona App**, selezionare l'App desiderata nell'elenco di **applicazioni basate su Cloud** . Ad esempio, selezionare Exchange Online di Office 365. Fare clic su **Seleziona** e **Fine**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="517d1-p132">Per richiedere compatibile con PC, ma non Compatible telefoni e Tablet, scegliere **dispositivo piattaforme**e **condizioni** . Scegliere "piattaforme seleziona dispositivo" e selezionare **Windows** e **Mac OS**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose "Select device platforms" and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="517d1-527">Scegliere **Concedi** nella sezione **Controlli di accesso**.</span><span class="sxs-lookup"><span data-stu-id="517d1-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="517d1-p133">Scegliere **concedere l'accesso**, selezionare **Richiedi dispositivo deve essere contrassegnato come compatibile**.  Per più controlli, selezionare **Richiedi tutti i controlli selezionati**, quindi scegliere **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p133">Choose **Grant access**, select **Require device to be marked as compliant**.  For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="517d1-530">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="517d1-530">Click **Create**.</span></span>

<span data-ttu-id="517d1-p134">L'obiettivo è richiedere compatibile con PC *e* dispositivi mobili, non selezionare le piattaforme. In questo modo conforme per tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="517d1-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliant for all devices.</span></span> 




## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="517d1-533">Richiedi compatibile con PC *e* dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="517d1-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="517d1-534">Per richiedere la conformità per tutti i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="517d1-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="517d1-p135">Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.</span><span class="sxs-lookup"><span data-stu-id="517d1-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="517d1-537">Scegliere **Azure Active Directory** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="517d1-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="517d1-538">Nella sezione **Sicurezza** scegliere **Accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="517d1-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="517d1-539">Scegliere **Nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="517d1-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="517d1-540">Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="517d1-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="517d1-541">Scegliere **App cloud**.</span><span class="sxs-lookup"><span data-stu-id="517d1-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="517d1-p136">Scegliere **Seleziona App**, selezionare l'App desiderata nell'elenco di **applicazioni basate su Cloud** . Ad esempio, selezionare Exchange Online di Office 365. Fare clic su **Seleziona** e **Fine**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="517d1-545">Scegliere **Concedi** nella sezione **Controlli di accesso**.</span><span class="sxs-lookup"><span data-stu-id="517d1-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="517d1-p137">Scegliere **concedere l'accesso**, selezionare **Richiedi dispositivo deve essere contrassegnato come compatibile**. Per più controlli, selezionare **Richiedi tutti i controlli selezionati**, quindi scegliere **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="517d1-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="517d1-548">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="517d1-548">Click **Create**.</span></span>

<span data-ttu-id="517d1-p138">Quando si crea il criterio, non selezionare le piattaforme. In questo modo compatibile con dispositivi.</span><span class="sxs-lookup"><span data-stu-id="517d1-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="517d1-551">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="517d1-551">Next steps</span></span>

<span data-ttu-id="517d1-552">[Learn about policy recommendations for securing email](secure-email-recommended-policies.md) (Informazioni sui criteri consigliati per la protezione della posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="517d1-552">[Learn about policy recommendations for securing email](secure-email-recommended-policies.md)</span></span>
