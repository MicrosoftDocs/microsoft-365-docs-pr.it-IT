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
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204955"
---
# <a name="anti-spoofing-protection-faq"></a>Domande frequenti sulla protezione anti-spoofing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In questo articolo vengono fornite domande frequenti e risposte sulla protezione anti-spoofing per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online o organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online.

Per domande e risposte sulla protezione da posta indesiderata, vedere Domande frequenti sulla protezione [da posta indesiderata.](anti-spam-protection-faq.md)

Per domande e risposte sulla protezione antimalware, vedere Domande frequenti sulla [protezione antimalware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Perché Microsoft ha scelto di posta indesiderata non autenticata in ingresso?

Microsoft ritiene che il rischio di continuare a consentire la posta elettronica in ingresso non autenticata sia superiore al rischio di perdere la posta elettronica in ingresso legittima.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>La posta indesiderata non autenticata in ingresso causa la segnalazione di posta elettronica legittima come posta indesiderata?

Quando Microsoft ha abilitato questa funzionalità nel 2018, si sono verificati alcuni falsi positivi (i messaggi buoni sono stati contrassegnati come non riusciti). Tuttavia, nel tempo, i mittenti si adattano ai requisiti. Il numero di messaggi non identificati come falsificati è diventato irrilevante per la maggior parte dei percorsi di posta elettronica.

Microsoft ha adottato i nuovi requisiti di autenticazione della posta elettronica diverse settimane prima di distribuirlo ai clienti. Anche se all'inizio si è verificato un problema di disgregazione, ed è diminuito gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>La spoof intelligence è disponibile per i clienti di Microsoft 365 senza Defender per Office 365?

Sì. A partire da ottobre 2018, la spoof intelligence è disponibile per tutte le organizzazioni con cassette postali in Exchange Online e per le organizzazioni EOP autonome senza cassette postali di Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Come si fa a segnalare messaggi di posta indesiderata o non a Microsoft?

Vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>I'm an admin and I don't know all of sources for messages in my email domain!

Vedere [Non si conoscono tutte le origini per la posta elettronica.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Cosa succede se si disabilita la protezione anti-spoofing per l'organizzazione?

Non è consigliabile disabilitare la protezione anti-spoofing. La disabilitazione della protezione consentirà di recapitare più messaggi di phishing e posta indesiderata nell'organizzazione. Non tutto il phishing è spoofing e non tutti i messaggi falsificati verranno persi. Tuttavia, il rischio sarà maggiore.

Ora che [il filtro avanzato](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) per i connettori è disponibile, non è più consigliabile disattivare la protezione anti-spoofing quando la posta elettronica viene instradata tramite un altro servizio prima di EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>La protezione anti-spoofing significa che sarà protetto da tutti i tentativi di phishing?

Purtroppo, no. Gli utenti malintenzionati si adatteranno all'uso di altre tecniche(ad esempio, account compromessi o account nei servizi di posta elettronica gratuiti). Tuttavia, la protezione anti-phishing funziona molto meglio per rilevare questi altri tipi di metodi di phishing. I livelli di protezione in EOP sono progettati insieme e si basano l'uno sull'altro.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Altri servizi di posta elettronica di grandi dimensioni bloccano la posta elettronica in ingresso non autenticata?

Quasi tutti i servizi di posta elettronica di grandi dimensioni implementano i controlli SPF, DKIM e DMARC tradizionali. Alcuni servizi dispongono di altri controlli più rigorosi, ma pochi vanno fino a EOP per bloccare la posta elettronica non autenticata e trattarli come messaggi contraffatti. Tuttavia, il settore sta diventando sempre più consapevole dei problemi relativi alla posta elettronica non autenticata, in particolare a causa del problema del phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>È ancora necessario abilitare l'impostazione del filtro posta indesiderata avanzato "Record SPF: hard fail" (_MarkAsSpamSpfRecordHardFail_) se si abilita l'anti-spoofing?

No. Questa impostazione ASF non è più necessaria. La protezione anti-spoofing considera sia gli errori hard SPF che un set di criteri molto più ampio. Se è abilitata la funzionalità di anti-spoofing e il **record SPF: non riuscito** (_MarkAsSpamSpfRecordHardFail_) è attivato, è probabile che vengano configurati più falsi positivi.

È consigliabile disabilitare questa funzionalità in quanto non offre quasi alcun vantaggio aggiuntivo per il rilevamento di messaggi di posta indesiderata o di phishing, generando invece principalmente falsi positivi. Per ulteriori informazioni, vedere [Advanced Spam Filter (ASF) settings in EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Lo schema di riscrittura del mittente consente di correggere la posta elettronica inoltrata?

L’SRS risolve solo parzialmente il problema del messaggio di posta elettronica inoltrato. Riscrittura di SMTP **MAIL FROM**, SRS può garantire che il messaggio inoltrato passi SPF alla destinazione successiva. Tuttavia, poiché l'anti-spoofing si basa sull'indirizzo **From** in combinazione con il dominio di firma **MAIL FROM** o DKIM (o altri segnali), non è sufficiente impedire che la posta elettronica inoltrata da SRS venga contrassegnata come contraffatta.