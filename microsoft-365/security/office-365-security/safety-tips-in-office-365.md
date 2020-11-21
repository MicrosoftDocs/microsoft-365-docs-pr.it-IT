---
title: Suggerimenti per la sicurezza nei messaggi di posta elettronica
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Informazioni sul modo in cui EOP e Office 365 proteggono i messaggi di posta indesiderata, phishing e antimalware aggiungendo un suggerimento per la sicurezza all'inizio della posta elettronica.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e36887e2bb0146c86a8a4f1526f1e712a38b46ba
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376620"
---
# <a name="safety-tips-in-email-messages"></a>Suggerimenti per la sicurezza nei messaggi di posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) e Microsoft 365 proteggono i propri messaggi di posta indesiderata, phishing e prevenzione antimalware. Oggi, alcuni di questi attacchi sono così ben congegnati che sembrano legittimi. L'invio di messaggi alla cartella posta indesiderata non è sempre sufficiente. A questo punto, quando si controlla il messaggio di posta elettronica in Outlook o Outlook sul Web o in un altro client di posta elettronica, EOP controlla automaticamente il mittente e aggiunge una punta di sicurezza all'inizio della posta elettronica.

I suggerimenti per la sicurezza in Outlook non dipendono dalla versione di Outlook in uso perché il suggerimento per la sicurezza è incrinato e viene inserito direttamente nel corpo del messaggio. Questo significa che il suggerimento per la sicurezza verrà visualizzato in qualunque client di posta elettronica che si sta utilizzando. Viene eseguito a livello di filtro della posta elettronica e non viene eseguito il rendering a livello di client di posta, quindi non viene visualizzato solo in qualsiasi versione di Outlook, ma viene visualizzato anche in qualsiasi client di posta elettronica.

Il suggerimento per la sicurezza, un messaggio con codice a colori, avvisa i messaggi potenzialmente dannosi. La maggior parte dei messaggi nella posta in arrivo non avrà un suggerimento per la sicurezza. Saranno visibili solo quando EOP e Microsoft 365 dispongono di informazioni necessarie per impedire attacchi di posta indesiderata, phishing e malware. Se nella cartella posta in arrivo sono presenti suggerimenti per la sicurezza, è possibile utilizzare gli esempi seguenti per ulteriori informazioni su ogni tipo di suggerimento per la sicurezza.

- Posta elettronica sospetta (punta di sicurezza rossa).

    ![Schermata che visualizza un suggerimento per la sicurezza rossa.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Un suggerimento per la sicurezza rossa in un messaggio di posta elettronica indica che l'utente ricevuto contiene elementi sospetti, ad esempio una truffa di phishing. È consigliabile eliminare questo tipo di messaggio di posta elettronica dalla posta in arrivo senza aprirlo.

- Posta elettronica sicura (suggerimento per la sicurezza verde).

    ![Schermata che visualizza un suggerimento per la sicurezza verde.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Oltre ai messaggi non sicuri, verranno inoltre illustrati i messaggi validi provenienti da mittenti attendibili con un suggerimento per la sicurezza verde. Un suggerimento per la sicurezza verde in un messaggio di posta elettronica indica che il mittente è stato controllato e verificato che sia sicuro. Microsoft gestisce questo elenco di mittenti attendibili che include organizzazioni finanziarie e altri spesso contraffatti o rappresentati.

## <a name="working-with-safety-tips"></a>Utilizzo dei suggerimenti per la sicurezza

I suggerimenti per la sicurezza sono sempre abilitati per Outlook sul Web, anche se non tutti i messaggi ne ricevono uno. Gli amministratori possono disattivare i suggerimenti di sicurezza per altri client di posta elettronica, ad esempio Outlook. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

Se non si è d'accordo con il modo in cui EOP ha categorizzato un messaggio (ovvero il messaggio non è posta indesiderata o dovrebbe essere stato contrassegnato come posta indesiderata), è possibile inviare i messaggi a Microsoft per l'analisi per migliorare l'esperienza. Per istruzioni, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md). È anche possibile fare clic sul collegamento commenti e suggerimenti sulla sicurezza per inviare commenti direttamente a Microsoft per aiutarci a migliorare.
