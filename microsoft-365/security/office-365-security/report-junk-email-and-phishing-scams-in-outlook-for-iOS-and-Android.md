---
title: Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sulle opzioni di creazione di report di posta indesiderata, non indesiderata e di phishing in Outlook per iOS e Android.
ms.openlocfilehash: 23668a762301ee442bc805e62863079ee7ae6076
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350856"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o nelle cassette postali locali che usano l' [autenticazione moderna ibrida](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), è possibile utilizzare le opzioni predefinite di Reporting in Outlook per iOS e Android per inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

- Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).

- È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).

- Per ulteriori informazioni sul reporting dei messaggi a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).

  > [!NOTE]
  > Se la segnalazione della posta indesiderata è disabilitata per Outlook nel criterio di invio dell'utente, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella posta indesiderata e non riportati nell'amministratore o Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android

Per i messaggi nella posta in arrivo o in qualsiasi altra cartella di posta elettronica, tranne la posta indesiderata, attenersi alla procedura seguente per segnalare messaggi di posta indesiderata e di phishing per iOS e Android:

1. Selezionare uno o più messaggi.
2. Nell'angolo superiore destro toccare i tre punti verticali. Verrà aperto il menu azione.

   ![Segnalare messaggi di posta indesiderata o di phishing dal menu azione](../../media/Android-report-as-junk-dialog.png)

3. Toccare **segnala indesiderata** e quindi fare clic su **posta indesiderata** o **phishing**.

   ![Segnalare messaggi di posta indesiderata o di phishing](../../media/Android-report-junk-or-phishing.png)

4. Nella finestra di dialogo che viene visualizzata, è possibile scegliere **segnala** o **No grazie**. Se si seleziona **No Thanks**, se si utilizza la posta **indesiderata** , il messaggio viene spostato nella cartella posta indesiderata, se il messaggio viene toccato tramite **phishing** , la cartella degli elementi eliminati viene spostata. Selezionare **segnala** anche per inviare una copia del messaggio a Microsoft.

   ![Segnalare le opzioni di segnalazione di posta indesiderata o phishing](../../media/Android-junk-email-reporting-options.png)

Se si cambia idea, selezionare **Annulla** nella notifica del toast che viene visualizzata. Il messaggio rimane nella cartella posta in arrivo.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Segnalare i messaggi non di posta indesiderata dalla cartella posta indesiderata in Outlook per iOS e Android

Nella cartella posta indesiderata, attenersi alla procedura seguente per segnalare la posta indesiderata dei falsi positivi:

1. Selezionare uno o più messaggi.
2. Nell'angolo superiore destro toccare i tre punti verticali. Verrà aperto il menu azione.

   ![Segnala non posta indesiderata dal menu azione](../../media/Android-not-junk-email.png)

3. Toccare **non indesiderato**.

Viene visualizzata una notifica del brindisi che il messaggio di posta elettronica è stato spostato nella cartella posta in arrivo. Se si cambia idea, selezionare **Annulla** sulla notifica del toast. Il messaggio di posta elettronica rimane nella cartella di posta indesiderata.
