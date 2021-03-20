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
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

- Per la migliore esperienza di invio degli utenti, ti consigliamo di usare i componenti aggiuntivi Segnala messaggio e Segnala phishing. Per ulteriori informazioni, vedere [Enable the Report Message add-in](./enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](./enable-the-report-phish-add-in.md)

- Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)

- Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

  > [!NOTE]
  > Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.