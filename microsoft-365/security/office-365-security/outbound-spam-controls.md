---
title: Protezione dalla posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere i controlli della posta indesiderata in uscita in Exchange Online Protection (EOP) e cosa fare se è necessario inviare messaggi di posta elettronica di massa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f9d434c858f7c66f82dd4f551bac99458b9e5c8c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287630"
---
# <a name="outbound-spam-protection-in-eop"></a>Protezione da posta indesiderata in uscita in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, la gestione della posta indesiderata in uscita è molto importante. Un cliente che invia intenzionalmente o involontariamente posta indesiderata dall'organizzazione può ridurre la reputazione dell'intero servizio e può influire sul recapito della posta elettronica per altri clienti.

In questo argomento vengono descritti i controlli e le notifiche progettati per impedire la posta indesiderata in uscita e le attività che è possibile eseguire se è necessario inviare messaggi di posta elettronica di massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Cosa possono fare gli amministratori per controllare la posta indesiderata in uscita

- Utilizzare le notifiche predefinite: quando un utente [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) supera [](configure-the-outbound-spam-policy.md) i limiti di invio del servizio o dei criteri di posta indesiderata in uscita e non può inviare messaggi di posta elettronica, il criterio di avviso predefinito denominato **Utente** a cui è stato limitato l'invio di messaggi di posta elettronica invia notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** ( **Amministratori** globali). Per configurare gli altri utenti che ricevono queste notifiche, vedere [Verificare le impostazioni degli avvisi per gli utenti con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Inoltre, i criteri  di avviso predefiniti  denominati Limite invio posta elettronica superato e modelli di invio di posta elettronica sospetti rilevati inviano notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Amministratori** globali). Per ulteriori informazioni sui criteri di avviso, vedere [Criteri di avviso nel Centro sicurezza e conformità](../../compliance/alert-policies.md).

- Esaminare i reclami di posta indesiderata provenienti da provider di posta elettronica di terze **parti:** molti servizi di posta elettronica come Outlook.com, Yahoo e AOL forniscono un ciclo di feedback in cui se un utente nel servizio contrassegna un messaggio di posta elettronica da Microsoft 365 come posta indesiderata, il messaggio viene inviato a Microsoft per la revisione. Per ulteriori informazioni sul supporto del mittente Outlook.com, passare a <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Come EOP controlla la posta indesiderata in uscita

- **Separazione del traffico di posta elettronica in uscita:** ogni messaggio in uscita inviato tramite il servizio viene analizzato alla ricerca di posta indesiderata. Se il messaggio viene determinato come posta indesiderata, viene recapitato da un pool di indirizzi IP secondario meno affidabile denominato pool di recapito ad _alto rischio._ Per altre informazioni, vedere [Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitoraggio della reputazione degli indirizzi IP di origine:** Microsoft 365 esegue query su vari elenchi di indirizzi IP di terze parti. Se uno degli indirizzi IP utilizzati per la posta elettronica in uscita viene visualizzato in questi elenchi, viene generato un avviso. Ciò ci consente di reagire rapidamente quando la posta indesiderata ha causato la degradazione della reputazione. Quando viene generato un avviso, è disponibile una documentazione interna che descrive come rimuovere (eliminare) gli indirizzi IP dagli elenchi di indirizzi bloccati.

- **Disabilitare** gli account che inviano troppi messaggi di posta indesiderata: anche se la posta indesiderata in uscita viene isolata nel pool di recapito ad alto rischio, non è possibile consentire a un account (spesso un account compromesso) di inviare posta indesiderata a tempo <sup>\*</sup> indeterminato. Monitoriamo gli account che inviano posta indesiderata e, quando superano un limite non divulato, all'account viene impedito di inviare messaggi di posta elettronica. Esistono soglie diverse per i singoli utenti e per l'intero tenant.

- Disabilitazione degli account che inviano troppi messaggi di posta elettronica troppo rapidamente: oltre ai limiti che ricercano i messaggi contrassegnati come posta indesiderata, esistono anche dei limiti che bloccano gli account quando raggiungono un limite globale per i messaggi in uscita, indipendentemente dal verdetto del filtro posta indesiderata sui messaggi in <sup>\*</sup> uscita. Un account compromesso potrebbe inviare posta indesiderata zero-day (in precedenza non riconosciuta) che non viene riconosciuta dal filtro di protezione da posta indesiderata. Poiché può essere difficile identificare una campagna di invio di massa legittima rispetto a una campagna di posta indesiderata, questi limiti consentono di ridurre al minimo i potenziali danni.

<sup>\*</sup> Non vengono annunciati i limiti esatti in modo che gli spammer non possano giocare con il sistema e quindi possiamo aumentarne o ridurli in base alle esigenze. I limiti sono sufficientemente elevati da impedire a un utente aziendale medio di superarli e sufficientemente bassi da contenere i danni causati da uno spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Consigli per i clienti che desiderano inviare mailing di massa tramite EOP

È difficile trovare un equilibrio tra i clienti che desiderano inviare un gran numero di messaggi di posta elettronica e proteggere il servizio da account compromessi e mittenti di posta elettronica in blocco con procedure di acquisizione dei destinatari scadenti. Il costo di un'origine di posta elettronica di Microsoft 365 che si trova in un elenco di indirizzi IP bloccati di terze parti è maggiore rispetto al blocco di un utente che invia troppi messaggi di posta elettronica.

Come descritto nella descrizione del servizio [Exchange Online,](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)l'utilizzo di EOP per inviare posta elettronica in blocco non è un utilizzo supportato del servizio ed è consentito solo su base "ottimale". Per i clienti che desiderano inviare posta elettronica in blocco, si consigliano le soluzioni seguenti:

- **Inviare posta elettronica in** blocco tramite server di posta elettronica locali: ciò significa che i clienti dovranno mantenere la propria infrastruttura di posta elettronica per l'invio di massa.

- **Utilizzare un provider di posta** elettronica in blocco di terze parti: sono disponibili diversi provider di soluzioni di posta elettronica in blocco di terze parti che è possibile utilizzare per inviare messaggi di posta elettronica di massa. Queste società hanno un interesse a lavorare con i clienti per garantire buone procedure di invio della posta elettronica.

Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) pubblica la propria lista di appartenenza all'indirizzo <https://www.maawg.org/about/roster> . Nell'elenco sono presenti diversi provider di posta elettronica in blocco, noti come internet cittadini responsabili.
