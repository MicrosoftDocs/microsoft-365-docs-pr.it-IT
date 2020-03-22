---
title: Protezione dalla posta indesiderata in uscita in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Gli amministratori possono sapere come Office 365 e Exchange Online Protection (EOP) proteggono i clienti dalla posta indesiderata in uscita e cosa fare se è necessario inviare messaggi di posta elettronica di massa.
ms.openlocfilehash: 99e764944335be923ee1918851d4072ea98d3a32
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895324"
---
# <a name="outbound-spam-protection-in-office-365"></a>Protezione dalla posta indesiderata in uscita in Office 365

Si prende sul serio la gestione della posta indesiderata in uscita, perché Office 365 (Exchange Online o standalone Exchange Online Protection (EOP) senza cassette postali di Exchange Online) è un servizio online in cui molti clienti utilizzano un pool di risorse condiviso. Un utente di Office 365 che invia intenzionalmente o involontariamente posta indesiderata dalla propria organizzazione può peggiorare la reputazione di tutto il servizio e può influire sul recapito della posta elettronica per gli altri clienti.

In questo argomento vengono descritti i controlli e le notifiche che sono stati creati per impedire la posta indesiderata in uscita e cosa è possibile fare se è necessario inviare messaggi di posta elettronica di massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Operazioni che possono essere eseguite dagli amministratori per controllare la posta indesiderata in uscita

- **Utilizzo delle notifiche**predefinite: quando un utente supera i limiti di invio del [servizio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o dei criteri di [posta indesiderata in uscita](configure-the-outbound-spam-policy.md) ed è limitato dall'invio di messaggi di posta elettronica, il criterio di avviso predefinito denominato utente con **limitazioni dall'invio di posta** elettronica Invia notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**). Per configurare l'utente che riceve queste notifiche, vedere [Verify the Alert Settings for Restricted Users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Inoltre, i criteri di avviso predefiniti denominati **limite di invio del messaggio di posta elettronica superato** e i modelli di invio di posta elettronica **sospetti rilevato** inviano notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**). Per ulteriori informazioni sui criteri di avviso, vedere [criteri di avviso nel centro sicurezza e conformità](../../compliance/alert-policies.md).

- **Esaminare i problemi di posta indesiderata dai provider di posta elettronica di terze parti**: molti servizi di posta elettronica come Outlook.com, Yahoo e AOL forniscono un ciclo di commenti e suggerimenti in cui se un utente del servizio contrassegna una posta elettronica da Office 365 come posta indesiderata, il messaggio viene inserito e inviato a noi per la revisione. Per ulteriori informazioni sul supporto dei mittenti per Outlook.com, accedere <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>a.

## <a name="how-eop-controls-outbound-spam"></a>Come EOP controlla la posta indesiderata in uscita

- **Segregazione del traffico di posta elettronica in uscita**: tutti i messaggi in uscita inviati tramite il servizio vengono analizzati per la posta indesiderata. Se il messaggio è determinato come posta indesiderata, viene recapitato da un pool di indirizzi IP secondario e meno attendibile denominato _pool di recapito ad alto rischio_. Per ulteriori informazioni, vedere [pool di recapito ad alto rischio per i messaggi in uscita in Office 365](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitoraggio della reputazione dell'indirizzo IP di origine**: Office 365 esegue una query su diversi elenchi di indirizzi IP bloccati di terze parti. Viene generato un avviso se uno degli indirizzi IP utilizzati per la posta elettronica in uscita viene visualizzato negli elenchi. In questo modo è possibile reagire rapidamente quando la posta indesiderata ha provocato un peggioramento della reputazione. Quando viene generato un avviso, è presente una documentazione interna che descrive come ottenere gli indirizzi IP rimossi dagli elenchi bloccati.

- **Disabilitare gli account che inviano troppa posta indesiderata**<sup>\*</sup>: anche se noi segregiamo la posta indesiderata in uscita nel pool di recapito ad alto rischio, non è possibile consentire a un account (spesso un account compromesso) di inviare messaggi di posta indesiderati. Monitoriamo gli account che inviano messaggi di posta indesiderata e quando superano un limite nascosto, l'account è bloccato dall'invio di posta elettronica. Sono disponibili diverse soglie per singoli utenti e per l'intero tenant.

- **Disabilitare gli account che inviano troppa posta elettronica troppo rapidamente**<sup>\*</sup>: oltre ai limiti che cercano i messaggi contrassegnati come posta indesiderata, esistono anche limiti che bloccano gli account quando raggiungono un limite globale dei messaggi in uscita, indipendentemente dal verdetto del filtro della posta indesiderata nei messaggi in uscita. Un account compromesso potrebbe inviare lo spam zero-day (in precedenza non riconosciuto) mancante dal filtro di posta indesiderata. Poiché può essere difficile identificare una campagna di mailing di massa legittima rispetto a una campagna di posta indesiderata, questi limiti contribuiscono a minimizzare eventuali danni.

<sup>\*</sup>I limiti esatti non vengono pubblicizzati in modo che gli spammer non possano giocare il sistema e quindi è possibile aumentare o diminuire i limiti in base alle esigenze. I limiti sono abbastanza alti da impedire che un utente medio dell'azienda venga mai superato e che sia sufficientemente basso da contenere i danni causati da uno spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Consigli per i clienti che desiderano inviare invii di massa tramite EOP

È difficile trovare un equilibrio tra i clienti che desiderano inviare un volume elevato di posta elettronica rispetto alla protezione del servizio da account compromessi e mittenti di posta elettronica in blocco con procedure di acquisizione dei destinatari insufficienti. Il costo di un atterraggio di origine di posta elettronica di Office 365 su un elenco di indirizzi IP bloccati di terze parti è maggiore del blocco di un utente che invia troppa posta elettronica.

Come descritto nella [Descrizione del servizio Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), l'utilizzo di EOP per inviare messaggi di posta elettronica in blocco non è un utilizzo supportato del servizio e può essere consentito solo in base a "Best-Effort". Per i clienti che desiderano inviare messaggi di posta elettronica in blocco, è consigliabile utilizzare le soluzioni seguenti:

- **Inviare messaggi di posta elettronica in blocco tramite i server di posta elettronica locali**: ciò significa che i clienti dovranno mantenere la propria infrastruttura di posta elettronica per i messaggi di massa.

- **Utilizzo di un provider di posta elettronica in blocco di terze parti**: sono disponibili diversi provider di soluzioni di posta elettronica di terze parti che è possibile utilizzare per inviare invii di massa. Tali società hanno un interesse acquisito nell'utilizzo dei clienti per garantire buone prassi di invio della posta elettronica.

Il gruppo di lavoro per la messaggistica, la telefonia mobile e anti-abuso di malware (MAAWG <https://www.maawg.org/about/roster>) pubblica il proprio roster di appartenenza. Numerosi provider di posta elettronica in blocco sono presenti nell'elenco e sono noti come cittadini Internet responsabili.
