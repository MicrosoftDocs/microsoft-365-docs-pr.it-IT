---
title: Risolvere le informazioni dettagliate del dominio del mittente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sull'Insight del dominio del mittente Fix nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635173"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="57f71-103">Risolvere le informazioni dettagliate del dominio del mittente</span><span class="sxs-lookup"><span data-stu-id="57f71-103">Fix sender domain insight</span></span>

<span data-ttu-id="57f71-104">Microsoft 365 richiede l'invio di messaggi da ambienti di posta elettronica locali interni a Microsoft 365 per rispondere a determinati criteri di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="57f71-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="57f71-105">È stato creato un connettore in ingresso in Microsoft 365 per autenticare le connessioni SMTP dal server di posta elettronica locale utilizzando l'indirizzo IP di origine o un certificato.</span><span class="sxs-lookup"><span data-stu-id="57f71-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="57f71-106">Il server di posta elettronica locale è stato configurato per inoltrare la posta elettronica tramite Microsoft 365 al mondo esterno.</span><span class="sxs-lookup"><span data-stu-id="57f71-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="57f71-107">Nella configurazione, una delle seguenti affermazioni è vera:</span><span class="sxs-lookup"><span data-stu-id="57f71-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="57f71-108">Il dominio di posta elettronica del mittente è registrato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="57f71-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="57f71-109">Per ulteriori informazioni, vedere Add Domains in Office 365.</span><span class="sxs-lookup"><span data-stu-id="57f71-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="57f71-110">Il server di posta elettronica locale è configurato per l'utilizzo di un certificato per l'invio di posta elettronica a Microsoft 365, il certificato contiene o corrisponde esattamente a un nome di dominio registrato in Microsoft 365 ed è stato creato un connettore basato su certificato in Microsoft 365 con tale dominio.</span><span class="sxs-lookup"><span data-stu-id="57f71-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="57f71-111">I messaggi che non soddisfano i criteri non verranno attribuiti all'organizzazione e potrebbero essere rifiutati.</span><span class="sxs-lookup"><span data-stu-id="57f71-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="57f71-112">La **correzione del dominio del mittente** consente di visualizzare la posta elettronica dall'ambiente locale che non soddisfa i criteri, consente di identificare le macchine e gli account utente potenzialmente compromessi nell'ambiente di posta elettronica locale e consente di eseguire azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="57f71-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![L'Insight del dominio del mittente Fix nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="57f71-114">Quando si fa clic su **Visualizza dettagli**, si viene indirizzati a un altro widget con maggiori dettagli, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="57f71-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Il widget dettagli nell'Insight del dominio del mittente FIX](../../media/sender-domain-view-details.png)

<span data-ttu-id="57f71-116">Verrà visualizzato il connettore in ingresso utilizzato per recapitare i messaggi a Office 365.</span><span class="sxs-lookup"><span data-stu-id="57f71-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="57f71-117">È inoltre possibile fare clic su **Visualizza ID messaggio di esempio** per visualizzare i dettagli relativi ai messaggi inviati dall'ambiente di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="57f71-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="57f71-118">Poiché questi messaggi sono stati rifiutati da Office 365, non è possibile utilizzare la traccia dei messaggi, ma gli ID del messaggio di esempio possono essere rintracciati nell'ambiente di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="57f71-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Visualizzare gli ID dei messaggi di esempio nell'Insight del dominio del mittente FIX](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="57f71-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57f71-120">See also</span></span>

<span data-ttu-id="57f71-121">Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="57f71-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
