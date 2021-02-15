---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di SharePoint
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
description: Ottenere il report sull'utilizzo delle attività di SharePoint per conoscere l'attività di ogni utente di SharePoint, il numero di file condivisi e l'utilizzo dello spazio di archiviazione.
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649832"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di SharePoint

In qualità di amministratore di Microsoft 365, il **dashboard** Report mostra la panoramica delle attività in vari prodotti dell'organizzazione. Consente di eseguire il drill-down per ottenere informazioni più dettagliate sulle attività specifiche di ogni prodotto. Consultare i report attività nell'interfaccia di amministrazione di [Microsoft 365.](activity-reports.md)
  
Ad esempio, è possibile comprendere l'attività di tutti gli utenti con licenza per l'uso di SharePoint osservandone l'interazione con i file. È anche utile per comprendere il livello di collaborazione in corso osservando il numero di file condivisi.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Come si torna al report attività in SharePoint?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Dalla home page del dashboard fare clic sul pulsante **Visualizza altro** nella scheda di SharePoint.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretare il report attività di SharePoint

È possibile visualizzare le attività nel report di SharePoint scegliendo la **scheda** Attività.<br/>![Report di Microsoft 365 - Report attività di Microsoft SharePoint.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività di SharePoint - scegliere colonne](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Indirizzo di posta elettronica dell'utente che ha eseguito l'attività nel sito di SharePoint.  <br/> |
|Data ultima attività (UTC)  <br/> |Ultima data in cui è stata eseguita un'attività su file o visitata una pagina per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.  <br/> |
|File visualizzati o modificati  <br/> |Numero di file caricati, scaricati, modificati o visualizzati dall'utente.   <br/> |
|File sincronizzati  <br/> |Numero di file sincronizzati dal dispositivo locale di un utente al sito di SharePoint. <br/> |
|File condivisi internamente  <br/> | Il numero di file condivisi con gli utenti all'interno dell'organizzazione o con gli utenti all'interno di gruppi (che potrebbero includere utenti esterni).  <br/> |
|File condivisi esternamente  <br/> |Numero di file condivisi con utenti esterni all'organizzazione. <br/>|
|Pagine visitate  <br/> |Visite alle pagine univoche dell'utente. <br/>|
|Eliminato  <br/> | Ciò indica che la licenza dell'utente è stata rimossa.  <br/>  **NOTA:** L'attività di un utente eliminato continuerà a essere visualizzata nel report, purché gli sia stata concessa una licenza in un determinato momento durante il periodo di tempo selezionato. La colonna Eliminati consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.  <br/> |
|Data eliminazione  <br/> |Data in cui è stata rimossa la licenza dell'utente. <br/>|
|Prodotto assegnato  <br/> |I prodotti Microsoft 365 concessi in licenza all'utente.|
|||