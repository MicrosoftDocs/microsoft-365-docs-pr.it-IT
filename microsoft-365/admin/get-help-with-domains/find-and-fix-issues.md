---
title: Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Informazioni su come tenere traccia degli eventuali problemi che si verificano durante la configurazione di un dominio personalizzato verificando che i record DNS siano configurati correttamente.
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926391"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Configurare il dominio per l'utilizzo con Microsoft 365 può essere difficile. Il sistema DNS non è facile da usare e la configurazione del DNS per il dominio influisce su attività aziendali importanti, come la posta elettronica.

> [!NOTE]
> È possibile verificare la presenza di problemi con il dominio controllandone lo stato. Passare a **Setup**  >  **Domains** e visualizzare le notifiche nella **colonna** Status. Se si verifica un problema, selezionare Altre azioni (tre puntini) e quindi scegliere **Controlla integrità.** Nel riquadro visualizzato verranno descritti gli eventuali problemi che si verificano con il dominio.
  
## <a name="whats-going-on"></a>Per quale motivo?

- [Non è possibile verificare il dominio?](#cant-verify-your-domain)
    
- [Outlook non funziona?](#outlook-isnt-working)
    
- [La posta elettronica di tutti gli utenti è passata a Microsoft 365 e si desidera passare solo alla posta elettronica?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Non è possibile confermare lo stato dell'account no profit o dell'istituto di istruzione?](#cant-confirm-non-profit-or-school-account-status)

- [I servizi non funzionano con il dominio?](#services-not-working-with-your-domain)
    
- [L'accesso al sito Web non funziona?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Non si riesce a verificare il dominio?
<a name="BKMK_verify"> </a>

La verifica del dominio potrebbe non funzionare in alcuni scenari comuni:
  
1. **Il valore del record di verifica non è corretto.** Controllare di aver copiato e incollato il valore esatto nel record di verifica TXT presso l'host DNS. Un problema comune è l'omissione della parte "MS =" del record, che invece è necessaria. 
    
2. **Il record non è stato salvato.** Presso alcuni host DNS è necessario eseguire un ulteriore passaggio per salvare il file di zona (in cui è archiviato il record DNS) in modo che venga aggiornato su Internet. Assicurarsi di aver salvato le modifiche in modo che Microsoft 365 possa visualizzare e verificare il record. 
    
3. **Il record non è stato aggiornato su Internet.** La possibilità di visualizzare il nuovo record richiede in genere solo alcuni minuti, ma a volte può richiedere fino a qualche ora. 
    
## <a name="outlook-isnt-working"></a>Outlook non funziona?
<a name="BKMK_OutlookBroken"> </a>

Se la configurazione del record MX e di altri record DNS per il dominio è stata eseguita correttamente ma la posta elettronica non funziona, contattare il supporto per la [risoluzione dei problemi di Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>La posta elettronica di tutti gli utenti è passata a Microsoft 365 e si desidera passare solo alla posta elettronica?
<a name="BKMK_EmailSwitched"> </a>

Quando si aggiunge il dominio a Microsoft 365, in genere il record MX del dominio viene aggiornato (dall'utente o da Microsoft 365) in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere inviati a Microsoft 365. Assicurarsi di aver creato cassette postali in Microsoft 365 per tutti gli utenti che hanno posta elettronica nel dominio prima di modificare il record MX.
  
Cosa succede se non si vuole spostare la posta elettronica per tutti gli utenti del dominio in Microsoft 365? È possibile eseguire la procedura pilota [di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)con pochi indirizzi di posta elettronica.
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Non è possibile confermare lo stato dell'account no profit o dell'istituto di istruzione?
<a name="BKMK_validateAcct"> </a>

Esistono due scenari in cui è sufficiente verificare il dominio dell'organizzazione e non configurare alcun servizio. Ad esempio, per dimostrare a Microsoft 365 che l'organizzazione è qualificata per un abbonamento scolastico.
  
Consultare le indicazioni in Verificare il dominio [di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) per dimostrare la proprietà, lo stato dell'organizzazione no profit o dell'istruzione o per attivare Yammer per assicurarsi di aver completato tutti i passaggi necessari. È leggermente diverso per ogni situazione. 
  
## <a name="services-not-working-with-your-domain"></a>I servizi non funzionano con il proprio dominio?
<a name="BKMK_Test"> </a>

Sono disponibili strumenti e informazioni per individuare i problemi relativi alla configurazione del DNS del dominio. Lo strumento di risoluzione dei problemi dei domini in Microsoft 365 mostrerà tutti i record che devono essere riparati e esattamente su quali record devono essere impostati. 

> [!TIP]
> Il DNS è configurato correttamente ma la posta elettronica non funziona in Outlook sul desktop? Consultare i diversi scenari del flusso di posta che è possibile avere con [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) per verificare che le operazioni siano configurate correttamente per l'azienda. Oppure, per altre informazioni sulla risoluzione dei problemi di posta, vedere [Risolvere i problemi di Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>L'accesso al sito Web non funziona?
<a name="BKMK_Website"> </a>

Se gli errori del DNS sono stati corretti ma si verificano ancora problemi, provare una della soluzioni seguenti.
  
- Le persone non riescono ad accedere al sito Web all'indirizzo www.mydomain.com: [Risolvere i problemi relativi al sito Web](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Non è possibile aggiornare il record A o CNAME in modo che punti al sito Web: [aggiornare i record DNS personalizzati in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)

## <a name="related-content"></a>Contenuti correlati

[Risoluzione dei problemi: controllare i dati sulla modifica del dominio verificata](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
