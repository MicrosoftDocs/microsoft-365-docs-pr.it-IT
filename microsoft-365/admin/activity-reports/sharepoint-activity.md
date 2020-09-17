---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-attività di SharePoint
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: Ottenere il report sull'utilizzo di attività di SharePoint per conoscere l'attività di ogni utente di SharePoint, il numero di file condivisi e l'utilizzo di archiviazione.
ms.openlocfilehash: b0c628300647e83889e273268bef7abd9e337ed4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948869"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-attività di SharePoint

In qualità di amministratore Microsoft 365, nel dashboard dei **report** viene illustrata la panoramica delle attività in vari prodotti dell'organizzazione. Consente di eseguire il drill-down per ottenere informazioni più dettagliate sulle attività specifiche di ogni prodotto. Consultare i [report attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di tutti gli utenti con licenza per l'uso di SharePoint osservandone l'interazione con i file. È anche utile per comprendere il livello di collaborazione in corso osservando il numero di file condivisi.
  
> [!NOTE]
> Alcune funzionalità vengono introdotte gradualmente. Questo significa che questa funzionalità potrebbe non essere ancora disponibile o essere diversa da quella descritta negli articoli della Guida. Se non è ancora disponibile, lo sarà tra breve. 
  
Per conoscere la quantità di attività eseguita in ogni sito di SharePoint e l'utilizzo dello spazio di archiviazione, visualizzare il [report utilizzo dei siti di SharePoint](sharepoint-site-usage.md).
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Come si torna al report attività in SharePoint?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare attività di **SharePoint** \> **Activity**.
  
## <a name="interpreting-the-sharepoint-activity-report"></a>Interpretazione del report attività di SharePoint

Per avere una visuale dell'attività di SharePoint, è possibile osservare le visualizzazioni **File** e **Utenti**.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il **report attività di SharePoint** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |La visualizzazione **File** consente di conoscere il numero univoco di utenti con licenza che interagiscono con i file archiviati nei siti di SharePoint.  <br/> |
|4.  <br/> |La visualizzazione **Pagine** mostra il numero di pagine univoche visitate dagli utenti.  <br/> |
|5.  <br/> |La visualizzazione **Utenti** consente di conoscere la tendenza nel numero di utenti attivi. Un utente viene considerato attivo se ha eseguito un'attività sui file, ad esempio salvataggio, sincronizzazione, modifica o condivisione, o ha visitato una pagina in un intervallo di tempo specificato.  <br/> Nota: un'attività dei file può verificarsi più volte per un singolo file, ma verrà conteggiato solo come un file attivo. Ad esempio, è possibile salvare e sincronizzare più volte lo stesso file in un periodo di tempo specificato, ma verrà conteggiato come un solo file attivo e un solo file sincronizzato nei dati.           |
|6.  <br/> | Nel grafico **File** l'asse Y è il numero di file univoci che un utente ha salvato, sincronizzato, modificato oppure condiviso.  <br/>  Nel grafico **Utenti** l'asse Y è il numero di utenti univoci che hanno eseguito attività su un file, ad esempio salvataggio, sincronizzazione, modifica o condivisione, in un sito.  <br/>  Nel grafico **Pagine** l'asse X corrisponde al numero di pagine univoche visitate dagli utenti.  <br/>  L'asse X in tutti i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|7.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **file** selezionare **visualizzato o modificato**, **sincronizzato**, **condiviso internamente**o **condiviso esternamente** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> |
|8.  <br/> | La tabella mostra un'analisi delle attività a livello di sito.  <br/>  <br/> **Username** è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività nel sito di SharePoint.  <br/> **Data ultima attività (UTC)** è la data più recente in cui è stata eseguita un'attività sui file o è stata visitata una pagina nell'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.  <br/> ![Selezionare una data specifica nel grafico](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> In questo modo la tabella verrà filtrata per visualizzare i dati relativi alle attività dei file solo per gli utenti che hanno eseguito l'attività in quel giorno specifico.  <br/>  **File visualizzati o modificati** è il numero di file che l'utente ha caricato, scaricato, modificato o visualizzato.  <br/>  **File sincronizzati** è il numero di file che sono stati sincronizzati dal dispositivo locale di un utente al sito di SharePoint.  <br/>  **File condivisi internamente** è il numero di file che sono stati condivisi con gli utenti all'interno dell'organizzazione o con utenti all'interno di gruppi (che potrebbero includere utenti esterni).  <br/>  **File condivisi esternamente** è il numero di file che sono stati condivisi con gli utenti all'esterno dell'organizzazione.  <br/>  Le **pagine visitate** sono le visite alle pagine univoche da parte dell'utente.  <br/>  **Eliminato** indica che la licenza dell'utente è stata rimossa.  <br/>  **Nota:** L'attività per un utente eliminato continuerà a essere visualizzata nel report purché sia stata concessa una licenza in un determinato momento durante il periodo di tempo selezionato. La colonna Eliminati consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.  <br/> **Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.  <br/>  **Prodotto assegnato** sono i prodotti Microsoft 365 che sono concessi in licenza all'utente.  <br/> |
|9.  <br/> |Selezionare l'icona **Gestisci colonne** ![ gestione colonne ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) per aggiungere o rimuovere colonne dal report.  <br/> |
|10.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriori analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   

