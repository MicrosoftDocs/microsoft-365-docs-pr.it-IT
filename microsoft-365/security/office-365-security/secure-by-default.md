---
title: Proteggere per impostazione predefinita in Office 365
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
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288514"
---
# <a name="secure-by-default-in-office-365"></a>Proteggere per impostazione predefinita in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile.

Tuttavia, la sicurezza deve essere bilanciata con la produttività. Ciò può includere il bilanciamento tra:

- **Usabilità:** le impostazioni non devono intasarsi della produttività degli utenti.
- **Rischio:** la sicurezza potrebbe bloccare le attività importanti.
- **Impostazioni legacy:** potrebbe essere necessario mantenere alcune configurazioni per prodotti e funzionalità meno recenti per motivi aziendali, anche se vengono migliorate nuove impostazioni moderne.

Le organizzazioni di Microsoft 365 con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP). Questa protezione include:

- I messaggi di posta elettronica con malware sospetto verranno automaticamente messi in quarantena e i destinatari riceveranno una notifica. Vedere [Configurare i criteri antimalware in EOP.](configure-anti-malware-policies.md)
- La posta elettronica identificata come phishing ad alta probabilità verrà gestita in base all'azione del criterio di protezione da posta indesiderata. Vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP.](configure-your-spam-filter-policies.md)

Per ulteriori informazioni su EOP, vedere [Panoramica di Exchange Online Protection.](exchange-online-protection-overview.md)

Poiché Microsoft vuole proteggere i clienti per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per malware o phishing ad alta probabilità. Queste sostituzioni includono:

- Elenchi di mittenti consentiti o elenchi di domini consentiti (criteri di protezione da posta indesiderata)
- Mittenti attendibili di Outlook
- Elenco indirizzi IP consentiti (filtro connessioni)

Ulteriori informazioni su queste sostituzioni sono disponibili in [Creare elenchi di mittenti attendibili.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> We're in the process of deprecating the **Move message to Junk Email folder** action for a High confidence phishing **email** verdict in EOP anti-spam policies. I criteri di protezione dalla posta indesiderata che utilizzano questa azione per i messaggi di phishing ad alta probabilità verranno convertiti in **messaggi in quarantena.** **L'azione Reindirizza messaggio all'indirizzo di** posta elettronica per i messaggi di phishing ad alta probabilità non è influenzata.

La protezione per impostazione predefinita non è un'impostazione che può essere attivata o disattivata, ma è il modo in cui il filtro funziona per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali. I messaggi di phishing con probabilità elevata e malware devono essere messi in quarantena. Solo gli amministratori possono gestire i messaggi messi in quarantena come malware o phishing ad alta probabilità e possono anche segnalare falsi positivi a Microsoft da qui. Per ulteriori informazioni, vedere Gestire i messaggi e i file in quarantena [come amministratore in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Ulteriori informazioni sul motivo per cui si sta eseguendo questa operazione

Per impostazione predefinita, il livello di sicurezza è la stessa azione che verrebbe eseguita nel messaggio se si conoscesse il messaggio come dannoso, anche quando un'eccezione configurata consentirebbe altrimenti il recapito del messaggio. Questo è lo stesso approccio che abbiamo sempre usato per il malware e ora stiamo estendendo questo stesso comportamento ai messaggi di phishing ad alta probabilità.

I dati indicano che un utente ha 30 volte più probabilità di fare clic su un collegamento dannoso nei messaggi nella cartella Posta indesiderata rispetto alla quarantena. I dati indicano anche che il tasso di falsi positivi (messaggi validi contrassegnati come non validi) per i messaggi di phishing con alta probabilità è molto basso e gli amministratori possono risolvere eventuali falsi positivi con invii di amministratori.

È stato inoltre stabilito che gli elenchi di mittenti ed elenchi di domini consentiti nei criteri di protezione da posta indesiderata e Mittenti attendibili in Outlook erano troppo ampi e causavano più danni che buone.

Per dirla in altro modo: come servizio di sicurezza, microsoft agisce per conto dell'utente per impedire che gli utenti vengano compromessi. 

## <a name="exceptions"></a>Eccezioni

L'unico override che consente ai messaggi di phishing ad alta probabilità di ignorare il filtro sono le regole del flusso di posta di Exchange (note anche come regole di trasporto). Per utilizzare le regole del flusso di posta per ignorare il filtro, vedere Utilizzare le regole del flusso di posta [per impostare il valore SCL nei messaggi.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

È consigliabile utilizzare le sostituzioni solo negli scenari seguenti:

- Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.
- Cassette postali di sicurezza/SecOps: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buona che negativa). Teams può quindi esaminare se contengono contenuti dannosi.
- Filtri di terze parti: la protezione per impostazione predefinita non si applica quando il record MX del dominio non punta a Office 365.
- Falsi positivi: è possibile consentire temporaneamente determinati messaggi ancora in fase di analisi da Microsoft tramite invii [da parte dell'amministratore.](admin-submission.md) Come per tutte le sostituzioni, è consigliabile che siano temporanee.
