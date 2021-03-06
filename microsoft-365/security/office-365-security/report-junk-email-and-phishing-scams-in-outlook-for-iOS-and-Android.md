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
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

- Per una migliore esperienza di invio da parte dell'utente, ti consigliamo di usare i componenti aggiuntivi Segnala messaggio e Segnala phishing. Per [ulteriori informazioni,](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) vedere Abilitare il componente aggiuntivo Segnala messaggio e Abilitare [il](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) componente aggiuntivo Segnala phishing.

- Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità. Per altre informazioni, vedi Usare l'invio dell'amministratore per inviare posta [indesiderata, phish, URL e file sospetti a Microsoft.](admin-submission.md)

- È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per altre informazioni, vedi [Criteri per gli invii degli utenti.](user-submission.md)

- Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.
