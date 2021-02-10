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
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166820"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)è possibile utilizzare le opzioni di creazione di report predefinite in Outlook per iOS e Android per inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

- Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft.](admin-submission.md)

- È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per altre informazioni, vedi [Criteri per gli invii degli utenti.](user-submission.md)

- Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Segnalare messaggi di posta indesiderata e phishing in Outlook per iOS e Android

Per i messaggi nella Cartella Posta in arrivo o in qualsiasi altra cartella di posta ad eccezione della posta indesiderata, utilizzare la procedura seguente per segnalare i messaggi di posta indesiderata e phishing per iOS e Android:

1. Selezionare uno o più messaggi.
2. Nell'angolo superiore destro tocca i tre punti verticali. Verrà visualizzato il menu azioni.

   ![Segnalare posta indesiderata o phishing dal menu azione](../../media/Android-report-as-junk-dialog.png)

3. Toccare **Segnala posta** indesiderata e quindi selezionare Posta **indesiderata** **o Phishing.**

   ![Segnalare posta indesiderata o phishing](../../media/Android-report-junk-or-phishing.png)

4. Nella finestra di dialogo visualizzata, è possibile scegliere **Segnala** o **No Grazie.** Se si **seleziona No Grazie,** se il messaggio viene toccato viene spostato nella cartella Posta indesiderata, se si tocca **Phishing,** il messaggio viene spostato nella cartella Posta eliminata.  Selezionare **Segnala** anche per inviare una copia del messaggio a Microsoft.

   ![Opzioni di segnalazione della posta indesiderata o di phishing](../../media/Android-junk-email-reporting-options.png)

Se cambi idea, seleziona **Annulla** nella notifica di tipo avviso popup visualizzata. Il messaggio rimane nella cartella Posta in arrivo.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Segnalare i messaggi non indesiderati dalla cartella Posta indesiderata in Outlook per iOS e Android

Nella cartella Posta indesiderata, utilizzare la procedura seguente per segnalare falsi positivi della posta indesiderata:

1. Selezionare uno o più messaggi.
2. Nell'angolo superiore destro tocca i tre punti verticali. Verrà visualizzato il menu azioni.

   ![Segnalare la posta non indesiderata dal menu azioni](../../media/Android-not-junk-email.png)

3. Toccare **Non indesiderato**.

Viene visualizzata una notifica di tipo avviso popup che indica che il messaggio di posta elettronica è stato spostato nella posta in arrivo. Se cambi idea, seleziona Annulla **nella** notifica di tipo avviso popup. Il messaggio di posta elettronica rimane nella cartella Posta indesiderata.
