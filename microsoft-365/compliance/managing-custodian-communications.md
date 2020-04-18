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
description: Advanced eDiscovery facilita la gestione del flusso di lavoro di notifica per la conservazione legale in merito alla notifica ai depositari nelle indagini legali.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551242"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="1e76e-103">Utilizzare le comunicazioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1e76e-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="1e76e-104">Advanced eDiscovery consente ai reparti legali di semplificare i propri processi per il monitoraggio e la distribuzione delle notifiche di blocco legale.</span><span class="sxs-lookup"><span data-stu-id="1e76e-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="1e76e-105">Lo strumento di comunicazione del custode consente ai servizi legali di gestire e automatizzare l'intero processo di conservazione, dalle notifiche iniziali ai promemoria e alle escalation, tutto in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="1e76e-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="1e76e-106">Che cos'è una notifica di conservazione legale?</span><span class="sxs-lookup"><span data-stu-id="1e76e-106">What is a legal hold notification?</span></span>

<span data-ttu-id="1e76e-107">Avviso di conservazione (noto anche come *blocco per controversia*legale) è una notifica inviata dal reparto legale di un'organizzazione ai dipendenti, al personale contingente o ai depositari di dati che potrebbero essere rilevanti per un'indagine legale.</span><span class="sxs-lookup"><span data-stu-id="1e76e-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="1e76e-108">Tali notifiche indicano ai depositari di conservare le informazioni archiviate elettronicamente, nonché qualsiasi contenuto che potrebbe essere pertinente a una questione legale attiva o imminente.</span><span class="sxs-lookup"><span data-stu-id="1e76e-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="1e76e-109">I team legali devono sapere che ogni custode ha ricevuto, letto, compreso e ha accettato di conformarsi alle istruzioni fornite.</span><span class="sxs-lookup"><span data-stu-id="1e76e-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="1e76e-110">Processo di notifica per il blocco legale</span><span class="sxs-lookup"><span data-stu-id="1e76e-110">The legal hold notification process</span></span>

<span data-ttu-id="1e76e-111">Un'organizzazione ha il dovere di conservare le informazioni rilevanti quando viene a conoscenza di una controversia legale imminente o di un'indagine di regolamentazione.</span><span class="sxs-lookup"><span data-stu-id="1e76e-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="1e76e-112">Per soddisfare i requisiti di conservazione di un'indagine, l'organizzazione deve informare immediatamente i potenziali depositari del proprio dovere di preservare le informazioni rilevanti.</span><span class="sxs-lookup"><span data-stu-id="1e76e-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="1e76e-113">Con Advanced eDiscovery, i team legali possono creare e personalizzare il flusso di lavoro di notifica per la conservazione legale.</span><span class="sxs-lookup"><span data-stu-id="1e76e-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="1e76e-114">Lo strumento di comunicazione del custode consente ai team legali di configurare le notifiche e i flussi di lavoro seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e76e-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="1e76e-115">**Avviso di rilascio:** Un avviso per la conservazione legale è emesso (o iniziato) da una notifica da parte del reparto legale ai depositari che potrebbero avere informazioni rilevanti sulla questione del caso.</span><span class="sxs-lookup"><span data-stu-id="1e76e-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="1e76e-116">Questo avviso indica ai depositari di conservare tutte le informazioni che potrebbero essere necessarie per l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="1e76e-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="1e76e-117">**Notifica di riemissione:** Nel corso di un caso, è possibile che ai depositari venga richiesto di conservare contenuto aggiuntivo (o meno contenuto) rispetto a quanto richiesto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1e76e-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="1e76e-118">Per questo scenario, è possibile aggiornare l'avviso di conservazione esistente e ristamparlo in depositari.</span><span class="sxs-lookup"><span data-stu-id="1e76e-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="1e76e-119">**Avviso di rilascio:** Dopo aver risolto il problema e il custode non è più soggetto a un requisito di conservazione, il custode può essere rilasciato dal caso.</span><span class="sxs-lookup"><span data-stu-id="1e76e-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="1e76e-120">Inoltre, è possibile notificare al custode che non sono più necessari per mantenere il contenuto e fornire istruzioni su come riprendere la normale attività lavorativa in relazione ai dati.</span><span class="sxs-lookup"><span data-stu-id="1e76e-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="1e76e-121">**Promemoria e escalation:** In alcuni casi, solo l'emissione di un avviso non è sufficiente per soddisfare i requisiti di individuazione legale.</span><span class="sxs-lookup"><span data-stu-id="1e76e-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="1e76e-122">Con ogni notifica, i team legali possono programmare una serie di flussi di lavoro di promemoria e di escalation per il follow-up automatico con custodi insensibili.</span><span class="sxs-lookup"><span data-stu-id="1e76e-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="1e76e-123">**Promemoria:** Dopo che è stato emesso o riemesso un avviso per la conservazione legale in una serie di depositari, un'organizzazione può impostare i promemoria per avvisare gli amministratori che non rispondono.</span><span class="sxs-lookup"><span data-stu-id="1e76e-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="1e76e-124">**Escalation:** In alcuni casi, se un custode rimane inattivo anche dopo una serie di promemoria per un determinato periodo di tempo, il team legale può impostare un flusso di lavoro di escalation per notificare ai depositari insensibili e al loro manager.</span><span class="sxs-lookup"><span data-stu-id="1e76e-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="1e76e-125">Per ulteriori informazioni sulla gestione del processo di comunicazione del custode, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e76e-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="1e76e-126">Creare un avviso per la conservazione legale</span><span class="sxs-lookup"><span data-stu-id="1e76e-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="1e76e-127">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="1e76e-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="1e76e-128">Gestire le notifiche di blocco</span><span class="sxs-lookup"><span data-stu-id="1e76e-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="1e76e-129">Confermare la ricezione di una notifica di blocco</span><span class="sxs-lookup"><span data-stu-id="1e76e-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)