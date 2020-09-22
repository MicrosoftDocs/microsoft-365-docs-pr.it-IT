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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: L'amministratore può ottenere informazioni sulle opzioni per la configurazione del flusso di posta e del routing in Exchange Online Protection (EOP).
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200704"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="dc1e9-103">Flusso di posta in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc1e9-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dc1e9-104">In Microsoft 365 organizzazioni con cassette postali di Exchange Online o organizzazioni autonome di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li vedano.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="dc1e9-105">Sono disponibili opzioni su come instradare i messaggi che passano attraverso EOP per l'elaborazione prima che vengano instradati alle cassette postali di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="dc1e9-106">Utilizzo dei messaggi e delle opzioni di accesso ai messaggi</span><span class="sxs-lookup"><span data-stu-id="dc1e9-106">Working with messages and message access options</span></span>

<span data-ttu-id="dc1e9-107">EOP offre flessibilità nel modo in cui i messaggi vengono instradati.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="dc1e9-108">Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="dc1e9-109">[Utilizzare il blocco Edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco Edge basato su directory che consente di rifiutare i messaggi per i destinatari non validi nel perimetro della rete di servizi.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="dc1e9-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="dc1e9-111">Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="dc1e9-112">Per ulteriori informazioni sui sottodomini, vedere [Enable Mail Flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="dc1e9-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="dc1e9-113">[Configure Mail Flow using Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduce connettori e visualizza come utilizzarli per personalizzare il routing della posta.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="dc1e9-114">Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="dc1e9-115">[Filtro avanzato per i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) viene descritto come configurare i connettori se la posta viene instradata a un servizio o a un dispositivo prima di EOP.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="dc1e9-116">Nelle organizzazioni di EOP autonome, è necessario eseguire una procedura di configurazione di coppia per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="dc1e9-117">Sono descritti in dettaglio in [Configure standalone EOP per recapitare la posta indesiderata alla cartella posta indesiderata in ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="dc1e9-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="dc1e9-118">Se non si desidera spostare i messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata (noti anche come criteri di filtro dei contenuti).</span><span class="sxs-lookup"><span data-stu-id="dc1e9-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="dc1e9-119">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dc1e9-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="dc1e9-120">Verificare il flusso di posta</span><span class="sxs-lookup"><span data-stu-id="dc1e9-120">Verify mail flow</span></span>

<span data-ttu-id="dc1e9-p106">Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="dc1e9-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="dc1e9-123">[Testare il flusso di posta convalidando i connettori Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornisce le istruzioni per testare che il flusso di posta è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="dc1e9-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
