---
title: Confermare la ricezione di una notifica di blocco
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
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come usare le Advanced eDiscovery per inviare e seguire le notifiche di blocco legale tramite posta elettronica, nonché monitorare lo stato dell'obbligo.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034886"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="bdb9c-103">Confermare la ricezione di una notifica di blocco</span><span class="sxs-lookup"><span data-stu-id="bdb9c-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="bdb9c-104">Quando si risponde a una richiesta o a un'indagine normativa, potrebbe essere necessario informare i custodi dell'obbligo di conservare le informazioni archiviate elettronicamente (ESI) e qualsiasi materiale che possa essere rilevante per una questione legale attiva o imminente.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="bdb9c-105">Una volta inviato, i team legali devono sapere che ogni responsabile ha ricevuto, letto, compreso e accettato di seguire le istruzioni fornite.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="bdb9c-106">Per ridurre il tempo, i costi e gli sforzi per seguire i tuoi custodi, Advanced eDiscovery consente di inviare e seguire le notifiche di blocco legale tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="bdb9c-107">Oltre agli avvisi tramite posta elettronica, ogni responsabile avrà accesso a un portale di conformità individualizzato, consentendo ai custodi di essere informati delle modifiche apportate al loro stato di obbligo.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="bdb9c-108">Notifiche tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="bdb9c-108">Email notifications</span></span>

<span data-ttu-id="bdb9c-109">Dopo l'emissione di una notifica di blocco legale, ogni responsabile riceverà un'e-mail univoca e personalizzata contenente l'avviso di blocco legale definito e le istruzioni aggiunte.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="bdb9c-110">Scopri come puoi usare  [l'editor](using-communications-editor.md) di comunicazione incorporato per consentire ai tuoi custodi di confermare l'avviso o accedere al portale di conformità direttamente dalla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="bdb9c-111">In base alla configurazione della notifica di blocco legale, i tuoi custodi potrebbero ricevere le seguenti notifiche:</span><span class="sxs-lookup"><span data-stu-id="bdb9c-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="bdb9c-112">**Avviso di rilascio:** Il primo avviso inviato al tuo responsabile.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="bdb9c-113">Questo avviso conterrà le istruzioni di rilascio e l'avviso di blocco aggiunto alla fine del messaggio.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="bdb9c-114">**Avviso promemoria:** Se abilitata, ai tuoi custodi verrà inviata una notifica di promemoria in base alla frequenza e all'intervallo specificati.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="bdb9c-115">I promemoria continueranno a essere inviati fino a quando il custode non avrà riconosciuto l'avviso o finché il numero di promemoria non sarà esaurito.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="bdb9c-116">**Avviso di escalation:** Se abilitata, una notifica di escalation verrà inviata al responsabile e al responsabile dopo che le notifiche di promemoria sono state esaurite.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="bdb9c-117">Il sistema invierà automaticamente avvisi di escalation fino al completamento del numero specificato di escalation o fino a quando il responsabile non riconosce la notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="bdb9c-118">**Avviso di riemissione:** Nel corso di un'indagine, se il contenuto dell'avviso di blocco viene aggiornato, l'avviso aggiornato verrà inviato automaticamente al responsabile.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="bdb9c-119">**Avviso di rilascio:** Quando un responsabile viene rilasciato dal caso, gli verrà inviato l'avviso di rilascio.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="bdb9c-120">Portale di conformità</span><span class="sxs-lookup"><span data-stu-id="bdb9c-120">Compliance Portal</span></span>

<span data-ttu-id="bdb9c-121">Oltre alle notifiche tramite posta elettronica, ogni responsabile avrà accesso a un portale di conformità univoco.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="bdb9c-122">Tramite il portale, ogni responsabile può visualizzare, accedere e confermare le notifiche di blocco attive.</span><span class="sxs-lookup"><span data-stu-id="bdb9c-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portale di conformità per un responsabile](../media/CustodianPortal.jpg)
