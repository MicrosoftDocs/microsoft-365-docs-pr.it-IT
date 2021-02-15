---
title: Impostazioni interazioni tra gruppi di Microsoft 365 e SharePoint
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
description: Informazioni sulle interazioni tra le impostazioni tra i gruppi di Microsoft 365 e SharePoint
ms.openlocfilehash: a00e863fead8e74cf0f169471ebb36f9539ed103
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613491"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Impostazioni interazioni tra gruppi di Microsoft 365 e SharePoint

Alcune impostazioni per i gruppi di Microsoft 365 e SharePoint in Microsoft 365, in particolare relative alla condivisione e alla creazione di gruppi e siti del team, si sovrappongono tra loro. In questo articolo vengono fornite le descrizioni di queste interazioni e le procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma di Venn delle funzionalità di SharePoint, Yammer e gruppi](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Effetti delle impostazioni di SharePoint sui gruppi di Microsoft 365

|Impostazione di SharePoint|Descrizione|Effetto sui gruppi di Microsoft 365|Consiglio|
|:-----------------|:----------|:-----------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se è possibile condividere siti, file e cartelle con utenti esterni all'organizzazione.|Se le impostazioni di SharePoint e dei gruppi non corrispondono, gli utenti guest del gruppo potrebbero essere bloccati dall'accesso al sito oppure l'accesso esterno potrebbe essere disponibile nel sito, ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare sia le impostazioni dei gruppi che le impostazioni del sito di SharePoint per i siti del team connessi a gruppi.<br><br>Vedere [Collaborare con gli utenti guest in un sito.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Dominio consentito/blocco|Consente o impedisce la condivisione del contenuto con domini specificati.|I gruppi non riconoscono gli elenchi consentiti o bloccati di SharePoint. Gli utenti dei domini non consentiti in SharePoint potrebbero accedere a SharePoint tramite un gruppo.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Vedere [le impostazioni di dominio di SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e le impostazioni del dominio di Azure [AD](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Consentire la condivisione esterna solo agli utenti di gruppi di sicurezza specifici.|Specifica i gruppi di sicurezza che possono condividere siti, cartelle e file esternamente.|Questa impostazione non influisce sui proprietari dei gruppi che condividono i gruppi esternamente. Gli utenti guest del gruppo hanno accesso al sito di SharePoint associato.||
|Impostazioni di condivisione siti di SharePoint|Determina gli utenti che possono condividere il sito direttamente all'esterno dell'appartenenza al gruppo. Questa impostazione viene configurata dal proprietario del gruppo o del sito.|Questa impostazione non influisce direttamente sul gruppo, ma può consentire agli utenti di essere aggiunti a un sito senza avere accesso ad altre risorse del gruppo|È consigliabile utilizzare questa impostazione per limitare la condivisione del sito direttamente e gestire l'accesso al sito tramite il gruppo.|
|Consentire agli utenti di creare siti dalla pagina iniziale di SharePoint e OneDrive|Specifica se gli utenti possono creare nuovi siti di SharePoint.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi a gruppi creando un gruppo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Effetti dell'impostazione dei gruppi di Microsoft 365 in SharePoint

|Impostazione dei gruppi di Microsoft 365|Descrizione|Effetto su SharePoint|Consiglio|
|:---------------------------|:----------|:-------------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi del nome del gruppo e le parole bloccate per la creazione del gruppo|I criteri vengono applicati per gli utenti che creano siti del team connessi a gruppi, ma non per siti di comunicazione o siti con altri modelli.|Creare indicazioni sulla denominazione separate per i siti di comunicazione, se necessario.|
|Accesso guest di gruppo|Specifica se è possibile aggiungere persone esterne all'organizzazione ai gruppi.|Se le impostazioni di SharePoint e dei gruppi non corrispondono, gli utenti guest del gruppo potrebbero essere bloccati dall'accesso al sito oppure l'accesso esterno potrebbe essere disponibile nel sito, ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare sia le impostazioni dei gruppi che le impostazioni del sito di SharePoint per i siti del team connessi a gruppi.<br><br>Vedere [Collaborare con gli utenti guest in un sito](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non potranno creare un sito del team connesso a un gruppo.|Assicurati che il processo per richiedere un gruppo includa istruzioni per richiedere un sito.|
|Criteri di scadenza dei gruppi|Specifica un periodo di tempo dopo il quale i gruppi non utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, viene eliminato anche il sito di SharePoint associato. Il contenuto protetto dai criteri di conservazione viene conservato.|Utilizzare i criteri di scadenza per evitare un'espansione dei gruppi e dei siti inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Procedura dettagliata per la pianificazione della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Collaborare con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Gestire la creazione di siti in SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)