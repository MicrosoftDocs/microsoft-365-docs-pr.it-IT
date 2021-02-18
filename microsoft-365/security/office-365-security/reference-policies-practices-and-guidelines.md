---
title: Criteri, procedure e linee guida di riferimento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure consigliate del settore per proteggere gli utenti da posta elettronica abusiva, indesiderata o dannosa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1065fdef5f804214ca48f7ca54170e6e417490d7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289206"
---
# <a name="reference-policies-practices-and-guidelines"></a>Informazioni di riferimento: criteri, procedure e linee guida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft si impegna a fornire l'esperienza utente più attendibile sul Web. Di conseguenza, Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure consigliate del settore per proteggere gli utenti da posta elettronica abusiva, indesiderata o dannosa. I mittenti che tentano di inviare messaggi di posta elettronica agli utenti devono assicurarsi di comprendere appieno e di seguire le indicazioni fornite in questo articolo per aiutare in questo sforzo ed evitare potenziali problemi di recapito.

Se non si è conformi a questi criteri e linee guida, il team di supporto potrebbe non essere in grado di assisterlo. Se si rispettano le linee guida, le procedure e i criteri presentati in questo articolo e si verificano ancora problemi di recapito in base all'indirizzo IP di invio, seguire la procedura per inviare una richiesta di diserzione. Per istruzioni, vedere [Usare il portale di eliminazione per rimuoversi dall'elenco dei mittenti bloccati.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>Criteri generali di Microsoft

La posta elettronica inviata agli utenti di Microsoft 365 deve essere conforme a tutti i criteri Microsoft che regolano la trasmissione e l'uso della posta elettronica di Microsoft 365.

- Condizioni per i servizi applicabili a Microsoft 365; in particolare, il divieto di utilizzare il servizio per posta indesiderata o distribuire malware.

- [Contratto di servizi Microsoft](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Normative governative

I messaggi di posta elettronica inviati agli utenti di Microsoft 365 devono rispettare tutte le leggi e le normative applicabili che regolano le comunicazioni di posta elettronica nella giurisdizione applicabile.

- [CAN-SPAM Act: Guida alla conformità per le aziende](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [Risposte e responsabilità "Rimuovimi": gli esperti di e-mail devono rispettare le attestazioni di annullamento della sottoscrizione](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Linee guida tecniche

I messaggi di posta elettronica inviati a Microsoft 365 devono essere conformi alle raccomandazioni applicabili elencate nei documenti seguenti (alcuni collegamenti sono disponibili solo in inglese).

- [RFC 2505: Suggerimenti per la protezione da posta indesiderata per gli MTA SMTP](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: Estensione del servizio SMTP per il pipelining dei comandi](https://www.ietf.org/rfc/rfc2920.txt)

Inoltre, i server di posta elettronica che si connettono a Microsoft 365 devono rispettare i requisiti seguenti:

- Il mittente deve rispettare tutti gli standard tecnici per la trasmissione della posta elettronica Internet, come pubblicato dalla Internet Engineering Task Force (IETF) della Internet Society, tra cui RFC 5321, RFC 5322 e altri.

- Dopo aver specificato un codice di risposta di errore SMTP numerico compreso tra 500 e 599 (noto anche come risposta di mancato recapito permanente o rapporto di mancato recapito), il mittente non deve tentare di ritrasmettere il messaggio a tale destinatario.

- Dopo più risposte di mancato recapito, il mittente deve cessare ulteriori tentativi di invio di posta elettronica a tale destinatario.

- I messaggi non devono essere trasmessi tramite server proxy o relay di posta elettronica non sicuri.

- Il meccanismo di annullamento della sottoscrizione, da singoli elenchi o da tutti gli elenchi ospitati dal mittente, deve essere chiaramente documentato e facile da trovare e utilizzare per i destinatari.

- Le connessioni dallo spazio IP dinamico potrebbero non essere accettate.

- I server di posta elettronica devono avere record DNS inversa validi.

## <a name="reputation-management"></a>Gestione della reputazione

I mittenti, gli ISP e altri provider di servizi devono gestire attivamente la reputazione degli indirizzi IP in uscita.

## <a name="microsoft-365-limits"></a>Limiti di Microsoft 365

I mittenti devono rispettare i limiti di Microsoft 365 elencati nei [limiti di Exchange Online Protection.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>Risorse e organizzazioni per il recapito della posta elettronica

Microsoft collabora attivamente con enti del settore e provider di servizi per migliorare l'ecosistema di internet e posta elettronica. Queste organizzazioni hanno pubblicato i documenti delle procedure consigliate che vengono supportati e consigliati ai mittenti di attenersi. In questo modo si migliora la possibilità di recapitare la posta elettronica tra diversi provider di servizi di posta elettronica in tutto il mondo.

- [Gruppo di lavoro anti-abuso di malware di messaggistica mobile](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Email Sender & Provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Segnalazione di abuso e posta indesiderata

Per segnalare messaggi di posta elettronica illegali, abusivi, indesiderati o dannosi, vedere Segnalare messaggi [e file a Microsoft.](report-junk-email-messages-to-microsoft.md) L'invio di questi tipi di comunicazioni è una violazione dei criteri Microsoft e verranno intraprese azioni appropriate sui report confermati.

## <a name="law-enforcement"></a>Forze dell'ordine

If you are a member of law enforcement and wish to serve Microsoft Corporation with legal documentation regarding Office 365, or if you have questions regarding legal documentation you have submitted to Microsoft, please call (1) (425) 722-1299.
