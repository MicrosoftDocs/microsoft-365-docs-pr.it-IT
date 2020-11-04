---
title: Informazioni dettagliate sui messaggi di posta elettronica dei nuovi domini inoltrati
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono scoprire come utilizzare i nuovi domini che vengono inoltrati tramite posta elettronica nell'interfaccia di amministrazione di Exchange moderna per esaminare quando gli utenti dell'organizzazione stanno inoltrando messaggi a domini esterni che non sono mai stati inoltrati.
ms.openlocfilehash: 7dfdd63a9358b1057313962bc21424a325d7bc52
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877742"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nuovi domini che vengono inoltrati Insight di posta elettronica nel centro sicurezza & Compliance

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Anche se è possibile che si disponga di motivi aziendali validi per inoltrare messaggi di posta elettronica a destinatari esterni in domini specifici, è sospetto quando gli utenti dell'organizzazione iniziano improvvisamente a inoltrare messaggi a domini esterni e nessuno nell'organizzazione ha mai inoltrato i messaggi a tali domini prima (nuovi domini). Questa condizione potrebbe indicare che gli account utente sono compromessi. Se si sospetta che gli account siano stati compromessi, vedere [rispondere a un account di posta elettronica compromesso](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

I **nuovi domini che vengono inoltrati tramite posta elettronica** nel [Centro sicurezza & Compliance](https://protection.office.com) notifica quando gli utenti dell'organizzazione stanno inoltrando i messaggi ai nuovi domini.

Questa intuizione viene visualizzata solo quando il problema viene rilevato e viene visualizzato nella pagina del [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report) .

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi domini inoltrati](../../media/mfi-new-domains-being-forwarded.png)

Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report).

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic sui nuovi domini che vengono inoltrati Insight della posta elettronica](../../media/mfi-new-domains-being-forwarded-details.png)

È inoltre possibile accedere a questa pagina dei dettagli quando si seleziona l'Insight dopo aver fatto clic su **Visualizza tutti** nell'area **suggerimenti & consigliati** (dashboard dei **report** \> **Dashboard** o <https://protection.office.com/insightdashboard> ).

Per impedire l'inoltro automatico dei messaggi ai domini esterni, configurare un dominio remoto per alcuni o per tutti i domini esterni. Per ulteriori informazioni, vedere [Manage Remote Domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
