---
title: Flusso di posta in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: L'amministratore può ottenere informazioni sulle opzioni per la configurazione del flusso di posta e del routing in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd5bfcc95227c59f645422d4939ea6ff77bee1e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206363"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="1d9fa-103">Flusso di posta in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1d9fa-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1d9fa-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="1d9fa-104">**Applies to**</span></span>
- [<span data-ttu-id="1d9fa-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1d9fa-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1d9fa-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="1d9fa-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1d9fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d9fa-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1d9fa-108">Nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online o nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti le vedano.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="1d9fa-109">Sono disponibili opzioni su come instradare i messaggi che passano attraverso EOP per l'elaborazione prima che siano instradati alle cartelle Posta in arrivo dei lavoratori.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="1d9fa-110">Utilizzo dei messaggi e delle opzioni di accesso ai messaggi</span><span class="sxs-lookup"><span data-stu-id="1d9fa-110">Working with messages and message access options</span></span>

<span data-ttu-id="1d9fa-111">EOP offre flessibilità nel modo in cui i messaggi vengono instradati.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="1d9fa-112">Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="1d9fa-113">[Usare Il blocco edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco edge basato su directory che consente di rifiutare i messaggi per i destinatari non validi nel perimetro della rete del servizio.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="1d9fa-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="1d9fa-115">Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="1d9fa-116">Per ulteriori informazioni sui sottodomini, vedere [Enable mail flow for subdomains in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="1d9fa-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="1d9fa-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduce i connettori e mostra come usarli per personalizzare il routing della posta.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="1d9fa-118">Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="1d9fa-119">[Il filtro avanzato per i connettori](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) descrive come configurare i connettori se la posta viene instradata a un servizio o a un dispositivo prima di EOP.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="1d9fa-120">Nelle organizzazioni EOP autonome, è necessario eseguire un paio di passaggi di configurazione per assicurarsi che la posta indesiderata venga instradata correttamente alla cartella posta indesiderata di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="1d9fa-121">Queste informazioni sono dettagliate in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="1d9fa-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="1d9fa-122">Se non si desidera spostare i messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata (noti anche come criteri di filtro del contenuto).</span><span class="sxs-lookup"><span data-stu-id="1d9fa-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="1d9fa-123">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1d9fa-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="1d9fa-124">Verificare il flusso di posta</span><span class="sxs-lookup"><span data-stu-id="1d9fa-124">Verify mail flow</span></span>

<span data-ttu-id="1d9fa-p106">Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="1d9fa-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="1d9fa-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span><span class="sxs-lookup"><span data-stu-id="1d9fa-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>