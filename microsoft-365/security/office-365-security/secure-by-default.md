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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Per ulteriori informazioni sull'impostazione sicura per impostazione predefinita in Exchange Online Protection (EOP)
ms.openlocfilehash: 54000d351463ba90751f1f27638fb52847cf05ce
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558515"
---
# <a name="secure-by-default-in-office-365"></a>Protezione per impostazione predefinita in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile.

Tuttavia, la sicurezza deve essere bilanciata con la produttività. Ciò può includere il bilanciamento tra:

- Usabilità: le impostazioni non devono essere **inutilizzate** per la produttività degli utenti.
- **Rischio**: la sicurezza potrebbe bloccare attività importanti.
- **Impostazioni legacy**: potrebbe essere necessario mantenere le configurazioni per i prodotti e le funzionalità meno recenti, anche se sono state migliorate nuove impostazioni moderne.

Microsoft 365 le organizzazioni con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP). Questa protezione include:

- La posta elettronica con sospetto di malware verrà automaticamente messa in quarantena e i destinatari verranno informati. Vedere [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).
- La posta elettronica identificata come phishing con elevata sicurezza verrà gestita in base all'azione relativa ai criteri di protezione da posta indesiderata. Vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Poiché Microsoft desidera mantenere i clienti sicuri per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per il phishing con malware o con elevato livello di sicurezza. Tali sostituzioni includono:

- Elenchi mittenti consentiti o elenchi di domini consentiti (criteri di protezione dalla posta indesiderata
- Mittenti attendibili di Outlook
- Elenco indirizzi IP consentiti (filtro connessioni)

Per ulteriori informazioni su tali sostituzioni, vedere [creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md).

Secure per impostazione predefinita non è un'impostazione che può essere attivata o disattivata, ma è il modo in cui il filtro funziona fuori dalla casella per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali. I messaggi di phishing con elevata sicurezza e malware devono essere messi in quarantena. Solo gli amministratori possono gestire i messaggi che vengono messi in quarantena come malware o phishing con elevato livello di sicurezza e possono anche segnalare falsi positivi a Microsoft da qui. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Altre informazioni sul motivo per cui si sta eseguendo questa operazione

Lo spirito di sicurezza per impostazione predefinita è: è possibile eseguire la stessa operazione sul messaggio che si desidera utilizzare se si conosce il messaggio dannoso, anche se si è verificato un Consenti sul posto. Questo è lo stesso approccio utilizzato per il malware e ora si sta estendendo lo stesso comportamento ai messaggi di phishing con elevata sicurezza. I dati indicano che il tasso di falsi positivi per i messaggi di phishing con elevata sicurezza è molto basso e gli amministratori possono risolvere eventuali falsi positivi con invii di amministratore. I dati indicano inoltre che gli elenchi di mittenti consentiti e gli elenchi di domini consentiti nei criteri di protezione da posta indesiderata e nei mittenti attendibili in Outlook erano troppo vasti e causavano più danni che buoni.

Per inserirlo in un altro modo: come servizio di sicurezza, stiamo agendo per conto dell'utente per evitare che gli utenti vengano compromessi. Inoltre, Secure per impostazione predefinita non è un rilevamento completo delle opzioni disponibili per i messaggi di phishing con sicurezza elevata nei criteri di protezione da posta indesiderata. Anche se si consiglia la quarantena, le altre azioni che sono sempre disponibili sono ancora disponibili (passare alla cartella posta indesiderata o reindirizzare a un indirizzo di posta elettronica).

## <a name="exceptions"></a>Eccezioni

L'unica sostituzione che consente ai messaggi di phishing con elevata sicurezza di ignorare il filtro è la regola del flusso di posta di Exchange (nota anche come regole di trasporto). Per utilizzare le regole del flusso di posta per ignorare il filtro, vedere [Use Mail Flow Rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

È consigliabile utilizzare solo le sostituzioni negli scenari seguenti:

- Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influenzi l'organizzazione.
- Cassette postali di sicurezza/secops: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buoni che cattivi). I team possono quindi verificare se contengono contenuto dannoso.
- Filtri di terze parti: alcuni fornitori di terze parti consigliano di disattivare EOP (SCL =-1) come filtro di terze parti per gestire il filtro della posta. Microsoft non consiglia di disattivare EOP poiché EOP è obbligatorio per Defender per Office 365. In questo caso, è consigliabile abilitare il [filtro avanzato per i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
- Falsi positivi: è possibile che si desideri consentire temporaneamente alcuni messaggi che vengono ancora analizzati da Microsoft [tramite invii di amministratore](admin-submission.md). Come per tutte le sostituzioni, è consigliabile che siano temporanei.
