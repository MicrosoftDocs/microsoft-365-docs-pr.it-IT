---
title: Configurazione e controllo dell'inoltro della posta elettronica esterno, inoltro automatico, accesso negato per 5.7.520, disabilitazione dell'inoltro esterno, l'amministratore ha disabilitato l'inoltro esterno, i criteri di protezione dalla posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: dff2ea4e144f8f8fcc0f42732141e110effe7e9e
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774094"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controllare l'inoltro automatico di messaggi di posta elettronica esterni in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Come amministratore, è possibile che i requisiti della società possano limitare o controllare i messaggi inoltrati automaticamente a destinatari esterni (destinatari all'esterno dell'organizzazione). L'inoltro della posta elettronica può essere utile, ma può anche rappresentare un rischio per la sicurezza a causa della possibile divulgazione delle informazioni. Gli utenti malintenzionati possono utilizzare queste informazioni per attaccare l'organizzazione o i partner.

In Microsoft 365 sono disponibili i seguenti tipi di inoltro automatico:

- Gli utenti possono configurare [le regole di posta in arrivo](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) per inoltrare automaticamente i messaggi ai mittenti esterni (deliberatamente o come risultato di un account compromesso).

- Gli amministratori possono configurare l' [inoltro delle cassette postali](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (noto anche come inoltro SMTP) per inoltrare automaticamente i messaggi ai destinatari esterni.

È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni. Sono disponibili tre impostazioni:

- **Automatico** : l'inoltro automatico esterno è bloccato. L'inoltro automatico interno dei messaggi continuerà a funzionare. Questa è l'impostazione predefinita.

- **On** : l'inoltro automatico esterno è consentito e non è limitato.

- **Disattivata** : l'inoltro automatico esterno è disabilitato e si verificherà un rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo) al mittente.

Per istruzioni su come configurare queste impostazioni, vedere [configurare il filtro della posta indesiderata in uscita in EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
> 
> - La disabilitazione dell'inoltro automatico disattiverà anche le regole di posta in arrivo che reindirizzano i messaggi agli indirizzi esterni.
> 
>   Office 365 non consente l'inoltro automatico esterno tramite le regole di posta in arrivo o la configurazione della cassetta postale, che fornisce un criterio predefinito sicuro. Tuttavia, l'amministratore può modificare queste impostazioni per tutti gli utenti dell'organizzazione. Creare [criteri di posta indesiderata in uscita](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) e modificare la sezione di inoltro automatico per controllare l'inoltro automatico della posta elettronica da parte degli utenti a mittenti esterni. Questo può essere applicato in un secondo momento ai mittenti interni ai quali si applica il criterio. L'inoltro dei messaggi tra utenti interni non è influenzato da tale modifica.
> 
> - È possibile visualizzare informazioni sugli utenti che inoltrano automaticamente i messaggi a destinatari esterni nel [rapporto messaggi auto-inoltrati](mfi-auto-forwarded-messages-report.md).

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Funzionamento delle impostazioni dei criteri di filtro della posta indesiderata in uscita con altri controlli di inoltro della posta elettronica automatici

Come amministratore, è possibile che siano già stati configurati altri controlli per consentire o bloccare l'inoltro automatico della posta elettronica. Ad esempio:

- [Domini remoti](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) per consentire o bloccare l'inoltro automatico dei messaggi di posta elettronica ad alcuni o a tutti i domini esterni.

- Condizioni e azioni nelle [regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) per rilevare e bloccare automaticamente i messaggi inoltrati ai destinatari esterni.

Le impostazioni del dominio remoto e le regole del flusso di posta sono indipendenti dalle impostazioni nei criteri di filtro della posta indesiderata in uscita. Ad esempio:

- È possibile consentire l'inoltro automatico per un dominio remoto, ma si blocca l'inoltro automatico nei criteri di filtro per la posta indesiderata in uscita. In questo esempio, i messaggi inoltrati automaticamente vengono bloccati.

- È possibile consentire l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita, ma si utilizzano le regole del flusso di posta o le impostazioni del dominio remoto per bloccare la posta elettronica inoltrata automaticamente In questo esempio, le regole del flusso di posta o le impostazioni del dominio remoto bloccano automaticamente i messaggi inoltrati.

Questa funzionalità di indipendenza consente di (ad esempio) consentire l'inoltro automatico nei criteri di filtro per la posta indesiderata in uscita, ma usare domini remoti per controllare i domini esterni a cui gli utenti possono inoltrare i messaggi.

## <a name="the-blocked-email-forwarding-message"></a>Il messaggio di inoltro della posta elettronica bloccato

Quando un messaggio viene rilevato come inoltrato automaticamente e il criterio dell'organizzazione *blocca* tale attività, il messaggio viene restituito al mittente in un rapporto di mancato recapito che contiene le informazioni seguenti:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
