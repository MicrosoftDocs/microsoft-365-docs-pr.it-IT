---
title: 'Passaggio 1: pianificazione per utenti e gruppi'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Pianificare il set di utenti e gruppi che lavoreranno per l'organizzazione.
ms.openlocfilehash: c74ff672ce84a5609c11eb4fa7a0405d350349ab
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553295"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="1ec0d-103">Passaggio 1: pianificazione per utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="1ec0d-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="1ec0d-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1ec0d-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="1ec0d-p101">Questo passaggio consente di creare un'infrastruttura di gestione delle identità che combina utenti, gruppi e appartenenza a gruppi con caratteristiche di sicurezza nella configurazione corretta. In questo modo è possibile:</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="1ec0d-107">Mantenere il controllo su chi accede alle risorse nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="1ec0d-108">Proteggere l'accesso con i controlli che assicurano delle forti garanzie di identità (gli utenti sono chi dicono di essere) e l'accesso da dispositivi sicuri.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="1ec0d-109">Effettuare il provisioning delle risorse nell'ambiente con le autorizzazioni adeguate per ridurre i rischi di danni e perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="1ec0d-110">Monitorare l'ambiente per individuare comportamenti anomali degli utenti e intervenire automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="1ec0d-111">Pianificare il provider di identità primaria</span><span class="sxs-lookup"><span data-stu-id="1ec0d-111">Plan your primary identity provider</span></span>

<span data-ttu-id="1ec0d-p102">Per creare l'infrastruttura di gestione delle identità, è necessario designare un provider di identità primaria. Questo servizio consente di archiviare gli account utente e i loro attributi, i gruppi e le loro appartenenze e supporta l'amministrazione in corso.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="1ec0d-114">Quando un'organizzazione utilizza Microsoft 365 Enterprise, il provider di identità primaria può essere:</span><span class="sxs-lookup"><span data-stu-id="1ec0d-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="1ec0d-115">**Active Directory Domain Services**, un provider di identità Intranet ospitato su computer che eseguono Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-115">**Active Directory Domain Services (AD DS)**, an intranet identity provider hosted on computers running Windows Server.</span></span> <span data-ttu-id="1ec0d-116">Questa opzione viene generalmente usata dalle organizzazioni che possiedono un provider di identità locale esistente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-116">This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="1ec0d-117">**Azure Active Directory (Azure AD**), un'identità come servizio (IDaaS) basata sul cloud che offre un'ampia gamma di funzionalità per gestire e proteggere l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-117">**Azure Active Directory (Azure AD)**, a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment.</span></span> <span data-ttu-id="1ec0d-118">Questa opzione viene generalmente usata dalle organizzazioni che non dispongono di un'infrastruttura locale esistente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-118">This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="1ec0d-119">Se l'organizzazione dispone di un provider di identità locale esistente, non è necessario sincronizzare gli account e i gruppi utente da AD DS ad Azure AD per fornire un accesso più semplice ai servizi basati sul cloud di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-119">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from Active Directory Domain Services (AD DS) to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="1ec0d-120">È anche possibile usare Azure AD per creare e gestire gruppi presenti solo nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-120">You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="1ec0d-121">Una volta impostati gli utenti e i gruppi in Azure AD, è possibile:</span><span class="sxs-lookup"><span data-stu-id="1ec0d-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="1ec0d-122">Gestire tutti gli account di Azure AD per tutte le applicazioni cloud.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="1ec0d-123">Utilizzare lo stesso set di controlli per proteggere l'accesso alle applicazioni all'interno dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="1ec0d-124">Collaborare con partner esterni.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="1ec0d-125">Monitorare comportamenti anomali degli account, come per esempio tentativi sospetti di accesso, per poi intervenire automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="1ec0d-126">Seguire le istruzioni nelle prossime due sezioni per pianificare e implementare gli account e i gruppi utente.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="1ec0d-127">Categorizzare gli utenti</span><span class="sxs-lookup"><span data-stu-id="1ec0d-127">Categorize your users</span></span>
<span data-ttu-id="1ec0d-p106">Gli utenti nelle organizzazioni possono essere categorizzati in molti modi. Per esempio, alcuni sono dipendenti e hanno un contratto permanente. Altri sono fornitori, terzisti o partner con un contratto temporaneo. Altri ancora sono utenti esterni che non dispongono di un account utente, ma che devono avere un accesso garantito a servizi e risorse specifiche per supportare l'interazione e la collaborazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="1ec0d-133">Gli account tenant rappresentano gli utenti all'interno dell'organizzazione con la licenza per i servizi cloud</span><span class="sxs-lookup"><span data-stu-id="1ec0d-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="1ec0d-134">Gli account Business to Business (B2B) rappresentano gli utenti esterni all'organizzazione che vengono invitati a collaborare.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="1ec0d-p107">È consigliabile tener conto dei tipi di utente dell'organizzazione. Come sono raggruppati? Per esempio, è possibile raggruppare gli utenti in base alle funzioni di alto livello o all'obiettivo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="1ec0d-p108">Inoltre, alcuni servizi cloud possono essere condivisi al di fuori dell'organizzazione senza alcun account utente. È necessario identificare anche questi gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a><span data-ttu-id="1ec0d-140">Pianificare i gruppi di Active Directory Domain Services e Azure AD</span><span class="sxs-lookup"><span data-stu-id="1ec0d-140">Plan for AD DS and Azure AD groups</span></span>

