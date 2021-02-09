---
title: Informazioni dettagliate sul flusso di posta in ingresso e in uscita nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Gli amministratori possono ottenere informazioni dettagliate sul flusso di posta in ingresso e in uscita nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcce6981369217f21ace5fdf2abbf23ca8606569
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150809"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="0d749-103">Informazioni dettagliate sul flusso di posta in ingresso e in uscita nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="0d749-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d749-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="0d749-104">**Applies to**</span></span>
- [<span data-ttu-id="0d749-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0d749-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="0d749-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="0d749-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="0d749-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d749-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="0d749-108">Le **informazioni** dettagliate sul flusso di posta [in](https://protection.office.com) ingresso e in uscita nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza & conformità combinano le informazioni del report connettore e del precedente [report](view-mail-flow-reports.md#connector-report) di panoramica **di TLS** in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="0d749-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="0d749-109">Il widget visualizza la crittografia TLS utilizzata per la connessione quando i messaggi vengono recapitati da e verso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d749-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="0d749-110">Le connessioni stabilite con altri servizi di posta elettronica vengono crittografate da TLS quando TLS è offerto da entrambi i lati.</span><span class="sxs-lookup"><span data-stu-id="0d749-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="0d749-111">Il widget offre uno snapshot dell'ultima settimana del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="0d749-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget Flusso di posta in ingresso e in uscita nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="0d749-113">Le informazioni nel widget sono correlate ai connettori e alla protezione dei messaggi TLS in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d749-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="0d749-114">Per ulteriori informazioni, vedere gli argomenti riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="0d749-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="0d749-115">Configurare il flusso di posta utilizzando i connettori</span><span class="sxs-lookup"><span data-stu-id="0d749-115">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="0d749-116">Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0d749-116">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="0d749-117">Informazioni di riferimento tecniche sulla crittografia in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d749-117">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="0d749-118">Messaggio protetto in transito (da TLS)</span><span class="sxs-lookup"><span data-stu-id="0d749-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="0d749-119">Quando si fa clic su **Visualizza** dettagli nel widget, il riquadro a comparsa Messaggio protetto in transito **(da TLS)** mostra la protezione TLS per i messaggi che entrano e lasciano l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d749-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Riquadro a comparsa Messaggi protetti in transito (da TLS) che viene visualizzato dopo aver fatto clic su Visualizza dettagli nel widget Posta elettronica in uscita e in ingresso](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="0d749-121">Attualmente, TLS 1.2 è la versione più sicura di TLS offerta da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d749-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="0d749-122">Spesso, è necessario conoscere la crittografia TLS utilizzata per i controlli di conformità.</span><span class="sxs-lookup"><span data-stu-id="0d749-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="0d749-123">Probabilmente non si ha una relazione diretta con la maggior parte dei server di posta elettronica di origine e di destinazione (non si è proprietari di tali server e nemmeno con Microsoft), quindi non sono disponibili molte opzioni per migliorare la crittografia TLS utilizzata da tali server.</span><span class="sxs-lookup"><span data-stu-id="0d749-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="0d749-124">Tuttavia, è possibile utilizzare [i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) per garantire la migliore protezione TLS disponibile per i messaggi inviati tra i server di posta elettronica e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d749-124">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="0d749-125">Il flusso di posta tra Microsoft 365 e i server o i server di posta elettronica che appartengono ai partner è spesso più importante e sensibile dei messaggi normali, quindi è necessario applicare maggiore sicurezza e vigilanza a tali messaggi.</span><span class="sxs-lookup"><span data-stu-id="0d749-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="0d749-126">È possibile aggiornare o correggere i propri server di posta elettronica per migliorare la crittografia TLS in uso oppure contattare i partner per eseguire la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="0d749-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="0d749-127">Il **rapporto connettore** visualizza sia il volume del flusso di posta che la crittografia TLS per i messaggi che utilizzano i connettori di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d749-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="0d749-128">È possibile fare clic sul collegamento del **rapporto** connettore per passare al [rapporto connettore.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="0d749-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="0d749-129">Se è stata rilevata la condizione associata, nella pagina del **report** del connettore potrebbero essere disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d749-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="0d749-130">**Il connettore partner in ingresso vede un flusso di posta TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="0d749-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="0d749-131">**Connettore OnPremises in ingresso che vede un flusso di posta TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="0d749-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="0d749-132">Per le connessioni TLS 1.0, è effettivamente necessario aggiornare o risolvere il server di posta elettronica o il server del partner per evitare problemi quando il supporto di TLS 1.0 è deprecato in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d749-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d749-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d749-133">See also</span></span>

<span data-ttu-id="0d749-134">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="0d749-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
