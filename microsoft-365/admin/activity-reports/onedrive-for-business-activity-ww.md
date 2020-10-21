---
title: Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di OneDrive for business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Ottenere il report di utilizzo di OneDrive per l'organizzazione e conoscere l'attività di ogni utente di OneDrive, il numero di file condivisi e l'utilizzo dello spazio di archiviazione.
ms.openlocfilehash: e83ec835f0aa4a453f14a44d9582edcfd5aa6433
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649812"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di OneDrive for business

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di tutti gli utenti con licenza per l'uso di OneDrive osservandone l'interazione con i file in OneDrive. È anche utile per comprendere il livello di collaborazione in corso osservando il numero di file condivisi.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Come ottenere il report Attività di OneDrive?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altro** sulla scheda OneDrive.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretare il report sull'attività di OneDrive for Business

È possibile visualizzare le attività nel report di OneDrive scegliendo la scheda **attività** .<br/>![Microsoft 365 Reports-report attività di Microsoft OneDrive.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività di OneDrive-scegliere colonne](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Nome utente del proprietario dell'account OneDrive.  <br/> |
|Data ultima attività (UTC)  <br/> |La data più recente in cui è stata eseguita un'attività sui file nell'account OneDrive per l'intervallo di date selezionato. . Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.  <br/> |
|File visualizzati o modificati  <br/> |Il numero di file che l'utente ha caricato, scaricato, modificato o visualizzato.   <br/> |
|File sincronizzati  <br/> |Il numero di file che sono stati sincronizzati dal dispositivo locale di un utente all'account OneDrive. <br/> |
|File condivisi internamente  <br/> | Il numero di file che sono stati condivisi con gli utenti all'interno dell'organizzazione o con utenti all'interno di gruppi (che possono includere utenti esterni).  <br/> |
|File condivisi esternamente  <br/> |Il numero di file che sono stati condivisi con utenti esterni all'organizzazione. <br/>|
|Eliminato  <br/> | Ciò indica che la licenza dell'utente è stata rimossa.  <br/> Nota: l'attività per un utente eliminato continuerà a essere visualizzata in un report a condizione che sia stata concessa una licenza in un determinato momento durante il periodo di tempo selezionato. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.  <br/> |
|Data di eliminazione  <br/> |La data in cui la licenza dell'utente è stata rimossa. <br/>|
|Prodotto assegnato  <br/> |Prodotti Microsoft 365 che sono concessi in licenza all'utente.|
|||