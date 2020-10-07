---
title: Opzioni di conformità per i gruppi di Microsoft 365, i team e la collaborazione di SharePoint
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
description: Informazioni sulle opzioni di conformità per i gruppi di Microsoft 365, i team e la collaborazione di SharePoint.
ms.openlocfilehash: 0383b0728d9b8ea12ce75de8bf0e250932d14ae5
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377534"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opzioni di conformità per i gruppi di Microsoft 365, i team e la collaborazione di SharePoint

Microsoft 365 offre una serie completa di strumenti per mantenere la conformità durante la collaborazione tra gli utenti. Esaminare queste opzioni e valutare il modo in cui vengono mappate alle esigenze aziendali, la sensibilità dei dati e l'ambito delle persone con cui gli utenti devono collaborare.

Nella tabella seguente viene fornita una guida di riferimento rapida per i controlli di conformità disponibili in Microsoft 365. Ulteriori informazioni sono disponibili nelle sezioni seguenti.

|Categoria|Descrizione|Riferimenti|
|:-------|:----------|:--------|
|Conservazione delle informazioni|||
||Mantenere i gruppi di posta e contenuto di SharePoint|[Informazioni sui criteri di conservazione per SharePoint e OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Mantieni chat e messaggi|[Informazioni sui criteri di conservazione per Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Classificazione delle informazioni|||
||Classificare gruppi e team|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Classificazione automatica del contenuto riservato|[Applicare automaticamente un'etichetta di riservatezza al contenuto](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Crittografare il contenuto riservato|[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Protezione delle informazioni|||
||Impedire la perdita di informazioni riservate|[Panoramica sulla prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Proteggere le informazioni riservate in chat.|[Prevenzione della perdita di dati e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definire le informazioni riservate dell'organizzazione|[Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Segmentazione utente|||
||Limitare la comunicazione tra segmenti di utenti|[Barriere informative](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Conservazione delle informazioni

I criteri di conservazione sono disponibili per conservare o eliminare gli elementi utilizzati per la collaborazione in gruppi e team, inclusi i file, i messaggi e la posta elettronica. I criteri possono essere impostati in modo da conservare ed eliminare, conservare solo o eliminare solo. Le informazioni coperte da un criterio di conservazione sono protette nel caso in cui il gruppo o il team SCADA o venga eliminato in altro modo.

La configurazione di un criterio di conservazione per i gruppi di Microsoft 365 copre la cassetta postale del gruppo e i file e il sito di SharePoint associati.

- [Informazioni sui criteri di conservazione per SharePoint e OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

I criteri di conservazione per i team mantengono i messaggi chat e Channel. Anche se i messaggi chat e Channel sono archiviati in cassette postali di Exchange, non sono intaccati dai criteri di conservazione di Exchange. È necessario impostare i criteri di conservazione da applicare alle chat dei team e ai messaggi del canale team:

- [Informazioni sui criteri di conservazione per Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Criteri di conservazione in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

È possibile impostare un singolo criterio di conservazione per applicarlo ai messaggi dei gruppi di Microsoft 365, chat team e teams. 

Risorse aggiuntive:

- [Informazioni sui criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Tag di conservazione e criteri di conservazione](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Classificazione delle informazioni

È possibile utilizzare le etichette di riservatezza per gestire l'accesso guest, la privacy del gruppo e del team e l'accesso da dispositivi non gestiti per gruppi e team. Applicando l'etichetta, queste impostazioni vengono configurate automaticamente come specificato dalle impostazioni dell'etichetta.

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

È possibile configurare Microsoft 365 per applicare automaticamente le etichette di riservatezza ai file e ai messaggi di posta elettronica in base ai criteri specificati, tra cui il rilevamento di tipi di informazioni riservate o la corrispondenza dei modelli con i classificatori addestrabili.

- [Applicare automaticamente un'etichetta di riservatezza al contenuto](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

È possibile utilizzare le etichette di riservatezza per crittografare i file, consentendo solo coloro che dispongono delle autorizzazioni per decrittografarli e leggerli.

- [Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Configurare un team con l'isolamento di sicurezza](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Risorse aggiuntive:

- [Informazioni sulle etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Protezione delle informazioni

I criteri DLP possono impedire la condivisione accidentale di informazioni riservate in SharePoint, Exchange e teams. È possibile creare criteri che specifichino le azioni da eseguire, ad esempio il blocco dell'accesso, in base a un set di regole.

- [Panoramica sulla prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP in teams è in grado di proteggere le informazioni riservate in teams chat and Channel messages eliminando i messaggi che contengono informazioni riservate.

- [Prevenzione della perdita di dati e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Se si dispone di informazioni riservate specifiche per l'organizzazione, ad esempio i nomi di codice del progetto, è possibile creare tipi di informazioni riservate personalizzati e applicarli ai criteri DLP per proteggere il contenuto in gruppi, team e SharePoint.

- [Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Segmentazione utente

Con barriere informative, è possibile suddividere i dati e gli utenti per limitare la comunicazione indesiderata e la collaborazione tra i gruppi ed evitare conflitti di interesse nell'organizzazione. Barriere informative consente di creare criteri che consentano o impediscano la collaborazione, la chat, la chiamata o la riunione degli inviti tra gruppi di persone nell'organizzazione.

- [Barriere informative](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Barriere informative in Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Utilizzo di barriere informative con SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza e conformità per Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Proteggere le informazioni](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


