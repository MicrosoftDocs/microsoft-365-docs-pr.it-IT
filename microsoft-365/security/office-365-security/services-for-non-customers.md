---
title: Servizi per non clienti che inviano posta a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Per mantenere la fiducia degli utenti nell'uso della posta elettronica, Microsoft ha messo in atto diversi criteri e tecnologie per proteggere i nostri utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206513"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="c3e2b-103">Servizi per non clienti che inviano posta a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3e2b-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c3e2b-104">L'abuso della posta elettronica, la posta indesiderata e le e-mail fraudolente (phishing) continuano a gravare sull'intero ecosistema di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="c3e2b-105">Per mantenere la fiducia degli utenti nell'uso della posta elettronica, Microsoft ha messo in atto diversi criteri e tecnologie per proteggere i nostri utenti.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="c3e2b-106">Tuttavia, Microsoft è a conoscenza del fatto che la posta elettronica legittima non deve essere influenzata negativamente.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="c3e2b-107">Di conseguenza, abbiamo creato una famiglia di servizi per aiutare i mittenti a migliorare la loro capacità di recapitare la posta elettronica agli utenti Microsoft 365 gestendo in modo proattivo la reputazione di invio.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="c3e2b-108">Questa panoramica fornisce informazioni sui vantaggi offerti all'organizzazione anche se non si è un cliente.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="c3e2b-109">Soluzioni mittente</span><span class="sxs-lookup"><span data-stu-id="c3e2b-109">Sender solutions</span></span>

****

|<span data-ttu-id="c3e2b-110">Servizio</span><span class="sxs-lookup"><span data-stu-id="c3e2b-110">Service</span></span>|<span data-ttu-id="c3e2b-111">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="c3e2b-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="c3e2b-112">Contenuto della Guida online</span><span class="sxs-lookup"><span data-stu-id="c3e2b-112">This online help content</span></span>|<span data-ttu-id="c3e2b-113">Fornisce:</span><span class="sxs-lookup"><span data-stu-id="c3e2b-113">Provides:</span></span> <ul><li><span data-ttu-id="c3e2b-114">Un punto di partenza per tutte le domande relative al recapito delle comunicazioni agli utenti di EOP.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="c3e2b-115">Include una semplice guida online con i criteri e i requisiti.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="c3e2b-116">Panoramica dei filtri per la posta indesiderata e delle tecnologie di autenticazione utilizzate da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="c3e2b-117">Supporto Tecnico Microsoft</span><span class="sxs-lookup"><span data-stu-id="c3e2b-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="c3e2b-118">Fornisce supporto self-help e escalation per i problemi di recapito.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="c3e2b-119">Portale antispam IP Delist</span><span class="sxs-lookup"><span data-stu-id="c3e2b-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="c3e2b-120">Uno strumento per inviare la richiesta di delist ip.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="c3e2b-121">Prima di inviare questa richiesta, è responsabilità del mittente assicurarsi che qualsiasi ulteriore posta proveniente dall'IP in questione non sia offensiva o dannosa.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="c3e2b-122">Segnalazione di abuso e posta indesiderata per la posta indesiderata proveniente da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3e2b-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="c3e2b-123">Impedisce l'invio di posta indesiderata e altri messaggi indesiderati da Exchange Online e l'ingombro di Internet e del sistema di posta.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="c3e2b-124">Supporto Tecnico Microsoft</span><span class="sxs-lookup"><span data-stu-id="c3e2b-124">Microsoft support</span></span>

<span data-ttu-id="c3e2b-125">Microsoft offre diverse opzioni di supporto per gli utenti che hanno problemi a inviare posta Microsoft 365 destinatari.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="c3e2b-126">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="c3e2b-126">We recommend that you:</span></span>

- <span data-ttu-id="c3e2b-127">Seguire le istruzioni contenute in qualsiasi rapporto di mancato recapito ricevuto.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="c3e2b-128">Vedere i problemi più comuni riscontrati dai non clienti in Risoluzione dei problemi relativi alla posta [inviata Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c3e2b-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="c3e2b-129">Usa il [Microsoft 365 delist per](https://sender.office.com) inviare una richiesta di rimozione dell'IP dall'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="c3e2b-130">Leggere i [forum della community Microsoft](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="c3e2b-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="c3e2b-131">Contattare il cliente che si sta tentando di inviare tramite posta elettronica utilizzando un altro metodo e chiedere loro di contattare il Supporto Tecnico Microsoft e aprire un ticket di supporto per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="c3e2b-132">In alcuni casi, per motivi legali, il supporto Tecnico Microsoft deve comunicare direttamente con il mittente proprietario dello spazio IP bloccato.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="c3e2b-133">Tuttavia, i non clienti in genere non possono aprire ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="c3e2b-134">Per ulteriori informazioni sul supporto tecnico Microsoft per Office 365, vedere [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="c3e2b-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="c3e2b-135">Portale antispam IP Delist</span><span class="sxs-lookup"><span data-stu-id="c3e2b-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="c3e2b-136">Si tratta di un portale self-service che è possibile utilizzare per rimuovere se stessi dall'Microsoft 365 dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="c3e2b-137">Utilizzare questo portale se si riceve un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Microsoft 365 e non si pensa di doverlo fare.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="c3e2b-138">Per altre informazioni, vedere [Usare il portale per l'esclusione di indirizzi IP dal filtro della posta indesiderata per rimuoversi dall'elenco di mittenti bloccati](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="c3e2b-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="c3e2b-139">Segnalazione di abuso e posta indesiderata per la posta indesiderata proveniente da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3e2b-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="c3e2b-140">A volte Microsoft365 viene utilizzato da terze parti per inviare posta indesiderata, in violazione delle condizioni per l'utilizzo e i criteri.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="c3e2b-141">Se si riceve posta indesiderata da Office 365, è possibile segnalare questi messaggi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3e2b-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="c3e2b-142">Per istruzioni, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c3e2b-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>