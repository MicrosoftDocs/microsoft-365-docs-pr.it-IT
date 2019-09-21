---
title: Riconoscere le notifiche di esenzioni
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
description: ''
ms.openlocfilehash: 1a627a0927d6ffa2244e9f3580867379ff1fbdc5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083385"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="ad073-102">Confermare la ricezione di una notifica di blocco</span><span class="sxs-lookup"><span data-stu-id="ad073-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="ad073-103">Quando si risponde a una richiesta di regolamentazione o a un'indagine, potrebbe essere necessario informare i depositari dell'obbligo di conservare le informazioni archiviate elettronicamente (ESI), nonché qualsiasi materiale pertinente a una questione legale attiva o imminente.</span><span class="sxs-lookup"><span data-stu-id="ad073-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="ad073-104">Una volta inviati, i team legali devono sapere che ogni custode ha ricevuto, letto e compreso e ha accettato di conformarsi alle istruzioni fornite.</span><span class="sxs-lookup"><span data-stu-id="ad073-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

<span data-ttu-id="ad073-105">Per contribuire a ridurre il tempo, il costo e lo sforzo di follow-up con i propri depositari, Advanced eDiscovery consente di inviare e seguire le notifiche di archiviazione legale tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ad073-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow-up on legal hold notifications through email.</span></span> <span data-ttu-id="ad073-106">Oltre alle notifiche di posta elettronica, ogni custode avrà accesso anche a un portale di conformità individualizzato, consentendo ai depositari di essere informati delle modifiche apportate al loro stato di obbligo.</span><span class="sxs-lookup"><span data-stu-id="ad073-106">In addition to email notices, each custodian will also have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="ad073-107">Notifiche tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ad073-107">Email notifications</span></span>
<span data-ttu-id="ad073-108">Dopo aver emesso una notifica per la conservazione legale, ogni custode riceverà un messaggio di posta elettronica univoco e personalizzato contenente l'avviso di conservazione legale definito e le istruzioni aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ad073-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="ad073-109">Vedere come è possibile utilizzare l' [editor di comunicazione](using-communications-editor.md) incorporato per consentire ai depositari di riconoscere la propria notifica o accedere al proprio portale di conformità direttamente dal proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ad073-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="ad073-110">In base alla configurazione della notifica di conservazione legale, i depositari possono ricevere gli avvisi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad073-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="ad073-111">**Avviso di pubblicazione** -questo è il primo avviso inviato al custode.</span><span class="sxs-lookup"><span data-stu-id="ad073-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="ad073-112">Questo conterrà le istruzioni di rilascio e l'avviso di blocco aggiunto alla fine del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ad073-112">This will contain your issuance instructions as well as the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="ad073-113">**Avviso di promemoria** -se abilitato, un avviso di promemoria verrà inviato ai depositari in base alla frequenza e all'intervallo specificati.</span><span class="sxs-lookup"><span data-stu-id="ad073-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="ad073-114">I promemoria continueranno a essere inviati fino a quando il custode non avrà riconosciuto la propria notifica o fino a quando il numero di promemoria non è stato esaurito.</span><span class="sxs-lookup"><span data-stu-id="ad073-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="ad073-115">**Avviso di escalation** -se abilitato, un avviso di escalation verrà inviato al custode e al loro manager dopo che le notifiche di promemoria sono state esaurite.</span><span class="sxs-lookup"><span data-stu-id="ad073-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="ad073-116">Il sistema invierà automaticamente le notifiche di escalation fino a quando non sono state completate le escalation allocate o fino a quando il custode non riconosce la notifica di esenzione.</span><span class="sxs-lookup"><span data-stu-id="ad073-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="ad073-117">**Avviso di riemissione** -nel corso di un'indagine, se il contenuto dell'avviso di conservazione viene aggiornato, l'avviso aggiornato verrà inviato automaticamente al custode.</span><span class="sxs-lookup"><span data-stu-id="ad073-117">**Re-issue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="ad073-118">**Avviso di rilascio** -quando un custode viene rilasciato dal caso, verrà inviato l'avviso di rilascio.</span><span class="sxs-lookup"><span data-stu-id="ad073-118">**Release notice** - When a custodian is released from the case, they will be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="ad073-119">Portale di conformità</span><span class="sxs-lookup"><span data-stu-id="ad073-119">Compliance Portal</span></span>
<span data-ttu-id="ad073-120">Oltre alle notifiche tramite posta elettronica, ogni custode avrà anche accesso a un portale di conformità univoco.</span><span class="sxs-lookup"><span data-stu-id="ad073-120">In addition to the email notifications, each custodian will also have access to a unique Compliance Portal.</span></span> <span data-ttu-id="ad073-121">Tramite il portale, ogni custode sarà in grado di visualizzare, accedere e riconoscere le notifiche di blocco attive.</span><span class="sxs-lookup"><span data-stu-id="ad073-121">Through the portal, each custodian will be able to view, access, and acknowledge their active hold notifications.</span></span>

![Portale di conformità per un custode](media/CustodianPortal.jpg)
