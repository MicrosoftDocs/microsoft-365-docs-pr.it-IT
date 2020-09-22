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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure consigliate per aiutare a proteggere gli utenti da messaggi di posta elettronica abusivi, indesiderati o dannosi.
ms.openlocfilehash: b971823201fb805c9e17da8402250065d274668d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202376"
---
# <a name="reference-policies-practices-and-guidelines"></a>Informazioni di riferimento: criteri, procedure e linee guida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft è dedicato all'assistenza per fornire l'esperienza utente più affidabile sul Web. Pertanto, Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure consigliate per aiutare a proteggere gli utenti da messaggi di posta elettronica abusivi, indesiderati o dannosi. I mittenti che tentano di inviare messaggi di posta elettronica agli utenti devono accertarsi di comprendere appieno e seguire le indicazioni contenute in questo articolo per contribuire a questo sforzo e per evitare potenziali problemi di recapito.

Se non si è in conformità con questi criteri e linee guida, potrebbe non essere possibile per il team di supporto aiutarla. Se si rispettano le linee guida, le procedure e i criteri illustrati in questo articolo e si verificano ancora problemi di recapito in base all'indirizzo IP di invio, attenersi alla procedura seguente per inviare una richiesta di delisting. Per istruzioni, vedere [use the delist Portal to Remove from the Blocked Senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Criteri generali di Microsoft

I messaggi di posta elettronica inviati a Microsoft 365 gli utenti devono essere conformi a tutti i criteri Microsoft che regolano la trasmissione e l'utilizzo di Microsoft 365.

- Termini di servizi applicabili a Microsoft 365; in particolare, il divieto di utilizzare il servizio per la posta indesiderata o la distribuzione di malware.

- [Accordo sui servizi Microsoft](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Regolamenti governativi

La posta elettronica inviata a Microsoft 365 gli utenti devono rispettare tutte le leggi e i regolamenti applicabili che disciplinano le comunicazioni di posta elettronica nella giurisdizione applicabile.

- [CAN-SPAM Act: una guida alla conformità per le aziende](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Rimuovi" risposte e responsabilità: i marketer della posta elettronica devono onorare le attestazioni di "annullamento della sottoscrizione"](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Linee guida tecniche

I messaggi di posta elettronica inviati a Microsoft 365 devono essere conformi alle raccomandazioni applicabili elencate nei documenti riportati di seguito (alcuni collegamenti sono disponibili solo in inglese).

- [RFC 2505: suggerimenti per la protezione da posta indesiderata per MTA SMTP](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: estensione del servizio SMTP per il pipelining dei comandi](https://www.ietf.org/rfc/rfc2920.txt)

Inoltre, i server di posta elettronica che si connettono a Microsoft 365 devono attenersi ai requisiti seguenti:

- Il mittente deve essere conforme a tutti gli standard tecnici per la trasmissione della posta elettronica Internet, come pubblicato dall'IETF (Internet Engineering Task Force), tra cui RFC 5321, RFC 5322 e altri.

- Dopo aver specificato un codice di risposta di errore SMTP numerico compreso tra 500 e 599 (noto anche come risposta di mancato recapito permanente o NDR), il mittente non deve tentare di ritrasmettere tale messaggio al destinatario.

- Dopo più risposte di mancato recapito, il mittente deve interrompere ulteriori tentativi di inviare messaggi di posta elettronica al destinatario.

- I messaggi non devono essere trasmessi tramite l'inoltro di posta elettronica insicuro o i server proxy.

- Il meccanismo di annullamento della sottoscrizione, sia da singoli elenchi che da tutti gli elenchi ospitati dal mittente, deve essere chiaramente documentato e facile da trovare e utilizzare per i destinatari.

- Non è possibile accettare le connessioni dallo spazio IP dinamico.

- I server di posta elettronica devono disporre di record DNS inversi validi.

## <a name="reputation-management"></a>Gestione della reputazione

I mittenti, gli ISP e gli altri provider di servizi dovrebbero gestire attivamente la reputazione degli indirizzi IP in uscita.

## <a name="microsoft-365-limits"></a>Limiti relativi a Microsoft 365

I mittenti devono attenersi ai limiti di Microsoft 365 elencati in [Exchange Online Protection limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Risorse e organizzazioni per il recapito della posta elettronica

Microsoft collabora attivamente con gli enti del settore e i provider di servizi per migliorare Internet e l'ecosistema di posta elettronica. Queste organizzazioni hanno pubblicato documenti di Best practice che supportano e consiglia ai mittenti di aderire. Questo consente di migliorare la possibilità di inviare posta elettronica tra diversi provider di servizi di posta elettronica in tutto il mondo.

- [Gruppo di lavoro anti-abuso mobile per la messaggistica](https://www.m3aawg.org/)

- [Alleanza Fiduciaria online](https://www.otalliance.org/resources)

- [Coalizione & provider di messaggi di posta elettronica](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Segnalazione di abusi e posta indesiderata

Per segnalare messaggi di posta elettronica illeciti, abusivi, indesiderati o dannosi, vedere [report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md). L'invio di questi tipi di comunicazioni è una violazione dei criteri di Microsoft e verranno intraprese azioni appropriate sui rapporti confermati.

## <a name="law-enforcement"></a>Applicazione della legge

Se si è membri di Law Enforcement e si desidera servire Microsoft Corporation con documentazione legale relativa a Office 365 o se si dispone di domande relative alla documentazione legale inviata a Microsoft, chiamare il (1) (425) 722-1299.
