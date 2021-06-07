---
title: Configurazione e controllo dell'inoltro esterno della posta elettronica, inoltro automatico, accesso negato 5.7.520, disabilitazione dell'inoltro esterno, L'amministratore ha disabilitato l'inoltro esterno, i criteri di protezione da posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b96d3d656a89e7102550d09a2f5052fdb5ae818
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52792957"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controllare l'inoltro automatico della posta elettronica esterna in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Gli amministratori potrebbero avere requisiti aziendali per limitare o controllare i messaggi inoltrati automaticamente a destinatari esterni (destinatari esterni all'organizzazione). L'inoltro della posta elettronica può essere utile, ma può anche rappresentare un rischio per la sicurezza a causa della potenziale divulgazione di informazioni. Gli utenti malintenzionati potrebbero usare queste informazioni per attaccare l'organizzazione o i partner.

I seguenti tipi di inoltro automatico sono disponibili in Microsoft 365:

- Gli utenti possono configurare [le regole di Posta](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) in arrivo per inoltrare automaticamente i messaggi ai mittenti esterni (deliberatamente o a seguito di un account compromesso).
- Gli amministratori possono configurare [l'inoltro delle cassette](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) postali (noto anche come inoltro _SMTP)_ per inoltrare automaticamente i messaggi ai destinatari esterni. L'amministratore può scegliere se inoltrare semplicemente i messaggi o conservare copie dei messaggi inoltrati nella cassetta postale.

È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni. Sono disponibili tre impostazioni:

- **Automatico - Controllato dal sistema:** l'inoltro esterno automatico è bloccato. L'inoltro automatico interno dei messaggi continuerà a funzionare. Questa è l'impostazione predefinita.
- **On**: l'inoltro esterno automatico è consentito e non limitato.
- **Disattivato:** l'inoltro esterno automatico è disabilitato e verrà visualizzato un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito) al mittente.

Per istruzioni su come configurare queste impostazioni, vedere [Configure outbound spam filtering in EOP.](configure-the-outbound-spam-policy.md)

> [!NOTE]
>
> - La disabilitazione dell'inoltro automatico disabilita le regole di Posta in arrivo (utenti) o l'inoltro delle cassette postali (amministratori) che reindirizzano i messaggi a indirizzi esterni.
>
> - L'inoltro automatico dei messaggi tra utenti interni non è influenzato dalle impostazioni dei criteri di filtro della posta indesiderata in uscita.
>
> - È possibile visualizzare le informazioni sugli utenti che inoltrano automaticamente i messaggi ai destinatari esterni nel [rapporto Messaggi inoltrati automaticamente.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Funzionamento delle impostazioni dei criteri di filtro della posta indesiderata in uscita con altri controlli di inoltro automatico della posta elettronica

Come amministratore, potresti aver già configurato altri controlli per consentire o bloccare l'inoltro automatico della posta elettronica. Ad esempio:

- [Domini remoti per](/exchange/mail-flow-best-practices/remote-domains/remote-domains) consentire o bloccare l'inoltro automatico della posta elettronica ad alcuni o a tutti i domini esterni.
- Condizioni e azioni in Exchange del flusso di posta [(note](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) anche come regole di trasporto) per rilevare e bloccare i messaggi inoltrati automaticamente ai destinatari esterni.

Le impostazioni del dominio remoto e le regole del flusso di posta sono indipendenti dalle impostazioni dei criteri di filtro della posta indesiderata in uscita. Ad esempio:

- Si consente l'inoltro automatico per un dominio remoto, ma si blocca l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita. In questo esempio, i messaggi inoltrati automaticamente vengono bloccati.
- Si consente l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita, ma si utilizzano le regole del flusso di posta o le impostazioni del dominio remoto per bloccare la posta elettronica inoltrata automaticamente. In questo esempio, le regole del flusso di posta o le impostazioni del dominio remoto bloccano i messaggi inoltrati automaticamente.

Questa funzionalità consente, ad esempio, di consentire l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita, ma di utilizzare i domini remoti per controllare i domini esterni a cui gli utenti possono inoltrare i messaggi.

## <a name="blocked-email-forwarding-messages"></a>Messaggi di inoltro della posta elettronica bloccati

Quando un messaggio viene rilevato come [](configure-the-outbound-spam-policy.md) inoltrato automaticamente e il criterio di filtro della posta indesiderata in uscita blocca tale attività, il messaggio viene restituito al mittente in un rapporto di mancato recapito contenente le informazioni seguenti: 

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
