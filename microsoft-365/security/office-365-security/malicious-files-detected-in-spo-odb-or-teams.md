---
title: Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Per informazioni su come eseguire le operazioni su tali file, vedere l'articolo relativo alla visualizzazione dei file dannosi rilevati in SharePoint, OneDrive o teams.
ms.openlocfilehash: 95f497c5be16d1ba1d4fa9fc57f0dd9650450414
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635401"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams

[Office 365 ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) protegge l'organizzazione da file dannosi nelle raccolte documenti e nei siti del team. Quando viene rilevato un file dannoso, il file viene bloccato in modo che nessuno possa aprirlo, copiarlo, spostarlo o condividerlo fino a quando non vengono intraprese altre azioni da parte del team di sicurezza dell'organizzazione. Leggere questo articolo per scoprire come visualizzare le informazioni sui file rilevati e le azioni da intraprendere. 

Per eseguire le attività descritte in questo articolo, è necessario disporre delle [autorizzazioni necessarie per il &amp; Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visualizzare i report con informazioni sui file rilevati

Per visualizzare lo stato e informazioni dettagliate sui file che sono stati rilevati da Office 365 ATP, è possibile utilizzare il rapporto sullo stato di protezione dalle minacce.
  
1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com), scegliere **segnala** \> **Dashboard** \> **lo stato di protezione delle minacce**del dashboard.
    
2. Nell'angolo in alto a destra del report, scegliere **Visualizza dettagli tabella**.
    
3. Visualizzare l'elenco dei file che sono stati rilevati nel report.
    
4. Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluse le azioni eseguite, il nome del file, il percorso del file e altro ancora.
    
5. Scegliere la scheda **analisi avanzata** per visualizzare le informazioni, ad esempio il comportamento osservato e i dettagli dell'analisi. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Visualizzare ed eseguire azioni sui file in quarantena

1. Nel centro sicurezza &amp; e conformità, scegliere **quarantena** **Revisione** \> di **Threat Management** \> . È anche possibile passare direttamente a [https://protection.office.com/quarantine](https://protection.office.com/quarantine).
    
2. Nell'angolo in alto a sinistra, cambiare il menu a discesa dai **messaggi di posta elettronica** ai **file**. Se l'elenco dei risultati include troppi elementi, utilizzare la funzionalità di **filtro** per restringere la selezione.
    
3. Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluso l'URL del file.
    
4. Scegliere un'azione disponibile.
    
    - Scegliere **Release file** per sbloccare il file. 

      Selezionare **Invia rapporto a Microsoft** per segnalare il file come falso positivo a Microsoft. 

    - Scegliere **Download file** per analizzare ulteriormente il file. 

    - Scegliere **Rimuovi dalla quarantena** per rimuovere il file dall'elenco degli elementi in quarantena. Se si sceglie questa opzione, è necessario eliminare anche il file dalla rispettiva raccolta in SharePoint Online, OneDrive for business o Microsoft teams. Questa opzione non sblocca un file dall'apertura o dalla condivisione. 
    
5. Fare clic su **Chiudi** per chiudere i dettagli per un elemento selezionato. 
  
  

