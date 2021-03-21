---
title: Interazioni delle impostazioni tra i gruppi di Microsoft 365 e SharePoint
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
ms.openlocfilehash: e1aeaca792fb551de503bd4c68256ccf14f45022
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921037"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interazioni delle impostazioni tra i gruppi di Microsoft 365 e SharePoint

Alcune impostazioni per i gruppi di Microsoft 365 e SharePoint in Microsoft 365, in particolare relative alla condivisione e alla creazione di gruppi e siti del team, si sovrappongono tra loro. In questo articolo vengono fornite descrizioni di queste interazioni e procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma di Venn delle funzionalità di SharePoint, Yammer e gruppi](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Effetti delle impostazioni di SharePoint sui gruppi di Microsoft 365

|Impostazione di SharePoint|Descrizione|Effetto sui gruppi di Microsoft 365|Consiglio|
|:-----------------|:----------|:-----------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se è possibile condividere siti, file e cartelle con utenti esterni all'organizzazione.|Se le impostazioni di SharePoint e dei gruppi non corrispondono, agli utenti guest del gruppo potrebbe essere impedito l'accesso al sito oppure l'accesso esterno potrebbe essere disponibile nel sito ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare sia le impostazioni dei gruppi che le impostazioni del sito di SharePoint per i siti del team connessi a gruppi.<br><br>Vedere [Collaborare con gli utenti guest in un sito.](./collaborate-in-site.md)|
|Domain allow/block|Consente o impedisce la condivisione del contenuto con domini specificati.|I gruppi non riconoscono gli elenchi consentiti o bloccati di SharePoint. Gli utenti dei domini non consentiti in SharePoint potrebbero accedere a SharePoint tramite un gruppo.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Vedere [Impostazioni di dominio di SharePoint](/sharepoint/restricted-domains-sharing) e Impostazioni di dominio di Azure [AD](/azure/active-directory/b2b/allow-deny-list)|
|Consentire la condivisione esterna solo agli utenti di gruppi di sicurezza specifici.|Specifica i gruppi di sicurezza che possono condividere siti, cartelle e file esternamente.|Questa impostazione non influisce sui proprietari dei gruppi che condividono i gruppi esternamente. Gli utenti guest del gruppo hanno accesso al sito di SharePoint associato.||
|Impostazioni di condivisione siti di SharePoint|Determina chi può condividere il sito direttamente all'esterno dell'appartenenza al gruppo. Questa impostazione viene configurata dal proprietario del gruppo o del sito.|Questa impostazione non influisce direttamente sul gruppo, ma può consentire agli utenti di essere aggiunti a un sito e di non avere accesso ad altre risorse del gruppo|Prendere in considerazione l'utilizzo di questa impostazione per limitare la condivisione del sito direttamente e gestire l'accesso al sito tramite il gruppo.|
|Consentire agli utenti di creare siti dalla pagina iniziale di SharePoint e OneDrive|Specifica se gli utenti possono creare nuovi siti di SharePoint.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi a gruppi creando un gruppo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Effetti dell'impostazione dei gruppi di Microsoft 365 su SharePoint

|Impostazione dei gruppi di Microsoft 365|Descrizione|Effetto su SharePoint|Consiglio|
|:---------------------------|:----------|:-------------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi dei nomi di gruppo e le parole bloccate per la creazione del gruppo|I criteri vengono applicati agli utenti che creano siti del team connessi a gruppi, ma non a siti di comunicazione o siti con altri modelli.|Se necessario, creare indicazioni di denominazione separate per i siti di comunicazione.|
|Accesso guest di gruppo|Specifica se le persone esterne all'organizzazione possono essere aggiunte ai gruppi.|Se le impostazioni di SharePoint e dei gruppi non corrispondono, agli utenti guest del gruppo potrebbe essere impedito l'accesso al sito oppure l'accesso esterno potrebbe essere disponibile nel sito ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare sia le impostazioni dei gruppi che le impostazioni del sito di SharePoint per i siti del team connessi a gruppi.<br><br>Vedere [Collaborare con gli utenti guest in un sito](./collaborate-in-site.md)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non potranno creare un sito del team connesso a un gruppo.|Assicurati che il processo di richiesta di un gruppo includa istruzioni per richiedere un sito.|
|Criteri di scadenza gruppo|Specifica un periodo di tempo dopo il quale i gruppi non utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, viene eliminato anche il sito di SharePoint associato. Il contenuto protetto dai criteri di conservazione viene conservato.|Utilizzare i criteri di scadenza per evitare un'espansione di siti e gruppi inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Collaborare con persone esterne all'organizzazione](./collaborate-with-people-outside-your-organization.md)

[Gestire la creazione di siti in SharePoint](/sharepoint/manage-site-creation)