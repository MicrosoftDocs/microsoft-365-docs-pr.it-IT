---
title: Limitare l'accesso agli argomenti negli argomenti di Microsoft Viva
description: Come escludere gli argomenti per impedirne l'individuare.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: b8c49c96ace14ac1ba03411b5670d8e77268109a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453909"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="8b333-103">Limitare l'accesso agli argomenti negli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="8b333-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="8b333-104">In Microsoft Viva, gli stakeholder dell'organizzazione potrebbero voler assicurarsi che argomenti specifici non siano individuati ed esposti agli utenti con licenza.</span><span class="sxs-lookup"><span data-stu-id="8b333-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="8b333-105">Ad esempio, potresti lavorare a un progetto di cui non vuoi ancora esporre informazioni.</span><span class="sxs-lookup"><span data-stu-id="8b333-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="8b333-106">Anche se le autorizzazioni di Office 365 per siti, file e altre risorse impediranno agli utenti di Esperienze argomento di visualizzare informazioni riservate negli argomenti, esistono ulteriori misure di sicurezza per impedire che argomenti specifici vengano mai individuati.</span><span class="sxs-lookup"><span data-stu-id="8b333-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="8b333-107">Anche se gli amministratori delle conoscenze controllano le impostazioni della rete di conoscenze per impedire l'apprendimento degli argomenti, i responsabili della conoscenza e altri stakeholder devono sapere come vengono eseguite in modo che possano collaborare.</span><span class="sxs-lookup"><span data-stu-id="8b333-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="8b333-108">In questo articolo vengono descritti i modi per impedire che gli argomenti vengano identificati tramite l'intelligenza artificiale o visualizzati nel proprio ambiente come un'ulteriore protezione della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8b333-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="8b333-109">È importante notare che in Viva Topics gli utenti non possono visualizzare nulla in un argomento a cui non è consentito l'accesso tramite le autorizzazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b333-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="8b333-110">Anche se un utente è in grado di visualizzare un argomento, i relativi file, siti e pagine non dispongono delle autorizzazioni per la visualizzazione di Office 365 non saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="8b333-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="8b333-111">Assicurarsi che le autorizzazioni per i file sensibili siano impostate correttamente deve essere la protezione principale.</span><span class="sxs-lookup"><span data-stu-id="8b333-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="8b333-112">Impedire l'identificazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="8b333-112">Prevent topics from being identified</span></span>

<span data-ttu-id="8b333-113">L'amministratore della knowledge base può limitare l'accesso ad argomenti specifici impedendoli di essere trovati nell'indicizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="8b333-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="8b333-114">Esistono due modi per eseguire questa attività nelle impostazioni di amministrazione di Knowledge Network nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b333-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="8b333-115">[Selezionare i siti di SharePoint da escludere dall'individuazione](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)degli argomenti: è possibile utilizzare questa impostazione per impedire la ricerca per indicizzazione di siti di SharePoint specifici per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="8b333-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="8b333-116">[Escludere gli argomenti in base al nome:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)gli amministratori possono utilizzare questa impostazione per impedire che argomenti specifici vengano individuati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="8b333-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="8b333-117">Nelle impostazioni di amministrazione di Knowledge Network, un amministratore può caricare un elenco di argomenti da escludere in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="8b333-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="8b333-118">È possibile escludere gli argomenti con corrispondenze esatte o parziali di un nome di argomento.</span><span class="sxs-lookup"><span data-stu-id="8b333-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="8b333-119">Impedire la visualizzazione degli argomenti da parte di utenti specifici</span><span class="sxs-lookup"><span data-stu-id="8b333-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="8b333-120">Gli amministratori della knowledge base possono anche [selezionare gli utenti che possono visualizzare gli argomenti nell'organizzazione.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="8b333-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="8b333-121">Questa impostazione consente di selezionare gli utenti con licenza che possono visualizzare tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="8b333-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="8b333-122">In un ambiente pilota, ad esempio, è possibile consentire solo a un piccolo gruppo di utenti di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="8b333-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="8b333-123">Rimuovere gli argomenti dalla visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8b333-123">Remove topics from being viewed</span></span>

<span data-ttu-id="8b333-124">I responsabili della conoscenza possono scegliere [di rimuovere gli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) in modo che gli utenti non possano più vederli.</span><span class="sxs-lookup"><span data-stu-id="8b333-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="8b333-125">Nella pagina **Gestisci argomenti** del **Centro** argomenti i knowledge manager possono scegliere di rifiutare argomenti specifici per impedirne la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b333-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="8b333-126">Gli argomenti possono essere rimossi indipendentemente dal fatto che si presentino in uno stato consigliato o confermato.</span><span class="sxs-lookup"><span data-stu-id="8b333-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="8b333-127">Gli argomenti rimossi possono essere successivamente aggiunti nuovamente come argomenti visualizzabili, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8b333-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="8b333-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b333-128">See also</span></span>



  






