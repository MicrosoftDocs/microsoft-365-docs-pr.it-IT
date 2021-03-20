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
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907027"
---
# <a name="mail-flow-in-eop"></a>Flusso di posta in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online o nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti le vedano. Sono disponibili opzioni su come instradare i messaggi che passano attraverso EOP per l'elaborazione prima che siano instradati alle cartelle Posta in arrivo dei lavoratori.

## <a name="working-with-messages-and-message-access-options"></a>Utilizzo dei messaggi e delle opzioni di accesso ai messaggi

EOP offre flessibilità nel modo in cui i messaggi vengono instradati. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.

[Usare Il blocco edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco edge basato su directory che consente di rifiutare i messaggi per i destinatari non validi nel perimetro della rete del servizio.

[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.

Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Enable mail flow for subdomains in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduce i connettori e mostra come usarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.

[Il filtro avanzato per i connettori](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) descrive come configurare i connettori se la posta viene instradata a un servizio o a un dispositivo prima di EOP.

Nelle organizzazioni EOP autonome, è necessario eseguire un paio di passaggi di configurazione per assicurarsi che la posta indesiderata venga instradata correttamente alla cartella posta indesiderata di ogni utente. Queste informazioni sono dettagliate in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se non si desidera spostare i messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata (noti anche come criteri di filtro del contenuto). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificare il flusso di posta

Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).

[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.