---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-gruppi Microsoft 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Ottenere un rapporto sui gruppi di Microsoft 365 per conoscere i gruppi e le relative attività.
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611948"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-gruppi Microsoft 365

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel rapporto sui gruppi di Microsoft 365, è possibile ottenere informazioni approfondite sull'attività dei gruppi nell'organizzazione e vedere quanti gruppi vengono creati e utilizzati.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
  
## <a name="how-to-get-to-the-groups-report"></a>Come accedere al report gruppi

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altre informazioni** sulle app Active users-Microsoft 365 o sulla scheda Active users-Microsoft 365 Services per accedere alla pagina di report di Office 365.
  
## <a name="interpret-the-groups-report"></a>Interpretare il report gruppi

È possibile visualizzare le attivazioni nel report di Office 365 scegliendo la scheda **attività gruppi** .<br/>![Microsoft 365 Reports-attività sui gruppi di Microsoft Office 365.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività gruppi di Office 365-scegliere colonne](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 

|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome del gruppo  <br/> |Nome del gruppo.  <br/> |
|Eliminato  <br/> |Numero di gruppi eliminati. Se il gruppo viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con questo flag impostato su true.  <br/> |
|Proprietario del gruppo  <br/> |Nome del proprietario del gruppo.  <br/> |
|Data ultima attività (UTC)  <br/> |La data più recente in cui un messaggio è stato ricevuto dal gruppo. Si tratta dell'ultima data in cui si è verificata un'attività in una conversazione di posta elettronica, in Yammer o nel sito.  <br/> |
|Tipo  <br/> |Tipo di gruppo. Può essere privato o pubblico.  <br/> |
|Messaggi di posta elettronica ricevuti in Exchange  <br/> |Il numero di messaggi ricevuti dal gruppo.|
|Messaggi di posta elettronica in Exchange (totale)  <br/> |Il numero totale di elementi nella cassetta postale del gruppo.  <br/> |
|Archiviazione delle cassette postali utilizzata per Exchange (MB)  <br/> |Lo spazio di archiviazione utilizzato dalla cassetta postale del gruppo. <br/>|
|File di SharePoint (totale)  <br/> |Il numero di file archiviati nei siti del gruppo di SharePoint.  <br/> |
|File di SharePoint (attivo)  <br/> |Il numero di file nel sito del gruppo di SharePoint che sono stati attivati (visualizzati o modificati, sincronizzati, condivisi internamente o esternamente) durante il periodo di riferimento.  <br/> |
|Archiviazione totale del sito utilizzata per SharePoint (MB)  <br/> |La quantità di spazio di archiviazione in MB utilizzata durante il periodo di riferimento.  <br/> |
|Messaggi in Yammer (postato)  <br/> |Il numero di messaggi inseriti nel gruppo di Yammer nel periodo di riferimento.  <br/> |
|Messaggi in Yammer (lettura)  <br/> |Il numero di conversazioni lette nel gruppo Yammer nel periodo di riferimento.  <br/> |
|Messaggi in Yammer (liked)  <br/> |Il numero di messaggi graditi nel gruppo Yammer nel periodo di riferimento.  <br/> |
|Membri  <br/> |Il numero di membri del gruppo.  <br/> |
|Membri esterni |Il numero di utenti esterni nel gruppo.|
|||