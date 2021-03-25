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
description: Gli amministratori possono ottenere informazioni sui controlli della posta indesiderata in uscita in Exchange Online Protection (EOP) e su cosa fare se è necessario inviare mailing di massa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e84cd636abee42a03ff8590091542c96714f2d8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205454"
---
# <a name="outbound-spam-protection-in-eop"></a>Protezione da posta indesiderata in uscita in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, la gestione della posta indesiderata in uscita è molto importante. Un cliente che invia intenzionalmente o involontariamente posta indesiderata dall'organizzazione può compromettere la reputazione dell'intero servizio e influire sul recapito della posta elettronica per altri clienti.

In questo argomento vengono descritti i controlli e le notifiche progettati per impedire la posta indesiderata in uscita e le attività che è possibile eseguire se è necessario inviare messaggi di posta elettronica di massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Cosa possono fare gli amministratori per controllare la posta indesiderata in uscita

- Utilizzare le notifiche predefinite: quando un utente [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) supera [](configure-the-outbound-spam-policy.md) i limiti di invio del servizio o dei criteri di posta indesiderata in uscita e non può inviare messaggi di posta elettronica, il criterio di avviso predefinito denominato **Utente** con restrizioni per l'invio di messaggi di posta elettronica invia notifiche di posta elettronica ai membri del gruppo **TenantAdmins** ( **Amministratori** globali). Per configurare gli altri utenti che ricevono queste notifiche, vedere [Verificare le impostazioni degli avvisi per gli utenti con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Inoltre, i criteri  di avviso predefiniti  denominati Limite invio posta elettronica superato e Modelli di invio di posta elettronica sospetti rilevati inviano notifiche di posta elettronica ai membri del gruppo **TenantAdmins** (**Amministratori** globali). Per ulteriori informazioni sui criteri di avviso, vedere [Criteri di avviso nel Centro sicurezza e conformità](../../compliance/alert-policies.md).

- Esaminare i reclami di posta indesiderata provenienti da provider di posta elettronica di terze **parti:** molti servizi di posta elettronica come Outlook.com, Yahoo e AOL forniscono un ciclo di feedback in cui se un utente nel proprio servizio contrassegna un messaggio di posta elettronica da Microsoft 365 come posta indesiderata, il messaggio viene in pacchetto e inviato a Microsoft per la revisione. Per ulteriori informazioni sul supporto dei mittenti Outlook.com, passare a <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Come EOP controlla la posta indesiderata in uscita

- **Separazione del traffico di posta elettronica in uscita**: ogni messaggio in uscita inviato tramite il servizio viene analizzato alla ricerca di posta indesiderata. Se il messaggio viene determinato come posta indesiderata, viene recapitato da un pool di indirizzi IP secondario meno affidabile denominato pool di recapito _ad alto rischio._ Per altre informazioni, vedere [Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitoraggio della reputazione dell'indirizzo IP di origine:** Microsoft 365 esegue query su vari elenchi di indirizzi IP di terze parti. Se uno degli indirizzi IP utilizzati per la posta elettronica in uscita viene visualizzato in questi elenchi, viene generato un avviso. Questo ci consente di reagire rapidamente quando la posta indesiderata ha causato la degradazione della reputazione. Quando viene generato un avviso, è disponibile una documentazione interna che descrive come rimuovere (eliminare) gli indirizzi IP dagli elenchi di blocco.

- **Disabilitare** gli account che inviano troppa posta indesiderata: anche se la posta indesiderata in uscita viene segregata nel pool di recapito ad alto rischio, non è possibile consentire a un account (spesso un account compromesso) di inviare posta indesiderata a tempo <sup>\*</sup> indeterminato. Monitoriamo gli account che inviano posta indesiderata e quando superano un limite non chiuso, all'account viene impedito di inviare posta elettronica. Esistono soglie diverse per i singoli utenti e per l'intero tenant.

- **Disabilitazione** degli account che inviano troppi messaggi di posta elettronica troppo rapidamente: oltre ai limiti che ricercano i messaggi contrassegnati come posta indesiderata, esistono anche limiti che bloccano gli account quando raggiungono un limite complessivo per i messaggi in uscita, indipendentemente dal verdetto del filtro posta indesiderata sui messaggi in <sup>\*</sup> uscita. Un account compromesso potrebbe inviare posta indesiderata zero-day (in precedenza non riconosciuta) che non viene riconosciuta dal filtro di protezione da posta indesiderata. Poiché può essere difficile identificare una campagna di mailing di massa legittima rispetto a una campagna di posta indesiderata, questi limiti consentono di ridurre al minimo eventuali danni potenziali.

<sup>\*</sup> Non annunciamo i limiti esatti in modo che gli spammer non possano giocare al sistema e quindi possiamo aumentare o ridurre i limiti in base alle esigenze. I limiti sono sufficientemente alti da impedire a un utente aziendale medio di superarli e sufficientemente bassi da contenere i danni causati da uno spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Suggerimenti per i clienti che desiderano inviare mailing di massa tramite EOP

È difficile trovare un equilibrio tra i clienti che desiderano inviare un grande volume di posta elettronica rispetto alla protezione del servizio da account compromessi e mittenti di posta elettronica in blocco con procedure di acquisizione dei destinatari scadenti. Il costo di un'origine di posta elettronica di Microsoft 365 che atterra su un elenco di indirizzi IP di terze parti è superiore al blocco di un utente che invia troppo posta elettronica.

Come descritto nella descrizione del servizio [Exchange Online,](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)l'utilizzo di EOP per inviare messaggi di posta elettronica in blocco non è un utilizzo supportato del servizio ed è consentito solo su base ottimale. Per i clienti che desiderano inviare messaggi di posta elettronica in blocco, è consigliabile utilizzare le soluzioni seguenti:

- **Inviare messaggi di posta** elettronica in blocco tramite server di posta elettronica locali: ciò significa che i clienti dovranno gestire la propria infrastruttura di posta elettronica per gli invii di massa.

- **Utilizzare un provider di posta elettronica in** blocco di terze parti: sono disponibili diversi provider di soluzioni di posta elettronica in blocco di terze parti che è possibile utilizzare per inviare mailing di massa. Queste società hanno un interesse a lavorare con i clienti per garantire buone pratiche di invio della posta elettronica.

Il Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) pubblica il proprio elenco di membri all'indirizzo <https://www.maawg.org/about/roster> . Diversi provider di posta elettronica in blocco sono presenti nell'elenco e sono noti per essere responsabili di internet citizens.