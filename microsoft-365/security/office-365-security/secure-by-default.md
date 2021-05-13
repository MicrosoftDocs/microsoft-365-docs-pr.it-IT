---
title: Protezione per impostazione predefinita in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Ulteriori informazioni sull'impostazione di protezione per impostazione predefinita in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 957ca3b563d4f1466dd537c3ae974a4fd61aa6f2
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346317"
---
# <a name="secure-by-default-in-office-365"></a>Protezione per impostazione predefinita in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile.

Tuttavia, la sicurezza deve essere bilanciata con la produttività. Ciò può includere il bilanciamento tra:

- **Usabilità:** Impostazioni non deve essere intasato dalla produttività degli utenti.
- **Rischio:** la sicurezza potrebbe bloccare le attività importanti.
- **Impostazioni legacy:** alcune configurazioni per prodotti e funzionalità meno recenti potrebbero dover essere mantenute per motivi aziendali, anche se vengono migliorate nuove impostazioni moderne.

Microsoft 365 organizzazioni con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP). Questa protezione include:

- I messaggi di posta elettronica con malware sospetto verranno automaticamente messi in quarantena e i destinatari riceveranno una notifica. Vedere [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).
- I messaggi di posta elettronica identificati come phishing ad alta probabilità verranno gestiti in base all'azione dei criteri di protezione da posta indesiderata. Vedere [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

Per ulteriori informazioni su EOP, vedere [Exchange Online Protection panoramica.](exchange-online-protection-overview.md)

Poiché Microsoft vuole proteggere i clienti per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per malware o phishing ad alta sicurezza. Queste sostituzioni includono:

- Elenchi di mittenti consentiti o elenchi di domini consentiti (criteri di protezione da posta indesiderata)
- Outlook Mittenti attendibili
- Elenco indirizzi IP consentiti (filtro connessioni)

Per ulteriori informazioni su queste sostituzioni, vedere [Create safe sender lists.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> È in corso il processo  di deprecazione dell'azione Sposta il messaggio nella cartella Posta indesiderata per un verdetto di posta elettronica di **phishing** ad alta probabilità nei criteri di protezione da posta indesiderata di EOP. I criteri di protezione da posta indesiderata che utilizzano questa azione per i messaggi di phishing ad alta probabilità verranno convertiti in **messaggio di quarantena.** **L'azione Reindirizza messaggio all'indirizzo di** posta elettronica per i messaggi di phishing ad alta probabilità non è influenzata.

La protezione per impostazione predefinita non è un'impostazione che può essere attivata o disattivata, ma è il modo in cui il filtro funziona per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali. Il malware e i messaggi di phishing ad alta probabilità devono essere messi in quarantena. Solo gli amministratori possono gestire i messaggi messi in quarantena come malware o phishing ad alta probabilità e possono anche segnalare falsi positivi a Microsoft da lì. Per ulteriori informazioni, vedere [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Ulteriori informazioni sul motivo per cui si sta eseguendo questa operazione

Lo spirito di protezione per impostazione predefinita è: stiamo prendendo la stessa azione sul messaggio che si farebbe se si conoscesse il messaggio dannoso, anche quando un'eccezione configurata consentirebbe altrimenti il recapito del messaggio. Questo è lo stesso approccio che abbiamo sempre usato per il malware e ora stiamo estendendo questo stesso comportamento ai messaggi di phishing ad alta confidenza.

I nostri dati indicano che un utente ha 30 volte più probabilità di fare clic su un collegamento dannoso nei messaggi nella cartella Posta indesiderata rispetto alla quarantena. I nostri dati indicano anche che il tasso di falsi positivi (messaggi positivi contrassegnati come non validi) per i messaggi di phishing ad alta probabilità è molto basso e gli amministratori possono risolvere eventuali falsi positivi con invii di amministratori.

È stato inoltre determinato che il mittente consentito e gli elenchi di domini consentiti nei criteri di protezione da posta indesiderata e Mittenti attendibili in Outlook erano troppo ampi e causavano più danni che buoni.

Per dirla in un altro modo: come servizio di sicurezza, microsoft agisce per conto dell'utente per evitare che gli utenti vengano compromessi.

## <a name="exceptions"></a>Eccezioni

> [!NOTE]
> A luglio 2021, la protezione per impostazione predefinita verrà estesa Exchange regole del flusso di posta (note anche come regole di trasporto). Se si utilizzano regole del flusso di posta per consentire simulazioni di phishing di terze parti o il [](configure-advanced-delivery.md) recapito non filtrato alle cassette postali delle operazioni di sicurezza, è infine necessario eliminare queste regole e passare all'utilizzo dei criteri di recapito avanzati quando la funzionalità è _disponibile._

L'unico override che consente ai messaggi di phishing ad alta probabilità di ignorare il filtro sono le regole del flusso di posta. Per utilizzare le regole del flusso di posta per ignorare il filtro, vedere [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

È consigliabile utilizzare le sostituzioni solo negli scenari seguenti:

- Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.
- Cassette postali Di sicurezza/SecOps: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buoni che non filtrati). Teams possono quindi esaminare per verificare se contengono contenuti dannosi.
- Filtri di terze parti: la protezione per impostazione predefinita non si applica quando il record MX del dominio non punta a Office 365.
- Falsi positivi: è possibile consentire temporaneamente determinati messaggi ancora in fase di analisi da Microsoft [tramite invii di amministratori.](admin-submission.md) Come per tutte le sostituzioni, è consigliabile che siano temporanee.