<span data-ttu-id="1ec0d-p109">È possibile utilizzare i gruppi in Azure AD in molteplici modi che semplificano la gestione dell'ambiente cloud. Per esempio, per i gruppi di Azure AD è possibile:</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="1ec0d-143">Usare la licenza basata su gruppo per assegnare automaticamente le licenze per Office 365 ed Enterprise Mobility + Security (EMS) agli account utente appena vengono aggiunti in Azure AD o sincronizzati da Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from AD DS.</span></span> 
- <span data-ttu-id="1ec0d-144">Aggiungere account utente a gruppi specifici in modo dinamico in base agli attributi dell'account utente, come per esempio il reparto.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="1ec0d-145">Effettuare automaticamente il provisioning degli utenti per le applicazioni Software as a Service (SaaS) e proteggere l'accesso a tali applicazioni con l'autenticazione a più fattori e altre regole di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="1ec0d-p110">Effettuare il provisioning delle autorizzazioni e dei livelli di accesso per i siti del team di SharePoint Online. I gruppi di Azure AD possono essere utilizzati anche con i criteri di Azure Information Protection per proteggere i file con crittografia e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="1ec0d-148">Risultati</span><span class="sxs-lookup"><span data-stu-id="1ec0d-148">Results</span></span>

<span data-ttu-id="1ec0d-149">Dopo aver completato questo passaggio, si ottiene quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1ec0d-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="1ec0d-150">Un elenco degli account utente in Azure AD che corrispondono ai dipendenti dell'organizzazione, a fornitori, terzisti e partner esterni che collaborano con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="1ec0d-151">Un set di gruppi e la loro relativa appartenenza in Azure AD che riflette dei set logici di account utente e altri gruppi per il provisioning automatico delle licenze delle impostazioni di sicurezza per i servizi cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="1ec0d-152">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-user-groups) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>

<span data-ttu-id="1ec0d-153">Dopo avere creato gli utenti e i gruppi di Azure AD, è possibile iniziare ad assegnare le licenze e a usare Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ec0d-153">Once your Azure AD users and groups are created, you can start assigning licenses and using Exchange Online.</span></span> <span data-ttu-id="1ec0d-154">Per implementare Exchange Online per gli utenti, vedere [Distribuire Exchange Online per Microsoft 365 Enterprise](exchangeonline-workload.md).</span><span class="sxs-lookup"><span data-stu-id="1ec0d-154">To roll out Exchange Online to your users, see [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="1ec0d-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1ec0d-155">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="1ec0d-156">Proteggere le identità con privilegi</span><span class="sxs-lookup"><span data-stu-id="1ec0d-156">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |

