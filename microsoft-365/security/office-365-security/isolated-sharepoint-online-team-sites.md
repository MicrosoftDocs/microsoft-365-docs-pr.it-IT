---
title: Siti del team di SharePoint Online isolati
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 'Sintesi: informazioni sugli utilizzi dei siti del team di SharePoint Online isolati.'
ms.openlocfilehash: b62223b231c4b6dc0d233d899472800226503323
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634111"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="5fe93-103">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="5fe93-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="5fe93-104">**Sintesi:** informazioni sugli utilizzi dei siti del team di SharePoint Online isolati.</span><span class="sxs-lookup"><span data-stu-id="5fe93-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="5fe93-p101">I siti del team di SharePoint Online consentono di creare rapidamente uno spazio per la collaborazione a note, documenti, articoli, un calendario e altre risorse in Microsoft Office 365. Un sito del team di SharePoint Online si basa su un gruppo di Microsoft 365 e dispone di un modello di amministrazione semplificato per consentire la collaborazione aperta con un set privato di membri del gruppo o con l'intera organizzazione. Un sito del team SharePoint Online predefinito consente ai membri del gruppo di Microsoft 365 di invitare altri utenti e di tenere sotto controllo le impostazioni delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5fe93-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on an Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="5fe93-p102">In alcuni casi, tuttavia, si desidera creare un sito del team SharePoint Online per la collaborazione in cui le autorizzazioni del sito siano più controllate tramite l'appartenenza ai gruppi e livelli di autorizzazione SharePoint Online, che vengono gestiti solo dagli amministratori di SharePoint. Si tratta di ciò che viene definito un sito isolato, che è isolato per il set di utenti che collaborano nel sito, che ne visualizzano i contenuti o che lo amministrano. Potrebbe essere necessario un sito isolato nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="5fe93-p102">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="5fe93-111">Un progetto segreto all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe93-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="5fe93-112">La posizione di informazioni altamente riservate o di proprietà intellettuale importante.</span><span class="sxs-lookup"><span data-stu-id="5fe93-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="5fe93-113">Le risorse per un'azione legale intrapresa dall'organizzazione o alla quale è soggetta.</span><span class="sxs-lookup"><span data-stu-id="5fe93-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="5fe93-114">Per condividere un abbonamento a Microsoft 365 tra più organizzazioni con alcune sovrapposizioni, ma per la maggior parte esistono entità aziendali separate.</span><span class="sxs-lookup"><span data-stu-id="5fe93-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="5fe93-115">Di seguito sono riportati i requisiti di un sito isolato:</span><span class="sxs-lookup"><span data-stu-id="5fe93-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="5fe93-116">Solo gli amministratori di SharePoint Online possono gestire il sito, la cui amministrazione include l'appartenenza ai gruppi per l'accesso al sito e la configurazione di autorizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5fe93-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="5fe93-117">I membri del sito non possono invitare altri membri nel sito del team.</span><span class="sxs-lookup"><span data-stu-id="5fe93-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="5fe93-p103">Gli utenti che non sono membri del sito isolato non possono richiedere l'accesso al sito. Quando tentano di accedere a qualsiasi URL associato al sito, viene loro negato l'accesso alla pagina Web.</span><span class="sxs-lookup"><span data-stu-id="5fe93-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="5fe93-p104">Lo svantaggio di richiedere il controllo dell'accesso centralizzato e le autorizzazioni personalizzate dagli amministratori di SharePoint Online è che il sito rimane isolato nel tempo. Ad esempio, i membri correnti non possono, intenzionalmente o accidentalmente, invitare o configurare autorizzazioni personalizzate per altri utenti all'interno dell'abbonamento a Microsoft 365 che non devono essere membri del sito.</span><span class="sxs-lookup"><span data-stu-id="5fe93-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="5fe93-122">Un sito isolato può essere usato con altre funzionalità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5fe93-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="5fe93-123">Information Rights Management per garantire che le risorse nel sito rimangano crittografate anche se vengono scaricate in locale e caricate in un altro sito disponibile per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe93-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="5fe93-124">Prevenzione della perdita dei dati per impedire agli utenti di inviare le risorse del sito, come i file, tramite la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5fe93-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="5fe93-125">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5fe93-125">Next steps</span></span>

<span data-ttu-id="5fe93-126">Per provare a usare un sito del team di SharePoint Online isolato in una sottoscrizione di valutazione, vedere le istruzioni dettagliate disponibili in [Sito team di SharePoint Online isolato nell'ambiente di sviluppo e di testing di Office 365](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5fe93-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="5fe93-127">Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="5fe93-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5fe93-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fe93-128">See Also</span></span>

[<span data-ttu-id="5fe93-129">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5fe93-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="5fe93-130">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5fe93-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="5fe93-131">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5fe93-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


