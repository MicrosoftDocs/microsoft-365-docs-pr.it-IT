---
title: Segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: "Il componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft per Microsoft Office Outlook offre all'utente diversi modi per segnalare messaggi indesiderati:"
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033663"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="195ad-103">Segnalare i messaggi e i file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="195ad-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="195ad-104">Gli utenti e gli amministratori di Office 365 organizzazioni con cassette postali in Exchange Online o organizzazioni standalone di Exchange Online Protection (EOP) senza cassette postali di Exchange Online per inviare messaggi di posta elettronica dispongono di diversi metodi per la segnalazione dei messaggi e file a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="195ad-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="195ad-105">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="195ad-105">**Method**</span></span>|<span data-ttu-id="195ad-106">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="195ad-106">**Description**</span></span>|
|[<span data-ttu-id="195ad-107">Utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata sospetti, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="195ad-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="195ad-108">Questo è il metodo di segnalazione consigliato per gli amministratori nelle organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo).</span><span class="sxs-lookup"><span data-stu-id="195ad-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="195ad-109">Abilitare il componente aggiuntivo per i messaggi di report in Office 365</span><span class="sxs-lookup"><span data-stu-id="195ad-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="195ad-110">Compatibile con Outlook, Outlook per Mac e Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="195ad-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="195ad-111">Questo è il componente aggiuntivo consigliato.</span><span class="sxs-lookup"><span data-stu-id="195ad-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="195ad-112">A seconda della licenza, i messaggi segnalati sono disponibili nei [risultati di ricerca e risposta (aria) automatizzati](air-view-investigation-results.md), nel [rapporto messaggi segnalati dall'utente](view-email-security-reports.md#user-reported-messages-report) e in [Esplora minacce](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="195ad-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="195ad-113">Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook in Office 365</span><span class="sxs-lookup"><span data-stu-id="195ad-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="195ad-114">Funziona solo in Outlook.</span><span class="sxs-lookup"><span data-stu-id="195ad-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="195ad-115">Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web in Office 365</span><span class="sxs-lookup"><span data-stu-id="195ad-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="195ad-116">Utilizzare le funzionalità predefinite in Outlook sul Web per le organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo).</span><span class="sxs-lookup"><span data-stu-id="195ad-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="195ad-117">Inviare malware e non malware a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="195ad-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="195ad-118">Utilizzare il sito di Microsoft Security Intelligence per inviare allegati e altri file.</span><span class="sxs-lookup"><span data-stu-id="195ad-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="195ad-119">Se i messaggi di posta indesiderata o di phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel centro sicurezza & conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="195ad-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="195ad-120">Per informazioni dettagliate, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="195ad-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>