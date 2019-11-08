---
title: Risolvere i problemi di recapito della posta elettronica per il codice di errore 5.7.7 XX in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Informazioni su come risolvere i problemi di posta elettronica per il codice di errore 5.7.7 XX in Exchange Online (tenant bloccato dall'invio di messaggi di posta elettronica).
ms.openlocfilehash: 28ed444d821cbe00cfcb92872de15bb43a65ae28
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033877"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Risolvere i problemi di recapito della posta elettronica per il codice di errore 5.7.7 XX in Exchange Online

In questo argomento vengono descritte le operazioni che è possibile eseguire se viene visualizzato il codice di stato 550 5.7.7 XX in un rapporto di mancato recapito (noto anche come NDR, messaggio di rimbalzo, notifica sullo stato del recapito o DSN). Questa notifica automatica viene visualizzata quando il tenant è limitato dall'invio di messaggi di posta elettronica in un modo o nell'altro. Questi codici di errore vengono in genere disponibili come 705 o 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: tenant ha superato la restrizione di soglia: informazioni utili

I mittenti interni possono vedere questo rapporto di mancato recapito quando si tenta di inviare messaggi di posta elettronica se il tenant è stato compromesso. Questo solitamente occus quando la maggior parte del traffico proveniente dal tenant è stata rilevata come sospetta e ha portato al divieto di inviare l'abilità per il tenant. Questo può verificarsi anche se gli utenti inviano una grande quantità di posta in blocco da Office 365. Come indicato nella descrizione del servizio, i clienti di Exchange Online che hanno la necessità di inviare messaggi di posta elettronica commerciali legittimi (ad esempio, i bollettini dei clienti) devono utilizzare provider di terze parti specializzati in tali servizi.

Una volta che gli utenti collettivamente, come tenant, inviano una certa quantità di posta sospette tramite il servizio, a tutti gli utenti può essere impedito di inviare posta finché il problema non viene risolto. Gli utenti riceveranno un rapporto di mancato recapito (NDR) che indica quanto segue:

- 550 5.7.705 accesso negato, il tenant ha superato la soglia

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: limitazione della posta elettronica del dominio non registrato: informazioni utili

Office 365 consente ai tenant di inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Un esempio supportato potrebbe essere quello in cui gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno invia loro la posta elettronica, ma l'inoltro della posta elettronica è configurato in modo che rientri nella cassetta postale esterna dell'utente. Questo è il più comune negli ambienti scolastici in cui gli studenti desiderano sfruttare la propria interfaccia di posta elettronica personale, ma continuano a ricevere messaggi di posta elettronica correlati alla scuola. Un altro esempio è quando i clienti sono in uno scenario ibrido e dispongono di server locali che inviano messaggi di posta elettronica da EOP.

### <a name="problems-with-unregistered-domains"></a>Problemi relativi ai domini non registrati

Il problema è quando i server locali vengono compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata fuori EOP. In quasi tutti i casi, i connettori giusti sono configurati, ma il messaggio di posta elettronica viene inviato dall'annullamento della registrazione, noto anche come Unprovisioned, Domains. Office 365 consente una quantità ragionevole di messaggi di posta elettronica provenienti da domini non registrati, ma un dominio accettato deve essere configurato nell'interfaccia di amministrazione per ogni dominio in cui si intende inviare.

Una volta compromesso, ai tenant verrà impedito di inviare la posta in uscita per i domini non registrati. Gli utenti riceveranno un rapporto di mancato recapito (NDR) che indica quanto segue:

- 550 servizio 5.7.750 non disponibile. Client bloccato dall'invio di domini non registrati

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>Come sbloccare tenant per inviare di nuovo

Se il tenant viene bloccato per l'invio di messaggi di posta elettronica, è necessario eseguire diverse operazioni:

1. Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Microsoft 365. Ulteriori informazioni sono disponibili [qui](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Cercare connettori inusuali. Gli attori maligni spesso creano nuovi connettori in ingresso nel tenant di Office 365 per inviare la posta indesiderata. Ulteriori informazioni su come controllare i connettori sono disponibili [qui](https://docs.microsoft.com/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloccare i server locali e assicurarsi che non vengano compromessi.

> [!TIP]
> Vi sono numerosi fattori coinvolti in questo articolo, soprattutto se si tratta di server di terze parti. Indipendentemente da ciò, è necessario essere in grado di confermare che tutti i messaggi che lasciano i server siano legittimi.

4. Dopo aver completato l'operazione, è necessario chiamare il supporto tecnico Microsoft e chiedere di ottenere il tenant sbloccato per inviare di nuovo i domini non registrati.  Fornire il codice di errore è utile, ma sarà necessario dimostrare che l'ambiente è protetto e che la posta indesiderata non verrà più inviata. Ulteriori informazioni sull'apertura di un caso di supporto sono disponibili [qui](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Rapporti di mancato recapito della posta elettronica in Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurare l'inoltro della posta elettronica per una cassetta postale](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365](https://support.office.com/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Gestire i domini accettati in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
