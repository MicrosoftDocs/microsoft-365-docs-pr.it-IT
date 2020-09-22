---
title: Domande frequenti sulla protezione anti-spoofing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sulla protezione anti-spoofing in Exchange Online Protection (EOP).
ms.openlocfilehash: 207fa9b12c2b39571c72397abfb6a64fe992b43e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199112"
---
# <a name="anti-spoofing-protection-faq"></a>Domande frequenti sulla protezione anti-spoofing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In questo articolo sono riportate le domande frequenti e le risposte sulla protezione anti-spoofing per le organizzazioni Microsoft 365 con cassette postali in Exchange Online o organizzazioni di Exchange Online Protection (EOP) indipendenti senza cassette postali di Exchange Online.

Per domande e risposte sulla protezione dalla posta indesiderata, vedere [domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md).

Per domande e risposte sulla protezione anti-malware, vedere [anti-malware Protection FAQ](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Perché Microsoft ha scelto di indesiderare la posta elettronica in arrivo non autenticata?

Microsoft ritiene che il rischio di continuare a consentire la posta elettronica in arrivo non autenticata sia superiore al rischio di perdere la posta elettronica in arrivo legittima.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>La posta indesiderata non autenticata in ingresso causa la posta elettronica legittima per essere contrassegnata come posta indesiderata?

Quando Microsoft ha abilitato questa funzionalità in 2018, sono successe alcune false positive (i messaggi buoni sono stati contrassegnati come cattivi). Tuttavia, nel tempo, i mittenti sono stati adattati ai requisiti. Il numero di messaggi che sono stati erroneamente identificati come falsificati è diventato irrilevante per la maggior parte dei percorsi di posta elettronica.

Microsoft stesso ha adottato prima i nuovi requisiti di autenticazione della posta elettronica diverse settimane prima di distribuirlo ai clienti. Anche se all'inizio si è verificato un problema di disgregazione, ed è diminuito gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>L'intelligenza spoof è disponibile per i clienti Microsoft 365 senza ATP?

Sì. A ottobre 2018, l'intelligence spoof è disponibile per tutte le organizzazioni con cassette postali in Exchange Online e organizzazioni di EOP autonome senza cassette postali di Exchange Online.

La tecnologia anti-spoofing è stata inizialmente disponibile solo in Office 365 Advanced Threat Protection. Ad esempio, abbonamenti Microsoft E5 o componenti aggiuntivi ATP.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Come si fa a segnalare messaggi di posta indesiderata o non a Microsoft?

Vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Sono un amministratore e non conosco tutte le fonti per i messaggi nel mio dominio di posta elettronica!

Vedere [che non si conoscono tutte le fonti per la posta elettronica](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Cosa succede se si disattiva la protezione anti-spoofing per la propria organizzazione?

Non è consigliabile disabilitare la protezione anti-spoofing. La disattivazione della protezione consentirà di recapitare più messaggi di phishing e posta indesiderata nella propria organizzazione. Non tutti i tentativi di phishing sono spoofing e non tutti i messaggi falsificati verranno persi. Tuttavia, il rischio sarà più alto.

Ora che il [filtro avanzato per i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) è disponibile, non è più consigliabile disattivare la protezione anti-spoofing quando la posta elettronica viene instradata attraverso un altro servizio prima di EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>La protezione anti-spoofing significa che sarò protetto da tutti i tentativi di phishing?

Purtroppo no. I pirati informatici si adattano all'utilizzo di altre tecniche (ad esempio, account compromessi o account in servizi di posta elettronica liberi). Tuttavia, la protezione anti-phishing funziona molto meglio per rilevare questi altri tipi di metodi di phishing. I livelli di protezione in EOP sono stati disegnati insieme e si basano sull'uno dell'altro.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Altri servizi di posta elettronica di grandi dimensioni bloccano la posta elettronica in ingresso non autenticata?

Quasi tutti i servizi di posta elettronica di grandi dimensioni implementano i tradizionali controlli SPF, DKIM e DMARC. Alcuni servizi dispongono di altri controlli più rigorosi, ma alcuni si spostano fino a EOP per bloccare la posta elettronica non autenticata e trattarli come messaggi falsificati. Tuttavia, il settore è sempre più attento ai problemi relativi alla posta elettronica non autenticata, in particolare a causa del problema del phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>È ancora necessario abilitare l'impostazione del filtro di posta indesiderata avanzata "record SPF: non riuscito" (_MarkAsSpamSpfRecordHardFail_) se si Abilita l'anti-spoofing?

No. Questa impostazione ASF non è più necessaria. La protezione anti-spoofing considera entrambi i guasti SPF e un insieme di criteri molto più ampio. Se è abilitata la funzionalità di anti-spoofing e il **record SPF: non riuscito** (_MarkAsSpamSpfRecordHardFail_) è attivato, è probabile che vengano configurati più falsi positivi.

Si consiglia di disabilitare questa funzionalità poiché non fornisce quasi nessun vantaggio aggiuntivo per il rilevamento di messaggi di posta indesiderata o di phishing e genera invece falsi positivi principalmente. Per ulteriori informazioni, vedere [Advanced Spam Filter (ASF) Settings in EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Lo schema di riscrittura del mittente aiuta a risolvere il messaggio di posta elettronica inoltrato?

L’SRS risolve solo parzialmente il problema del messaggio di posta elettronica inoltrato. Riscrivendo la **posta SMTP da**, SRS può garantire che il messaggio inoltrato passi SPF alla prossima destinazione. Tuttavia, poiché l'anti-spoofing è basato sull'indirizzo **from** in combinazione con il dominio di **posta elettronica o di** DKIM (o altri segnali), non è sufficiente impedire che la posta elettronica inoltrata dal servizio SRS venga contrassegnata come contraffatta.
