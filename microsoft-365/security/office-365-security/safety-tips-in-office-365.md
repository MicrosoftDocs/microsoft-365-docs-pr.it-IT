---
title: Suggerimenti per la sicurezza nei messaggi di posta elettronica in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/6/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Introduce suggerimenti di sicurezza per i messaggi di posta elettronica filtrati dal filtro di posta indesiderata EOP e Office 365.
ms.openlocfilehash: 244b2ceb8ccf5e2e49b56fdebd370f75033f652b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598523"
---
# <a name="safety-tips-in-email-messages-in-office-365"></a>Suggerimenti per la sicurezza nei messaggi di posta elettronica in Office 365

Exchange Online Protection (EOP) e Office 365 proteggono i messaggi di posta indesiderata, phishing e prevenzione antimalware. Oggi, alcuni di questi attacchi sono così ben congegnati che sembrano legittimi. L'invio di messaggi alla cartella posta indesiderata non è sempre sufficiente. A questo punto, quando si controlla la posta elettronica in Outlook o Outlook sul Web, EOP controlla automaticamente il mittente e aggiunge una punta di sicurezza all'inizio della posta elettronica.

Il suggerimento per la sicurezza, ovvero un messaggio con codice a colori, avviserà i messaggi potenzialmente dannosi. La maggior parte dei messaggi nella posta in arrivo non avrà un suggerimento per la sicurezza. Sarà possibile visualizzarli solo quando EOP e Office 365 dispongono di informazioni necessarie per impedire attacchi di posta indesiderata, phishing e malware. Se nella cartella posta in arrivo sono presenti suggerimenti per la sicurezza, è possibile utilizzare gli esempi seguenti per ulteriori informazioni su ogni tipo di suggerimento per la sicurezza.

- Posta elettronica sospetta (punta di sicurezza rossa).

    ![Schermata che visualizza un suggerimento per la sicurezza rossa.](../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Un suggerimento per la sicurezza rossa in un messaggio di posta elettronica indica che l'utente ricevuto contiene elementi sospetti, ad esempio una truffa di phishing. È consigliabile eliminare questo tipo di messaggio di posta elettronica dalla posta in arrivo senza aprirlo.

- Posta indesiderata (suggerimento di sicurezza giallo).

    ![Schermata che visualizza un suggerimento per la sicurezza giallo.](../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    Un suggerimento giallo per la sicurezza in un messaggio di posta elettronica indica che è stato contrassegnato come posta indesiderata. Se non si riconosce e si considera attendibile il mittente del messaggio, non è possibile scaricare allegati o immagini e non fare clic su nessun collegamento nel messaggio. In Outlook sul Web, è possibile fare clic su **non è posta indesiderata** nella barra gialla di un elemento di posta indesiderata per spostare il messaggio nella posta in arrivo. Se il suggerimento di sicurezza giallo viene visualizzato in un messaggio che è stato recapitato nella posta in arrivo, è probabile che sia presente perché è stato disabilitato lo spostamento della posta indesiderata nella cartella posta indesiderata

- Posta elettronica sicura (suggerimento per la sicurezza verde).

    ![Schermata che visualizza un suggerimento per la sicurezza verde.](../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Oltre ai messaggi non sicuri, verranno inoltre illustrati i messaggi validi provenienti da mittenti attendibili con un suggerimento per la sicurezza verde. Un suggerimento per la sicurezza verde in un messaggio di posta elettronica indica che il mittente è stato controllato e verificato che sia sicuro. Microsoft gestisce questo elenco di mittenti attendibili che include organizzazioni finanziarie e altri spesso contraffatti o rappresentati.

- Posta non filtrata (suggerimento per la sicurezza grigia).

    ![Schermata che visualizza un suggerimento per la sicurezza grigia.](../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    Quando si ignora il controllo di un messaggio di posta elettronica, verrà inoltre visualizzato un mittente attendibile nell'elenco dei mittenti attendibili o se esiste una regola del flusso di posta per ignorare il filtro.

    La punta di sicurezza grigia viene visualizzata anche quando le immagini esterne sono bloccate, ovvero il messaggio è nella posta in arrivo e non sembra essere posta indesiderata, ma contiene immagini esterne che non si è scelto di scaricare.

## <a name="working-with-safety-tips"></a>Utilizzo dei suggerimenti per la sicurezza

I suggerimenti per la sicurezza sono sempre abilitati per Outlook sul Web, anche se non tutti i messaggi ne ricevono uno. Gli amministratori di Office 365 possono disattivare i suggerimenti di sicurezza per altri client di posta elettronica, ad esempio Outlook. Per ulteriori informazioni, vedere [abilitare o disabilitare i suggerimenti per la sicurezza in Office 365](enable-or-disable-safety-tips.md).

Se non si è d'accordo con il modo in cui Office 365 e EOP hanno categorizzato un messaggio (ovvero non è posta indesiderata o non è lecito), è possibile inviare i messaggi per l'analisi per migliorare l'esperienza. Per ulteriori informazioni, vedere [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). È anche possibile fare clic sul collegamento commenti e suggerimenti sulla sicurezza per inviare commenti direttamente a Microsoft per aiutarci a migliorare.

## <a name="see-also"></a>Vedere anche

[Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365](enable-or-disable-safety-tips.md)

