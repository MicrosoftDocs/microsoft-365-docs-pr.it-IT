---
title: Interazioni delle impostazioni tra Microsoft 365 Groups, Teams e SharePoint
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
description: Informazioni sulle interazioni delle impostazioni tra i gruppi di Microsoft 365, Teams e SharePoint
ms.openlocfilehash: ba3578903731a66d66c943f8daaec1a61943228c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921013"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Interazioni delle impostazioni tra Microsoft 365 Groups, Teams e SharePoint

Alcune impostazioni per i gruppi di Microsoft 365, Microsoft Teams e SharePoint in Microsoft 365, in particolare relative alla condivisione e alla creazione di gruppi/team e siti di SharePoint, si sovrappongono tra loro. In questo articolo vengono fornite descrizioni di queste interazioni e procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma di Venn delle funzionalità di SharePoint, Teams e gruppi](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Effetti delle impostazioni di SharePoint su gruppi e team

|Impostazione di SharePoint|Descrizione|Effetto sui gruppi di Microsoft 365 e Teams|Consiglio|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se è possibile condividere siti, file e cartelle con utenti esterni all'organizzazione.|Se le impostazioni di SharePoint, gruppi e Teams non corrispondono, agli utenti guest del team potrebbe essere impedito l'accesso al sito o potrebbe verificarsi un accesso esterno imprevisto.|Quando si modificano le impostazioni di condivisione, selezionare Impostazioni gruppi, Impostazioni di Teams e Impostazioni sito di SharePoint per i siti del team connessi al gruppo.<br><br> Vedere [Collaborare con gli utenti guest in un team](./collaborate-as-team.md)|
|Domain allow/block|Consente o impedisce la condivisione del contenuto con domini specificati.|I gruppi e Teams non riconoscono gli elenchi consentiti o bloccati di SharePoint. Gli utenti dei domini non consentiti in SharePoint potrebbero accedere ai siti o al contenuto di SharePoint tramite un team.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Vedere [Impostazioni di dominio di SharePoint](/sharepoint/restricted-domains-sharing) e Impostazioni di dominio di Azure [AD](/azure/active-directory/b2b/allow-deny-list)|
|Consentire la condivisione esterna solo agli utenti di gruppi di sicurezza specifici.|Specifica i gruppi di sicurezza che possono condividere siti, cartelle e file di SharePoint esternamente.|Questa impostazione non impedisce ai proprietari dei team di condividere i team esternamente. Gli utenti guest del team hanno accesso al sito di SharePoint associato.||
|Impostazioni di condivisione siti di SharePoint|Determina chi può condividere il sito direttamente all'esterno dell'appartenenza al team. Questa impostazione viene configurata dal proprietario del team o del sito.|Questa impostazione non influisce direttamente sul team, ma può consentire agli utenti di essere aggiunti a un sito e di non avere accesso al team stesso o ad altre risorse di Teams|Prendere in considerazione l'utilizzo di questa impostazione per limitare la condivisione del sito direttamente e gestire l'accesso al sito tramite il team.|
|Consentire agli utenti di creare siti dalla pagina iniziale di SharePoint e OneDrive|Specifica se gli utenti possono creare nuovi siti di SharePoint.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi a gruppi creando un team.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Effetti delle impostazioni dei gruppi sui team

|Impostazione dei gruppi di Microsoft 365|Descrizione|Effetto su Teams|Consiglio|
|:---------------------------|:----------|:--------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi dei nomi di gruppo e le parole bloccate per la creazione del gruppo|I criteri vengono applicati agli utenti che creano team.||
|Accesso guest di gruppo|Specifica se le persone esterne all'organizzazione possono essere aggiunte ai gruppi.|Se i gruppi o le impostazioni di condivisione guest di Teams sono disattivati, il team non può essere condiviso con gli utenti guest.|Quando si modificano le impostazioni di condivisione guest, controllare le impostazioni per Teams, Gruppi e il sito di SharePoint associato al team.<br><br> Vedere [Collaborare con gli utenti guest in un team](./collaborate-as-team.md)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non potranno creare un team.|Assicurarsi che il processo di richiesta di un gruppo includa istruzioni per richiedere un team o un sito di SharePoint.|
|Criteri di scadenza gruppo|Specifica un periodo di tempo dopo il quale i gruppi non utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, vengono eliminati anche il team e il sito di SharePoint associato. Il contenuto protetto dai criteri di conservazione viene conservato.|Utilizzare i criteri di scadenza per evitare un'espansione di team, gruppi e siti inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Collaborare con persone esterne all'organizzazione](./collaborate-with-people-outside-your-organization.md)

[Gestire la creazione di siti in SharePoint](/sharepoint/manage-site-creation)