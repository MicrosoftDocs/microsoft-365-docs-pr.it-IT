---
title: Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Informazioni su come individuare i problemi che si sono verificati durante la configurazione di un dominio personalizzato assicurandosi che i record DNS siano configurati correttamente.
ms.openlocfilehash: e3c66e10a673d840cfddad81a057739b6dfac721
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399945"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Ottenere il dominio configurato per l'uso con Microsoft 365 può essere difficile. Il sistema DNS non è facile da usare e la configurazione del DNS per il dominio influisce su attività aziendali importanti, come la posta elettronica.

> [!NOTE]
> È possibile verificare se si verificano problemi con il dominio verificando il relativo stato. Accedere a **Setup**  >  **domini** di installazione e visualizzare le notifiche nella colonna **stato** . Se viene visualizzato un problema, selezionare altre azioni (tre punti) e quindi fare clic su **Controlla integrità**. Il riquadro che si apre descriverà tutti i problemi che si verificano con il dominio.
  
## <a name="whats-going-on"></a>Per quale motivo?

- [Non è possibile verificare il dominio?](#cant-verify-your-domain)
    
- [Outlook non funziona?](#outlook-isnt-working)
    
- [LA posta elettronica di tutti è stata commutata in Microsoft 365 e si voleva solo che la posta elettronica cambiasse?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Non è possibile verificare lo stato di un account non profit o School?](#cant-confirm-non-profit-or-school-account-status)

- [Servizi che non utilizzano il dominio?](#services-not-working-with-your-domain)
    
- [L'accesso al sito Web non funziona?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Non si riesce a verificare il dominio?
<a name="BKMK_verify"> </a>

La verifica del dominio potrebbe non funzionare in alcuni scenari comuni:
  
1. **Il valore del record di verifica non è corretto.** Controllare di aver copiato e incollato il valore esatto nel record di verifica TXT presso l'host DNS. Un problema comune è l'omissione della parte "MS =" del record, che invece è necessaria. 
    
2. **Il record non è stato salvato.** Presso alcuni host DNS è necessario eseguire un ulteriore passaggio per salvare il file di zona (in cui è archiviato il record DNS) in modo che venga aggiornato su Internet. Assicurarsi di aver salvato le modifiche in modo che Microsoft 365 possa visualizzare e verificare il record. 
    
3. **Il record non è stato aggiornato su Internet.** In genere, è necessario solo qualche minuto perché sia possibile visualizzare il nuovo record, ma a volte può richiedere fino a poche ore. 
    
## <a name="outlook-isnt-working"></a>Outlook non funziona?
<a name="BKMK_OutlookBroken"> </a>

Se la configurazione del record MX e di altri record DNS per il dominio è stata eseguita correttamente ma la posta elettronica non funziona, contattare il supporto per la [risoluzione dei problemi di Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>LA posta elettronica di tutti è stata commutata in Microsoft 365 e si voleva solo che la posta elettronica cambiasse?
<a name="BKMK_EmailSwitched"> </a>

Quando si aggiunge il dominio a Microsoft 365, in genere il record MX del dominio viene aggiornato (dall'utente o da Microsoft 365) per puntare a Microsoft 365 e tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365. Assicurarsi di aver creato le cassette postali in Microsoft 365 per tutti gli utenti che hanno un messaggio di posta elettronica nel dominio prima di modificare il record MX.
  
Che cosa fare se non si desidera spostare la posta elettronica per tutti gli utenti del dominio in Microsoft 365? È possibile eseguire la procedura per [pilotare Microsoft 365 con solo alcuni indirizzi di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Non è possibile verificare lo stato di un account non profit o School?
<a name="BKMK_validateAcct"> </a>

Esistono due scenari in cui è solo necessario verificare il dominio dell'organizzazione e non configurare i servizi. Ad esempio, per dimostrare a Microsoft 365 che l'organizzazione è qualificata per un abbonamento scolastico.
  
Consultare le linee guida per [verificare il dominio Microsoft 365 per dimostrare la proprietà, l'organizzazione no profit o l'istruzione o per attivare Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) per assicurarsi di aver completato tutti i passaggi necessari. Si tratta di un po' diverso per ogni situazione. 
  
## <a name="services-not-working-with-your-domain"></a>I servizi non funzionano con il proprio dominio?
<a name="BKMK_Test"> </a>

Sono disponibili strumenti e informazioni per individuare i problemi relativi alla configurazione del DNS del dominio. La risoluzione dei problemi relativi ai domini in Microsoft 365 mostrerà gli eventuali record che devono essere fissati e gli elementi di cui è necessario impostare i record. 

> [!TIP]
> Il DNS è configurato correttamente ma la posta elettronica non funziona in Outlook sul desktop? Consultare i [diversi scenari del flusso di posta che è possibile avere con Microsoft 365](https://www.microsoft.com/?ref=go) per assicurarsi che siano configurati correttamente per la propria azienda. Oppure, per altre informazioni sulla risoluzione dei problemi di posta, vedere [Risolvere i problemi di Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>L'accesso al sito Web non funziona?
<a name="BKMK_Website"> </a>

Se gli errori del DNS sono stati corretti ma si verificano ancora problemi, provare una della soluzioni seguenti.
  
- Le persone non riescono ad accedere al sito Web all'indirizzo www.mydomain.com: [Risolvere i problemi relativi al sito Web](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Non è possibile aggiornare il record a record o CNAME in modo che punti al sito Web: [aggiornare i record DNS personalizzati in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
