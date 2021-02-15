---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di Dynamics 365 Customer Voice
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
description: Informazioni su come ottenere un report attività di Microsoft Dynamics 365 Customer Voice usando il dashboard report di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988955"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di Dynamics 365 Customer Voice

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di ogni utente con licenza per l'uso di Microsoft Dynamics 365 Customer Voice esaminando le interazioni con Dynamics 365 Customer Voice. Consente inoltre di comprendere il livello di collaborazione in corso esaminando il numero di sondaggi pro creati e di sondaggi pro a cui gli utenti hanno risposto. 
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Come accedere al report attività di Dynamics 365 Customer Voice

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Dalla home page del dashboard, fare clic **sul** pulsante Visualizza altro nella scheda Voce cliente di Dynamics 365.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretare il report attività di Dynamics 365 Customer Voice

È possibile visualizzare le attività nel report Di Dynamics 365 Customer Voice scegliendo la **scheda** Attività.<br/>![Report di Microsoft 365 - Report attività di Microsoft Dynamics 365 Customer Voice.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività di Dynamics 365 Customer Voice - scegliere le colonne](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Forms.  <br/> |
|Data ultima attività (UTC)  <br/> |Data più recente in cui l'utente ha eseguito un'attività del modulo per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/>In questo modo la tabella verrà filtrata in modo da visualizzare i dati sulle attività dei file solo per gli utenti che hanno eseguito l'attività in tale giorno specifico.  <br/> |
|Numero di sondaggi creati  <br/> |Numero di sondaggi creati dall'utente.   <br/> |
|Numero di risposte al sondaggio  <br/> |Numero di risposte dei risponditori a cui è stato distribuito il sondaggio.|
|||