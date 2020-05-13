---
title: Pool di recapito ad alto rischio per i messaggi in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Informazioni sul modo in cui il pool di recapito ad alto rischio viene utilizzato per proteggere la reputazione dei server di posta elettronica nei datacenter Microsoft 365.
ms.openlocfilehash: 190dc3bd7ed2a6cddb23c8bc7c117dee30fd4f13
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209188"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Pool di recapito ad alto rischio per i messaggi in uscita

I server di posta elettronica nei datacenter Microsoft 365 potrebbero essere temporaneamente colpevoli di inviare messaggi di posta indesiderata. Ad esempio, un attacco di posta indesiderata o malware in un'organizzazione di posta elettronica locale che invia la posta in uscita tramite Microsoft 365 o ha compromesso gli account di Microsoft 365. Questi scenari possono comportare l'indirizzo IP dei server del datacenter Microsoft 365 interessato che appaiono negli elenchi di blocco di terze parti. Le organizzazioni di posta elettronica di destinazione che utilizzano questi elenchi di blocco rifiuteranno la posta elettronica dalle origini dei messaggi.

Per evitare questo, tutti i messaggi in uscita dai server di datacenter Microsoft 365 che sono determinati come posta indesiderata o che superano i limiti di invio del [servizio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o i [criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md) vengono inviati attraverso il _pool di recapito ad alto rischio_.

Il pool di recapito ad alto rischio è un pool di indirizzi IP secondario per la posta elettronica in uscita utilizzata solo per l'invio di messaggi di "bassa qualità" (ad esempio, posta indesiderata e [backscattering](backscatter-messages-and-eop.md)). L'utilizzo del pool di recapito ad alto rischio impedisce che il pool di indirizzi IP normale per la posta elettronica in uscita invii la posta indesiderata. Il pool di indirizzi IP normale per la posta elettronica in uscita mantiene la reputazione che invia messaggi "di alta qualità", che riduce la probabilità che questi indirizzi IP vengano visualizzati negli elenchi di blocco IP.

La possibilità reale che gli indirizzi IP in un pool di recapito ad alto rischio venga disposta sugli elenchi di blocco IP rimane, ma è in base alla progettazione. Il recapito ai destinatari previsti non è garantito, perché molte organizzazioni di posta elettronica non accettano messaggi dal pool di recapito ad alto rischio.

Per ulteriori informazioni, vedere [controllare la posta indesiderata in uscita](outbound-spam-controls.md).

> [!NOTE]
> Messaggi in cui il dominio di posta elettronica di origine non ha un record e nessun record MX definito in DNS pubblico vengono sempre instradati attraverso il pool di recapito ad alto rischio, indipendentemente dalla posta indesiderata o dall'invio dei limiti.

## <a name="bounce-messages"></a>Messaggi di rimbalzo

Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i rapporti di mancato recapito (noti anche come NDR, messaggi di rimbalzo, notifiche sullo stato del recapito o DSN).

Le possibili cause di un aumento dei rapporti di mancato recapito includono:

- Una campagna di spoofing che influisce su uno dei clienti che utilizzano il servizio.
- Un attacco di raccolta directory.
- Un attacco di posta indesiderata.
- Un server di posta elettronica canaglia.

Tutti questi problemi possono portare a un improvviso aumento del numero di rapporti di mancato recapito elaborati dal servizio. Molte volte, questi rapporti di mancato recapito sembrano essere posta indesiderata ad altri server e servizi di posta elettronica (noti anche come _[backscatter](backscatter-messages-and-eop.md)_).
