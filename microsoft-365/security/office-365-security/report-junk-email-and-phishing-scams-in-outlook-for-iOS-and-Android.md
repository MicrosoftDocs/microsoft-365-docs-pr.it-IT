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
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289174"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="37f5a-103">Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="37f5a-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37f5a-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="37f5a-104">**Applies to**</span></span>
- [<span data-ttu-id="37f5a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="37f5a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="37f5a-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="37f5a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="37f5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37f5a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="37f5a-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile utilizzare le opzioni di creazione di report predefinite in Outlook per iOS e Android per inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="37f5a-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37f5a-109">Cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="37f5a-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="37f5a-110">Per una migliore esperienza di invio da parte dell'utente, ti consigliamo di usare i componenti aggiuntivi Segnala messaggio e Segnala phishing. Per [ulteriori informazioni,](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) vedere Abilitare il componente aggiuntivo Segnala [messaggio](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) e Abilitare il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="37f5a-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="37f5a-111">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="37f5a-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="37f5a-112">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="37f5a-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="37f5a-113">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="37f5a-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="37f5a-114">Per altre informazioni, vedi [Criteri per gli invii degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="37f5a-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="37f5a-115">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="37f5a-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="37f5a-116">Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="37f5a-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>