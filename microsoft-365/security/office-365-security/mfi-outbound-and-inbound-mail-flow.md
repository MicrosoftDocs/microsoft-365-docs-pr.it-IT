---
title: Insight sul flusso di posta in uscita e in ingresso nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Gli amministratori possono ottenere informazioni sull'Insight del flusso di posta in uscita e in ingresso nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: 347e53c51c347f12795008d39458773a94ff433f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577386"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="ead60-103">Insight sul flusso di posta in uscita e in ingresso nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="ead60-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="ead60-104">L'Insight sul **flusso di posta in uscita e in ingresso** nel dashboard del flusso di [posta](mail-flow-insights-v2.md) nel centro sicurezza & conformità unisce le informazioni del [rapporto connettore](view-mail-flow-reports.md#connector-report) e il precedente **rapporto di panoramica TLS** in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="ead60-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="ead60-105">Il widget Visualizza la crittografia TLS utilizzata per la connessione quando i messaggi vengono recapitati da e verso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ead60-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="ead60-106">Le connessioni stabilite con altri servizi di posta elettronica vengono crittografate tramite TLS quando TLS viene offerto da entrambi i lati.</span><span class="sxs-lookup"><span data-stu-id="ead60-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="ead60-107">Il widget offre un'istantanea dell'ultima settimana di flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="ead60-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget flusso di posta in uscita e in ingresso nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="ead60-109">Le informazioni contenute nel widget sono correlate ai connettori e alla protezione dei messaggi TLS in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ead60-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="ead60-110">Per ulteriori informazioni, vedere gli argomenti riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="ead60-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="ead60-111">Configurare il flusso di posta utilizzando i connettori</span><span class="sxs-lookup"><span data-stu-id="ead60-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="ead60-112">Come Exchange Online USA TLS per proteggere le connessioni di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ead60-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="ead60-113">Informazioni di riferimento tecnico sulla crittografia in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ead60-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="ead60-114">Protezione dei messaggi in transito (tramite TLS)</span><span class="sxs-lookup"><span data-stu-id="ead60-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="ead60-115">Quando si fa clic su **Visualizza dettagli** nel widget, il riquadro a comparsa del **messaggio protetto in transito (tramite TLS)** Mostra la protezione TLS per i messaggi in entrata e in uscita dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ead60-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Messaggi a comparsa protetti in transito (tramite TLS) visualizzati dopo aver fatto clic su Visualizza dettagli nel widget di posta elettronica in uscita e in ingresso](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="ead60-117">Attualmente, TLS 1,2 è la versione più sicura di TLS offerta da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ead60-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="ead60-118">Spesso, è necessario conoscere la crittografia TLS utilizzata per i controlli di conformità.</span><span class="sxs-lookup"><span data-stu-id="ead60-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="ead60-119">Probabilmente non si ha una relazione diretta con la maggior parte dei server di posta elettronica di origine e di destinazione (non è proprietaria e non è presente né Microsoft), pertanto non sono disponibili molte opzioni per migliorare la crittografia TLS utilizzata da tali server.</span><span class="sxs-lookup"><span data-stu-id="ead60-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="ead60-120">Tuttavia, è possibile utilizzare i [connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) per garantire la migliore protezione TLS disponibile per i messaggi inviati tra i server di posta elettronica e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ead60-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="ead60-121">Il flusso di posta tra Microsoft 365 e i server di posta elettronica personali o i server appartenenti ai propri partner è spesso più importante e sensibile rispetto ai messaggi normali, quindi si desidera applicare maggiore sicurezza e vigilanza ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="ead60-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="ead60-122">È possibile aggiornare o correggere i propri server di posta elettronica per migliorare la crittografia TLS utilizzata o rivolgersi ai propri partner per fare lo stesso.</span><span class="sxs-lookup"><span data-stu-id="ead60-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="ead60-123">Il **rapporto del connettore** Visualizza sia il volume del flusso di posta che la crittografia TLS per i messaggi che utilizzano i connettori Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ead60-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="ead60-124">È possibile fare clic sul collegamento del **rapporto connettore** per passare al [rapporto del connettore](view-mail-flow-reports.md#connector-report).</span><span class="sxs-lookup"><span data-stu-id="ead60-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="ead60-125">Se è stata rilevata la condizione associata, è possibile che nella pagina del **rapporto del connettore** siano disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ead60-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="ead60-126">**Connettore partner in ingresso che vede il flusso di posta TLS 1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="ead60-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="ead60-127">**Connettore onlocali in ingresso che vede il flusso di posta di TLS 1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="ead60-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="ead60-128">Per le connessioni TLS 1,0, è effettivamente necessario ottenere il server di posta elettronica o il server del partner aggiornato o risolto per evitare eventuali problemi quando il supporto di TLS 1,0 è obsoleto in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ead60-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="ead60-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ead60-129">See also</span></span>

<span data-ttu-id="ead60-130">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ead60-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
