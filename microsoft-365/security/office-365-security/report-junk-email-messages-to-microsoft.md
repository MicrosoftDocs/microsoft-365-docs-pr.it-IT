---
title: Segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Gli amministratori possono conoscere i diversi modi per segnalare messaggi e file a Microsoft per l'analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d7534d5d88fe19fba39ac1ebef16c72cac25cae7
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625042"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="645b7-103">Segnalazione di messaggi e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="645b7-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="645b7-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="645b7-104">**Applies to**</span></span>
- [<span data-ttu-id="645b7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="645b7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="645b7-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="645b7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="645b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="645b7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="645b7-108">Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, sia gli utenti che gli amministratori hanno diversi metodi per segnalare i messaggi di posta elettronica e i file a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="645b7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="645b7-109">Metodo</span><span class="sxs-lookup"><span data-stu-id="645b7-109">Method</span></span>|<span data-ttu-id="645b7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="645b7-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="645b7-111">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="645b7-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="645b7-112">Il metodo di creazione di report consigliato per gli amministratori nelle organizzazioni con Exchange Online cassette postali (non disponibile in EOP autonomo).</span><span class="sxs-lookup"><span data-stu-id="645b7-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="645b7-113">Abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="645b7-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="645b7-114">Funziona con Outlook e Outlook sul Web (in precedenza noto come Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="645b7-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="645b7-115">A seconda dell'abbonamento, i messaggi segnalati dagli utenti con i componenti aggiuntivi sono disponibili nel portale per gli invii di [amministratori,](admin-submission.md)nei risultati di analisi e risposta [automatizzati (AIR),](air-view-investigation-results.md)nel [report](view-email-security-reports.md#user-reported-messages-report)Messaggi segnalati dagli utenti e in [Esplora minacce.](threat-explorer-views.md#email--submissions)</span><span class="sxs-lookup"><span data-stu-id="645b7-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="645b7-116">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="645b7-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="645b7-117">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="645b7-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="645b7-118">Segnalare falsi positivi e falsi negativi a Outlook</span><span class="sxs-lookup"><span data-stu-id="645b7-118">Report false positives and false negatives to Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="645b7-119">Inviare falsi positivi (buona posta elettronica bloccata o inviata alla cartella posta indesiderata) e falsi negativi (posta elettronica indesiderata o phish recapitati nella posta in arrivo) a Exchange Online Protection (EOP) utilizzando la funzionalità Segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="645b7-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="645b7-120">Inviare manualmente i messaggi a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="645b7-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="645b7-121">Inviare manualmente i messaggi allegati a indirizzi di posta elettronica Microsoft specifici per posta indesiderata, non posta indesiderata e phishing.</span><span class="sxs-lookup"><span data-stu-id="645b7-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="645b7-122">Usare le regole del flusso di posta per vedere quali utenti segnalano a Microsoft</span><span class="sxs-lookup"><span data-stu-id="645b7-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="645b7-123">Informazioni su come creare una regola del flusso di posta (nota anche come regola di trasporto) che invia una notifica quando gli utenti segnalano messaggi a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="645b7-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="645b7-124">Inviare malware e non malware a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="645b7-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="645b7-125">Utilizzare il Intelligence di sicurezza Microsoft per inviare allegati e altri file.</span><span class="sxs-lookup"><span data-stu-id="645b7-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="645b7-126">Se i messaggi di posta indesiderata o phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="645b7-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="645b7-127">Per informazioni dettagliate, vedere [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="645b7-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="645b7-128">I dati degli invii a Microsoft risiedono nel Office 365 di conformità nei data center nordamericani.</span><span class="sxs-lookup"><span data-stu-id="645b7-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="645b7-129">I dati vengono esaminati dagli analisti del team di progettazione per migliorare l'efficacia dei filtri.</span><span class="sxs-lookup"><span data-stu-id="645b7-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
