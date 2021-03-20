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
description: Gli amministratori possono conoscere le opzioni predefinite per la segnalazione della posta indesiderata, non della posta indesiderata e del phishing in Outlook per iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eda0d8d43244834236a70374df6b7d6ccf0b69ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908819"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="f103b-103">Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f103b-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f103b-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f103b-104">**Applies to**</span></span>
- [<span data-ttu-id="f103b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f103b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f103b-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f103b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f103b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f103b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f103b-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f103b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f103b-109">Cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f103b-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="f103b-110">Per la migliore esperienza di invio degli utenti, ti consigliamo di usare i componenti aggiuntivi Segnala messaggio e Segnala phishing. Per ulteriori informazioni, vedere [Enable the Report Message add-in](./enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](./enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f103b-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="f103b-111">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="f103b-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f103b-112">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="f103b-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="f103b-113">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="f103b-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f103b-114">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f103b-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f103b-115">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f103b-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f103b-116">Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f103b-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>