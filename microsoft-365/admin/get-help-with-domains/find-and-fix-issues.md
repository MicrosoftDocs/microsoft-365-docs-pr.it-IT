---
title: Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Informazioni su come individuare i problemi che si sono verificati durante la configurazione di un dominio personalizzato assicurandosi che i record DNS siano configurati correttamente.
ms.openlocfilehash: 277e87ad6b06db0b1ef3b3cb5eaaa45a2e77ed6f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252956"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
La configurazione del dominio affinché funzioni con Office 365 può essere un'attività complicata. Il sistema DNS non è facile da usare e la configurazione del DNS per il dominio influisce su attività aziendali importanti, come la posta elettronica.

> [!NOTE]
> È possibile verificare se si verificano problemi con il dominio verificando il relativo stato. Andare a **** > **Domains** Settings e visualizzare le notifiche nella colonna **stato** . Se viene visualizzato un problema, selezionare altre azioni (tre punti) e quindi fare clic su **Controlla integrità**. Il riquadro che si apre descriverà tutti i problemi che si verificano con il dominio.
  
## <a name="whats-going-on"></a>Per quale motivo?

- [Non è possibile verificare il dominio?](#cant-verify-your-domain)
    
- [Outlook non funziona?](#outlook-isnt-working)
    
- [L'indirizzo di posta elettronica di tutti è stato spostato a Office 365 e si voleva solo che la posta elettronica cambiasse?](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [Non è possibile verificare lo stato di un account non profit o School?](#cant-confirm-non-profit-or-school-account-status)

- [Servizi che non utilizzano il dominio?](#services-not-working-with-your-domain)
    
- [L'accesso al sito Web non funziona?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Non si riesce a verificare il dominio?
<a name="BKMK_verify"> </a>

La verifica del dominio potrebbe non funzionare in alcuni scenari comuni:
  
1. **Il valore del record di verifica non è corretto.** Controllare di aver copiato e incollato il valore esatto nel record di verifica TXT presso l'host DNS. Un problema comune è l'omissione della parte "MS =" del record, che invece è necessaria. 
    
2. **Il record non è stato salvato.** Presso alcuni host DNS è necessario eseguire un ulteriore passaggio per salvare il file di zona (in cui è archiviato il record DNS) in modo che venga aggiornato su Internet. Verificare di avere salvato le modifiche affinché Office 365 possa visualizzare e verificare il record. 
    
3. **Il record non è stato aggiornato su Internet.** In genere, è necessario solo qualche minuto perché sia possibile visualizzare il nuovo record, ma a volte può richiedere fino a poche ore. 
    
## <a name="outlook-isnt-working"></a>Outlook non funziona?
<a name="BKMK_OutlookBroken"> </a>

Se la configurazione del record MX e di altri record DNS per il dominio è stata eseguita correttamente ma la posta elettronica non funziona, contattare il supporto per la [risoluzione dei problemi di Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>L'indirizzo di posta elettronica di tutti è stato spostato a Office 365 e si voleva solo che la posta elettronica cambiasse?
<a name="BKMK_EmailSwitched"> </a>

Quando si aggiunge il dominio a Office 365, in genere il record MX del dominio viene aggiornato (dall'utente o da Office 365) per puntare a Office 365 e tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a venire a Office 365. Assicurarsi di aver creato le cassette postali in Office 365 per tutti gli utenti che hanno un messaggio di posta elettronica nel dominio prima di modificare il record MX.
  
Che cosa fare se non si desidera spostare la posta elettronica per tutti gli utenti del dominio in Office 365? È possibile [eseguire una distribuzione pilota di Office 365 con solo alcuni indirizzi di posta elettronica](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Non è possibile verificare lo stato di un account non profit o School?
<a name="BKMK_validateAcct"> </a>

Esistono due scenari in cui è solo necessario verificare il dominio dell'organizzazione e non configurare i servizi. Ad esempio, per dimostrare a Office 365 che l'organizzazione è qualificata per un abbonamento scolastico.
  
Consultare le indicazioni contenute nella [Verifica del dominio di Office 365 per dimostrare la proprietà, l'organizzazione no profit o l'istruzione o per attivare Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) per assicurarsi di aver completato tutti i passaggi necessari. Si tratta di un po' diverso per ogni situazione. 
  
## <a name="services-not-working-with-your-domain"></a>I servizi non funzionano con il proprio dominio?
<a name="BKMK_Test"> </a>

Sono disponibili strumenti e informazioni per individuare i problemi relativi alla configurazione del DNS del dominio. Lo strumento di risoluzione dei problemi dei domini in Office 365 indica gli eventuali record che è necessario correggere e il modo esatto in cui devono essere configurati. 

> [!TIP]
> Il DNS è configurato correttamente ma la posta elettronica non funziona in Outlook sul desktop? Vedere i [diversi scenari del flusso di posta che si possono avere con Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) per assicurarsi che tutte le opzioni siano configurate correttamente per l'organizzazione. Oppure, per altre informazioni sulla risoluzione dei problemi di posta, vedere [Risolvere i problemi di Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## <a name="accessing-your-website-isnt-working"></a>L'accesso al sito Web non funziona?
<a name="BKMK_Website"> </a>

Se gli errori del DNS sono stati corretti ma si verificano ancora problemi, provare una della soluzioni seguenti.
  
- Le persone non riescono ad accedere al sito Web all'indirizzo www.mydomain.com: [Risolvere i problemi relativi al sito Web](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- Non è possibile aggiornare il record A o il record CNAME in modo che punti al sito Web: [Aggiornare i record DNS personalizzati in Office 365](../dns/add-or-edit-custom-dns-records.md)
    
