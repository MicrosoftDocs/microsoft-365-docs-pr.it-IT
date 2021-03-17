---
title: Opzioni di conformità per i gruppi di Microsoft 365, Teams e la collaborazione di SharePoint
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
description: Informazioni sulle opzioni di conformità per i gruppi di Microsoft 365, Teams e la collaborazione di SharePoint.
ms.openlocfilehash: f68381ab45e74b9b7c8f44465387add82bd4150a
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838652"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opzioni di conformità per i gruppi di Microsoft 365, Teams e la collaborazione di SharePoint

Microsoft 365 offre una famiglia completa di strumenti per mantenere la conformità mentre gli utenti collaborano. Esaminare queste opzioni e valutare il modo in cui vengono mappate alle esigenze aziendali, la riservatezza dei dati e l'ambito delle persone con cui gli utenti devono collaborare.

Nella tabella seguente viene fornito un riferimento rapido per i controlli di conformità disponibili in Microsoft 365. Nelle sezioni seguenti vengono fornite ulteriori informazioni.

|Categoria|Descrizione|Riferimenti|
|:-------|:----------|:--------|
|Conservazione delle informazioni|||
||Conservare la posta elettronica e il contenuto di SharePoint dei gruppi|[Informazioni sui criteri di conservazione per SharePoint e OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Conservare chat e messaggi|[Informazioni sui criteri di conservazione per Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Classificazione delle informazioni|||
||Classificare gruppi e team|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Classificare automaticamente il contenuto sensibile|[Applicare automaticamente un'etichetta di riservatezza al contenuto](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Crittografare contenuto sensibile|[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Protezione delle informazioni|||
||Evitare la perdita di informazioni riservate|[Panoramica sulla prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Proteggere le informazioni riservate in chat.|[Prevenzione della perdita dei dati e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definire le informazioni riservate dell'organizzazione|[Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Segmentazione utente|||
||Limitare la comunicazione tra segmenti di utenti|[Barriere informative](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Conservazione delle informazioni

I criteri di conservazione sono disponibili per conservare o eliminare gli elementi utilizzati per la collaborazione in gruppi e team, inclusi file, messaggi e posta. I criteri possono essere impostati per conservare ed eliminare, solo per conservare o eliminare solo. Le informazioni coperte da un criterio di conservazione sono protette nel caso in cui il gruppo o il team scada o viene eliminato in altro modo.

La configurazione di un criterio di conservazione per i gruppi di Microsoft 365 riguarda la cassetta postale del gruppo e il sito e i file di SharePoint associati.

- [Informazioni sui criteri di conservazione per SharePoint e OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

I criteri di conservazione per Teams mantengono i messaggi di chat e canali. Mentre i messaggi di chat e canali vengono archiviati nelle cassette postali di Exchange, non sono interessati dai criteri di conservazione di Exchange. È necessario impostare i criteri di conservazione da applicare alle chat di Teams e ai messaggi del canale di Teams. 

Le chat utente vengono mantenute a tempo indeterminato anche se un account utente viene eliminato. Se non si desidera conservare questi dati a tempo indeterminato, è consigliabile utilizzare un criterio di conservazione per eliminare le chat degli utenti dopo un periodo di tempo specificato o includere questa eliminazione nel processo di eliminazione degli utenti.

- [Informazioni sui criteri di conservazione per Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Criteri di conservazione in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

È possibile impostare un singolo criterio di conservazione per applicarlo ai messaggi di gruppi, chat di Teams e canali di Microsoft 365. 

Risorse aggiuntive:

- [Informazioni sui criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Tag di conservazione e criteri di conservazione](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Classificazione delle informazioni

Puoi usare le etichette di riservatezza per regolamentare l'accesso guest, la privacy di gruppi e team e l'accesso da parte di dispositivi non gestiti per gruppi e team. Applicando l'etichetta, queste impostazioni vengono configurate automaticamente come specificato dalle impostazioni dell'etichetta.

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

È possibile configurare Microsoft 365 per applicare automaticamente etichette di riservatezza a file e messaggi di posta elettronica in base ai criteri specificati, incluso il rilevamento di tipi di informazioni riservate o criteri di corrispondenza con classificatori addestrabili.

- [Applicare automaticamente un'etichetta di riservatezza al contenuto](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

È possibile utilizzare le etichette di riservatezza per crittografare i file, consentendo solo a quelli con autorizzazioni di decrittografarli e leggerli.

- [Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Configurare un team con l'isolamento di sicurezza](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Risorse aggiuntive:

- [Informazioni sulle etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Protezione delle informazioni

I criteri DLP possono impedire la condivisione accidentale di informazioni riservate tra SharePoint, Exchange e Teams. È possibile creare criteri che specificano le azioni da eseguire, ad esempio il blocco dell'accesso, in base a un set di regole.

- [Panoramica sulla prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

Dlp in Teams consente di proteggere le informazioni riservate nei messaggi di chat e canali di Teams eliminando i messaggi che contengono informazioni riservate.

- [Prevenzione della perdita dei dati e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Se si dispone di informazioni riservate univoche per l'organizzazione, ad esempio i nomi dei codici di progetto, è possibile creare tipi di informazioni riservate personalizzati e applicarle ai criteri DLP per proteggere il contenuto in gruppi, team e Sharepoint.

- [Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Segmentazione utente

Con le barriere di informazioni, è possibile segmentare i dati e gli utenti per limitare le comunicazioni indesiderate e la collaborazione tra gruppi ed evitare conflitti di interesse nell'organizzazione. Le barriere di informazioni consentono di creare criteri per consentire o impedire la collaborazione di file, chat, chiamate o inviti a riunioni tra gruppi di persone nell'organizzazione.

- [Barriere informative](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Barriere informazioni in Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Usare le barriere di informazioni con SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Sicurezza e conformità per Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Proteggere le informazioni](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
