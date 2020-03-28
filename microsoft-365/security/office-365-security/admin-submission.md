---
title: Invii di amministratore in Office 365, O365 invii, Office 365 spam problem, O365 false negative, Submit phishing in Office 365, inviare la posta elettronica per l'analisi, la posta elettronica sospetti in Office 365, analizzare una posta elettronica, avere Microsoft Scan per phishing, avere Microsoft Scan per la posta indesiderata, invio posta elettronica, inviare messaggi di posta elettronica, messaggi di posta elettronica dodgy, cattiva attore, posta elettronica sospetta, non attendibile, segnalare messaggi di phishing a Microsoft, segnalare messaggi di posta elettronica di phishing a Microsoft, segnalare e-mail dannose a Microsoft, segnalare la posta indesiderata a Microsoft, segnalare il malware nella posta elettronica a Microsoft, spam messaggi di posta elettronica in posta in arrivo Office 365, virus in e-mail Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informazioni su come inviare messaggi di posta elettronica sospetti, sospette mail di phishing, spam e altre potenzialmente nocive, URL e file dal tenant di Office 365 a Microsoft per l'analisi.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033615"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata sospetti, phishing, URL e file a Microsoft

Se si è un amministratore di un'organizzazione di Office 365 con le cassette postali in Exchange Online, è possibile utilizzare il portale degli invii nel centro sicurezza & conformità di Office 365 per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.

Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta. I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)

Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di Exchange Online Protection autonomo, vedere [connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per aggiungere, modificare ed eliminare i criteri di protezione da posta indesiderata, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza**o **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).

- Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnala messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Come indirizzare i contenuti sospetti a Microsoft per l'analisi di Office 365

Per inviare contenuto a Microsoft fare clic sul pulsante **nuovo invio** nella parte superiore sinistra della pagina invii. Viene visualizzato un riquadro a comparsa sul lato destro della pagina con l'opzione per inviare un messaggio di posta elettronica, un URL o un file.

### <a name="submit-a-questionable-email-to-microsoft"></a>Inviare un messaggio di posta elettronica discutibile a Microsoft

![Esempio di invio tramite posta elettronica](../../media/submission-flyout-email.PNG)

1. Per inviare un messaggio di posta elettronica, selezionare **posta elettronica** e specificare l' **ID della rete** di posta elettronica o caricare il file di posta elettronica.

2. Specificare il destinatario o i destinatari a cui si desidera eseguire il controllo dei criteri. Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa dei criteri a livello di utente o tenant.

3. Specificare se il messaggio di posta elettronica deve essere stato bloccato o meno. Se il messaggio di posta elettronica deve essere stato bloccato, specificare se deve essere stato bloccato come posta indesiderata, phishing o malware. Se non si è certi di quale tipo potrebbe essere, utilizzare il miglior giudizio.

   - Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.

   - Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti. Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato. Questo include i risultati del controllo dei criteri e il verdetto di rianalisi. Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.

4. Fare clic sul pulsante **Invia** .

### <a name="send-a-suspect-url-to-microsoft"></a>Inviare un URL sospetto a Microsoft

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

1. Per inviare un **URL selezionare URL dal riquadro a comparsa** . Digitare l'URL completo, incluso il protocollo (**https://**).

   Se è **stato selezionato deve essere stato filtrato**, specificare se l'URL è phishing o malware.

2. Fare clic sul pulsante **Invia** .

### <a name="submit-a-suspected-file-to-microsoft"></a>Inviare un file sospetto a Microsoft

![Esempio di invio tramite posta elettronica](../../media/submission-file-flyout.PNG)

1. Per inviare un file seleziona **file** dal riquadro a comparsa e caricare il file che si desidera analizzare.

2. Fare clic sul pulsante **Invia** .
