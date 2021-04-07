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
description: Informazioni su come vengono utilizzati i pool di recapito per proteggere la reputazione dei server di posta elettronica nei datacenter di Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599912"
---
# <a name="outbound-delivery-pools"></a>Pool di recapito in uscita

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I server di posta elettronica nei datacenter di Microsoft 365 potrebbero essere temporaneamente responsabili dell'invio di posta indesiderata. Ad esempio, un malware o un attacco di posta indesiderata dannoso in un'organizzazione di posta elettronica locale che invia posta in uscita tramite Microsoft 365 o account Microsoft 365 compromessi. Gli utenti malintenzionati cercano inoltre di evitare il rilevamento inoltrando i messaggi tramite l'inoltro di Microsoft 365.

Questi scenari possono comportare la visualizzazione dell'indirizzo IP dei server datacenter di Microsoft 365 interessati negli elenchi di indirizzi di terze parti. Le organizzazioni di posta elettronica di destinazione che utilizzano questi elenchi bloccanti rifiuteranno la posta elettronica da tali origini dei messaggi.

## <a name="high-risk-delivery-pool"></a>Pool di recapito ad alto rischio
Per evitare questo problema, tutti i messaggi in uscita dai server datacenter di Microsoft 365 [](configure-the-outbound-spam-policy.md) che sono determinati come posta indesiderata o che superano i limiti di invio del servizio o dei criteri di posta indesiderata in uscita vengono inviati tramite il _pool_ di recapito ad alto rischio. [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

Il pool di recapito ad alto rischio è un pool di indirizzi IP separato per la posta elettronica in uscita che viene utilizzato solo per inviare messaggi di "bassa qualità" (ad esempio, posta indesiderata e [backscatter).](backscatter-messages-and-eop.md) L'utilizzo del pool di recapito ad alto rischio consente di impedire al normale pool di indirizzi IP per la posta elettronica in uscita di inviare posta indesiderata. Il normale pool di indirizzi IP per la posta elettronica in uscita mantiene la reputazione che invia messaggi di "alta qualità", riducendo così la probabilità che questi indirizzi IP vengano visualizzati sugli elenchi indirizzi IP bloccati.

La possibilità reale che gli indirizzi IP nel pool di recapito ad alto rischio siano inseriti negli elenchi indirizzi IP non validi rimane, ma questo è per progettazione. Il recapito ai destinatari previsti non è garantito, perché molte organizzazioni di posta elettronica non accettano messaggi dal pool di recapito ad alto rischio.

Per ulteriori informazioni, vedere [Control outbound spam](outbound-spam-controls.md).

> [!NOTE]
> I messaggi in cui il dominio di posta elettronica di origine non dispone di un record A e nessun record MX definito nel DNS pubblico viene sempre instradato attraverso il pool di recapito ad alto rischio, indipendentemente dalla posta indesiderata o dall'eliminazione del limite di invio.

### <a name="bounce-messages"></a>Messaggi di mancato recapito

Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i rapporti di mancato recapito (noti anche come rapporti di mancato recapito, messaggi di mancato recapito, notifiche sullo stato del recapito o DSN).

Le possibili cause di un aumento dei dati di mancato recapito includono:

- Una campagna di spoofing che interessa uno dei clienti che usano il servizio.
- Un attacco di raccolta directory.
- Un attacco di posta indesiderata.
- Un server di posta elettronica non autorizzato.

Tutti questi problemi possono comportare un aumento repentino del numero di NNDR elaborati dal servizio. Molte volte, questi nomi di mancato recapito sembrano essere posta indesiderata per altri server e servizi di posta elettronica (noto anche come _[backscatter).](backscatter-messages-and-eop.md)_
