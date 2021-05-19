---
title: Impostazioni interazioni tra Microsoft 365 e SharePoint
ms.reviewer: mmclean
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
description: Informazioni sulle interazioni delle impostazioni tra Microsoft 365 gruppi e SharePoint
ms.openlocfilehash: 23e9553ce07514b18bafada5c93bcadab19806fe
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538160"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Impostazioni interazioni tra Microsoft 365 e SharePoint

Alcune impostazioni per Microsoft 365 gruppi e SharePoint in Microsoft 365, in particolare correlate alla condivisione e alla creazione di gruppi e siti del team, si sovrappongono tra loro. In questo articolo vengono fornite descrizioni di queste interazioni e procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma venn di SharePoint, Yammer e gruppi](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Effetti delle impostazioni SharePoint su Microsoft 365 gruppi

|SharePoint impostazioni|Descrizione|Effetto sui Microsoft 365 di lavoro|Consiglio|
|:-----------------|:----------|:-----------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se è possibile condividere siti, file e cartelle con utenti esterni all'organizzazione.|Se SharePoint e i gruppi non corrispondono, gli utenti guest del gruppo potrebbero essere bloccati dall'accesso al sito oppure l'accesso esterno potrebbe essere disponibile nel sito, ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare le impostazioni dei gruppi SharePoint per i siti del team connessi al gruppo.<br><br>Vedere [Collaborare con gli utenti guest in un sito.](./collaborate-in-site.md)|
|Domain allow/block|Consente o impedisce la condivisione del contenuto con domini specificati.|I gruppi non riconoscono gli SharePoint consentiti o bloccati. Gli utenti dei domini non consentiti in SharePoint possono accedere a SharePoint tramite un gruppo.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Vedere [SharePoint di dominio e](/sharepoint/restricted-domains-sharing) le impostazioni di dominio di Azure [AD](/azure/active-directory/b2b/allow-deny-list)|
|Consentire la condivisione esterna solo a utenti di gruppi di sicurezza specifici|Specifica i gruppi di sicurezza che possono condividere siti, cartelle e file esternamente.|Questa impostazione non influisce sui proprietari dei gruppi che condividono i gruppi esternamente. Gli utenti guest del gruppo hanno accesso al sito SharePoint utente associato.||
|SharePoint di condivisione del sito|Determina chi può condividere il sito direttamente all'esterno dell'appartenenza al gruppo. Questa impostazione viene configurata dal proprietario del gruppo o del sito.|Questa impostazione non influisce direttamente sul gruppo, ma può consentire agli utenti di essere aggiunti a un sito e di non avere accesso ad altre risorse del gruppo|Prendere in considerazione l'utilizzo di questa impostazione per limitare la condivisione del sito direttamente e gestire l'accesso al sito tramite il gruppo.|
|Consentire agli utenti di creare siti dalla SharePoint iniziale e OneDrive|Specifica se gli utenti possono creare nuovi SharePoint siti.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi a gruppi creando un gruppo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Gli effetti dell'impostazione Microsoft 365 gruppi su SharePoint

|Microsoft 365 dei gruppi|Descrizione|Effetto sulla SharePoint|Consiglio|
|:---------------------------|:----------|:-------------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi dei nomi di gruppo e le parole bloccate per la creazione del gruppo|I criteri vengono applicati agli utenti che creano siti del team connessi a gruppi, ma non a siti di comunicazione o siti con altri modelli.|Se necessario, creare indicazioni di denominazione separate per i siti di comunicazione.|
|Accesso guest di gruppo|Specifica se le persone esterne all'organizzazione possono essere aggiunte ai gruppi.|Se SharePoint e i gruppi non corrispondono, gli utenti guest del gruppo potrebbero essere bloccati dall'accesso al sito oppure l'accesso esterno potrebbe essere disponibile nel sito, ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare le impostazioni dei gruppi SharePoint per i siti del team connessi al gruppo.<br><br>Vedere [Collaborare con gli utenti guest in un sito](./collaborate-in-site.md)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non potranno creare un sito del team connesso a un gruppo.|Assicurati che il processo di richiesta di un gruppo includa istruzioni per richiedere un sito.|
|Criteri di scadenza gruppo|Specifica un periodo di tempo dopo il quale i gruppi non utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, viene eliminato SharePoint sito associato. Il contenuto protetto dai criteri di conservazione viene conservato.|Utilizzare i criteri di scadenza per evitare un'espansione di siti e gruppi inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Collaborare con persone esterne all'organizzazione](./collaborate-with-people-outside-your-organization.md)

[Gestire la creazione di siti in SharePoint](/sharepoint/manage-site-creation)