---
title: Opzioni di conformità per Microsoft 365 gruppi, Teams e SharePoint collaborazione
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informazioni sulle opzioni di conformità per Microsoft 365, Teams e SharePoint collaborazione.
ms.openlocfilehash: a9a94f0c1886ac5b60292f5f4d4b9b9d6d84380c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241677"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opzioni di conformità per Microsoft 365 gruppi, Teams e SharePoint collaborazione

Microsoft 365 offre una famiglia completa di strumenti per mantenere la conformità mentre gli utenti collaborano. Esaminare queste opzioni e valutare il modo in cui vengono mappate alle esigenze aziendali, la riservatezza dei dati e l'ambito delle persone con cui gli utenti devono collaborare.

Nella tabella seguente viene fornito un riferimento rapido per i controlli di conformità disponibili in Microsoft 365. Nelle sezioni seguenti vengono fornite ulteriori informazioni.

|Categoria|Descrizione|Riferimenti|
|:-------|:----------|:--------|
|Conservazione delle informazioni|||
||Conservare i gruppi di posta e SharePoint contenuto|[Informazioni sui criteri di conservazione per SharePoint e OneDrive](../compliance/retention-policies-sharepoint.md)|
||Conservare chat e messaggi|[Informazioni sui criteri di conservazione per Microsoft Teams](../compliance/retention-policies-teams.md)|
|Classificazione delle informazioni|||
||Classificare gruppi e team|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Classificare automaticamente il contenuto sensibile|[Applicare automaticamente un'etichetta di riservatezza al contenuto](../compliance/apply-sensitivity-label-automatically.md)|
||Crittografare contenuto sensibile|[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](../compliance/encryption-sensitivity-labels.md)|
|Protezione delle informazioni|||
||Evitare la perdita di informazioni riservate|[Informazioni sulla prevenzione della perdita di dati](../compliance/dlp-learn-about-dlp.md)|
||Proteggere le informazioni riservate in chat.|[Prevenzione della perdita di dati e Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||Definire le informazioni riservate dell'organizzazione|[Tipi di informazioni sensibili personalizzati](../compliance/sensitive-information-type-learn-about.md)|
|Segmentazione utente|||
||Limitare la comunicazione tra segmenti di utenti|[Barriere informative](../compliance/information-barriers.md)|
|Residenza dati|||
||Archiviare i dati in posizioni geografiche specifiche|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Conservazione delle informazioni

I criteri di conservazione sono disponibili per conservare o eliminare gli elementi utilizzati per la collaborazione in gruppi e team, inclusi file, messaggi e posta. I criteri possono essere impostati per conservare ed eliminare, solo per conservare o eliminare solo. Le informazioni coperte da un criterio di conservazione sono protette nel caso in cui il gruppo o il team scada o viene eliminato in altro modo.

La configurazione di un criterio di conservazione per Microsoft 365 gruppi riguarda la cassetta postale del gruppo e il sito SharePoint e i file associati.

- [Informazioni sui criteri di conservazione per SharePoint e OneDrive](../compliance/retention-policies-sharepoint.md)

I criteri di conservazione per Teams i messaggi di chat e canali. Mentre i messaggi di chat e canali vengono archiviati Exchange cassette postali, non sono interessati dai criteri Exchange di conservazione. È necessario impostare i criteri di conservazione da applicare Teams chat e Teams canali. 

Le chat utente vengono mantenute a tempo indeterminato anche se un account utente viene eliminato. Se non si desidera conservare questi dati a tempo indeterminato, è consigliabile utilizzare un criterio di conservazione per eliminare le chat degli utenti dopo un periodo di tempo specificato o includere questa eliminazione nel processo di eliminazione degli utenti.

- [Informazioni sui criteri di conservazione per Microsoft Teams](../compliance/retention-policies-teams.md)

- [Criteri di conservazione in Microsoft Teams](/microsoftteams/retention-policies)

Un singolo criterio di conservazione può essere impostato per essere applicato Teams messaggi di chat Teams canale. 

Risorse aggiuntive:

- [Informazioni sui criteri di conservazione](../compliance/retention.md)

- [Tag di conservazione e criteri di conservazione](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Classificazione delle informazioni

Puoi usare le etichette di riservatezza per regolamentare l'accesso guest, la privacy di gruppi e team e l'accesso da parte di dispositivi non gestiti per gruppi e team. Applicando l'etichetta, queste impostazioni vengono configurate automaticamente come specificato dalle impostazioni dell'etichetta.

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

È possibile configurare Microsoft 365 per applicare automaticamente etichette di riservatezza a file e messaggi di posta elettronica in base ai criteri specificati, incluso il rilevamento di tipi di informazioni riservate o criteri di corrispondenza con classificatori addestrabili.

- [Applicare automaticamente un'etichetta di riservatezza al contenuto](../compliance/apply-sensitivity-label-automatically.md)

È possibile utilizzare le etichette di riservatezza per crittografare i file, consentendo solo a quelli con autorizzazioni di decrittografarli e leggerli.

- [Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](../compliance/encryption-sensitivity-labels.md)

- [Configurare un team con l'isolamento di sicurezza](./secure-teams-security-isolation.md)

Risorse aggiuntive:

- [Informazioni sulle etichette di riservatezza](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Protezione delle informazioni

I criteri DLP possono impedire la condivisione accidentale di informazioni riservate tra SharePoint, Exchange e Teams. È possibile creare criteri che specificano le azioni da eseguire, ad esempio il blocco dell'accesso, in base a un set di regole.

- [Informazioni sulla prevenzione della perdita di dati](../compliance/dlp-learn-about-dlp.md)

DLP in Teams può aiutare a proteggere le informazioni riservate nei messaggi Teams chat e canali eliminando i messaggi che contengono informazioni riservate.

- [Prevenzione della perdita di dati e Microsoft Teams](../compliance/dlp-microsoft-teams.md)

Se si dispone di informazioni riservate univoche per l'organizzazione, ad esempio i nomi dei codici di progetto, è possibile creare tipi di informazioni riservate personalizzati e applicarle ai criteri DLP per proteggere il contenuto in gruppi, team e Sharepoint.

- [Tipi di informazioni sensibili personalizzati](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Segmentazione utente

Con le barriere di informazioni, è possibile segmentare i dati e gli utenti per limitare le comunicazioni indesiderate e la collaborazione tra gruppi ed evitare conflitti di interesse nell'organizzazione. Le barriere di informazioni consentono di creare criteri per consentire o impedire la collaborazione di file, chat, chiamate o inviti a riunioni tra gruppi di persone nell'organizzazione.

- [Barriere informative](../compliance/information-barriers.md)

- [Barriere informazioni in Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Usare barriere alle informazioni con SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Residenza dati

Con Microsoft 365 Multi-Geo, è possibile effettuare il provisioning e archiviare i dati a riposo nelle posizioni geografiche scelte per soddisfare i requisiti di residenza dei dati. In un ambiente Multi-Geo, il tenant di Microsoft 365 è costituito da una posizione centrale (in cui è stato originariamente effettuato il provisioning della sottoscrizione di Microsoft 365) e da una o più posizioni satellite in cui è possibile archiviare i dati.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Piano per Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Sicurezza e conformità per Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Proteggere le informazioni](../compliance/information-protection.md)
