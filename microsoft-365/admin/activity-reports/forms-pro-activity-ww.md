---
title: Microsoft 365 report nell'interfaccia di amministrazione-Dynamics 365 Customer Voice
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
description: Informazioni su come ottenere un report attività vocale del cliente di Microsoft Dynamics 365 utilizzando il Dashboard Microsoft 365 Reports nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988955"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365 report nell'interfaccia di amministrazione-Dynamics 365 Customer Voice

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di ogni utente concesso in licenza per l'utilizzo di Microsoft Dynamics 365 Customer Voice analizzando le interazioni con la voce del cliente Dynamics 365. Consente inoltre di comprendere il livello di collaborazione che si sta verificando analizzando il numero di sondaggi Pro creati e le indagini Pro a cui gli utenti hanno risposto. 
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Come accedere al report attività vocali del cliente Dynamics 365

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altro** sulla scheda vocale Dynamics 365 Customer.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretare il report attività vocali del cliente Dynamics 365

È possibile visualizzare le attività del rapporto vocale del cliente Dynamics 365 scegliendo la scheda **attività** .<br/>![Report Microsoft 365-report attività vocali del cliente Microsoft Dynamics 365.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività vocali del cliente Dynamics 365-scegliere colonne](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |L'indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Forms.  <br/> |
|Data ultima attività (UTC)  <br/> |La data più recente in cui l'utente ha eseguito un'attività del modulo per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/>In questo modo la tabella verrà filtrata per visualizzare i dati relativi alle attività dei file solo per gli utenti che hanno eseguito l'attività in quel giorno specifico.  <br/> |
|Numero di sondaggi creati  <br/> |Il numero di indagini create dall'utente.   <br/> |
|Numero di risposte di sondaggio  <br/> |Il numero di risposte provenienti da risponditori a cui è stato distribuito il sondaggio.|
|||