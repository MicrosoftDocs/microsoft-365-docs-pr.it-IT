---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di Microsoft 365
ms.author: sirkkuw
author: sirkkuw
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
description: Informazioni su come ottenere un report di Microsoft 365 Apps for usage usando il dashboard report di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 0c30cee0c1abd76553d3adfebebb8fe38e92c56a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611918"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di Microsoft 365

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md).

 Ad esempio, è possibile comprendere l'attività di ogni utente concesso in licenza per l'uso delle app di Microsoft 365 Apps esaminando la propria attività tra le app e il modo in cui vengono utilizzati nelle diverse piattaforme.


 > [!NOTE]
 > Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint o Skype for Business.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Come accedere al report sull'utilizzo di Microsoft 365 Apps

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Dalla home page del dashboard, fare clic sul pulsante Visualizza **altro** nella scheda Utenti attivi - App di Microsoft 365.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretare il report sull'utilizzo di Microsoft 365 Apps

È possibile visualizzare l'attività delle app di Microsoft 365 dell'utente esaminando i grafici **Utenti** **e** Piattaforma.

![Report sull'utilizzo di Microsoft 365 Apps](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Elemento|Descrizione|
 |:-----|:-----|
 |1. <br/> |Il report sull'utilizzo di **Microsoft 365 Apps** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report). <br/> |
 |2. <br/> |I dati in ogni report in genere riguardano fino agli ultimi sette giorni. <br/> |
 |3. <br/> |La **visualizzazione** Utenti mostra la tendenza del numero di utenti attivi per ogni app: Outlook, Word, Excel, PowerPoint, OneNote e Teams. Gli "utenti attivi" sono gli utenti che eseguono qualsiasi azione intenzionale all'interno di queste app. <br/> |
 |4. <br/> |La **visualizzazione** Piattaforme mostra la tendenza degli utenti attivi in tutte le app per ogni piattaforma: Windows, Mac, Web e Mobile. <br/> |
 |5.<br/>|Nel grafico **Utenti** l'asse Y è il numero di utenti attivi univoci per la rispettiva app. Nel grafico **Piattaforme,**   l'asse Y è il numero di utenti univoci per la rispettiva piattaforma. L'asse X in entrambi i grafici è la data in cui un'app è stata usata in una determinata piattaforma.<br/>|
 6.<br/>|È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio,  nel grafico Utenti selezionare Outlook, Word, Excel, PowerPoint, OneDrive o Teams per visualizzare solo le informazioni relative a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia sottostante.|
 |7.<br/>|La tabella visualizza un'analisi dei dati a livello di utente. È possibile aggiungere o rimuovere colonne in una tabella. <br/><br/>**Il nome** utente è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Apps.<br><br/>**La data dell'ultima attivazione (UTC)** è l'ultima data in cui l'utente ha attivato l'abbonamento a Microsoft 365 Apps.<br/><br/>**Data ultima attività (UTC)** è la data più recente in cui un'attività intenzionale è stata eseguita dall'utente. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/><br/>Le altre colonne identificano se l'utente era attivo nella piattaforma per l'app (all'interno di Microsoft 365 Apps) nel periodo selezionato. |
 |8.<br/>|Selezionare **l'icona Scegli** colonne per aggiungere o rimuovere colonne dal report.|
 |9.<br/>|È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** In questo modo vengono esportati i dati per tutti gli utenti e è possibile eseguire semplici operazioni di aggregazione, ordinamento e filtro per un'ulteriore analisi. Se sono presenti meno di 100 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se sono presenti più di 100 utenti, per filtrare e ordinare, sarà necessario esportare i dati.|
