---
title: Flusso di posta in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: L'amministratore può ottenere informazioni sulle opzioni per la configurazione del flusso di posta e del routing in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842495"
---
# <a name="mail-flow-in-eop"></a>Flusso di posta in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali di Exchange Online o organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti le vedano. Sono disponibili opzioni su come instradare i messaggi che passano attraverso EOP per l'elaborazione prima che siano instradati alle cartelle Posta in arrivo dei lavoratori.

## <a name="working-with-messages-and-message-access-options"></a>Utilizzo dei messaggi e delle opzioni di accesso ai messaggi

EOP offre flessibilità nel modo in cui i messaggi vengono instradati. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.

[Usare Il blocco edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco edge basato su directory che consente di rifiutare i messaggi per i destinatari non validi nel perimetro della rete del servizio.

[In View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) viene descritto come gestire i domini associati al servizio EOP.

Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduce i connettori e mostra come usarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.

[Il filtro avanzato per i connettori](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) descrive come configurare i connettori se la posta viene instradata a un servizio o a un dispositivo prima di EOP.

Negli ambienti ibridi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (anche note come regole di trasporto) in Exchange locale per tradurre il verdetto filtro posta indesiderata in modo che la regola della posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per dettagli, vedere [Configurare EOP per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Se non si desidera spostare i messaggi nella cartella Posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata (noti anche come criteri di filtro del contenuto). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificare il flusso di posta

Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](/exchange/standalone-eop/set-up-your-eop-service).

[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.
