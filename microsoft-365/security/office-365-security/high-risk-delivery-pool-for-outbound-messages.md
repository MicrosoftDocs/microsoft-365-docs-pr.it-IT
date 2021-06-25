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
description: Informazioni su come vengono utilizzati i pool di recapito per proteggere la reputazione dei server di posta elettronica nei Microsoft 365 datacenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137719"
---
# <a name="outbound-delivery-pools"></a>Pool di recapito in uscita

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I server di posta elettronica nei Microsoft 365 data center potrebbero essere temporaneamente responsabili dell'invio di posta indesiderata. Ad esempio, un malware o un attacco di posta indesiderata dannoso in un'organizzazione di posta elettronica locale che invia posta in uscita tramite Microsoft 365 o account Microsoft 365 compromessi. Gli utenti malintenzionati cercano inoltre di evitare il rilevamento inoltrando i messaggi Microsoft 365 inoltro.

Questi scenari possono comportare la visualizzazione dell'indirizzo IP Microsoft 365 server datacenter interessati negli elenchi di indirizzi di terze parti. Le organizzazioni di posta elettronica di destinazione che utilizzano questi elenchi bloccanti rifiuteranno la posta elettronica da tali origini dei messaggi.

## <a name="high-risk-delivery-pool"></a>Pool di recapito ad alto rischio
Per evitare questo problema, tutti i messaggi Microsoft 365 uscita dai server datacenter che sono [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) determinati come [](configure-the-outbound-spam-policy.md) posta indesiderata o che superano i limiti di invio del servizio o dei criteri di posta indesiderata in uscita vengono inviati tramite il _pool_ di recapito ad alto rischio.

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


### <a name="relay-pool"></a>Pool di inoltro

I messaggi inoltrati o inoltrati tramite Microsoft 365 in determinati scenari verranno inviati utilizzando uno speciale pool di inoltro, perché la destinazione non deve considerare Microsoft 365 come mittente effettivo. È importante isolare questo traffico di posta elettronica, perché esistono scenari legittimi e non validi per l'inoltro automatico o l'inoltro della posta elettronica Microsoft 365. Analogamente al pool di recapito ad alto rischio, per l'inoltro della posta viene utilizzato un pool di indirizzi IP separato. Questo pool di indirizzi non viene pubblicato perché può cambiare spesso e non fa parte del record SPF pubblicato per Microsoft 365.

Microsoft 365 necessario verificare che il mittente originale sia legittimo in modo da poter recapitare con sicurezza il messaggio inoltrato.

Il messaggio inoltrato/inoltrato deve soddisfare uno dei criteri seguenti per evitare di utilizzare il pool di inoltro:

- Il mittente in uscita si trova in [un dominio accettato.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- SPF passa quando il messaggio viene inviato Microsoft 365.
- DKIM nel dominio del mittente passa quando il messaggio Microsoft 365.
 
È possibile indicare che un messaggio è stato inviato tramite il pool di inoltro esaminando l'IP del server in uscita (il pool di inoltro sarà compreso nell'intervallo 40.95.0.0/16) o osservando il nome del server in uscita (avrà "rly" nel nome).

Nei casi in cui è possibile autenticare il mittente, viene utilizzato lo schema di riscrittura del mittente (SRS) per aiutare il sistema di posta elettronica del destinatario a sapere che il messaggio inoltrato è di origine attendibile. Ulteriori informazioni su come funziona e su cosa è possibile fare per assicurarsi che il dominio di invio passi l'autenticazione in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).

Per il funzionamento di DKIM, assicurati di abilitare DKIM per il dominio di invio. Ad esempio, fabrikam.com fa parte di contoso.com ed è definito nei domini accettati dell'organizzazione. Se il mittente del messaggio sender@fabrikam.com, DKIM deve essere abilitato per fabrikam.com. per informazioni su come abilitare l'utilizzo di DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato, vedere Use [DKIM to validate outbound email sent from your custom domain.](use-dkim-to-validate-outbound-email.md)

Per aggiungere un dominio personalizzato, seguire la procedura descritta in [Aggiungere un dominio a Microsoft 365](../../admin/setup/add-domain.md).
