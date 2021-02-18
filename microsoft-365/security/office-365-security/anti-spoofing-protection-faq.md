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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sulla protezione anti-spoofing in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288910"
---
# <a name="anti-spoofing-protection-faq"></a>Domande frequenti sulla protezione anti-spoofing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In questo articolo vengono fornite domande frequenti e risposte sulla protezione anti-spoofing per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online o organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online.

Per domande e risposte sulla protezione da posta indesiderata, vedere Domande frequenti [sulla protezione da posta indesiderata.](anti-spam-protection-faq.md)

Per domande e risposte sulla protezione antimalware, vedere [Domande frequenti sulla protezione antimalware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Perché Microsoft ha scelto di posta indesiderata in ingresso non autenticata?

Microsoft ritiene che il rischio di continuare a consentire la posta elettronica in ingresso non autenticata sia superiore al rischio di perdere messaggi di posta elettronica legittimi in ingresso.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>La posta indesiderata in ingresso non autenticata causa il contrassegnato come posta indesiderata?

Quando Microsoft ha abilitato questa funzionalità nel 2018, si sono verificati alcuni falsi positivi (i messaggi positivi sono stati contrassegnati come non riusciti). Tuttavia, nel tempo, i mittenti si adattano ai requisiti. Il numero di messaggi che sono stati falsificati come falsificati è diventato trascurabile per la maggior parte dei percorsi di posta elettronica.

Microsoft stessa ha adottato i nuovi requisiti di autenticazione della posta elettronica diverse settimane prima di distribuirlo ai clienti. Anche se all'inizio si è verificato un problema di disgregazione, ed è diminuito gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>L'intelligence per lo spoofing è disponibile per i clienti di Microsoft 365 senza Defender per Office 365?

Sì. A partire da ottobre 2018, spoof intelligence è disponibile per tutte le organizzazioni con cassette postali in Exchange Online e per le organizzazioni EOP autonome senza cassette postali di Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Come si fa a segnalare messaggi di posta indesiderata o non a Microsoft?

Vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>I'm an admin and I don't know all of sources for messages in my email domain!

See [You don't know all sources for your email.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Cosa succede se si disabilita la protezione anti-spoofing per l'organizzazione?

Non è consigliabile disabilitare la protezione anti-spoofing. La disabilitazione della protezione consentirà di recapitare più messaggi di phishing e posta indesiderata nell'organizzazione. Non tutti i tentativi di phishing sono spoofing e non tutti i messaggi falsificati verranno persi. Tuttavia, il rischio sarà maggiore.

Ora che [il filtro avanzato](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) per i connettori è disponibile, non è più consigliabile disattivare la protezione anti-spoofing quando la posta elettronica viene instradata attraverso un altro servizio prima di EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>La protezione anti-spoofing significa che sarà protetto da tutti i tentativi di phishing?

Purtroppo no. Gli utenti malintenzionati si adatteranno all'uso di altre tecniche (ad esempio, account compromessi o account nei servizi di posta elettronica gratuiti). Tuttavia, la protezione anti-phishing funziona molto meglio per rilevare questi altri tipi di metodi di phishing. I livelli di protezione in EOP sono progettati insieme e si basano l'uno sull'altro.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Altri servizi di posta elettronica di grandi dimensioni bloccano la posta elettronica in ingresso non autenticata?

Quasi tutti i servizi di posta elettronica di grandi dimensioni implementano i controlli SPF, DKIM e DMARC tradizionali. Alcuni servizi dispongono di altri controlli più rigorosi, ma pochi vanno fino a EOP per bloccare la posta elettronica non autenticata e trattarli come messaggi falsificati. Tuttavia, il settore sta diventando più consapevole dei problemi relativi alla posta elettronica non autenticata, in particolare a causa del problema del phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>È ancora necessario abilitare l'impostazione "Record SPF: hard fail" del filtro di protezione da posta indesiderata avanzata (_MarkAsSpamSpfRecordHardFail_) se si abilita l'anti-spoofing?

No. Questa impostazione ASF non è più necessaria. La protezione anti-spoofing considera sia gli errori SPF che un set di criteri molto più ampio. Se è abilitata la funzionalità di anti-spoofing e il **record SPF: non riuscito** (_MarkAsSpamSpfRecordHardFail_) è attivato, è probabile che vengano configurati più falsi positivi.

Si consiglia di disabilitare questa funzionalità perché non offre quasi alcun vantaggio aggiuntivo per il rilevamento di posta indesiderata o messaggio di phishing e genera principalmente falsi positivi. Per ulteriori informazioni, vedere [Advanced Spam Filter (ASF) settings in EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Lo schema di riscrittura del mittente consente di correggere la posta elettronica inoltrata?

L’SRS risolve solo parzialmente il problema del messaggio di posta elettronica inoltrato. Riscritndo SMTP **MAIL FROM,** SRS può garantire che il messaggio inoltrato passi SPF alla destinazione successiva. Tuttavia, poiché l'anti-spoofing  si basa sull'indirizzo Da in combinazione con il dominio di firma **MAIL FROM** o DKIM (o altri segnali), non è sufficiente impedire che la posta elettronica inoltrata da SRS venga contrassegnata come contraffatta.
