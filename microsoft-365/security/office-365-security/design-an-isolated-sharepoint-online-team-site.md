---
title: Progettare un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Sintesi: viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.'
ms.openlocfilehash: 671baadb3f7226be8c9919874f62cee576f7d294
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084531"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="02c37-103">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="02c37-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="02c37-104">**Sintesi:** viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.</span><span class="sxs-lookup"><span data-stu-id="02c37-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="02c37-105">In questo articolo viene fornita una descrizione dettagliata delle scelte fondamentali relative alla progettazione necessarie prima di creare un sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="02c37-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="02c37-106">Fase 1: determinare i gruppi di SharePoint e i livelli di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="02c37-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="02c37-107">Per impostazione predefinita, ogni sito del team di SharePoint Online viene creato con i seguenti gruppi di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="02c37-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="02c37-108">\<nome del sito> membri</span><span class="sxs-lookup"><span data-stu-id="02c37-108">\<site name> Members</span></span>
    
- <span data-ttu-id="02c37-109">\<nome del sito> visitatori</span><span class="sxs-lookup"><span data-stu-id="02c37-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="02c37-110">\<nome del sito> proprietari</span><span class="sxs-lookup"><span data-stu-id="02c37-110">\<site name> Owners</span></span>
    
<span data-ttu-id="02c37-111">Questi gruppi sono separati dai gruppi di Office 365 e Azure Active Directory (AD) e costituiscono la base per l'assegnazione di autorizzazioni per le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="02c37-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="02c37-p101">Il set di autorizzazioni specifiche che determina le operazioni disponibili per un membro di un gruppo di SharePoint in un sito rappresenta un livello di autorizzazione. Esistono tre livelli di autorizzazione per impostazione predefinita per un sito del team di SharePoint Online: Modifica, Lettura e Controllo completo. Nella tabella seguente vengono illustrati la correlazione predefinita dei gruppi di SharePoint e i livelli di autorizzazione assegnati:</span><span class="sxs-lookup"><span data-stu-id="02c37-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="02c37-115">**Gruppo di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="02c37-115">**SharePoint group**</span></span>|<span data-ttu-id="02c37-116">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="02c37-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="02c37-117">\<nome del sito> membri</span><span class="sxs-lookup"><span data-stu-id="02c37-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="02c37-118">Modifica</span><span class="sxs-lookup"><span data-stu-id="02c37-118">Edit</span></span>  <br/> |
|<span data-ttu-id="02c37-119">\<nome del sito> visitatori</span><span class="sxs-lookup"><span data-stu-id="02c37-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="02c37-120">Lettura</span><span class="sxs-lookup"><span data-stu-id="02c37-120">Read</span></span>  <br/> |
|<span data-ttu-id="02c37-121">\<nome del sito> proprietari</span><span class="sxs-lookup"><span data-stu-id="02c37-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="02c37-122">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="02c37-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="02c37-p102">**Procedura consigliata:** È possibile creare ulteriori gruppi di SharePoint e livelli di autorizzazione. Tuttavia, è consigliabile usare questi gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="02c37-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="02c37-125">Di seguito sono disponibili i gruppi di SharePoint e i livelli di autorizzazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="02c37-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![I gruppi di SharePoint e i livelli di autorizzazione predefiniti per un sito di SharePoint Online.](../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="02c37-127">Fase 2: assegnare autorizzazioni agli utenti con i gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="02c37-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="02c37-p103">È possibile assegnare autorizzazioni agli utenti aggiungendo il loro account utente (o un gruppo di Office 365 o Azure AD di cui l'account utente è membro) ai gruppi di SharePoint. Al termine di questa operazione, agli account utente di Office 365, direttamente o indirettamente tramite l'appartenenza a un gruppo di Office 365 o Azure AD, viene assegnato il livello di autorizzazione associato al gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="02c37-p103">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups. Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="02c37-130">Utilizzo di gruppi di SharePoint predefiniti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="02c37-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="02c37-131">I membri del \*\* \<nome del sito> membri\*\* di gruppo di SharePoint, che possono includere sia gli account utente che i gruppi, vengono assegnati il livello di autorizzazione **modifica** .</span><span class="sxs-lookup"><span data-stu-id="02c37-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="02c37-132">Membri del \*\* \<nome del sito>\*\* gruppo di SharePoint visitatori, che può includere sia gli account utente che i gruppi, viene assegnato il livello di autorizzazione **lettura** .</span><span class="sxs-lookup"><span data-stu-id="02c37-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="02c37-133">I membri del \*\* \<nome del sito> proprietari\*\* del gruppo di SharePoint, che può includere sia gli account utente che i gruppi, vengono assegnati il livello di autorizzazione **controllo completo** .</span><span class="sxs-lookup"><span data-stu-id="02c37-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="02c37-p104">**Procedura consigliata:** Anche se è possibile gestire le autorizzazioni per singoli account utente, è consigliabile utilizzare un singolo gruppo di Azure AD, noto come gruppo di accesso. In questo modo si semplifica la gestione delle autorizzazioni tramite l'appartenenza al gruppo di accesso, anziché gestire l'elenco di account utente per ogni gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="02c37-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="02c37-136">I gruppi di Azure AD per Office 365 sono diversi da quelli di Office 365.</span><span class="sxs-lookup"><span data-stu-id="02c37-136">Azure AD groups for Office 365 are different than Office 365 groups.</span></span> <span data-ttu-id="02c37-137">I gruppi di Azure AD vengono visualizzati nell'interfaccia di amministrazione di Microsoft 365 con il relativo **tipo** impostato su **sicurezza** e non dispongono di un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="02c37-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="02c37-138">I gruppi di Azure AD possono essere gestiti all'interno di:</span><span class="sxs-lookup"><span data-stu-id="02c37-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="02c37-139">Servizi di dominio Active Directory (AD DS)</span><span class="sxs-lookup"><span data-stu-id="02c37-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="02c37-140">Si tratta di gruppi che sono stati creati nell'infrastruttura di servizi di dominio Active Directory locale e sincronizzati con la sottoscrizione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="02c37-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Office 365 subscription.</span></span> <span data-ttu-id="02c37-141">Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno **lo stato** **sincronizzato con Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="02c37-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="02c37-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="02c37-142">Office 365</span></span>
    
    <span data-ttu-id="02c37-143">Si tratta di gruppi che sono stati creati utilizzando l'interfaccia di amministrazione di Microsoft 365, il portale di Azure o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02c37-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="02c37-144">Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno **lo stato** **cloud**.</span><span class="sxs-lookup"><span data-stu-id="02c37-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="02c37-145">**Procedura consigliata:** Se si utilizza servizi di dominio Active Directory in locale e si esegue la sincronizzazione con l'abbonamento a Office 365, eseguire la gestione di utenti e gruppi con servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="02c37-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Office 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="02c37-146">Per i siti del team di SharePoint Online isolati, la struttura del gruppo consigliata è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="02c37-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="02c37-147">**Gruppo di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="02c37-147">**SharePoint group**</span></span>|<span data-ttu-id="02c37-148">**Gruppo di accesso basato su Azure AD**</span><span class="sxs-lookup"><span data-stu-id="02c37-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="02c37-149">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="02c37-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="02c37-150">\<nome del sito> membri</span><span class="sxs-lookup"><span data-stu-id="02c37-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="02c37-151">\<nome del sito> membri</span><span class="sxs-lookup"><span data-stu-id="02c37-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="02c37-152">Modifica</span><span class="sxs-lookup"><span data-stu-id="02c37-152">Edit</span></span>  <br/> |
|<span data-ttu-id="02c37-153">\<nome del sito> visitatori</span><span class="sxs-lookup"><span data-stu-id="02c37-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="02c37-154">\<nome del sito> visualizzatori</span><span class="sxs-lookup"><span data-stu-id="02c37-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="02c37-155">Lettura</span><span class="sxs-lookup"><span data-stu-id="02c37-155">Read</span></span>  <br/> |
|<span data-ttu-id="02c37-156">\<nome del sito> proprietari</span><span class="sxs-lookup"><span data-stu-id="02c37-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="02c37-157">\<nome del sito> amministratori</span><span class="sxs-lookup"><span data-stu-id="02c37-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="02c37-158">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="02c37-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="02c37-159">**Procedura consigliata:** Sebbene sia possibile utilizzare i gruppi di Office 365 o Azure AD come membri dei gruppi di SharePoint, è consigliabile utilizzare i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="02c37-159">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="02c37-160">I gruppi di Azure AD, gestiti tramite servizi di dominio Active Directory o Office 365, offrono maggiore flessibilità nell'utilizzo dei gruppi nidificati per assegnare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="02c37-160">Azure AD groups, managed either through AD DS or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="02c37-161">Di seguito sono disponibili i gruppi di SharePoint predefiniti configurati per l'utilizzo dei gruppi di accesso basati su Azure AD.</span><span class="sxs-lookup"><span data-stu-id="02c37-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Utilizzo di gruppi di accesso come membri dei gruppi di siti di SharePoint Online predefiniti.](../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="02c37-163">Quando si progettano i tre gruppi di accesso, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="02c37-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="02c37-164">I membri del gruppo di accesso \*\* \<> Admins\*\* devono essere presenti solo alcuni utenti, che corrispondono a un numero limitato di amministratori di SharePoint Online che gestiscono il sito del team.</span><span class="sxs-lookup"><span data-stu-id="02c37-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="02c37-165">La maggior parte dei membri del sito è presente nel \*\* \<nome del sito> membri\*\* o \*\* \<nel nome del sito>\*\* gruppi di accesso dei visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="02c37-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="02c37-166">Poiché i membri del sito del gruppo di \*\* \<accesso> membri\*\* del sito hanno la possibilità di eliminare o modificare le risorse nel sito, è opportuno considerare con attenzione la propria appartenenza.</span><span class="sxs-lookup"><span data-stu-id="02c37-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="02c37-167">In caso di dubbi, aggiungere il membro del sito al gruppo di accesso dei \*\* \<visualizzatori> nome del sito\*\* .</span><span class="sxs-lookup"><span data-stu-id="02c37-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="02c37-168">Di seguito è riportato un esempio di gruppi di SharePoint e gruppi di accesso per un sito isolato denominato ProjectX.</span><span class="sxs-lookup"><span data-stu-id="02c37-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Un esempio di utilizzo dei gruppi di accesso per un sito di SharePoint Online denominato ProjectX.](../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="02c37-170">Fase 3: utilizzare i gruppi di Azure AD nidificati</span><span class="sxs-lookup"><span data-stu-id="02c37-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="02c37-171">Per un progetto con un numero limitato di persone, un singolo livello di gruppi di accesso basati su Azure AD aggiunti ai gruppi di SharePoint del sito si adatterà alla maggior parte degli scenari.</span><span class="sxs-lookup"><span data-stu-id="02c37-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="02c37-172">Tuttavia, se si dispone di un numero elevato di persone e quelle persone sono già membri di gruppi di Azure AD stabiliti, è possibile assegnare più facilmente le autorizzazioni di SharePoint utilizzando gruppi nidificati o gruppi che contengono altri gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="02c37-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="02c37-p111">Ad esempio, si desidera creare un sito del team di SharePoint Online isolato per la collaborazione tra i dirigenti dei reparti delle vendite, marketing, ingegneria, legali e del supporto e tali reparti fanno parte di gruppi di account utente della direzione esecutiva. Anziché creare un nuovo gruppo per i nuovi membri del sito e inserirvi tutti i singoli account utente esecutivi, inserire i gruppi di dirigenti esistenti per ogni reparto nel nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="02c37-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="02c37-p112"> Se si condivide un abbonamento a Office 365 tra più organizzazioni, un solo livello di appartenenza ai gruppi per un sito isolato per un'organizzazione potrebbe diventare difficile da gestire a causa del gran numero di account utente. In questo caso, è possibile utilizzare gruppi di Azure AD per ogni organizzazione con i gruppi all'interno delle organizzazioni per gestire le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="02c37-p112">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts. In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="02c37-177">Per utilizzare i gruppi di Azure AD nidificati:</span><span class="sxs-lookup"><span data-stu-id="02c37-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="02c37-178">Individuare o creare i gruppi di Azure AD che conterranno gli account utente e aggiungere gli account utente appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="02c37-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="02c37-179">Creare il gruppo di accesso basato su Azure AD che conterrà gli altri gruppi di Azure AD e aggiungere i gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="02c37-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="02c37-180"> Per il livello di accesso appropriato per il gruppo di accesso contenitore, individuare il gruppo di SharePoint e il livello di autorizzazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="02c37-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="02c37-181">Non è possibile utilizzare i gruppi di Office 365 nidificati.</span><span class="sxs-lookup"><span data-stu-id="02c37-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="02c37-182">Di seguito è riportato un esempio di gruppi di Azure AD nidificati per il gruppo di accesso ai membri di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="02c37-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Un esempio di utilizzo dei gruppi di accesso annidati per il gruppo di accesso dei membri per il sito di ProjectX.](../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="02c37-184">Poiché tutti gli account utente dei lead team di ricerca, ingegneria e progetto sono destinati a essere membri del sito, è più facile aggiungere i propri gruppi di Azure ad al gruppo di accesso dei membri di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="02c37-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="02c37-185">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="02c37-185">Next step</span></span>

<span data-ttu-id="02c37-186">Quando si è pronti per creare e configurare un sito isolato nell'ambiente di produzione, vedere [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="02c37-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02c37-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02c37-187">See Also</span></span>

[<span data-ttu-id="02c37-188">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="02c37-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="02c37-189">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="02c37-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="02c37-190">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="02c37-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



