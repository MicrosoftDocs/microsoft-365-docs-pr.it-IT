---
title: Pool di recapito in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Informazioni su come vengono usati i pool di recapito per proteggere la reputazione dei server di posta elettronica nei datacenter di Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289806"
---
# <a name="outbound-delivery-pools"></a>Pool di recapito in uscita

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I server di posta elettronica nei datacenter di Microsoft 365 potrebbero essere temporaneamente responsabili dell'invio di posta indesiderata. Ad esempio, un attacco di malware o di posta indesiderata dannoso in un'organizzazione di posta elettronica locale che invia la posta in uscita tramite Microsoft 365 o ha compromesso gli account di Microsoft 365. Gli utenti malintenzionati tentano anche di evitare il rilevamento inoltrando i messaggi tramite l'inoltro di Microsoft 365.

Questi scenari possono comportare la visualizzazione dell'indirizzo IP dei server datacenter di Microsoft 365 interessati negli elenchi di indirizzi di blocco di terze parti. Le organizzazioni di posta elettronica di destinazione che utilizzano questi elenchi di blocco rifiuteranno la posta elettronica da tali origini dei messaggi.

## <a name="high-risk-delivery-pool"></a>Pool di recapito ad alto rischio
Per evitare questo problema, tutti i messaggi in uscita dai server datacenter di Microsoft 365 [](configure-the-outbound-spam-policy.md) che sono stati definiti come posta indesiderata o che superano i limiti di invio del servizio o i criteri di posta indesiderata in uscita vengono inviati tramite il _pool_ di recapito ad alto rischio. [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

Il pool di recapito ad alto rischio è un pool di indirizzi IP separato per la posta elettronica in uscita che viene utilizzato solo per inviare messaggi di "bassa qualità" (ad esempio posta indesiderata e [posta indesiderata).](backscatter-messages-and-eop.md) L'utilizzo del pool di recapito ad alto rischio consente di impedire al normale pool di indirizzi IP per la posta elettronica in uscita di inviare posta indesiderata. Il normale pool di indirizzi IP per la posta elettronica in uscita mantiene la reputazione che invia messaggi di "alta qualità", riducendo la probabilità che questi indirizzi IP vengano visualizzati in elenchi di indirizzi IP bloccati.

La possibilità molto reale che gli indirizzi IP nel pool di recapito ad alto rischio siano inseriti negli elenchi di indirizzi IP bloccati rimane, ma questo è da progettazione. Il recapito ai destinatari non è garantito, perché molte organizzazioni di posta elettronica non accetteranno messaggi dal pool di recapito ad alto rischio.

Per ulteriori informazioni, vedere [Controllare la posta indesiderata in uscita.](outbound-spam-controls.md)

> [!NOTE]
> I messaggi in cui il dominio di posta elettronica di origine non dispone di un record A e nessun record MX definito nel DNS pubblico viene sempre instradato attraverso il pool di recapito ad alto rischio, indipendentemente dalla posta indesiderata o dall'eliminazione del limite di invio.

### <a name="bounce-messages"></a>Messaggi di mancato recapito

Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i rapporti di mancato recapito (noti anche come rapporti di mancato recapito, notifiche sullo stato del recapito o DSN).

Le possibili cause di un sovraccarico nei tipi di mancato recapito includono:

- Una campagna di spoofing che interessa uno dei clienti che usano il servizio.
- Un attacco directory harvest.
- Un attacco di posta indesiderata.
- Un server di posta elettronica non autorizzato.

Tutti questi problemi possono comportare un improvviso aumento del numero di NR elaborati dal servizio. Molte volte, questi tipi di mancato recapito sembrano essere posta indesiderata per altri server e servizi di posta elettronica (noti anche come _[posta indesiderata da posta indesiderata).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Pool di inoltro

I messaggi inoltrati o inoltrati da Microsoft 365 vengono inviati utilizzando uno speciale pool di inoltro, poiché la destinazione finale non deve considerare Microsoft 365 come mittente effettivo. È anche importante isolare questo traffico, perché esistono scenari legittimi e non validi per l'inoltro automatico o l'inoltro della posta elettronica da Microsoft 365. Analogamente al pool di recapito ad alto rischio, per l'inoltro della posta viene utilizzato un pool di indirizzi IP separato. Questo pool di indirizzi non viene pubblicato perché può cambiare spesso.

Microsoft 365 deve verificare che il mittente originale sia legittimo per poter recapitare con sicurezza il messaggio inoltrato. A tale scopo, l'autenticazione della posta elettronica (SPF, DKIM e DMARC) deve passare quando il messaggio viene inviato. Nei casi in cui è possibile autenticare il mittente, viene utilizzata la riscrittura del mittente per aiutare il destinatario a sapere che il messaggio inoltrato è da un'origine attendibile. Ulteriori informazioni sul funzionamento e sulle operazioni che è possibile eseguire per assicurarsi che il dominio di invio passi l'autenticazione nello schema di riscrittura dei [mittenti (SRS, Sender Rewriting Scheme).](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)
