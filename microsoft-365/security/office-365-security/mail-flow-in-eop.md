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
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167240"
---
# <a name="mail-flow-in-eop"></a>Flusso di posta in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti le vedano. Sono disponibili opzioni su come instradare i messaggi che passano attraverso EOP per l'elaborazione prima che siano instradati alle cartelle Posta in arrivo dei lavoratori.

## <a name="working-with-messages-and-message-access-options"></a>Utilizzo dei messaggi e delle opzioni di accesso ai messaggi

EOP offre flessibilità nel modo in cui i messaggi vengono instradati. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.

[Utilizzare Directory Based Edge Blocking per rifiutare i messaggi inviati a destinatari non validi](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descrive la funzionalità di blocco edge basato su directory che consente di rifiutare i messaggi per destinatari non validi nel perimetro della rete del servizio.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.

Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Abilitare il flusso di posta per i sottodomini in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Configurare il flusso di posta utilizzando i](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) connettori introduce i connettori e mostra come utilizzarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.

[Il filtro avanzato per i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) descrive come configurare i connettori se la posta viene instradata a un servizio o a un dispositivo prima di EOP.

Nelle organizzazioni EOP autonome, è necessario eseguire un paio di passaggi di configurazione per garantire che la posta indesiderata venga instradata correttamente alla cartella posta indesiderata di ogni utente. Queste informazioni sono dettagliate in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Se non si desidera spostare i messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro dei contenuti). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificare il flusso di posta

Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).

[Testare il flusso di posta convalidando](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) i connettori di Microsoft 365 fornisce istruzioni per verificare che il flusso di posta sia configurato correttamente.
