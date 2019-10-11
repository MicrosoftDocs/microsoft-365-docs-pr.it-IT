---
title: Domande frequenti su EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'Di seguito vengono riportate le risposte alle domande più frequenti sul servizio di filtro della posta elettronica ospitato su cloud di Microsoft Exchange Online Protection (EOP). Per ulteriori argomenti sulle domande frequenti (FAQ), accedere ai collegamenti seguenti:'
ms.openlocfilehash: b49bb92cea781dc2c2120f1c0512a9de5182f16a
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441503"
---
# <a name="eop-general-faq"></a>Domande frequenti su Exchange Online Protection

Di seguito vengono riportate le risposte alle domande più frequenti sul servizio di filtro della posta elettronica ospitato su cloud di Microsoft Exchange Online Protection (EOP). Per ulteriori argomenti sulle domande frequenti (FAQ), accedere ai collegamenti seguenti:
  
- [Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Domande frequenti sull'amministrazione con delega](delegated-administration-faq.md)

- [Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)

- [Elenchi di mittenti attendibili e bloccati in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

- [Domande frequenti sulla quarantena](quarantine-faq.md)

- [Domande frequenti sulla protezione antimalware](anti-malware-protection-faq-eop.md)

- [Domande frequenti su Traccia messaggio](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx)

**D. Definizione di EOP**
  
R. EOP è un servizio di filtro della posta elettronica ospitato su cloud ideato per proteggere i clienti da posta indesiderata e malware e per implementare le regole criterio personalizzate.
  
**D. Come iscriversi alla versione di valutazione o alla versione per l'acquisto di EOP.**
  
R. È possibile iscriversi alla versione di valutazione o per l'acquisto di EOP tramite il Web nella [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Le funzionalità di una versione di prova sono uguali a quelle di un abbonamento a pagamento, ma quest'ultimo include anche funzionalità aggiuntive fornite con il piano di abbonamento a [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).
  
**D. Qual è il prezzo di EOP.**
  
R. EOP richiede una licenza per utente. Per informazioni più recenti sul prezzo, vedere la [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).
  
**D. Tempo stimato per mettere in funzione EOP.**
  
R. Quando vengono modificati il record MX, come evidenziato nella procedura in [Installazione del servizio EOP](set-up-your-eop-service.md), e i flussi di posta tramite EOP, il filtro viene immediatamente avviato. Il record MX potrebbe richiedere dalle 24 alle 48 ore per la propagazione tramite DNS. È possibile ottimizzare le impostazioni di protezione nell'interfaccia amministrativa di Exchange in qualsiasi momento del processo.
  
**D. È necessario utilizzare tutte le funzionalità di Microsoft Office 365 per utilizzare EOP? È possibile utilizzare solamente la protezione EOP?**
  
R. È possibile utilizzare solamente EOP per proteggere le cassette postali locali senza utilizzare altre funzionalità di Office 365. Questa soluzione è nota come sottoscrizione indipendente. Un elenco di funzionalità EOP è consultabile in [Descrizione del servizio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).
  
**D. Perché è necessario un tenant di Office 365 quando si effettua la registrazione per il filtro di posta elettronica tramite EOP?**
  
R. Office 365 è il nome dato a una raccolta di prodotti e servizi a cui è possibile accedere tramite tenant di Office 365. Pensare al tenant di Office 365 come il punto di inizio a cui aggiungere licenze per il filtro della posta elettronica.
  
**D. EOP dispone di un portale di comunicazione, nel quale è possibile trovare informazioni su problemi noti e possibili risoluzioni? Le informazioni sulle nuove funzionalità?**
  
R. L'interfaccia di amministrazione di Microsoft 365 avrà alcune di queste informazioni. Se si ha un impatto su un evento di servizio, dovrebbe essere visualizzato un avviso di comunicazione (in genere accompagnato da un'icona del campanello) dopo aver eseguito l'accesso all'interfaccia di amministrazione di Microsoft 365. Si consiglia di leggere e intervenire su tutti gli elementi, come necessario.
  
In relazione alle funzionalità EOP, la [guida a Office 365 for business](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) è un ottima risorsa per trovare informazioni sulle nuove imminenti funzionalità. Verranno inoltre disposte articoli di Blog sulle nuove funzionalità per il sito Web [Microsoft 365 Blog](https://www.microsoft.com/en-us/microsoft-365/blog/) .
  
**D. Il servizio funziona con le versioni legacy di Exchange (ad esempio, Exchange Server 2010) e negli ambienti non Exchange?**
  
R. Sì, il servizio è indipendente dal server e può essere utilizzato con qualsiasi agente di trasferimento messaggi SMTP.
  
**D. Per utilizzare il servizio, quali dimensioni deve avere un'organizzazione?**
  
R. Qualsiasi dimensione. La rete EOP dispone di capacità sufficienti per rispondere alle esigenze di crescita dell'organizzazione, a prescindere dalla velocità di crescita.
  
**Di quali autorizzazioni ho bisogno per configurare EOP?**
  
Per configurare EOP, l'utente deve essere Amministratore globale di Office 365 o Amministratore aziendale di Exchange (gruppo dei ruoli di gestione dell'organizzazione).
  
**D. Come è possibile verificare che i dati e le informazioni private siano al sicuro?**
  
R. Per ulteriori informazioni sulla garanzia della sicurezza dei dati e delle informazioni private, incluse le informazioni sui contratti di servizio, vedere [Centro protezione Office 365](https://www.microsoft.com/trust-center).
  
**D. Esistono limiti che devo conoscere, ad esempio limitazioni relative alle dimensioni del messaggio?**
  
Per ulteriori informazioni sui limiti in EOP, vedere [Limiti Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).
  
**D: EOP supporta PowerShell?**
  
R. Sì, la funzionalità EOP completa è disponibile tramite PowerShell. Per ulteriori informazioni, vedere [PowerShell di Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).
