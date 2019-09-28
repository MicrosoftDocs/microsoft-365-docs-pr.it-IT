---
title: Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: f2271ec7822efd442474aa322535da26d42788db
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306110"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams

[Office 365 ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) protegge l'organizzazione da file dannosi nelle raccolte documenti e nei siti del team. Quando viene rilevato un file dannoso, il file viene bloccato in modo che nessuno possa aprirlo, copiarlo, spostarlo o condividerlo fino a quando non vengono intraprese altre azioni da parte del team di sicurezza dell'organizzazione. Leggere questo articolo per scoprire come visualizzare le informazioni sui file rilevati e le azioni da intraprendere. 

Per eseguire le attività descritte in questo articolo, è necessario disporre delle [autorizzazioni necessarie per il Centro sicurezza &amp; e conformità di Office 365](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visualizzare i report con informazioni sui file rilevati

Per visualizzare lo stato e informazioni dettagliate sui file che sono stati rilevati da Office 365 ATP, è possibile utilizzare il rapporto sullo stato di protezione dalle minacce.
  
1. Nel [Centro sicurezza &amp; e conformità di Office 365](https://protection.office.com)scegliere **segnala** \> **** \> **lo stato di protezione delle minacce**del dashboard.
    
2. Nell'angolo in alto a destra del report, scegliere **Visualizza dettagli tabella**.
    
3. Visualizzare l'elenco dei file che sono stati rilevati nel report.
    
4. Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluse le azioni eseguite, il nome del file, il percorso del file e altro ancora.
    
5. Scegliere la scheda **analisi avanzata** per visualizzare le informazioni, ad esempio il comportamento osservato e i dettagli dell'analisi. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Visualizzare ed eseguire azioni sui file in quarantena

1. &amp; Nel centro sicurezza e conformità di Office 365 scegliere **quarantena**di **Revisione** \> della **gestione** \> delle minacce. È anche possibile passare direttamente a [https://protection.office.com/quarantine](https://protection.office.com/quarantine).
    
2. Nell'angolo in alto a sinistra, cambiare il menu a discesa dai **messaggi di posta elettronica** ai **file**. Se l'elenco dei risultati include troppi elementi, utilizzare la funzionalità di **filtro** per restringere la selezione.
    
3. Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluso l'URL del file.
    
4. Scegliere un'azione disponibile.
    
  - Scegliere **Release file** per sbloccare il file. 
    
    Selezionare **Invia rapporto a Microsoft** per segnalare il file come falso positivo a Microsoft. 
    
  - Scegliere **Download file** per analizzare ulteriormente il file. 
    
  - Scegliere **Rimuovi dalla quarantena** per rimuovere il file dall'elenco degli elementi in quarantena. Se si sceglie questa opzione, è necessario eliminare anche il file dalla rispettiva raccolta in SharePoint Online, OneDrive for business o Microsoft teams. Questa opzione non sblocca un file dall'apertura o dalla condivisione. 
    
5. Fare clic su **Chiudi** per chiudere i dettagli per un elemento selezionato. 
  
  

