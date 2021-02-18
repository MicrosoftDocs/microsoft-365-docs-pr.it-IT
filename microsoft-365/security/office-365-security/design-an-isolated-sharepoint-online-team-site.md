---
title: Progettare un sito del team di SharePoint Online isolato
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Progettare siti del team di SharePoint Online isolati, inclusi determinare i livelli di autorizzazione, assegnare autorizzazioni agli utenti con gruppi di accesso e gruppi di Azure AD annidati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288336"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="5e861-103">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5e861-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5e861-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5e861-104">**Applies to**</span></span>
- [<span data-ttu-id="5e861-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5e861-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="5e861-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e861-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="5e861-107">**Sintesi:** viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.</span><span class="sxs-lookup"><span data-stu-id="5e861-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="5e861-108">In questo articolo viene fornita una descrizione dettagliata delle scelte fondamentali relative alla progettazione necessarie prima di creare un sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="5e861-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="5e861-109">Fase 1: determinare i gruppi di SharePoint e i livelli di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5e861-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="5e861-110">Per impostazione predefinita, ogni sito del team di SharePoint Online viene creato con i seguenti gruppi di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="5e861-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="5e861-111">\<site name> Membri</span><span class="sxs-lookup"><span data-stu-id="5e861-111">\<site name> Members</span></span>

- <span data-ttu-id="5e861-112">\<site name> Visitatori</span><span class="sxs-lookup"><span data-stu-id="5e861-112">\<site name> Visitors</span></span>

- <span data-ttu-id="5e861-113">\<site name> Proprietari</span><span class="sxs-lookup"><span data-stu-id="5e861-113">\<site name> Owners</span></span>

<span data-ttu-id="5e861-114">Questi gruppi sono separati dai gruppi di Microsoft 365 e Azure Active Directory (AD) e sono la base per l'assegnazione delle autorizzazioni per le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="5e861-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="5e861-p101">Il set di autorizzazioni specifiche che determina le operazioni disponibili per un membro di un gruppo di SharePoint in un sito rappresenta un livello di autorizzazione. Esistono tre livelli di autorizzazione per impostazione predefinita per un sito del team di SharePoint Online: Modifica, Lettura e Controllo completo. Nella tabella seguente vengono illustrati la correlazione predefinita dei gruppi di SharePoint e i livelli di autorizzazione assegnati:</span><span class="sxs-lookup"><span data-stu-id="5e861-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="5e861-118">Gruppo di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5e861-118">SharePoint group</span></span>|<span data-ttu-id="5e861-119">Livello di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5e861-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="5e861-120">\<site name> Membri</span><span class="sxs-lookup"><span data-stu-id="5e861-120">\<site name> Members</span></span>|<span data-ttu-id="5e861-121">Modifica</span><span class="sxs-lookup"><span data-stu-id="5e861-121">Edit</span></span>|
|<span data-ttu-id="5e861-122">\<site name> Visitatori</span><span class="sxs-lookup"><span data-stu-id="5e861-122">\<site name> Visitors</span></span>|<span data-ttu-id="5e861-123">Lettura</span><span class="sxs-lookup"><span data-stu-id="5e861-123">Read</span></span>|
|<span data-ttu-id="5e861-124">\<site name> Proprietari</span><span class="sxs-lookup"><span data-stu-id="5e861-124">\<site name> Owners</span></span>|<span data-ttu-id="5e861-125">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="5e861-125">Full control</span></span>|
|

 <span data-ttu-id="5e861-p102">**Procedura consigliata:** È possibile creare ulteriori gruppi di SharePoint e livelli di autorizzazione. Tuttavia, è consigliabile usare questi gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="5e861-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="5e861-128">Ecco i gruppi e i livelli di autorizzazione di SharePoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5e861-128">Here are the default SharePoint groups and permission levels.</span></span>

![Gruppi e livelli di autorizzazione di SharePoint predefiniti per un sito di SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="5e861-130">Fase 2: assegnare autorizzazioni agli utenti con i gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="5e861-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="5e861-131">È possibile assegnare autorizzazioni agli utenti aggiungendo il proprio account utente o un gruppo di Microsoft 365 o Azure AD di cui l'account utente è membro, ai gruppi di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5e861-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="5e861-132">Dopo l'aggiunta, agli account utente, direttamente o indirettamente tramite l'appartenenza a un gruppo di Microsoft 365 o Azure AD, viene assegnato il livello di autorizzazione associato al gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5e861-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="5e861-133">Utilizzo di gruppi di SharePoint predefiniti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e861-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="5e861-134">Ai membri del **\<site name> gruppo Membri** di SharePoint, che può includere sia account utente che gruppi, viene assegnato il **livello di** autorizzazione Modifica</span><span class="sxs-lookup"><span data-stu-id="5e861-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="5e861-135">Ai membri del **\<site name> gruppo visitatori** di SharePoint, che può includere sia account utente che gruppi, viene assegnato il **livello di** autorizzazione Lettura</span><span class="sxs-lookup"><span data-stu-id="5e861-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="5e861-136">Ai membri del **\<site name> gruppo proprietari** di SharePoint, che può includere sia account utente che gruppi, viene assegnato il **livello di** autorizzazione Controllo completo</span><span class="sxs-lookup"><span data-stu-id="5e861-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="5e861-p104">**Procedura consigliata:** Anche se è possibile gestire le autorizzazioni per singoli account utente, è consigliabile utilizzare un singolo gruppo di Azure AD, noto come gruppo di accesso. In questo modo si semplifica la gestione delle autorizzazioni tramite l'appartenenza al gruppo di accesso, anziché gestire l'elenco di account utente per ogni gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5e861-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="5e861-139">I gruppi di Azure AD per Microsoft 365 sono gruppi diversi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e861-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="5e861-140">I gruppi di Azure AD vengono visualizzati nell'interfaccia  di amministrazione di Microsoft 365 con il tipo impostato su Sicurezza e non hanno un indirizzo di posta elettronica. </span><span class="sxs-lookup"><span data-stu-id="5e861-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="5e861-141">I gruppi di Azure AD possono essere gestiti all'interno di:</span><span class="sxs-lookup"><span data-stu-id="5e861-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="5e861-142">Servizi di dominio Active Directory (AD DS)</span><span class="sxs-lookup"><span data-stu-id="5e861-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="5e861-143">Si tratta di gruppi che sono stati creati nell'infrastruttura di Servizi di dominio Active Directory locale e sincronizzati con l'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e861-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="5e861-144">Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno **lo** stato **Sincronizzato con Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="5e861-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="5e861-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="5e861-145">Office 365</span></span>

    <span data-ttu-id="5e861-146">Si tratta di gruppi creati tramite l'interfaccia di amministrazione di Microsoft 365, il portale di Azure o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e861-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="5e861-147">Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno lo **stato** **Cloud.**</span><span class="sxs-lookup"><span data-stu-id="5e861-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="5e861-148">**Procedura consigliata:** Se si usa Servizi di dominio Active Directory in locale e si esegue la sincronizzazione con l'abbonamento a Microsoft 365, eseguire la gestione di utenti e gruppi con Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5e861-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="5e861-149">Per i siti del team di SharePoint Online isolati, la struttura del gruppo consigliata è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="5e861-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="5e861-150">Gruppo di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5e861-150">SharePoint group</span></span>|<span data-ttu-id="5e861-151">Gruppo di accesso basato su Azure AD</span><span class="sxs-lookup"><span data-stu-id="5e861-151">Azure AD-based access group</span></span>|<span data-ttu-id="5e861-152">Livello di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5e861-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="5e861-153">\<site name> Membri</span><span class="sxs-lookup"><span data-stu-id="5e861-153">\<site name> Members</span></span>|<span data-ttu-id="5e861-154">\<site name> Membri</span><span class="sxs-lookup"><span data-stu-id="5e861-154">\<site name> Members</span></span>|<span data-ttu-id="5e861-155">Modifica</span><span class="sxs-lookup"><span data-stu-id="5e861-155">Edit</span></span>|
|<span data-ttu-id="5e861-156">\<site name> Visitatori</span><span class="sxs-lookup"><span data-stu-id="5e861-156">\<site name> Visitors</span></span>|<span data-ttu-id="5e861-157">\<site name> Visualizzatori</span><span class="sxs-lookup"><span data-stu-id="5e861-157">\<site name> Viewers</span></span>|<span data-ttu-id="5e861-158">Lettura</span><span class="sxs-lookup"><span data-stu-id="5e861-158">Read</span></span>|
|<span data-ttu-id="5e861-159">\<site name> Proprietari</span><span class="sxs-lookup"><span data-stu-id="5e861-159">\<site name> Owners</span></span>|<span data-ttu-id="5e861-160">\<site name> Amministratori</span><span class="sxs-lookup"><span data-stu-id="5e861-160">\<site name> Admins</span></span>|<span data-ttu-id="5e861-161">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="5e861-161">Full control</span></span>|
|

 <span data-ttu-id="5e861-162">**Procedura consigliata:** Anche se è possibile usare i gruppi di Microsoft 365 o Azure AD come membri dei gruppi di SharePoint, è consigliabile usare i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e861-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="5e861-163">I gruppi di Azure AD, gestiti tramite Servizi di dominio Active Directory o Microsoft 365, offrono una maggiore flessibilità nell'uso dei gruppi annidati per assegnare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5e861-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="5e861-164">Ecco i gruppi di SharePoint predefiniti configurati per l'uso dei gruppi di accesso basati su Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e861-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Utilizzo dei gruppi di accesso come membri dei gruppi del sito di SharePoint Online predefiniti.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="5e861-166">Quando si progettano i tre gruppi di accesso, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e861-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="5e861-167">Nel gruppo di accesso **\<site name> Admins** dovrebbero essere presenti solo alcuni membri, corrispondenti a un numero limitato di amministratori di SharePoint Online che gestiscono il sito del team.</span><span class="sxs-lookup"><span data-stu-id="5e861-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="5e861-168">La maggior parte dei membri del sito è in gruppi **\<site name> di** **\<site name> accesso** Membri o Visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="5e861-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="5e861-169">Poiché i membri del gruppo **\<site name> di** accesso Membri hanno la possibilità di eliminare o modificare le risorse nel sito, valutare attentamente l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="5e861-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="5e861-170">In caso di dubbi, aggiungere il membro del sito al gruppo di accesso **\<site name> Visualizzatori.**</span><span class="sxs-lookup"><span data-stu-id="5e861-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="5e861-171">Ecco un esempio dei gruppi di SharePoint e dei gruppi di accesso per un sito isolato denominato ProjectX.</span><span class="sxs-lookup"><span data-stu-id="5e861-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Esempio di utilizzo dei gruppi di accesso per un sito di SharePoint Online denominato ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="5e861-173">Fase 3: usare gruppi di Azure AD annidati</span><span class="sxs-lookup"><span data-stu-id="5e861-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="5e861-174">Per un progetto con un numero limitato di persone, un singolo livello di gruppi di accesso basati su Azure AD aggiunti ai gruppi di SharePoint del sito si adatterà alla maggior parte degli scenari.</span><span class="sxs-lookup"><span data-stu-id="5e861-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="5e861-175">Tuttavia, se si dispone di un numero elevato di persone e tali persone sono già membri di gruppi di Azure AD stabiliti, è possibile assegnare più facilmente le autorizzazioni di SharePoint utilizzando gruppi nidificati o gruppi che contengono altri gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="5e861-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="5e861-p111">Ad esempio, si desidera creare un sito del team di SharePoint Online isolato per la collaborazione tra i dirigenti dei reparti delle vendite, marketing, ingegneria, legali e del supporto e tali reparti fanno parte di gruppi di account utente della direzione esecutiva. Anziché creare un nuovo gruppo per i nuovi membri del sito e inserirvi tutti i singoli account utente esecutivi, inserire i gruppi di dirigenti esistenti per ogni reparto nel nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="5e861-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="5e861-178">Se si condivide un abbonamento a Microsoft 365 tra più organizzazioni, un singolo livello di appartenenza a un gruppo per un sito isolato per un'organizzazione potrebbe diventare difficile da gestire a causa del numero elevato di account utente.</span><span class="sxs-lookup"><span data-stu-id="5e861-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="5e861-179">In questo caso, è possibile utilizzare gruppi di Azure AD per ogni organizzazione con i gruppi all'interno delle organizzazioni per gestire le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5e861-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="5e861-180">Per utilizzare i gruppi di Azure AD nidificati:</span><span class="sxs-lookup"><span data-stu-id="5e861-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="5e861-181">Individuare o creare i gruppi di Azure AD che conterranno gli account utente e aggiungere gli account utente appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="5e861-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="5e861-182">Creare il gruppo di accesso basato su Azure AD che conterrà gli altri gruppi di Azure AD e aggiungere i gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="5e861-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="5e861-183"> Per il livello di accesso appropriato per il gruppo di accesso contenitore, individuare il gruppo di SharePoint e il livello di autorizzazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5e861-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="5e861-184">Non è possibile usare gruppi di Microsoft 365 annidati.</span><span class="sxs-lookup"><span data-stu-id="5e861-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="5e861-185">Ecco un esempio di gruppi di Azure AD annidati per il gruppo di accesso ai membri di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="5e861-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Esempio di utilizzo di gruppi di accesso annidati per il gruppo di accesso dei membri per il sito ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="5e861-187">Poiché tutti gli account utente nei team di ricerca, progettazione e project lead sono destinati a essere membri del sito, è più semplice aggiungere i gruppi di Azure AD al gruppo di accesso Membri di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="5e861-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="5e861-188">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="5e861-188">Next step</span></span>

<span data-ttu-id="5e861-189">Quando si è pronti per creare e configurare un sito isolato nell'ambiente di produzione, vedere [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="5e861-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e861-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e861-190">See Also</span></span>

[<span data-ttu-id="5e861-191">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="5e861-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="5e861-192">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5e861-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="5e861-193">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5e861-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
