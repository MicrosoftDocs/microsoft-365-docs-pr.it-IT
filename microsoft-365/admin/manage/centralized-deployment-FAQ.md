---
title: Domande frequenti sulla distribuzione centralizzata
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Leggere le risposte alle domande frequenti sulla distribuzione centralizzata dall'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 9f4841508701d4dd5878e99fcc51a436bc5824e2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915471"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="87b05-103">Domande frequenti sulla distribuzione centralizzata</span><span class="sxs-lookup"><span data-stu-id="87b05-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="87b05-104">La distribuzione centralizzata è il modo consigliato per un amministratore di Office 365 per distribuire componenti aggiuntivi di Office (Word, Excel, PowerPoint e Outlook) a utenti e gruppi all'interno di un'organizzazione, purché l'organizzazione soddisfi tutti i requisiti per l'utilizzo della distribuzione centralizzata, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="87b05-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="87b05-105">Come è possibile sapere se l'organizzazione è impostata per la distribuzione centralizzata?</span><span class="sxs-lookup"><span data-stu-id="87b05-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="87b05-106">La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino Microsoft 365 Apps for enterprise (e siano connessi a Office con le credenziali di accesso dell'organizzazione) e che le cassette postali di Exchange Online siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="87b05-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="87b05-107">La directory di sottoscrizione deve essere in Azure Active Directory o federata.</span><span class="sxs-lookup"><span data-stu-id="87b05-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="87b05-108">La distribuzione centralizzata è supportata solo per le cassette postali online.</span><span class="sxs-lookup"><span data-stu-id="87b05-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="87b05-109">Non supporta la distribuzione alle cassette postali di Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="87b05-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="87b05-110">È possibile utilizzare Verifica compatibilità distribuzione [centralizzata](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   per determinare se l'abbonamento è idoneo.</span><span class="sxs-lookup"><span data-stu-id="87b05-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="87b05-111">Come vengono mirate le assegnazioni degli utenti dei componenti aggiuntivi con la distribuzione centralizzata?</span><span class="sxs-lookup"><span data-stu-id="87b05-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="87b05-112">La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e a tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="87b05-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="87b05-113">La distribuzione centralizzata può essere utilizzata per gli utenti di gruppi di primo livello o gruppi senza gruppi padre, ma non per gli utenti di gruppi annidati o gruppi con gruppi padre.</span><span class="sxs-lookup"><span data-stu-id="87b05-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="87b05-114">La distribuzione centralizzata fa anche parte della maggior parte dei gruppi di Azure Active Directory, inclusi i gruppi di Office 365, le liste di distribuzione e i gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="87b05-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="87b05-115">È meglio usare le assegnazioni dei gruppi anziché l'assegnazione di singoli utenti per semplificare la gestione.</span><span class="sxs-lookup"><span data-stu-id="87b05-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="87b05-116">Per ulteriori informazioni, vedere [Assegnazioni di utenti e gruppi.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="87b05-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="87b05-117">Quanto tempo è necessario per la visualizzazione dei componenti aggiuntivi per tutti gli utenti?</span><span class="sxs-lookup"><span data-stu-id="87b05-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="87b05-118">La visualizzazione di un componente aggiuntivo per tutti gli utenti può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="87b05-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="87b05-119">Può richiedere la stessa quantità di tempo per gli aggiornamenti dei componenti aggiuntivi, le modifiche dall'attivazione o dalla disattivazione o le rimozioni dei componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="87b05-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="87b05-120">Come amministratore, come si gestisce l'accesso utente ai componenti aggiuntivi per l'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="87b05-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="87b05-121">Per una distribuzione agevole dei componenti aggiuntivi a utenti, gruppi o all'intera organizzazione, è consigliabile che gli amministratori utilizzino la distribuzione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="87b05-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="87b05-122">Per ulteriori informazioni sulla gestione dell'accesso utente, vedere:</span><span class="sxs-lookup"><span data-stu-id="87b05-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="87b05-123">Impedire i download di componenti aggiuntivi disattivando Office Store in tutti i client (ad eccezione di Outlook)</span><span class="sxs-lookup"><span data-stu-id="87b05-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="87b05-124">Specifica degli amministratori e degli utenti in grado di installare e gestire componenti aggiuntivi per Outlook</span><span class="sxs-lookup"><span data-stu-id="87b05-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="87b05-125">La distribuzione centralizzata offrirà agli amministratori la flessibilità di scegliere il metodo di distribuzione per i componenti aggiuntivi di Outlook?</span><span class="sxs-lookup"><span data-stu-id="87b05-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="87b05-126">Sì.</span><span class="sxs-lookup"><span data-stu-id="87b05-126">Yes.</span></span> <span data-ttu-id="87b05-127">La distribuzione centralizzata offre agli amministratori la flessibilità di scegliere uno dei tre metodi di distribuzione per i componenti aggiuntivi di Outlook durante la distribuzione dei componenti aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="87b05-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="87b05-128">**Risolto (predefinito)**   Il componente aggiuntivo viene distribuito automaticamente agli utenti assegnati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="87b05-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="87b05-129">**Disponibile** Gli utenti possono installare il componente aggiuntivo in Outlook scegliendo Home > Altri componenti aggiuntivi **> gestito dall'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="87b05-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="87b05-130">**Facoltativo** Il componente aggiuntivo viene distribuito automaticamente agli utenti assegnati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="87b05-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="87b05-131">Gli amministratori possono aggiornare i componenti aggiuntivi Line-of-Business (LOB) ?</span><span class="sxs-lookup"><span data-stu-id="87b05-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="87b05-132">Sì.</span><span class="sxs-lookup"><span data-stu-id="87b05-132">Yes.</span></span> <span data-ttu-id="87b05-133">Gli amministratori possono caricare un nuovo file manifesto per supportare le modifiche dei metadati per i componenti aggiuntivi LOB distribuiti dall'amministratore. Il componente aggiuntivo viene aggiornato al successivo avvio delle applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="87b05-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="87b05-134">L'applicazione Web può essere modificata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="87b05-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="87b05-135">Per ulteriori informazioni, vedere componente aggiuntivo [line-of-business](./manage-addins-in-the-admin-center.md#more-about-office-add-ins-security).</span><span class="sxs-lookup"><span data-stu-id="87b05-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="87b05-136">Gli amministratori possono disattivare i componenti aggiuntivi?</span><span class="sxs-lookup"><span data-stu-id="87b05-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="87b05-137">Sì.</span><span class="sxs-lookup"><span data-stu-id="87b05-137">Yes.</span></span> <span data-ttu-id="87b05-138">Gli amministratori possono attivare o disattivare i componenti aggiuntivi distribuiti per tutti gli utenti dall'interfaccia di amministrazione di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87b05-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="87b05-139">Per ulteriori informazioni, vedere [Stati dei componenti aggiuntivi](./manage-addins-in-the-admin-center.md#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="87b05-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="87b05-140">Gli amministratori possono eliminare o rimuovere componenti aggiuntivi?</span><span class="sxs-lookup"><span data-stu-id="87b05-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="87b05-141">Sì.</span><span class="sxs-lookup"><span data-stu-id="87b05-141">Yes.</span></span> <span data-ttu-id="87b05-142">Gli amministratori possono eliminare i componenti aggiuntivi distribuiti per tutti gli utenti dall'interfaccia di amministrazione di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87b05-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="87b05-143">Per ulteriori informazioni, vedere [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="87b05-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="87b05-144">Gli amministratori possono distribuire componenti aggiuntivi a pagamento da Office Store tramite la distribuzione centralizzata?</span><span class="sxs-lookup"><span data-stu-id="87b05-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="87b05-145">No.</span><span class="sxs-lookup"><span data-stu-id="87b05-145">No.</span></span> <span data-ttu-id="87b05-146">Non è possibile distribuire componenti aggiuntivi a pagamento da Office Store utilizzando la distribuzione centralizzata in questo momento.</span><span class="sxs-lookup"><span data-stu-id="87b05-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="87b05-147">Ti consigliamo di contattarlo per lo sviluppatore ISV per il componente aggiuntivo a pagamento per richiedere un file manifesto o un URL.</span><span class="sxs-lookup"><span data-stu-id="87b05-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="87b05-148">L'amministratore tenant può quindi distribuire il componente aggiuntivo come componente aggiuntivo LOB tramite distribuzione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="87b05-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="87b05-149">Quale ruolo di amministratore è necessario per gestire i componenti aggiuntivi per l'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="87b05-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="87b05-150">L'amministratore globale è il ruolo consigliato con accesso completo al ciclo di vita di gestione dei componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="87b05-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="87b05-151">Altri ruoli di amministratore hanno un accesso limitato al ciclo di vita della distribuzione dei componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="87b05-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="87b05-152">Se sei la persona che ha acquistato l'abbonamento a Microsoft 365 per le aziende, sei l'amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="87b05-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="87b05-153">La sottoscrizione include un set di ruoli di amministratore che è possibile assegnare ad altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="87b05-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="87b05-154">Ogni ruolo di amministratore è mappato a funzioni aziendali comuni e fornisce agli utenti dell'organizzazione le autorizzazioni per eseguire attività specifiche nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87b05-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="87b05-155">Per ulteriori informazioni, vedere [Assegnare ruoli di amministratore.](../add-users/assign-admin-roles.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="87b05-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 