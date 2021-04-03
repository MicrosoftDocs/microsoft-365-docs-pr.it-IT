---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività dei moduli
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
description: Informazioni su come ottenere un report attività di Microsoft Forms utilizzando il dashboard report di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: ce1109c6d6d626079794085b4dc742829841d06e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579675"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività dei moduli

Il **dashboard** dei report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di ogni utente con licenza per l'utilizzo di Microsoft Forms esaminando l'interazione con i moduli. Consente inoltre di comprendere il livello di collaborazione in corso esaminando il numero di moduli creati e di moduli a cui l'utente ha risposto.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Come accedere al report attività Moduli

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. **Nell'elenco a discesa Selezionare un report** selezionare Attività  \> **moduli.**

## <a name="interpret-the-forms-activity-report"></a>Interpretare il report attività delle maschere

È possibile visualizzare l'attività dei moduli dell'utente esaminando i grafici **Attività** **e** Utenti. 

![Report attività moduli](../../media/adminformsactivity.png)

|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il **report attività** Moduli può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data di generazione del report).  <br/> |
|2.  <br/> |I dati in ogni report in genere coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |La **visualizzazione** Utenti consente di comprendere la tendenza del numero di utenti di moduli attivi. Un utente viene considerato attivo se ha eseguito un'attività attorno a un modulo (creazione, modifica, visualizzazione e così via) o ha risposto a un modulo entro un periodo di tempo specifico.  <br/> |
|4.  <br/> |La **visualizzazione** Attività consente di comprendere la tendenza del numero di utenti attivi. Un utente viene considerato attivo se ha eseguito un'attività sui file, ad esempio salvataggio, sincronizzazione, modifica o condivisione, o ha visitato una pagina in un intervallo di tempo specificato.<br/> NOTA: un'attività può verificarsi più volte per un singolo modulo, ma verrà conteggiato come un solo modulo attivo. Ad esempio, è possibile creare un modulo e continuare a modificare lo stesso modulo più volte in un periodo di tempo specificato, ma verrà conteggiato come un unico modulo. Tuttavia, se un utente ha inviato più risposte per lo stesso modulo, ogni risposta sarà comunque una risposta individuale e quindi verrà conteggiata più volte. <br/> |
|5.<br/>|Nel grafico **Utenti,** l'asse Y è il numero di utenti univoci. L'asse X è la data in cui sono attivi gli utenti univoci. Le legende sono:<br/><br/>**I progettisti** significano che l'utente ha creato o modificato un modulo.<br/>**Risponditori** significa che l'utente ha inviato risposte a un modulo.<br/> **Utenti totali** significa chiunque nell'azienda sia stato progettista o risponditore.<br/><br/> Nel grafico **Attività,** l'asse Y è il numero di forme o risposte univoche. L'asse X è la data in cui si è verificata l'attività del modulo o della risposta. Le legende sono:<br/><br/>**I moduli** creati sono il numero di moduli univoci creati dagli utenti.<br/> **Risposte di accesso il** numero di risposte di accesso ricevute dagli utenti dell'organizzazione.<br/> **Risposte anonime** è il numero di risposte anonime ricevute dagli utenti dell'organizzazione.<br/><br/>|
|6.<br/>|È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico Utenti seleziona progettisti, risponditori o utenti totali per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella griglia sottostante.|
|7.<br/>|La tabella mostra una suddivisione delle attività a livello di utente. Le legende sono:<br/><br/>**Nome utente** è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Forms.<br/>**Data ultima attività (UTC)** è l'ultima data in cui un'attività del modulo è stata eseguita dall'utente per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/><br/>In questo modo la tabella verrà filtrata per visualizzare i dati relativi all'attività dei file solo per gli utenti che hanno eseguito l'attività in quel giorno specifico.<br/><br/>**Numero di moduli creati** è il numero di moduli creati dall'utente.<br/> **Numero di moduli a cui l'utente** ha risposto è il numero di moduli a cui l'utente ha inviato risposte.|
|8.<br/>|Selezionare **l'icona Gestisci** colonne per aggiungere o rimuovere colonne dal report.|
|9.<br/>|È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** In questo modo vengono esportati i dati per tutti gli utenti e è possibile eseguire semplici operazioni di aggregazione, ordinamento e filtro per un'ulteriore analisi. Se sono presenti meno di 100 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se si dispone di più di 100 utenti, per filtrare e ordinare, sarà necessario esportare i dati.|