---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo del sito di SharePoint
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
description: Ottenere il report sull'utilizzo del sito di SharePoint per conoscere il numero di file archiviati dagli utenti nei siti di SharePoint, il numero di utilizzi attivi e lo spazio di archiviazione totale utilizzato.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649827"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo del sito di SharePoint

In qualità di amministratore Microsoft 365, nel dashboard dei **report** viene illustrata la panoramica delle attività in vari prodotti dell'organizzazione. Consente di eseguire il drill-down per ottenere informazioni più dettagliate sulle attività specifiche di ogni prodotto. È possibile, ad esempio, ottenere una visualizzazione generale del valore ricavato da SharePoint in termini di numero totale di file archiviati dagli utenti nei siti di SharePoint, numero di file attivamente in uso e spazio di archiviazione utilizzato in tutti questi siti. È quindi possibile eseguire il drill-down del report sull'utilizzo dei siti di SharePoint per conoscere le tendenze e i dettagli a livello di sito. 
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.
I rapporti Microsoft 365 nell'interfaccia di amministrazione non sono supportati per i tenant GCC High e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Come ottenere il report sull'utilizzo del sito di SharePoint

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altro** sulla scheda SharePoint.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretare il report sull'utilizzo del sito di SharePoint

È possibile visualizzare l'utilizzo del sito nel report di SharePoint scegliendo la scheda **utilizzo sito** .<br/>![Microsoft 365 Reports-report sull'utilizzo del sito di Microsoft SharePoint.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report sull'utilizzo del sito di SharePoint-scegliere colonne](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|URL del sito  <br/> |URL completo del sito. <br/> |
|Eliminato  <br/> |Lo stato di eliminazione del sito. Occorrono almeno sette giorni affinché un account sia contrassegnato come eliminato.  <br/> |
|Proprietario del sito  <br/> |Il nome utente del proprietario principale del sito.   <br/> |
|Nome dell'entità del proprietario del sito  <br/> |L'indirizzo di posta elettronica del proprietario del sito. <br/> |
|Data ultima attività (UTC)  <br/> | La data dell'ultima volta in cui è stata rilevata l'attività del file oppure è stata visualizzata una pagina nel sito.  <br/> |
|File  <br/> |Il numero di file nel sito. <br/>|
|File attivi  <br/> | Il numero di file attivi nel sito.<br/> Nota: se i file sono stati rimossi durante il periodo di tempo specificato per il report, il numero di file attivi visualizzati nel report potrebbe essere superiore al numero corrente di file nel sito.  <br/> |
|Spazio di archiviazione utilizzato (MB)  <br/> |La quantità di spazio di archiviazione attualmente in uso nel sito.  <br/>|
|Spazio di archiviazione allocato (MB)  <br/> |La quantità massima di spazio di archiviazione allocata per il sito.  <br/>|
|Visualizzazioni pagina  <br/> |Il numero di volte in cui le pagine sono state visualizzate nel sito.  <br/>|
|Pagine visitate  <br/> |Il numero di pagine univoche visitate nel sito.  <br/>|
|Modello Web radice  <br/> |Modello utilizzato per la creazione del sito.  <br/> Nota: se si desidera filtrare i dati in base a diversi tipi di sito, esportare i dati e utilizzare la colonna modello Web radice. |
|||