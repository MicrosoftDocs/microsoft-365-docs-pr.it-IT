---
title: Eliminazione dei dati di Office 365 Skype for business
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, è possibile trovare una spiegazione dell'eliminazione dei dati in Skype for business, inclusi i tipi di contenuto che non vengono conservati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf317f2ecd3d547ae8601553a34fb43fb4b5bd9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691383"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="8a082-103">Eliminazione dei dati di Skype for business in Office 365</span><span class="sxs-lookup"><span data-stu-id="8a082-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="8a082-p101">Skype for Business fornisce le funzionalità di archiviazione dei messaggi istantanei peer-to-peer e con più partecipanti, nonché le attività di caricamento dei contenuti nelle riunioni. La capacità di archiviazione richiede Exchange ed è controllata dall'attributo di conservazione in locale della cassetta postale Exchange dell'utente, che archivia i contenuti di posta elettronica e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8a082-p101">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings. The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="8a082-p102">Tutta l'archiviazione in Skype for Business viene considerata "archiviazione a livello dell'utente" perché consente di abilitare o disabilitare l'archiviazione per uno o più utenti o gruppi di utenti specifici, creando, configurando e applicando criteri di archiviazione a livello di utente per tali utenti. Nell'interfaccia di amministrazione di Skype for Business non è disponibile un controllo diretto sulle impostazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8a082-p102">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users. There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="8a082-108">I seguenti tipi di contenuto non vengono archiviati in Skype for business:</span><span class="sxs-lookup"><span data-stu-id="8a082-108">The following types of content are not archived in Skype for Business:</span></span>

- <span data-ttu-id="8a082-109">Trasferimenti di file peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8a082-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="8a082-110">Audio e video per conferenze e messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8a082-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="8a082-111">Applicazioni condivise per conferenze e messaggi immediati peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8a082-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="8a082-112">Annotazioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="8a082-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="8a082-113">Conservazione del contenuto della riunione</span><span class="sxs-lookup"><span data-stu-id="8a082-113">Meeting Content Retention</span></span>

<span data-ttu-id="8a082-114">I clienti che utilizzano Skype for business possono caricare contenuti in una riunione di Skype for business come allegati, ad esempio presentazioni di PowerPoint, file OneNote e altri file.</span><span class="sxs-lookup"><span data-stu-id="8a082-114">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files.</span></span> <span data-ttu-id="8a082-115">Il periodo di conservazione del contenuto caricato durante una riunione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8a082-115">The retention period for content that has been uploaded to a meeting is as follows:</span></span>

- <span data-ttu-id="8a082-116">La riunione-contenuto **una tantum** viene conservata per 15 giorni a partire da quando l'ultima persona lascia la riunione.</span><span class="sxs-lookup"><span data-stu-id="8a082-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="8a082-117">Il contenuto di **riunioni ricorrenti** viene conservato per 15 giorni dopo che l'ultima persona ha lasciato l'ultima sessione della riunione.</span><span class="sxs-lookup"><span data-stu-id="8a082-117">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting.</span></span> <span data-ttu-id="8a082-118">Se un utente accede alla stessa sessione della riunione prima della scadenza dei 15 giorni, il tempo di conservazione viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="8a082-118">The retention timer resets if someone joins the same meeting session within 15 days.</span></span> <span data-ttu-id="8a082-119">Si supponga, ad esempio, che venga pianificata una riunione di Skype for business su base settimanale per un anno e che un file venga caricato alla riunione durante la prima istanza.</span><span class="sxs-lookup"><span data-stu-id="8a082-119">For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance.</span></span> <span data-ttu-id="8a082-120">Se almeno una persona entra a far parte della sessione di riunione ogni settimana, il file viene conservato nei server Skype for business online per tutto l'anno più 15 giorni dopo che l'ultima persona ha lasciato l'ultima riunione della serie.</span><span class="sxs-lookup"><span data-stu-id="8a082-120">If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="8a082-121">**Meet Now meeting** -Content viene conservato per 8 ore dopo l'ora di fine della riunione.</span><span class="sxs-lookup"><span data-stu-id="8a082-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="8a082-122">Se un utente non è autorizzato o disabilitato (ad esempio, se **msRTCSIP-UserEnabled** è impostato su *false*) e viene quindi riconcesso in licenza o riabilitato, il contenuto della riunione non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="8a082-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="8a082-123">Scadenza della riunione</span><span class="sxs-lookup"><span data-stu-id="8a082-123">Meeting Expiration</span></span>

