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
description: Potrebbe essere necessario informare i depositari dell'obbligo di conservare le informazioni archiviate elettronicamente come parte di un'indagine legale. Advanced eDiscovery consente di gestire facilmente il processo di notifica di blocco.
ms.openlocfilehash: 703034088b03badae309961c2abda9db80425b99
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080278"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="07910-104">Confermare la ricezione di una notifica di blocco</span><span class="sxs-lookup"><span data-stu-id="07910-104">Acknowledge a hold notification</span></span>

<span data-ttu-id="07910-105">Quando si risponde a una richiesta di regolamentazione o a un'indagine, potrebbe essere necessario informare i depositari dell'obbligo di conservare le informazioni archiviate elettronicamente (ESI) e qualsiasi materiale pertinente a una questione legale attiva o imminente.</span><span class="sxs-lookup"><span data-stu-id="07910-105">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="07910-106">Una volta inviati, i team legali devono sapere che ogni custode ha ricevuto, letto, compreso e accettato di seguire le istruzioni fornite.</span><span class="sxs-lookup"><span data-stu-id="07910-106">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="07910-107">Per contribuire a ridurre il tempo, il costo e lo sforzo di follow-up con i propri depositari, Advanced eDiscovery consente di inviare e seguire le notifiche di archiviazione legale tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="07910-107">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="07910-108">Oltre alle notifiche di posta elettronica, ogni custode avrà accesso a un portale di conformità individualizzato, consentendo ai depositari di essere informati delle modifiche apportate al loro stato di obbligo.</span><span class="sxs-lookup"><span data-stu-id="07910-108">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="07910-109">Notifiche tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="07910-109">Email notifications</span></span>

<span data-ttu-id="07910-110">Dopo che è stata emessa una notifica di conservazione legale, ogni custode riceverà un messaggio di posta elettronica univoco e personalizzato contenente l'avviso di conservazione legale definito e le istruzioni aggiunte.</span><span class="sxs-lookup"><span data-stu-id="07910-110">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="07910-111">Vedere come è possibile utilizzare l' [editor di comunicazione](using-communications-editor.md) incorporato per consentire ai depositari di riconoscere la propria notifica o accedere al proprio portale di conformità direttamente dal proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="07910-111">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="07910-112">In base alla configurazione della notifica di conservazione legale, i depositari possono ricevere gli avvisi seguenti:</span><span class="sxs-lookup"><span data-stu-id="07910-112">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="07910-113">**Avviso di rilascio:** Il primo avviso inviato al custode.</span><span class="sxs-lookup"><span data-stu-id="07910-113">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="07910-114">Questo avviso conterrà le istruzioni di rilascio e l'avviso di blocco aggiunto alla fine del messaggio.</span><span class="sxs-lookup"><span data-stu-id="07910-114">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="07910-115">**Avviso di promemoria:** Se abilitato, un avviso di promemoria verrà inviato ai depositari in base alla frequenza e all'intervallo specificati.</span><span class="sxs-lookup"><span data-stu-id="07910-115">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="07910-116">I promemoria continueranno a essere inviati fino a quando il custode non avrà riconosciuto la propria notifica o fino a quando il numero di promemoria non è stato esaurito.</span><span class="sxs-lookup"><span data-stu-id="07910-116">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="07910-117">**Avviso di escalation:** Se abilitato, un avviso di escalation verrà inviato al custode e al Manager dopo che le notifiche di promemoria sono state esaurite.</span><span class="sxs-lookup"><span data-stu-id="07910-117">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="07910-118">Il sistema invierà automaticamente le notifiche di escalation fino a quando non è stato completato il numero di escalation specificato o finché il custode non riconosce la notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="07910-118">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="07910-119">**Avviso di ristampa:** Nel corso di un'indagine, se il contenuto dell'avviso di conservazione viene aggiornato, l'avviso aggiornato verrà inviato automaticamente al custode.</span><span class="sxs-lookup"><span data-stu-id="07910-119">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="07910-120">**Avviso di rilascio:** Quando un custode viene rilasciato dal caso, verrà inviato l'avviso di rilascio.</span><span class="sxs-lookup"><span data-stu-id="07910-120">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="07910-121">Portale di conformità</span><span class="sxs-lookup"><span data-stu-id="07910-121">Compliance Portal</span></span>

<span data-ttu-id="07910-122">Oltre alle notifiche tramite posta elettronica, ogni custode avrà accesso a un portale di conformità univoco.</span><span class="sxs-lookup"><span data-stu-id="07910-122">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="07910-123">Tramite il portale, ogni custode può visualizzare, accedere e riconoscere le notifiche di blocco attive.</span><span class="sxs-lookup"><span data-stu-id="07910-123">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portale di conformità per un custode](../media/CustodianPortal.jpg)
