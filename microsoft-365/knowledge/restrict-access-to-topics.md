---
title: Limitare l'accesso agli argomenti
description: Come escludere gli argomenti per impedire che vengano scoperti.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: f7e8406ee7090387d4500f69955330466f28c6c0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976146"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="bb497-103">Limitare l'accesso agli argomenti nelle esperienze di argomento</span><span class="sxs-lookup"><span data-stu-id="bb497-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="bb497-104">Nelle esperienze degli argomenti, le parti interessate nell'organizzazione possono decidere di non individuare e esporre gli utenti con licenza.</span><span class="sxs-lookup"><span data-stu-id="bb497-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="bb497-105">Ad esempio, è possibile che si stia lavorando a un progetto di cui non si desidera esporre altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="bb497-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="bb497-106">Anche se le autorizzazioni di Office 365 per siti, file e altre risorse impediscono agli utenti di visualizzare le informazioni riservate negli argomenti, esistono ulteriori misure di salvaguardia per evitare che vengano scoperti argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="bb497-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="bb497-107">Mentre gli amministratori della Knowledge base controllano le impostazioni della rete di conoscenze per evitare che gli argomenti vengano scoperti, i Knowledge Manager e le altre parti interessate devono sapere come eseguire questa operazione affinché possano collaborare in questo modo.</span><span class="sxs-lookup"><span data-stu-id="bb497-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="bb497-108">In questo articolo vengono illustrati i modi per evitare che gli argomenti vengano identificati tramite AI o visualizzati nell'ambiente come protezione di sicurezza aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="bb497-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="bb497-109">È importante tenere presente che, nelle esperienze degli argomenti, gli utenti non sono autorizzati a visualizzare alcun elemento in un argomento a cui non è consentito l'accesso tramite le autorizzazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb497-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="bb497-110">Anche se un utente è in grado di visualizzare un argomento, i relativi file, siti e pagine che non dispongono delle autorizzazioni di Office 365 per la visualizzazione non saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="bb497-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="bb497-111">Assicurarsi che le autorizzazioni per i file riservati siano impostate correttamente devono essere il Safeguard di sicurezza principale.</span><span class="sxs-lookup"><span data-stu-id="bb497-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="bb497-112">Impedire l'identificazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="bb497-112">Prevent topics from being identified</span></span>

<span data-ttu-id="bb497-113">L'amministratore della Knowledge base può limitare l'accesso a argomenti specifici impedendo che vengano trovati nell'indicizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="bb497-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="bb497-114">Esistono due modi per eseguire questa operazione nelle impostazioni di amministrazione della rete di informazioni nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb497-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="bb497-115">[Selezionare i siti di SharePoint da escludere dall'individuazione](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)di un argomento: è possibile utilizzare questa impostazione per impedire la ricerca per indicizzazione di siti di SharePoint specifici per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="bb497-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="bb497-116">[Escludi argomenti per nome](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): gli amministratori possono utilizzare questa impostazione per evitare che argomenti specifici vengano scoperti per nome.</span><span class="sxs-lookup"><span data-stu-id="bb497-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="bb497-117">Nelle impostazioni di amministratore della rete della Knowledge base, un amministratore può caricare un elenco di argomenti da escludere in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="bb497-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="bb497-118">È possibile escludere gli argomenti che presentano corrispondenze esatte o parziali di un nome di argomento.</span><span class="sxs-lookup"><span data-stu-id="bb497-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="bb497-119">Impedire che gli argomenti vengano visualizzati da utenti specifici</span><span class="sxs-lookup"><span data-stu-id="bb497-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="bb497-120">Gli amministratori della Knowledge base possono anche [selezionare gli utenti autorizzati a visualizzare gli argomenti nell'organizzazione](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span><span class="sxs-lookup"><span data-stu-id="bb497-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="bb497-121">Questa impostazione consente di selezionare gli utenti con licenza in grado di visualizzare tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="bb497-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="bb497-122">Ad esempio, in un ambiente pilota, è possibile consentire solo a un piccolo gruppo di utenti di essere in grado di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="bb497-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="bb497-123">Rimuovere gli argomenti dalla visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bb497-123">Remove topics from being viewed</span></span>

<span data-ttu-id="bb497-124">I Knowledge Manager possono scegliere di [rimuovere gli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) in modo che gli utenti non possano più visualizzarli.</span><span class="sxs-lookup"><span data-stu-id="bb497-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="bb497-125">Nella pagina **Gestisci argomenti** del **centro** argomenti, i responsabili della Knowledge base possono scegliere di rifiutare argomenti specifici per impedire che vengano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="bb497-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="bb497-126">Gli argomenti possono essere rimossi indipendentemente dal fatto che si trovino in uno stato suggerito o confermato.</span><span class="sxs-lookup"><span data-stu-id="bb497-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="bb497-127">Gli argomenti rimossi possono essere aggiunti in un secondo momento come argomenti visualizzabili, se necessario.</span><span class="sxs-lookup"><span data-stu-id="bb497-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="bb497-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb497-128">See also</span></span>



  






