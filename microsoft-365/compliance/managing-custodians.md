---
title: Utilizzo dei depositari in Advanced eDiscovery
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
description: Lo strumento di gestione dei depositari in Advanced eDiscovery consente di gestire il flusso di lavoro attorno all'identificazione, alla conservazione e alla raccolta dei dati associati alle persone di interesse in un caso legale.
ms.openlocfilehash: fd796471ae4caeafbabc7b588dcf03b8cad80bc4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600493"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="c0655-103">Utilizzo dei depositari in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c0655-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="c0655-104">Quando un'organizzazione risponde a un'indagine legale, il flusso di lavoro relativo all'identificazione, alla conservazione e alla raccolta di contenuti potenzialmente rilevanti si basa sulle persone dell'organizzazione che sono depositarie dei dati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="c0655-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="c0655-105">In eDiscovery, questi individui sono denominati *depositari dei dati* (o solo *depositari*) e sono definiti come "persone che hanno il controllo amministrativo di un documento o di un file elettronico".</span><span class="sxs-lookup"><span data-stu-id="c0655-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="c0655-106">Ad esempio, il custode di un messaggio di posta elettronica potrebbe essere il proprietario della cassetta postale che contiene il messaggio pertinente.</span><span class="sxs-lookup"><span data-stu-id="c0655-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="c0655-107">Quando viene avviata un'indagine, il team di eDiscovery deve identificare rapidamente tutti i depositari rilevanti e le origini dati correlate al caso.</span><span class="sxs-lookup"><span data-stu-id="c0655-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="c0655-108">Nel corso del tempo, l'elenco dei depositari e delle relative origini dati può aumentare o decreasse.</span><span class="sxs-lookup"><span data-stu-id="c0655-108">Over time, the list of custodians and their data sources may increase or decreasse.</span></span> <span data-ttu-id="c0655-109">Di conseguenza, le organizzazioni devono mantenere un processo controllato attorno all'identificazione, alla conservazione e alla raccolta di contenuto affidatario per tutto il ciclo di vita di un caso.</span><span class="sxs-lookup"><span data-stu-id="c0655-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="c0655-110">In un caso avanzato di eDiscovery, i team legali possono aggiungere individui all'interno della propria organizzazione come depositari e identificare e preservare automaticamente le origini dati di tipo affidatario, ad esempio le cassette postali di Exchange, gli account OneDrive e i siti di SharePoint e teams.</span><span class="sxs-lookup"><span data-stu-id="c0655-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="c0655-111">Utilizzando lo strumento di gestione del custode incorporato in Advanced eDiscovery, le organizzazioni possono proteggere le informazioni archiviate elettronicamente dall'eliminazione involontaria (o intenzionale).</span><span class="sxs-lookup"><span data-stu-id="c0655-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="c0655-112">In questo modo è possibile eliminare il processo che richiede tempo e l'errore di dover eseguire manualmente i processi di archiviazione legale.</span><span class="sxs-lookup"><span data-stu-id="c0655-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="c0655-113">Per ulteriori informazioni sull'utilizzo dei depositari, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0655-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="c0655-114">Aggiungere responsabili a un caso</span><span class="sxs-lookup"><span data-stu-id="c0655-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="c0655-115">Gestire i depositari in un caso</span><span class="sxs-lookup"><span data-stu-id="c0655-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="c0655-116">Visualizzare l'attività dei responsabili</span><span class="sxs-lookup"><span data-stu-id="c0655-116">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a><span data-ttu-id="c0655-117">Autorizzazioni avanzate di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c0655-117">Advanced eDiscovery permissions</span></span>

<span data-ttu-id="c0655-118">In Advanced eDiscovery, è possibile utilizzare il gruppo di ruoli di eDiscovery Manager incorporato per assegnare le autorizzazioni necessarie agli investigatori legali in modo che possano gestire il flusso di lavoro end-to-end in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c0655-118">In Advanced eDiscovery, you can use the built-in eDiscovery Manager role group to assign the necessary permissions to legal investigators so they can manage the end-to-end workflow in Advanced eDiscovery.</span></span> <span data-ttu-id="c0655-119">In alternativa, è possibile creare gruppi di ruoli personalizzati con un sottoinsieme dei ruoli necessari per eseguire determinate azioni in un caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c0655-119">Alternatively, you can create custom role groups with a subset of the roles necessary to perform certain actions in a case in Advanced eDiscovery.</span></span> <span data-ttu-id="c0655-120">Per ulteriori informazioni sui ruoli correlati a eDiscovery, vedere [assign eDiscovery Permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c0655-120">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
