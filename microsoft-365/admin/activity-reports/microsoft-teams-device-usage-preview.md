---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo dei dispositivi di Microsoft Teams
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
description: Per informazioni dettagliate sulle app di Microsoft Teams usate nell'organizzazione, è possibile ottenere il report sull'utilizzo delle app di Microsoft Teams dai report di Microsoft 365.
ms.openlocfilehash: 54219b060767193e711c839d25780dd3b4a618bf
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233435"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo dei dispositivi di Microsoft Teams

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Utilizzo app Microsoft Teams è possibile ottenere informazioni approfondite sulle app di Microsoft Teams usate nell'organizzazione.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Come accedere al report Utilizzo app Microsoft Teams

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Dalla home page del dashboard, fare clic sul pulsante Visualizza **altro** nella scheda attività di Microsoft Teams.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretare il report Utilizzo app Microsoft Teams

È possibile visualizzare l'uso del dispositivo nel report di Teams scegliendo la **scheda Uso del** dispositivo.<br/>![Report di Microsoft 365 - Utilizzo dei dispositivi di Microsoft Teams.](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report dei dispositivi degli utenti di Teams - scegliere le colonne](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 

Il report **Utilizzo di dispositivi Microsoft Teams** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Nome visualizzato dell'utente.  <br/> |
|Windows  <br/> |Selezionato se l'utente era attivo nel client desktop di Teams in un computer basato su Windows.  <br/> |
|Mac  <br/> |Selezionato se l'utente era attivo nel client desktop di Teams in un computer macOS.  <br/> |
|iOS  <br/> |Selezionato se l'utente era attivo nel client per dispositivi mobili di Teams per iOS.  <br/> |
|Telefono Android  <br/> | Selezionato se l'utente era attivo nel client per dispositivi mobili di Teams per Android.  <br/> |
|Sistema operativo Chrome  <br/> |Selezionato se l'utente era attivo nel client desktop di Teams in un computer ChromeOS.|
|Linux  <br/> | Selezionato se l'utente era attivo nel client desktop di Teams in un computer Linux.  <br/> |
|Web  <br/> |Selezionato se l'utente era attivo nel client Web di Teams nei dispositivi.|
|Data ultima attività (UTC)  <br/> |L'ultima data (UTC) in cui l'utente ha partecipato a un'attività di Teams.  <br/> |
|È concesso in licenza|Selezionato se l'utente ha la licenza per l'uso di Teams.|
|||