<span data-ttu-id="8a082-124">Gli utenti possono accedere a una riunione specifica dopo che è terminata in base ai seguenti periodi di scadenza:</span><span class="sxs-lookup"><span data-stu-id="8a082-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>

- <span data-ttu-id="8a082-125">La riunione di **una tantum** scade 14 giorni dopo l'ora di fine della riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="8a082-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="8a082-126">**Riunione ricorrente con data di fine** -la riunione scade 14 giorni dopo l'ora di fine pianificata dell'ultima riunione.</span><span class="sxs-lookup"><span data-stu-id="8a082-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="8a082-127">**Meet Now meeting** -meeting scade dopo 8 ore.</span><span class="sxs-lookup"><span data-stu-id="8a082-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="8a082-128">Collaborazione lavagna</span><span class="sxs-lookup"><span data-stu-id="8a082-128">Whiteboard Collaboration</span></span>

<span data-ttu-id="8a082-129">Le annotazioni effettuate sulle lavagne verranno visualizzate da tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="8a082-129">Annotations made on whiteboards will be seen by all participants.</span></span> <span data-ttu-id="8a082-130">Quando si salva una lavagna, la lavagna e tutte le annotazioni verranno archiviate su un server Skype for business e verranno conservate sul server in base ai criteri di scadenza del contenuto delle riunioni impostati dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="8a082-130">When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="8a082-131">Servizio di test audio</span><span class="sxs-lookup"><span data-stu-id="8a082-131">Audio Test Service</span></span>

<span data-ttu-id="8a082-132">Durante la chiamata del servizio di test audio viene registrato un campione breve (circa 5 secondi) della voce.</span><span class="sxs-lookup"><span data-stu-id="8a082-132">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call.</span></span> <span data-ttu-id="8a082-133">Il campione vocale viene utilizzato dall'utente per verificare e/o verificare la qualità del suono della chiamata Skype for business in base alla qualità della registrazione.</span><span class="sxs-lookup"><span data-stu-id="8a082-133">The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording.</span></span> <span data-ttu-id="8a082-134">Quando viene terminata la chiamata al servizio di test audio, viene eliminato l'esempio di voce.</span><span class="sxs-lookup"><span data-stu-id="8a082-134">When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="8a082-135">Chat di gruppo persistente</span><span class="sxs-lookup"><span data-stu-id="8a082-135">Persistent Group Chat</span></span>

<span data-ttu-id="8a082-136">Persistent Group Chat archivia il contenuto delle conversazioni di Group Chat.</span><span class="sxs-lookup"><span data-stu-id="8a082-136">Persistent Group Chat stores the content of group chat conversations.</span></span> <span data-ttu-id="8a082-137">Se abilitato, l'amministratore può controllare il periodo di conservazione, il server in cui sono archiviate le informazioni, se la cronologia della chat di gruppo viene archiviata per la conformità o altri scopi e gestire/modificare le proprietà in una chat room.</span><span class="sxs-lookup"><span data-stu-id="8a082-137">If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room.</span></span> <span data-ttu-id="8a082-138">Gli utenti con ruoli diversi hanno accesso diverso ai dati permanenti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8a082-138">Users with different roles have different access to the persisted data, as follows:</span></span>

- <span data-ttu-id="8a082-139">Gli amministratori possono eliminare i contenuti meno recenti (ad esempio, il contenuto inserito prima di una determinata data) da qualsiasi chat room per evitare che le dimensioni del database crescano notevolmente.</span><span class="sxs-lookup"><span data-stu-id="8a082-139">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly.</span></span> <span data-ttu-id="8a082-140">In alternativa, è possibile rimuovere o sostituire i messaggi considerati inappropriati per una determinata chat room (o considerati inadatti).</span><span class="sxs-lookup"><span data-stu-id="8a082-140">Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="8a082-141">Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.</span><span class="sxs-lookup"><span data-stu-id="8a082-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="8a082-142">I responsabili della chat room possono disabilitare le sale ma non possono eliminare le sale.</span><span class="sxs-lookup"><span data-stu-id="8a082-142">Chat room managers can disable rooms but cannot delete rooms.</span></span> <span data-ttu-id="8a082-143">Solo gli amministratori possono eliminare una chat room dopo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="8a082-143">Only administrators can delete a chat room after it is created.</span></span>