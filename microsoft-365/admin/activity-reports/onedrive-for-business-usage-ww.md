---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo di OneDrive for business
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
description: "Ottenere il report sull'utilizzo di OneDrive for business per conoscere il numero totale di file e di archiviazione utilizzati nell'organizzazione. "
ms.openlocfilehash: 3855c7d06d202ee4d0590fcf5b8ca758d8120133
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649807"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo di OneDrive for business

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, la scheda OneDrive sul dashboard offre una panoramica generale del valore ricevuto da OneDrive for Business per quanto riguarda il numero totale di file e di risorse di archiviazione usati in tutti gli account nell'organizzazione. È quindi possibile analizzare questo valore per comprendere le tendenze degli account di OneDrive attivi, il numero di file con cui interagiscono gli utenti e le risorse di archiviazione usate. Vengono visualizzati anche dettagli per i singoli account di OneDrive.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Come ottenere il report Attività di OneDrive?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altro** sulla scheda OneDrive.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretare il report sull'utilizzo di OneDrive

È possibile visualizzare l'utilizzo nel report OneDrive scegliendo la scheda **utilizzo** .<br/>![Microsoft 365 Reports-report sull'utilizzo di Microsoft OneDrive.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report sull'utilizzo di OneDrive-scegliere colonne](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|URL  <br/> |L'indirizzo Web per l'OneDrive dell'utente. <br/> |
|Eliminato  <br/> |Lo stato di eliminazione di OneDrive. Un account viene contrassegnato come eliminato dopo almeno 7 giorni.  <br/> |
|Proprietario  <br/> |Il nome utente dell'amministratore principale di OneDrive.   <br/> |
|Nome dell'entità proprietario  <br/> |L'indirizzo di posta elettronica del proprietario del OneDrive. <br/> |
|Data ultima attività (UTC)  <br/> | La data più recente in cui è stata eseguita un'attività di file in OneDrive. Se in OneDrive non ci sono state attività sui file, il valore sarà vuoto.  <br/> |
|File  <br/> |Il numero di file in OneDrive. <br/>|
|File attivi  <br/> | Il numero di file attivi entro il periodo di tempo.<br/> Nota: se i file sono stati rimossi durante il periodo di tempo specificato per il report, il numero di file attivi visualizzati nel report potrebbe essere superiore al numero corrente di file in OneDrive. >  Gli utenti eliminati continueranno a essere visualizzati nei report per 180 giorni.  <br/> |
|Spazio di archiviazione utilizzato (MB)  <br/> |La quantità di spazio di archiviazione utilizzata da OneDrive in MB. |
|||