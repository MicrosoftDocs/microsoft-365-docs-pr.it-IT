---
title: Flusso di posta in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: L'amministratore può ottenere informazioni sulle opzioni per la configurazione del flusso di posta e del routing in Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208331"
---
# <a name="mail-flow-in-eop"></a>Flusso di posta in Exchange Online Protection

In Microsoft 365 organizzazioni con cassette postali di Exchange Online o organizzazioni autonome di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li vedano. Sono disponibili opzioni su come instradare i messaggi che passano attraverso EOP per l'elaborazione prima che vengano instradati alle cassette postali di lavoro.

## <a name="working-with-messages-and-message-access-options"></a>Utilizzo dei messaggi e delle opzioni di accesso ai messaggi

EOP offre flessibilità nel modo in cui i messaggi vengono instradati. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.

[Utilizzare il blocco Edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco Edge basato su directory che consente di rifiutare i messaggi per i destinatari non validi nel perimetro della rete di servizi.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.

Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Enable Mail Flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configure Mail Flow using Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduce connettori e visualizza come utilizzarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.

[Filtro avanzato per i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) viene descritto come configurare i connettori se la posta viene instradata a un servizio o a un dispositivo prima di EOP.

Nelle organizzazioni di EOP autonome, è necessario eseguire una procedura di configurazione di coppia per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ogni utente. Sono descritti in dettaglio in [Configure standalone EOP per recapitare la posta indesiderata alla cartella posta indesiderata in ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se non si desidera spostare i messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata (noti anche come criteri di filtro dei contenuti). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificare il flusso di posta

Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).

[Testare il flusso di posta convalidando i connettori Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornisce le istruzioni per testare che il flusso di posta è configurato correttamente.
