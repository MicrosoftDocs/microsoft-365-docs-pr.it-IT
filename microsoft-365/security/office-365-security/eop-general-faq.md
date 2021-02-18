---
title: Domande frequenti su EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Risposte alle domande più comuni sul servizio di filtro della posta elettronica ospitato su cloud di Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a1ce845ef50d7485113c211b0a8d7770ea57815
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290022"
---
# <a name="eop-general-faq"></a>Domande frequenti su Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Qui rispondiamo alle domande più comuni sul servizio di filtro della posta elettronica ospitato su cloud di Exchange Online Protection (EOP). Per ulteriori argomenti sulle domande frequenti (FAQ), accedere ai collegamenti seguenti:

- [Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Domande frequenti sull'amministrazione con delega](delegated-administration-faq.md)

- [Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)

- [Domande frequenti sulla quarantena](quarantine-faq.md)

- [Domande frequenti sulla protezione antimalware](anti-malware-protection-faq-eop.md)

- [Domande frequenti su Traccia messaggio](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Cos'è Exchange Online Protection?

EOP è un servizio di filtro della posta elettronica ospitato su cloud ideato per proteggere i clienti da posta indesiderata e malware e per implementare le regole criterio personalizzate. EOP è incluso in qualsiasi abbonamento a Microsoft 365 contenente cassette postali di Exchange Online. EOP è inoltre disponibile come offerta autonoma per proteggere gli ambienti di posta elettronica locali.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Come iscriversi alla versione di valutazione o alla versione per l'acquisto di EOP.

È possibile iscriversi alla versione di valutazione o per l'acquisto di EOP tramite il Web nella [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Le funzionalità di una versione di prova sono uguali a quelle di un abbonamento a pagamento, ma quest'ultimo include anche funzionalità aggiuntive fornite con il piano di abbonamento a [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>Qual è il prezzo di EOP.

EOP richiede una licenza per utente. Per informazioni più recenti sul prezzo, vedere la [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Tempo stimato per mettere in funzione EOP.

Quando vengono modificati il record MX, come evidenziato nella procedura in [Installazione del servizio EOP](set-up-your-eop-service.md), e i flussi di posta tramite EOP, il filtro viene immediatamente avviato. Il record MX potrebbe richiedere dalle 24 alle 48 ore per la propagazione tramite DNS. È possibile ottimizzare le impostazioni di protezione in qualsiasi momento durante questo processo.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>È necessario utilizzare tutte le funzionalità di Microsoft 365 per utilizzare EOP? Cosa succede se si desidera solo la protezione EOP e tutto qui?

È possibile utilizzare EOP per proteggere le cassette postali locali senza utilizzare altre funzionalità di Microsoft 365. Questa soluzione è nota come sottoscrizione indipendente. Un elenco di funzionalità EOP è consultabile in [Descrizione del servizio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Perché è necessario un tenant di Microsoft 365 quando ci si iscrive per il filtro della posta elettronica tramite EOP?

Microsoft 365 è il nome assegnato a una raccolta di prodotti e servizi a cui è possibile accedere tramite un tenant di Microsoft 365. Si pensi al tenant di Microsoft 365 come al punto di partenza a cui è possibile aggiungere licenze per il filtro della posta elettronica.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP dispone di un portale di comunicazione, nel quale è possibile trovare informazioni su problemi noti e possibili risoluzioni? Le informazioni sulle nuove funzionalità?

Alcune di queste informazioni saranno disponibili nell'interfaccia di amministrazione di Microsoft 365. Se si è influenzati da un evento del livello di servizio, dopo aver effettuato l'accesso all'interfaccia di amministrazione di Microsoft 365 dovrebbe essere visualizzato un avviso di comunicazione (in genere accompagnato da un'icona a forma di campanello). Si consiglia di leggere e intervenire su tutti gli elementi, come necessario.

Per quanto riguarda le nuove funzionalità di EOP, la roadmap di [Microsoft 365 per le aziende](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) è una buona risorsa per trovare informazioni sulle nuove funzionalità future. Inoltre, inseriamo articoli di blog sulle nuove funzionalità nel sito [Web blog di Microsoft 365.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Il servizio funziona con le versioni legacy di Exchange (ad esempio, Exchange Server 2010) e negli ambienti non Exchange?

Sì, il servizio è indipendente dal server e può essere utilizzato con qualsiasi agente di trasferimento messaggi SMTP.

## <a name="what-size-organization-can-use-the-service"></a>Per utilizzare il servizio, quali dimensioni deve avere un'organizzazione?

Qualsiasi dimensione. La rete EOP dispone di capacità sufficienti per rispondere alle esigenze di crescita dell'organizzazione, a prescindere dalla velocità di crescita.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Di quali autorizzazioni ho bisogno per configurare EOP?

Per configurare EOP, è necessario essere un amministratore globale o un amministratore aziendale di Exchange (il gruppo di ruoli Gestione organizzazione).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Come è possibile verificare che i dati e le informazioni private siano al sicuro?

Per ulteriori informazioni sulla garanzia della sicurezza dei dati e delle informazioni private, incluse le informazioni sui contratti di servizio, vedere [Centro protezione Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Esistono limiti che devo conoscere, ad esempio limitazioni relative alle dimensioni del messaggio?

Sì. Per ulteriori informazioni sui limiti in EOP, vedere [Limiti di Exchange Online Protection.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="does-eop-support-powershell"></a>EOP supporta PowerShell?

Sì, la funzionalità EOP completa è disponibile tramite PowerShell: PowerShell di Exchange Online per le organizzazioni con cassette postali di Exchange Online; PowerShell EOP autonomo per le organizzazioni EOP autonome. Per ulteriori informazioni, vedere [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) ed [Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)
