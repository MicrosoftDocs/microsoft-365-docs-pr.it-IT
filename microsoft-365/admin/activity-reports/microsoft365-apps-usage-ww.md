---
title: Microsoft 365 Report nell'interfaccia di amministrazione - Microsoft 365 Apps utilizzo
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
- MET150
- MOE150
- GEA150
description: Informazioni su come ottenere un Microsoft 365 Apps per i report di utilizzo usando il dashboard Microsoft 365 report nell'interfaccia Microsoft 365 di amministrazione.
ms.openlocfilehash: d41a1680b46709c3f41b5238d309794c68101cee
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860750"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365 Report nell'interfaccia di amministrazione - Microsoft 365 Apps utilizzo

Il dashboard Microsoft 365 **report mostra** la panoramica dell'attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md).

 Ad esempio, puoi comprendere l'attività di ogni utente con licenza per usare le app Microsoft 365 Apps esaminando le attività tra le app e il modo in cui vengono utilizzate su più piattaforme.


 > [!NOTE]
 > È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore Exchange, SharePoint o Skype for Business per visualizzare i report. Le attivazioni di computer condivisi non sono incluse in questo report.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Come accedere al report sull'Microsoft 365 Apps di utilizzo

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella home page del dashboard fai clic sul **pulsante** Visualizza altro nella scheda Utenti attivi - Microsoft 365 Apps posta elettronica.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretare il report Microsoft 365 Apps utilizzo

Puoi ottenere una visualizzazione dell'attività Microsoft 365 Apps utente esaminando i grafici **Utenti** **e** Piattaforma.

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Apps utilizzo](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Elemento|Descrizione|
 |:-----|:-----|
 |1. <br/> |Il **Microsoft 365 Apps di** utilizzo può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data di generazione del report). <br/> |
 |2. <br/> |I dati in ogni report in genere coprono fino agli ultimi due giorni. Ogni sei giorni, il report verrà aggiornato con aggiornamenti secondari per garantire la qualità dei dati. <br/> |
 |3. <br/> |La **visualizzazione** Utenti mostra la tendenza del numero di utenti attivi per ogni app: Outlook, Word, Excel, PowerPoint, OneNote e Teams. Gli "utenti attivi" sono tutti coloro che eseguono azioni intenzionali all'interno di queste app. <br/> |
 |4. <br/> |La **visualizzazione** Piattaforme mostra la tendenza degli utenti attivi in tutte le app per ogni piattaforma, Windows, Mac, Web e Mobile. <br/> |
 |5.<br/>|Nel grafico **Utenti,** l'asse Y è il numero di utenti attivi univoci per la rispettiva app. Nel grafico **Piattaforme,**   l'asse Y è il numero di utenti univoci per la rispettiva piattaforma. L'asse X in entrambi i grafici è la data in cui un'app è stata usata in una determinata piattaforma.<br/>|
 6.<br/>|È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio,  nel grafico Utenti selezionare Outlook, Word, Excel, PowerPoint, OneDrive o Teams per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella griglia sottostante.|
 |7.<br/>|La tabella visualizza un'analisi dei dati a livello di utente. È possibile aggiungere o rimuovere colonne in una tabella.  <br/><br/>**Nome utente** è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività Microsoft Apps.<br><br/>**Data ultima attivazione (UTC)** è l'ultima data in cui l'utente ha attivato la sottoscrizione Microsoft 365 Apps abbonamento.<br/><br/>**Data ultima attività (UTC)** è la data più recente in cui un'attività intenzionale è stata eseguita dall'utente. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/><br/>Le altre colonne identificano se l'utente era attivo nella piattaforma per l'app (entro Microsoft 365 Apps) nel periodo selezionato. |
 |8.<br/>|Selezionare **l'icona Scegli** colonne per aggiungere o rimuovere colonne dal report.|
 |9.<br/>|È inoltre possibile esportare i dati del report in Excel .csv file selezionando il **collegamento Esporta.** In questo modo vengono esportati i dati per tutti gli utenti e è possibile eseguire semplici operazioni di aggregazione, ordinamento e filtro per un'ulteriore analisi. Se si dispone di meno di 100 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se si dispone di più di 100 utenti, per filtrare e ordinare, sarà necessario esportare i dati.|
