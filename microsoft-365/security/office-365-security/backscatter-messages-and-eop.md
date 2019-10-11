---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. Tale elenco contiene gli indirizzi IP che inviano messaggi di posta indesiderata costituita da falsi rapporti di mancato recapito. Non è un elenco di mittenti di posta indesiderata per cui i mittenti inclusi non vengono rimossi dai server.
ms.openlocfilehash: 481203e4a91f24c9ae1992dce402b0d3e951110e
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440563"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="7e313-105">Posta indesiderata costituita da falsi rapporti di mancato recapito ed Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7e313-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="7e313-106">I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="7e313-106">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam.</span></span> <span data-ttu-id="7e313-107">Poiché EOP (Exchange Online Protection) è un servizio di filtro posta indesiderata, i messaggi di posta elettronica inviati a destinatari inesistenti a altri recapiti sospetti vengono rifiutati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="7e313-107">Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service.</span></span> <span data-ttu-id="7e313-108">In questo caso EOP genera un messaggio di mancato recapito (NDR) e lo rispedisce al "mittente".</span><span class="sxs-lookup"><span data-stu-id="7e313-108">When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender."</span></span> <span data-ttu-id="7e313-109">Dal momento che i mittenti di posta indesiderata utilizzano spesso un indirizzo di invio contraffatto o non valido nei propri messaggi, l'indirizzo del mittente a cui viene inviata la notifica di mancato recapito potrebbe generare un messaggio contenente un falso rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="7e313-109">Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message.</span></span> <span data-ttu-id="7e313-110">Quando si verifica questa condizione, i server in uscita associati alla rete EOP possono essere elencati nell'elenco di indirizzi bloccati DNS della posta indesiderata costituita da falsi rapporti di mancato recapito (DNSBL).</span><span class="sxs-lookup"><span data-stu-id="7e313-110">When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL).</span></span> <span data-ttu-id="7e313-111">Tale elenco contiene gli indirizzi IP che inviano messaggi di posta indesiderata costituita da falsi rapporti di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="7e313-111">The Backscatterer DNSBL is a list of IP addresses that send backscatter messages.</span></span> <span data-ttu-id="7e313-112">Non è un elenco di mittenti di posta indesiderata per cui i mittenti inclusi non vengono rimossi dai server.</span><span class="sxs-lookup"><span data-stu-id="7e313-112">It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span>

> [!TIP]
> <span data-ttu-id="7e313-p103">In base alle istruzioni riportate sul sito Web Backscatterer, l'utilizzo della modalità di rifiuto per tutta la posta in arrivo non è una configurazione consigliata o un utilizzo appropriato del servizio. Deve essere utilizzato invece in modalità sicura. Per ulteriori informazioni sull'implementazione della corretta configurazione della posta indesiderata costituita da falsi rapporti di mancato recapito, visitare il [sito Web Backscatterer.org](http://www.backscatterer.org/?target=usage).</span><span class="sxs-lookup"><span data-stu-id="7e313-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e313-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7e313-116">Related topics</span></span>

[<span data-ttu-id="7e313-117">Opzioni di filtro della posta indesiderata avanzate</span><span class="sxs-lookup"><span data-stu-id="7e313-117">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
