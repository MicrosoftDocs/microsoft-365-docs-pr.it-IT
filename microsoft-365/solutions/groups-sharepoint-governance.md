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
description: Informazioni sulle interazioni delle impostazioni tra i gruppi di Microsoft 365 e SharePoint
ms.openlocfilehash: e8d4189c2d945d5a6d2aa78bd7ea980a77360ce0
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377558"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interazioni delle impostazioni tra i gruppi di Microsoft 365 e SharePoint

Alcune impostazioni per i gruppi di Microsoft 365 e SharePoint in Microsoft 365, in particolare relative alla condivisione e alla creazione di siti di gruppo e team, si sovrappongono tra loro. In questo articolo vengono fornite le descrizioni di queste interazioni e procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma di Venn delle funzionalità di SharePoint, Yammer e gruppi](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Effetti delle impostazioni di SharePoint nei gruppi di Microsoft 365

|Impostazione di SharePoint|Descrizione|Effetto sui gruppi di Microsoft 365|Consiglio|
|:-----------------|:----------|:-----------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se i siti, i file e le cartelle possono essere condivisi con utenti esterni all'organizzazione.|Se le impostazioni di SharePoint e dei gruppi non corrispondono, è possibile che gli utenti del gruppo possano essere bloccati dall'accesso al sito o che l'accesso esterno possa essere disponibile nel sito, ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare le impostazioni dei gruppi e le impostazioni del sito di SharePoint per i siti del team connessi al gruppo.<br><br>Vedere [collaborare con gli utenti in un sito](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site).|
|Consenti/blocca dominio|Consente o impedisce che il contenuto venga condiviso con i domini specificati.|I gruppi non riconoscono gli elenchi consentiti o bloccati di SharePoint. Gli utenti provenienti da domini non consentiti in SharePoint possono accedere a SharePoint tramite un gruppo.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Visualizzare [le impostazioni del dominio di SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e [le impostazioni del dominio di Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Consenti la condivisione esterna solo agli utenti di gruppi di sicurezza specifici|Specifica i gruppi di sicurezza che possono condividere i siti, le cartelle e i file esternamente.|Questa impostazione non influisce sui proprietari di gruppi per la condivisione esterna. Gli utenti del gruppo hanno accesso al sito di SharePoint associato.||
|Impostazioni di condivisione siti di SharePoint|Determina gli utenti che possono condividere il sito direttamente al di fuori dell'appartenenza al gruppo. Questa impostazione è configurata dal gruppo o dal proprietario del sito.|Questa impostazione non influisce direttamente sul gruppo, ma può consentire agli utenti di essere aggiunti a un sito e non avere accesso ad altre risorse di gruppo.|Prendere in considerazione l'utilizzo di questa impostazione per limitare direttamente la condivisione del sito e gestire l'accesso al sito tramite il gruppo.|
|Consenti agli utenti di creare siti dalla pagina iniziale di SharePoint e OneDrive|Specifica se gli utenti possono creare nuovi siti di SharePoint.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi al gruppo creando un gruppo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Effetti dell'impostazione dei gruppi di Microsoft 365 su SharePoint

|Impostazione gruppi di Microsoft 365|Descrizione|Effetto su SharePoint|Consiglio|
|:---------------------------|:----------|:-------------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi dei nomi di gruppo e le parole bloccate per la creazione di gruppi|I criteri vengono applicati per gli utenti che creano siti del team connessi al gruppo, ma non i siti di comunicazione o i siti con altri modelli.|Se necessario, creare linee guida per la denominazione separate per i siti di comunicazione.|
|Accesso Guest del gruppo|Specifica se gli utenti esterni all'organizzazione possono essere aggiunti ai gruppi.|Se le impostazioni di SharePoint e dei gruppi non corrispondono, è possibile che gli utenti del gruppo possano essere bloccati dall'accesso al sito o che l'accesso esterno possa essere disponibile nel sito, ma non nel gruppo.|Quando si modificano le impostazioni di condivisione, controllare le impostazioni dei gruppi e le impostazioni del sito di SharePoint per i siti del team connessi al gruppo.<br><br>Vedere [collaborare con gli utenti in un sito](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non saranno in grado di creare un sito del team connesso al gruppo.|Verificare che il processo di richiesta di un gruppo includa le istruzioni per la richiesta di un sito.|
|Criteri di scadenza del gruppo|Specifica un periodo di tempo dopo il quale i gruppi che non vengono utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, viene eliminato anche il sito di SharePoint associato. Il contenuto protetto dai criteri di conservazione viene mantenuto.|Utilizzare i criteri di scadenza per evitare l'espansione di gruppi e siti inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Collaborare con utenti esterni all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Gestire la creazione di siti in SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)