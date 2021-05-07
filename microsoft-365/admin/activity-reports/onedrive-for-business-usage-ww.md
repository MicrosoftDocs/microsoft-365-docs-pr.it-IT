---
title: Microsoft 365 Report nell'interfaccia di amministrazione - OneDrive for Business utilizzo
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
description: "Ottenere informazioni OneDrive for Business report di utilizzo sul numero totale di file e spazio di archiviazione utilizzato nell'organizzazione. "
ms.openlocfilehash: 20b9ce6aff01942c23c0f8a98234432ea54d5953
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242049"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 Report nell'interfaccia di amministrazione - OneDrive for Business utilizzo

Il dashboard Microsoft 365 **report mostra** la panoramica dell'attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, la scheda OneDrive sul dashboard offre una panoramica generale del valore ricevuto da OneDrive for Business per quanto riguarda il numero totale di file e di risorse di archiviazione usati in tutti gli account nell'organizzazione. È quindi possibile analizzare questo valore per comprendere le tendenze degli account di OneDrive attivi, il numero di file con cui interagiscono gli utenti e le risorse di archiviazione usate. Vengono visualizzati anche dettagli per i singoli account di OneDrive.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Come ottenere il report Attività di OneDrive?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella home page del dashboard fai clic sul **pulsante** Visualizza altro nella OneDrive dashboard.
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretare il report sull'utilizzo di OneDrive

È possibile visualizzare l'utilizzo nel report OneDrive scegliendo la **scheda** Utilizzo.<br/>![Microsoft 365 report - Microsoft OneDrive utilizzo.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![OneDrive utilizzo : scegliere le colonne](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

È inoltre possibile esportare i dati del report in Excel .csv file selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|URL  <br/> |L'indirizzo Web dell'utente OneDrive. <br/> |
|Eliminato  <br/> |Lo stato di eliminazione del OneDrive. Un account viene contrassegnato come eliminato dopo almeno 7 giorni.  <br/> |
|Proprietario  <br/> |Nome utente dell'amministratore principale del OneDrive.   <br/> |
|Nome dell'entità proprietario  <br/> |L'indirizzo di posta elettronica del proprietario del OneDrive. <br/> |
|Data ultima attività (UTC)  <br/> | Data più recente in cui è stata eseguita un'attività di file nel OneDrive. Se in OneDrive non ci sono state attività sui file, il valore sarà vuoto.  <br/> |
|File  <br/> |Numero di file nell'OneDrive. <br/>|
|File attivi  <br/> | Numero di file attivi entro il periodo di tempo.<br/> NOTA: se i file sono stati rimossi durante il periodo di tempo specificato per il report, il numero di file attivi visualizzati nel report potrebbe essere superiore al numero corrente di file nel OneDrive. >  Gli utenti eliminati continueranno a essere visualizzati nei report per 180 giorni.  <br/> |
|Archiviazione utilizzato (MB)  <br/> |Quantità di spazio di archiviazione OneDrive in MB. |
|||