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
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537548"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Configurare il dominio per l'utilizzo con Microsoft 365 può essere difficile. Il sistema DNS non è facile da usare e la configurazione del DNS per il dominio influisce su attività aziendali importanti, come la posta elettronica.

> [!NOTE]
> Puoi verificare la presenza di problemi con il dominio controllandone lo stato. Vai a **Configurazione**  >  **domini** e visualizza le notifiche nella **colonna** Stato. Se si verifica un problema, selezionare i tre puntini (altre azioni), quindi scegliere **Controlla integrità**. Nel riquadro visualizzato verranno descritti gli eventuali problemi che si verificano con il dominio.
  
## <a name="whats-going-on"></a>Per quale motivo?

- [Non è possibile verificare il dominio?](#cant-verify-your-domain)
    
- [Outlook non funziona?](#outlook-isnt-working)
    
- [Tutti i messaggi di posta elettronica sono stati Microsoft 365 e si desidera passare solo alla posta elettronica?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Non è possibile verificare lo stato dell'account no profit o dell'istituto di istruzione?](#cant-confirm-non-profit-or-school-account-status)

- [I servizi non funzionano con il dominio?](#services-not-working-with-your-domain)
    
- [L'accesso al sito Web non funziona?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Non si riesce a verificare il dominio?
<a name="BKMK_verify"> </a>

La verifica del dominio potrebbe non funzionare in alcuni scenari comuni:
  
1. **Il valore del record di verifica non è corretto.** Controllare di aver copiato e incollato il valore esatto nel record di verifica TXT presso l'host DNS. Un problema comune è l'omissione della parte "MS =" del record, che invece è necessaria. 
    
2. **Il record non è stato salvato.** Presso alcuni host DNS è necessario eseguire un ulteriore passaggio per salvare il file di zona (in cui è archiviato il record DNS) in modo che venga aggiornato su Internet. Assicurarsi di aver salvato le modifiche in modo Microsoft 365 visualizzare e verificare il record. 
    
3. **Il record non è stato aggiornato su Internet.** In genere ci vogliono pochi minuti per poter visualizzare il nuovo record, ma a volte possono essere necessari fino a poche ore. 
    
## <a name="outlook-isnt-working"></a>Outlook non funziona?
<a name="BKMK_OutlookBroken"> </a>

Se la configurazione del record MX e di altri record DNS per il dominio è stata eseguita correttamente ma la posta elettronica non funziona, contattare il supporto per la [risoluzione dei problemi di Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Tutti i messaggi di posta elettronica sono stati Microsoft 365 e si desidera passare solo alla posta elettronica?
<a name="BKMK_EmailSwitched"> </a>

Quando si aggiunge il dominio a Microsoft 365, in genere il record MX del dominio viene aggiornato (da te o da Microsoft 365) in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere inviati Microsoft 365. Assicurarsi di aver creato cassette postali in Microsoft 365 per tutti gli utenti che hanno posta elettronica nel dominio prima di modificare il record MX.
  
Cosa succede se non si desidera spostare la posta elettronica per tutti gli utenti del dominio in Microsoft 365? È possibile eseguire operazioni pilota [Microsoft 365 solo alcuni indirizzi di posta elettronica.](../setup/domains-faq.yml)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Non è possibile verificare lo stato dell'account no profit o dell'istituto di istruzione?
<a name="BKMK_validateAcct"> </a>

Esistono un paio di scenari in cui è sufficiente verificare il dominio dell'organizzazione e non configurare alcun servizio. Ad esempio, per dimostrare Microsoft 365 che l'organizzazione è qualificata per una sottoscrizione dell'istituto di istruzione.
  
Consultare le indicazioni in Verificare il dominio Microsoft 365 per dimostrare lo stato di [proprietà,](../setup/domains-faq.yml) no profit o istruzione o per attivare Yammer per assicurarsi di aver completato tutti i passaggi necessari. È leggermente diverso per ogni situazione. 
  
## <a name="services-not-working-with-your-domain"></a>I servizi non funzionano con il proprio dominio?
<a name="BKMK_Test"> </a>

Sono disponibili strumenti e informazioni per individuare i problemi relativi alla configurazione del DNS del dominio. Lo strumento per la risoluzione dei Microsoft 365 dei domini mostrerà tutti i record che devono essere riparati e esattamente su quali record devono essere impostati. 

> [!TIP]
> Il DNS è configurato correttamente ma la posta elettronica non funziona in Outlook sul desktop? Consulta i diversi [scenari del flusso](/exchange/mail-flow-best-practices/mail-flow-best-practices) di posta che puoi avere con Microsoft 365 per assicurarti di aver configurato correttamente le cose per la tua azienda. Oppure, per altre informazioni sulla risoluzione dei problemi di posta, vedere [Risolvere i problemi di Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>L'accesso al sito Web non funziona?
<a name="BKMK_Website"> </a>

Se gli errori del DNS sono stati corretti ma si verificano ancora problemi, provare una della soluzioni seguenti.
  
- Le persone non riescono ad accedere al sito Web all'indirizzo www.mydomain.com: [Risolvere i problemi relativi al sito Web](../setup/add-domain.md)
    
- Non è possibile aggiornare il record A o il record CNAME in modo che punti al sito Web: [aggiornare i record DNS personalizzati in Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Contenuto correlato

[Risoluzione dei problemi: controllare i dati sulla modifica del dominio verificata](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

