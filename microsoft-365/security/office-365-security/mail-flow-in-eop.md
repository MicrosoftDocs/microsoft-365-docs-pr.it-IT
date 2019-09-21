---
title: Flusso di posta in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Come cliente di Exchange Online Protection (EOP), tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li visualizzino. A prescindere che tutte le cassette postali siano ospitate nel cloud con Exchange Online o siano locali (il cosiddetto scenario autonomo), ad esempio per continuare a sfruttare l'infrastruttura esistente, sono disponibili diverse opzioni di routing dei messaggi che passeranno attraverso EOP per l'elaborazione prima di essere instradati alle cassette postali dei dipendenti.
ms.openlocfilehash: 2d377e2cd7f6ce2856deda55052b4535649ef8b5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082815"
---
# <a name="mail-flow-in-eop"></a>Flusso di posta in Exchange Online Protection

Come cliente di Exchange Online Protection (EOP), tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li visualizzino. A prescindere che tutte le cassette postali siano ospitate nel cloud con Exchange Online o siano locali (il cosiddetto scenario autonomo), ad esempio per continuare a sfruttare l'infrastruttura esistente, sono disponibili diverse opzioni di routing dei messaggi che passeranno attraverso EOP per l'elaborazione prima di essere instradati alle cassette postali dei dipendenti.
  
È possibile configurare il routing della posta personalizzato ai fini della conformità della messaggistica a un requisito aziendale. Ad esempio, è possibile far passare tutta la posta in uscita attraverso l'applicazione di filtro dei criteri di posta.
  
## <a name="working-with-messages-and-message-access-options"></a>Utilizzo dei messaggi e delle opzioni di accesso ai messaggi

EOP offre molta flessibilità per il routing dei messaggi. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.
  
[Utilizzare il blocco Edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco Edge basato su directory che consente di rifiutare i messaggi per i destinatari non validi nel perimetro della rete di servizi. 
  
[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.
  
Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Enable Mail Flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).
  
In [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) vengono descritti i connettori EOP e come è possibile utilizzarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.
  
Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella Posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. Queste informazioni sono dettagliate [per garantire che la posta indesiderata venga instradata alla cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se non si intende spostare i messaggi nella cartella Posta indesiderata di ciascun utente, è possibile optare per un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
  
## <a name="verify-mail-flow"></a>Verificare il flusso di posta

Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).
  
[Test del flusso di posta convalidando i connettori di Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) , vengono fornite istruzioni per testare che il flusso di posta è configurato correttamente.
