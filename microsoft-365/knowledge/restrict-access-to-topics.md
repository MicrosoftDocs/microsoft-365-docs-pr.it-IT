---
title: Limitare l'accesso agli argomenti in Microsoft Viva Topics
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
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500874"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="4cc24-103">Limitare l'accesso agli argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4cc24-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="4cc24-104">In Microsoft Viva, gli stakeholder dell'organizzazione potrebbero voler assicurarsi che argomenti specifici non siano individuati ed esposti agli utenti con licenza.</span><span class="sxs-lookup"><span data-stu-id="4cc24-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="4cc24-105">Ad esempio, è possibile che si lavori a un progetto di cui non si desidera ancora esporre informazioni.</span><span class="sxs-lookup"><span data-stu-id="4cc24-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="4cc24-106">Sebbene Office 365 autorizzazioni per siti, file e altre risorse impediranno agli utenti di esperienze di argomento di visualizzare informazioni riservate negli argomenti, esistono ulteriori misure di sicurezza per impedire che vengano individuati argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4cc24-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="4cc24-107">Mentre gli amministratori delle conoscenze controllano le impostazioni per impedire l'individuare gli argomenti, i responsabili della conoscenza e altri stakeholder devono sapere come vengono eseguite in modo che possano collaborare.</span><span class="sxs-lookup"><span data-stu-id="4cc24-107">While knowledge admins control the settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="4cc24-108">In questo articolo vengono descritti i modi per impedire che gli argomenti vengano identificati tramite l'IA o visualizzati nell'ambiente come ulteriore protezione della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4cc24-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="4cc24-109">È importante notare che in Viva Topics, agli utenti non è consentito visualizzare nulla in un argomento a cui non è consentito accedere tramite Office 365 autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4cc24-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="4cc24-110">Anche se un utente è in grado di visualizzare un argomento, i relativi file, siti e pagine non dispongono delle autorizzazioni Office 365 per visualizzarlo non saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="4cc24-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="4cc24-111">Assicurarsi che le autorizzazioni per i file sensibili siano impostate correttamente deve essere la protezione principale.</span><span class="sxs-lookup"><span data-stu-id="4cc24-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="4cc24-112">Impedire l'identificazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="4cc24-112">Prevent topics from being identified</span></span>

<span data-ttu-id="4cc24-113">L'amministratore della knowledge base può limitare l'accesso a argomenti specifici impedendo che vengano trovati nell'indicizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="4cc24-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="4cc24-114">Esistono due modi per eseguire questa attività nelle impostazioni di amministrazione Viva Topics nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4cc24-114">There are two ways to do this task in the Viva Topics admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="4cc24-115">[Selezionare SharePoint siti](./topic-experiences-discovery.md#select-sharepoint-topic-sources)da escludere dall'individuazione degli argomenti: è possibile utilizzare questa impostazione per impedire la ricerca per indicizzazione di siti SharePoint specifici per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4cc24-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="4cc24-116">[Escludi gli argomenti](./topic-experiences-discovery.md#exclude-topics-by-name)in base al nome: gli amministratori possono utilizzare questa impostazione per impedire che argomenti specifici vengano individuati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="4cc24-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="4cc24-117">Nelle impostazioni di amministrazione Viva Topics, un amministratore può caricare un elenco di argomenti da escludere in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="4cc24-117">In the Viva Topics admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="4cc24-118">È possibile escludere gli argomenti con corrispondenze esatte o parziali di un nome di argomento.</span><span class="sxs-lookup"><span data-stu-id="4cc24-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="4cc24-119">Impedire la visualizzazione di argomenti da parte di utenti specifici</span><span class="sxs-lookup"><span data-stu-id="4cc24-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="4cc24-120">Gli amministratori della knowledge base possono anche [selezionare gli utenti che possono visualizzare gli argomenti nell'organizzazione.](./topic-experiences-knowledge-rules.md)</span><span class="sxs-lookup"><span data-stu-id="4cc24-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="4cc24-121">Questa impostazione consente di selezionare gli utenti con licenza che possono visualizzare tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4cc24-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="4cc24-122">In un ambiente pilota, ad esempio, è possibile consentire solo a un piccolo gruppo di utenti di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4cc24-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="4cc24-123">Rimuovere gli argomenti dalla visualizzazione</span><span class="sxs-lookup"><span data-stu-id="4cc24-123">Remove topics from being viewed</span></span>

<span data-ttu-id="4cc24-124">I responsabili della conoscenza possono scegliere [di rimuovere gli argomenti](./manage-topics.md) in modo che gli utenti non possano più vederli.</span><span class="sxs-lookup"><span data-stu-id="4cc24-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="4cc24-125">Nella pagina **Gestisci argomenti** del **Centro** argomenti i responsabili delle conoscenze possono scegliere di rifiutare argomenti specifici per impedirne la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="4cc24-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="4cc24-126">Gli argomenti possono essere rimossi indipendentemente dal fatto che siano in uno stato consigliato o confermato.</span><span class="sxs-lookup"><span data-stu-id="4cc24-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="4cc24-127">Se necessario, gli argomenti rimossi possono essere aggiunti nuovamente come argomenti visualizzabili.</span><span class="sxs-lookup"><span data-stu-id="4cc24-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="4cc24-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cc24-128">See also</span></span>



