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
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione. I report sulla sicurezza della posta elettronica sono disponibili nel centro sicurezza & conformità.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944480"
---
# <a name="secure-by-default-in-office-365"></a>Protezione per impostazione predefinita in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile. 

Tuttavia, la sicurezza deve essere bilanciata con la produttività. Ciò può includere il bilanciamento tra:
- Usabilità: le impostazioni non devono essere inutilizzate per la produttività degli utenti.
- Rischio: la sicurezza potrebbe bloccare attività importanti.
- Impostazioni legacy: potrebbe essere necessario mantenere le configurazioni per i prodotti e le funzionalità meno recenti, anche se sono state migliorate nuove impostazioni moderne. 

Microsoft 365 le organizzazioni con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP). Questa protezione include:
1. La posta elettronica con sospetto di malware verrà automaticamente messa in quarantena e i destinatari verranno informati. Vedere [Configure anti-malware Policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).
1. La posta elettronica di phishing identificata come "elevata sicurezza" verrà gestita in base all'azione relativa ai criteri di protezione da posta indesiderata. Vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).

Poiché Microsoft desidera mantenere i clienti sicuri per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per phishing di malware o high confidence. Tali sostituzioni includono:
- Elenchi mittenti consentiti o elenchi di domini consentiti (criteri di protezione dalla posta indesiderata
- Mittenti attendibili di Outlook
- Elenco indirizzi IP consentiti (filtro connessioni)

Per ulteriori informazioni su tali sostituzioni, vedere [creare elenchi di mittenti attendibili](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

Sicuro per impostazione predefinita qui non è un'impostazione che potrebbe essere attivata o disattivata, ma il modo in cui il filtro funziona fuori dalla casella per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali. I malware e phishing ad alta sicurezza devono essere inviati alla quarantena. Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware o phishing con elevato livello di sicurezza e possono anche segnalare falsi positivi a Microsoft da qui. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Eccezioni
Le uniche sostituzioni che ignoreranno tutti i filtri sono le seguenti:
- Regole di trasporto di Exchange (ETR)/mail.  Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi in EOP.
- Elenco Consenti/blocca tenant: gestire gli URL e i file nell'elenco Consenti/blocca tenant.


Questi tipi di sostituzioni sono utili per:
- Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale impatti la propria organizzazione.
- Cassette postali di sicurezza/secops: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buoni che cattivi). I team possono quindi verificare se contengono contenuto dannoso.
- Filtri di terze parti: alcuni fornitori di terze parti consigliano di disattivare EOP (SCL =-1) come filtro di terze parti per gestire il filtro della posta.  Microsoft non consiglia di disattivare EOP poiché EOP è obbligatorio per Defender per Office 365. 
- Falsi positivi: è possibile che si desideri consentire a alcuni messaggi che vengono ancora analizzati da Microsoft [tramite invii di amministratore](admin-submission.md). Come per tutte le sostituzioni, è consigliabile che siano temporanei.
