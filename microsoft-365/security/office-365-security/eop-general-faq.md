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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Ottenere le risposte alle domande generali più comuni relative al servizio di filtro della posta elettronica ospitato sul cloud di Exchange Online Protection (EOP).
ms.openlocfilehash: aa0b881250466c71cb05123216fcf9eccc64018d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202916"
---
# <a name="eop-general-faq"></a>Domande frequenti su Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Di seguito vengono riportate le domande generali più frequenti sul servizio di filtraggio della posta elettronica ospitato sul cloud di Exchange Online Protection (EOP). Per ulteriori argomenti sulle domande frequenti (FAQ), accedere ai collegamenti seguenti:

- [Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Domande frequenti sull'amministrazione con delega](delegated-administration-faq.md)

- [Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)

- [Domande frequenti sulla quarantena](quarantine-faq.md)

- [Domande frequenti sulla protezione antimalware](anti-malware-protection-faq-eop.md)

- [Domande frequenti su Traccia messaggio](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Cos'è Exchange Online Protection?

EOP è un servizio di filtro della posta elettronica ospitato su cloud ideato per proteggere i clienti da posta indesiderata e malware e per implementare le regole criterio personalizzate. EOP è incluso in qualsiasi sottoscrizione Microsoft 365 che contiene cassette postali di Exchange Online. EOP è disponibile anche come offerta autonoma per proteggere gli ambienti di posta elettronica locali.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Come iscriversi alla versione di valutazione o alla versione per l'acquisto di EOP.

È possibile iscriversi alla versione di valutazione o per l'acquisto di EOP tramite il Web nella [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Le funzionalità di una versione di prova sono uguali a quelle di un abbonamento a pagamento, ma quest'ultimo include anche funzionalità aggiuntive fornite con il piano di abbonamento a [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>Qual è il prezzo di EOP.

EOP richiede una licenza per utente. Per informazioni più recenti sul prezzo, vedere la [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Tempo stimato per mettere in funzione EOP.

Quando vengono modificati il record MX, come evidenziato nella procedura in [Installazione del servizio EOP](set-up-your-eop-service.md), e i flussi di posta tramite EOP, il filtro viene immediatamente avviato. Il record MX potrebbe richiedere dalle 24 alle 48 ore per la propagazione tramite DNS. È possibile ottimizzare le impostazioni di protezione in qualsiasi momento durante questo processo.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>È necessario utilizzare tutte le funzionalità di Microsoft 365 per utilizzare EOP? Che cosa succede se si desidera solo la protezione di EOP e questo è tutto?

È possibile utilizzare EOP per proteggere le cassette postali locali senza utilizzare altre caratteristiche di Microsoft 365. Questa soluzione è nota come sottoscrizione indipendente. Un elenco di funzionalità EOP è consultabile in [Descrizione del servizio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Perché è necessario un tenant di Microsoft 365 quando si effettua la registrazione per il filtraggio della posta elettronica tramite EOP?

Microsoft 365 è il nome assegnato a una raccolta di prodotti e servizi a cui è possibile accedere tramite un tenant di Microsoft 365. Si pensi al tenant di Microsoft 365 come punto di partenza per il quale è possibile aggiungere licenze per il filtro della posta elettronica.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP dispone di un portale di comunicazione, nel quale è possibile trovare informazioni su problemi noti e possibili risoluzioni? Le informazioni sulle nuove funzionalità?

L'interfaccia di amministrazione di Microsoft 365 avrà alcune di queste informazioni. Se si ha un impatto su un evento di servizio, dovrebbe essere visualizzato un avviso di comunicazione (in genere accompagnato da un'icona del campanello) dopo aver eseguito l'accesso all'interfaccia di amministrazione di Microsoft 365. Si consiglia di leggere e intervenire su tutti gli elementi, come necessario.

Per quanto riguarda le nuove funzionalità di EOP, la [Roadmap di Microsoft 365 for business](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) è una buona risorsa per trovare informazioni sulle nuove funzionalità future. Verranno inoltre disposte articoli di Blog sulle nuove funzionalità per il sito Web [Microsoft 365 Blog](https://www.microsoft.com/microsoft-365/blog/) .

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Il servizio funziona con le versioni legacy di Exchange (ad esempio, Exchange Server 2010) e negli ambienti non Exchange?

Sì, il servizio è indipendente dal server e può essere utilizzato con qualsiasi agente di trasferimento messaggi SMTP.

## <a name="what-size-organization-can-use-the-service"></a>Per utilizzare il servizio, quali dimensioni deve avere un'organizzazione?

Qualsiasi dimensione. La rete EOP dispone di capacità sufficienti per rispondere alle esigenze di crescita dell'organizzazione, a prescindere dalla velocità di crescita.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Di quali autorizzazioni ho bisogno per configurare EOP?

Al fine di configurare EOP, è necessario essere un amministratore globale o di Exchange Company Administrator (gruppo di ruoli Gestione organizzazione).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Come è possibile verificare che i dati e le informazioni private siano al sicuro?

Per ulteriori informazioni sulla garanzia della sicurezza dei dati e delle informazioni private, incluse le informazioni sui contratti di servizio, vedere [Centro protezione Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Esistono limiti che devo conoscere, ad esempio limitazioni relative alle dimensioni del messaggio?

Sì. Per ulteriori informazioni sui limiti in EOP, vedere [limiti di Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>EOP supporta PowerShell?

Sì, la funzionalità full EOP è disponibile tramite PowerShell: Exchange Online PowerShell per le organizzazioni con cassette postali di Exchange Online; PowerShell EOP autonomo per organizzazioni EOP autonome. Per ulteriori informazioni, vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) ed [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).
