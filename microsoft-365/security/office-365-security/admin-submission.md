---
title: Invii di amministratore in Office 365, O365 invii, Office 365 spam problem, O365 false negative, Submit phishing in Office 365, inviare la posta elettronica per l'analisi, la posta elettronica sospetti in Office 365, analizzare una posta elettronica, avere Microsoft Scan per phishing, avere Microsoft Scan per la posta indesiderata, invio posta elettronica, inviare messaggi di posta elettronica, messaggi di posta elettronica dodgy, cattiva attore, posta elettronica sospetta, non attendibile, segnalare messaggi di phishing a Microsoft, segnalare messaggi di posta elettronica di phishing a Microsoft, segnalare e-mail dannose a Microsoft, segnalare la posta indesiderata a Microsoft, segnalare il malware nella posta elettronica a Microsoft, spam messaggi di posta elettronica in posta in arrivo Office 365, virus in e-mail Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informazioni su come inviare messaggi di posta elettronica sospetti, sospette mail di phishing, spam e altre potenzialmente nocive, URL e file dal tenant di Office 365 a Microsoft per l'analisi.
ms.openlocfilehash: b123aef485628728df9db27875117b47295975ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083633"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>Come inviare messaggi di posta indesiderata, phishing, URL e file sospetti a Microsoft per l'analisi di Office 365

Gli amministratori possono inviare messaggi di posta elettronica utilizzando il file o l'ID del messaggio di rete, gli URL e i file per l'analisi da parte di Microsoft in Office 365.
La sezione aggiornamenti aggiornati include ancora i messaggi segnalati dall'utente e disponibili per tutti i clienti che utilizzano EOP.

Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta. I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Come indirizzare i contenuti sospetti a Microsoft per l'analisi di Office 365

Per inviare contenuto a Microsoft fare clic sul pulsante **nuovo invio** nella parte superiore sinistra della pagina invii. Viene visualizzato un riquadro a comparsa sul lato destro della pagina con l'opzione per inviare un messaggio di posta elettronica, un URL o un file.

### <a name="submit-a-questionable-email-to-microsoft"></a>Inviare un messaggio di posta elettronica discutibile a Microsoft

![Esempio di invio tramite posta elettronica](../../media/submission-flyout-email.PNG)

1. Per inviare un messaggio di posta elettronica, selezionare **posta elettronica** e specificare l' **ID della rete** di posta elettronica o caricare il file di posta elettronica.

2. Specificare il destinatario o i destinatari a cui si desidera eseguire il controllo dei criteri. Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa dei criteri a livello di utente o tenant.

3. Specificare se il messaggio di posta elettronica deve essere stato bloccato o meno. Se il messaggio di posta elettronica deve essere stato bloccato, specificare se deve essere stato bloccato come posta indesiderata, phishing o malware. Se non si è certi di quale tipo potrebbe essere, utilizzare il giudizio migliore.

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

## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection (Piano 2)](office-365-ti.md)

[Protezione dalle minacce in Office 365](protect-against-threats.md)

[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
