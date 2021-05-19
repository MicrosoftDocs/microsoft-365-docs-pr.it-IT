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
recommendations: false
description: Informazioni sulle interazioni delle impostazioni tra Microsoft 365 gruppi, Teams e SharePoint
ms.openlocfilehash: 14a21cd34fe38b47d93d0cbcec5e9cb2a3bc49c7
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539084"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Interazioni delle impostazioni tra Microsoft 365 Groups, Teams e SharePoint

Alcune impostazioni per Microsoft 365 Gruppi, Microsoft Teams e SharePoint in Microsoft 365, in particolare relative alla condivisione e alla creazione di gruppi/team e siti di SharePoint, si sovrappongono tra loro. In questo articolo vengono fornite descrizioni di queste interazioni e procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma venn di SharePoint, Teams e gruppi](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Effetti delle impostazioni SharePoint su gruppi e team

|SharePoint impostazioni|Descrizione|Effetto su Microsoft 365 gruppi e Teams|Consiglio|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se è possibile condividere siti, file e cartelle con utenti esterni all'organizzazione.|Se SharePoint, gruppi e Teams non corrispondono, gli utenti guest del team potrebbero essere bloccati dall'accesso al sito o potrebbe verificarsi un accesso esterno imprevisto.|Quando si modificano le impostazioni di condivisione, selezionare Impostazioni gruppi, Impostazioni Teams e impostazioni SharePoint sito per i siti del team connessi al gruppo.<br><br> Vedere [Collaborare con gli utenti guest in un team](./collaborate-as-team.md)|
|Domain allow/block|Consente o impedisce la condivisione del contenuto con domini specificati.|I gruppi e Teams non riconoscono gli SharePoint consentiti o bloccati. Gli utenti dei domini non consentiti in SharePoint possono accedere a SharePoint siti o contenuti tramite un team.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Vedere [SharePoint di dominio e](/sharepoint/restricted-domains-sharing) le impostazioni di dominio di Azure [AD](/azure/active-directory/b2b/allow-deny-list)|
|Consentire la condivisione esterna solo a utenti di gruppi di sicurezza specifici|Specifica i gruppi di sicurezza che possono condividere SharePoint siti, cartelle e file esternamente.|Questa impostazione non impedisce ai proprietari dei team di condividere i team esternamente. Gli utenti guest del team hanno accesso al sito SharePoint associato.||
|SharePoint di condivisione del sito|Determina chi può condividere il sito direttamente all'esterno dell'appartenenza al team. Questa impostazione viene configurata dal proprietario del team o del sito.|Questa impostazione non influisce direttamente sul team, ma può consentire agli utenti di essere aggiunti a un sito e di non avere accesso al team stesso o ad altre Teams risorse|Prendere in considerazione l'utilizzo di questa impostazione per limitare la condivisione del sito direttamente e gestire l'accesso al sito tramite il team.|
|Consentire agli utenti di creare siti dalla SharePoint iniziale e OneDrive|Specifica se gli utenti possono creare nuovi SharePoint siti.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi a gruppi creando un team.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Effetti delle impostazioni dei gruppi sui team

|Microsoft 365 dei gruppi|Descrizione|Effetto sulla Teams|Consiglio|
|:---------------------------|:----------|:--------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi dei nomi di gruppo e le parole bloccate per la creazione del gruppo|I criteri vengono applicati agli utenti che creano team.||
|Accesso guest di gruppo|Specifica se le persone esterne all'organizzazione possono essere aggiunte ai gruppi.|Se i gruppi o le Teams di condivisione guest sono disattivate, il team non può essere condiviso con gli utenti guest.|Quando si modificano le impostazioni di condivisione guest, controllare le impostazioni per Teams, gruppi e SharePoint sito associato al team.<br><br> Vedere [Collaborare con gli utenti guest in un team](./collaborate-as-team.md)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non potranno creare un team.|Assicurati che il processo per richiedere un gruppo includa istruzioni per richiedere un team o un SharePoint sito.|
|Criteri di scadenza gruppo|Specifica un periodo di tempo dopo il quale i gruppi non utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, vengono eliminati anche il team e SharePoint sito. Il contenuto protetto dai criteri di conservazione viene conservato.|Utilizzare i criteri di scadenza per evitare un'espansione di team, gruppi e siti inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Collaborare con persone esterne all'organizzazione](./collaborate-with-people-outside-your-organization.md)

[Gestire la creazione di siti in SharePoint](/sharepoint/manage-site-creation)