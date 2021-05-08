---
title: Microsoft 365 Report nell'interfaccia di amministrazione - OneDrive for Business attività
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Ottenere il OneDrive di utilizzo per l'organizzazione e conoscere l'attività di ogni OneDrive utente, il numero di file condivisi e l'utilizzo dello spazio di archiviazione.
ms.openlocfilehash: 8257d8e85819ff5edae96967fd4a687be3a903a1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244093"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365 Report nell'interfaccia di amministrazione - OneDrive for Business attività

Il dashboard Microsoft 365 **report mostra** la panoramica dell'attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di tutti gli utenti con licenza per l'uso di OneDrive osservandone l'interazione con i file in OneDrive. È anche utile per comprendere il livello di collaborazione in corso osservando il numero di file condivisi.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Come ottenere il report Attività di OneDrive?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella home page del dashboard fai clic sul **pulsante** Visualizza altro nella OneDrive dashboard.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretare il report sull'attività di OneDrive for Business

È possibile visualizzare le attività nel report OneDrive scegliendo la **scheda** Attività.<br/>![Microsoft 365 report - Microsoft OneDrive attività.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![OneDrive attività - Scegliere le colonne](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

È inoltre possibile esportare i dati del report in Excel .csv file selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Username  <br/> |Nome utente del proprietario dell'account OneDrive utente.  <br/> |
|Data ultima attività (UTC)  <br/> |Data più recente in cui è stata eseguita un'attività di file OneDrive'account per l'intervallo di date selezionato. . Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.  <br/> |
|File visualizzati o modificati  <br/> |Numero di file caricati, scaricati, modificati o visualizzati dall'utente.   <br/> |
|File sincronizzati  <br/> |Numero di file sincronizzati dal dispositivo locale di un utente all'account OneDrive utente. <br/> |
|File condivisi internamente  <br/> | Il numero di file che sono stati condivisi con gli utenti all'interno dell'organizzazione o con gli utenti all'interno di gruppi (che potrebbero includere utenti esterni).  <br/> |
|File condivisi esternamente  <br/> |Numero di file condivisi con utenti esterni all'organizzazione. <br/>|
|Eliminato  <br/> | Ciò indica che la licenza dell'utente è stata rimossa.  <br/> NOTA: l'attività per un utente eliminato continuerà a essere visualizzata in un report, purché sia stato concesso in licenza in un determinato momento durante il periodo di tempo selezionato. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.  <br/> |
|Data eliminazione  <br/> |Data in cui è stata rimossa la licenza dell'utente. <br/>|
|Prodotto assegnato  <br/> |Il Microsoft 365 prodotti concessi in licenza all'utente.|
|||