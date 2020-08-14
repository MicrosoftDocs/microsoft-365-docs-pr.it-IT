---
title: Interazioni delle impostazioni tra i gruppi di Microsoft 365, teams e SharePoint
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informazioni sulle interazioni delle impostazioni tra i gruppi di Microsoft 365, teams e SharePoint
ms.openlocfilehash: 3ad5011c2d7b4579e054b014237d5771049b3c91
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662691"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Interazioni delle impostazioni tra i gruppi di Microsoft 365, teams e SharePoint

Alcune impostazioni per i gruppi di Microsoft 365, Microsoft teams e SharePoint in Microsoft 365, in particolare relative alla condivisione e alla creazione di siti di gruppo e team e di SharePoint, si sovrappongono tra loro. In questo articolo vengono fornite le descrizioni di queste interazioni e procedure consigliate per l'utilizzo di queste impostazioni.

![Diagramma di Venn di funzionalità di SharePoint, team e gruppi](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Effetti delle impostazioni di SharePoint su gruppi e team

|Impostazione di SharePoint|Descrizione|Effetto sui gruppi e sui team di Microsoft 365|Consiglio|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Condivisione esterna per l'organizzazione e il sito|Determina se i siti, i file e le cartelle possono essere condivisi con utenti esterni all'organizzazione.|Se le impostazioni di SharePoint, gruppi e team non corrispondono, è possibile che gli utenti del team possano essere bloccati dall'accesso al sito o che si verifichi un accesso esterno inatteso.|Quando si modificano le impostazioni di condivisione, selezionare impostazioni gruppi, impostazioni team e impostazioni sito di SharePoint per i siti del team connessi al gruppo.<br><br> Vedere [collaborare con gli ospiti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Consenti/blocca dominio|Consente o impedisce che il contenuto venga condiviso con i domini specificati.|I gruppi e i team non riconoscono gli elenchi Consenti o blocca di SharePoint. Gli utenti provenienti da domini non consentiti in SharePoint possono accedere a siti o contenuti di SharePoint tramite un team.|Gestire gli elenchi di domini consentiti/bloccati per Azure AD e SharePoint insieme. Creare un processo di governance a livello di organizzazione per consentire e bloccare i domini.<br><br>Visualizzare [le impostazioni del dominio di SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e [le impostazioni del dominio di Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Consenti la condivisione esterna solo agli utenti di gruppi di sicurezza specifici|Specifica i gruppi di sicurezza in grado di condividere i siti, le cartelle e i file di SharePoint esternamente.|Questa impostazione non impedisce ai proprietari del team di condividere i team esternamente. Gli utenti del team hanno accesso al sito di SharePoint associato.||
|Impostazioni di condivisione siti di SharePoint|Determina gli utenti che possono condividere il sito direttamente al di fuori dell'appartenenza del team. Questa impostazione è configurata dal proprietario del sito o del team.|Questa impostazione non influisce direttamente sul team, ma può consentire agli utenti di essere aggiunti a un sito e di non avere accesso al team stesso o ad altre risorse dei team.|Prendere in considerazione l'utilizzo di questa impostazione per limitare direttamente la condivisione del sito e gestire l'accesso al sito tramite il team.|
|Consenti agli utenti di creare siti dalla pagina iniziale di SharePoint e OneDrive|Specifica se gli utenti possono creare nuovi siti di SharePoint.|Se questa impostazione è disattivata, gli utenti possono comunque creare siti del team connessi al gruppo creando un team.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Effetti delle impostazioni dei gruppi nei team

|Impostazione gruppi di Microsoft 365|Descrizione|Effetto sui team|Consiglio|
|:---------------------------|:----------|:--------------|:-------------|
|Criteri di denominazione|Specifica i prefissi e i suffissi dei nomi di gruppo e le parole bloccate per la creazione di gruppi|I criteri vengono applicati per gli utenti che creano team.||
|Accesso Guest del gruppo|Specifica se gli utenti esterni all'organizzazione possono essere aggiunti ai gruppi.|Se le impostazioni di condivisione Guest gruppi o teams sono disattivate, il team non può essere condiviso con gli utenti.|Quando si modificano le impostazioni di condivisione Guest, controllare le impostazioni per Team, gruppi e il sito di SharePoint associato al team.<br><br> Vedere [collaborare con gli ospiti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Creazione di gruppi per gruppo di sicurezza|I gruppi possono essere creati solo dai membri di un gruppo di sicurezza specifico.|Gli utenti che non sono membri del gruppo di sicurezza non saranno in grado di creare un team.|Verificare che il processo di richiesta di un gruppo includa le istruzioni per la richiesta di un team o di un sito di SharePoint.|
|Criteri di scadenza del gruppo|Specifica un periodo di tempo dopo il quale i gruppi che non vengono utilizzati attivamente verranno eliminati automaticamente.|Quando il gruppo viene eliminato, vengono eliminati anche il team e il sito di SharePoint associato. Il contenuto protetto dai criteri di conservazione viene mantenuto.|Utilizzare i criteri di scadenza per evitare l'espansione di Team, gruppi e siti inutilizzati.|

## <a name="related-topics"></a>Argomenti correlati

[Collaborare con utenti esterni all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Gestire la creazione di siti in SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
