---
title: Segnalare posta indesiderata e phishing in Outlook per iOS e Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono conoscere le opzioni di segnalazione della posta indesiderata, non della posta indesiderata e di phishing incorporate in Outlook per iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509327"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="a7cd7-103">Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a7cd7-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a7cd7-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a7cd7-104">**Applies to**</span></span>
- [<span data-ttu-id="a7cd7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a7cd7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a7cd7-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a7cd7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a7cd7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7cd7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a7cd7-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a7cd7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a7cd7-109">Cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a7cd7-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="a7cd7-110">Per una migliore esperienza di invio da parte dell'utente, ti consigliamo di usare i componenti aggiuntivi Segnala messaggio e Segnala phishing. Per [ulteriori informazioni,](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) vedere Abilitare il componente aggiuntivo Segnala messaggio e Abilitare [il](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="a7cd7-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="a7cd7-111">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="a7cd7-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a7cd7-112">Per altre informazioni, vedi Usare l'invio dell'amministratore per inviare posta [indesiderata, phish, URL e file sospetti a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a7cd7-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="a7cd7-113">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="a7cd7-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="a7cd7-114">Per altre informazioni, vedi [Criteri per gli invii degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a7cd7-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="a7cd7-115">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a7cd7-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7cd7-116">Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7cd7-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>
