---
title: Configurazione e controllo dell'inoltro della posta elettronica esterno, inoltro automatico, accesso negato per 5.7.520, disabilitazione dell'inoltro esterno, l'amministratore ha disabilitato l'inoltro esterno, i criteri di protezione dalla posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080114"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Configurazione dell'inoltro della posta elettronica esterno in Office 365

L'inoltro esterno è controllato dal *criterio di protezione dalla posta indesiderata in uscita* e dall'ambito agli utenti in base all'impostazione configurata. Attualmente sono supportate tre impostazioni:

- **Automatico** – in questa modalità, il sistema è responsabile di decidere se un messaggio inoltrato è consentito o meno.  Questa è la modalità predefinita e in questa modalità il sistema bloccherà l'inoltro esterno automatico.

- **On** – l'inoltro automatico esterno è consentito e non è limitato.

- **Off** – l'inoltro automatico esterno è disabilitato e si verificherà un rapporto di mancato recapito (NDR) all'utente finale.

Per ulteriori informazioni su come configurare queste impostazioni, vedere Configurare il filtro per la [posta indesiderata in uscita in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) .

## <a name="controlling-external-email-forwarding"></a>Controllo dell'inoltro della posta elettronica esterno

L'amministratore di un'organizzazione può avere i requisiti aziendali per limitare o controllare chi è in grado di inoltrare automaticamente i messaggi di posta elettronica utilizzando le regole Inbox o l'inoltro SMTP all'esterno dell'organizzazione. L'inoltro della posta elettronica può essere una funzionalità utile, ma può anche rappresentare un rischio tramite la divulgazione di informazioni, anche fornendo informazioni agli aggressori che possono essere utilizzati per attaccare l'organizzazione o i suoi partner.

Office 365 non consente l'inoltro automatico esterno tramite le regole di posta in arrivo o la configurazione della casella di posta, che fornisce un criterio predefinito sicuro. Tuttavia, l'amministratore può modificare queste impostazioni per tutti gli utenti dell'organizzazione. L'inoltro dei messaggi tra utenti interni non è influenzato da tale modifica.

> [!NOTE]
> La disattivazione dell'inoltro automatico agli indirizzi esterni in Office 365 viene distribuita in fasi con i dettagli comunicati tramite i post del [centro messaggi](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) . Per aiutare gli amministratori a prepararsi per queste modifiche, è necessario che modifichino i criteri in anticipo per garantire che non vi siano interruzioni per gli utenti.

Ulteriori informazioni sugli utenti che utilizzano l'inoltro automatico (regole di posta in arrivo o inoltro SMTP) nell'organizzazione possono essere trovate nel [rapporto messaggi auto-inoltrati](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).

## <a name="the-blocked-email-forwarding-message"></a>Il messaggio di inoltro della posta elettronica bloccato

Quando un messaggio viene rilevato come inoltrato automaticamente e il criterio dell'organizzazione *blocca* tale attività, verrà generato un **rapporto di mancato recapito (NDR, non-delivery report)** all'utente finale. Il rapporto indicherà che il messaggio non è stato recapitato. Il rapporto di mancato recapito avrà il formato seguente: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`