---
title: Utilizzare le comunicazioni in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery consente di gestire facilmente il flusso di lavoro di notifica del blocco legale per notificare ai custodi le indagini legali.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551242"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="dadf4-103">Utilizzare le comunicazioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="dadf4-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="dadf4-104">Advanced eDiscovery consente ai reparti legali di semplificare i processi relativi al monitoraggio e alla distribuzione delle notifiche di blocco legale.</span><span class="sxs-lookup"><span data-stu-id="dadf4-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="dadf4-105">Lo strumento di comunicazione depositario consente ai reparti legali di gestire e automatizzare l'intero processo di conservazione legale, dalle notifiche iniziali, ai promemoria e alle escalation, tutto in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="dadf4-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="dadf4-106">Che cos'è una notifica di blocco legale?</span><span class="sxs-lookup"><span data-stu-id="dadf4-106">What is a legal hold notification?</span></span>

<span data-ttu-id="dadf4-107">Un avviso di blocco legale (noto anche come blocco per controversia *legale)* è una notifica inviata dal reparto legale di un'organizzazione a dipendenti, personale contingente o custodi di dati che potrebbero essere rilevanti per un'indagine legale.</span><span class="sxs-lookup"><span data-stu-id="dadf4-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="dadf4-108">Queste notifiche incaricano i custodi di conservare le informazioni archiviate elettronicamente e qualsiasi contenuto che possa essere rilevante per una questione legale attiva o imminente.</span><span class="sxs-lookup"><span data-stu-id="dadf4-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="dadf4-109">I team legali devono sapere che ogni responsabile ha ricevuto, letto, compreso e ha accettato di rispettare le istruzioni fornite.</span><span class="sxs-lookup"><span data-stu-id="dadf4-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="dadf4-110">Processo di notifica di blocco legale</span><span class="sxs-lookup"><span data-stu-id="dadf4-110">The legal hold notification process</span></span>

<span data-ttu-id="dadf4-111">Un'organizzazione ha il dovere di conservare le informazioni rilevanti quando viene a sapere di un'imminente controversia legale o di un'indagine normativa.</span><span class="sxs-lookup"><span data-stu-id="dadf4-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="dadf4-112">Per conformarsi ai requisiti di conservazione di un'indagine, l'organizzazione deve informare immediatamente i potenziali custodi del proprio dovere di conservare le informazioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="dadf4-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="dadf4-113">Con Advanced eDiscovery, i team legali possono creare e personalizzare il flusso di lavoro di notifica di blocco legale.</span><span class="sxs-lookup"><span data-stu-id="dadf4-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="dadf4-114">Lo strumento di comunicazione del responsabile consente ai team legali di configurare le comunicazioni e i flussi di lavoro seguenti:</span><span class="sxs-lookup"><span data-stu-id="dadf4-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="dadf4-115">**Avviso di rilascio:** Un avviso di blocco legale viene emesso (o avviato) da una notifica dell'ufficio legale ai custodi che potrebbero avere informazioni pertinenti sulla questione.</span><span class="sxs-lookup"><span data-stu-id="dadf4-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="dadf4-116">Questo avviso indica ai responsabili di mantenere tutte le informazioni necessarie per l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="dadf4-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="dadf4-117">**Avviso di riemissione:** Durante un caso, i custodi potrebbero essere tenuti a conservare contenuto aggiuntivo (o meno contenuto) rispetto a quanto richiesto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dadf4-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="dadf4-118">Per questo scenario, è possibile aggiornare l'avviso di blocco esistente e riemettere l'avviso ai custodi.</span><span class="sxs-lookup"><span data-stu-id="dadf4-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="dadf4-119">**Avviso di rilascio:** Una volta risolta una questione e il responsabile non è più soggetto a un requisito di conservazione, il responsabile può essere rilasciato dal caso.</span><span class="sxs-lookup"><span data-stu-id="dadf4-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="dadf4-120">Inoltre, è possibile informare il responsabile che non è più necessario conservare il contenuto e fornire istruzioni su come riprendere la normale attività di lavoro in relazione ai dati.</span><span class="sxs-lookup"><span data-stu-id="dadf4-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="dadf4-121">**Promemoria e escalation:** In alcuni casi, l'emissione di un avviso non è sufficiente per soddisfare i requisiti di individuazione legale.</span><span class="sxs-lookup"><span data-stu-id="dadf4-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="dadf4-122">Con ogni notifica, i team legali possono pianificare un set di promemoria ed escalation per aggiornare automaticamente i responsabili che non rispondono.</span><span class="sxs-lookup"><span data-stu-id="dadf4-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="dadf4-123">**Promemoria:** Dopo che un avviso di blocco legale è stato emesso o riemesso a un gruppo di responsabili, un'organizzazione può impostare promemoria per avvisare i responsabili che non rispondono.</span><span class="sxs-lookup"><span data-stu-id="dadf4-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="dadf4-124">**Escalation:** In alcuni casi, se un responsabile non risponde anche dopo un insieme di promemoria per un periodo di tempo, il team legale può configurare un flusso di lavoro di escalation per notificare ai responsabili non rispondenti e al loro responsabile.</span><span class="sxs-lookup"><span data-stu-id="dadf4-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="dadf4-125">Per ulteriori informazioni sulla gestione del processo di comunicazione del responsabile, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dadf4-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="dadf4-126">Creare un avviso di blocco legale</span><span class="sxs-lookup"><span data-stu-id="dadf4-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="dadf4-127">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="dadf4-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="dadf4-128">Gestire le notifiche di blocco</span><span class="sxs-lookup"><span data-stu-id="dadf4-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="dadf4-129">Confermare la ricezione di una notifica di blocco</span><span class="sxs-lookup"><span data-stu-id="dadf4-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)