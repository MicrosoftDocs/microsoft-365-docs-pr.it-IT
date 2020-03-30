---
title: Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di OneDrive for business
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: Ottenere il report di utilizzo di OneDrive per l'organizzazione e conoscere l'attività di ogni utente di OneDrive, il numero di file condivisi e l'utilizzo dello spazio di archiviazione.
ms.openlocfilehash: b94e5e34f7599cc372b506c2c365503ea1334685
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "43047086"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di OneDrive for business

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di tutti gli utenti con licenza per l'uso di OneDrive osservandone l'interazione con i file in OneDrive. È anche utile per comprendere il livello di collaborazione in corso osservando il numero di file condivisi.
  
> [!NOTE]
> Alcune funzionalità vengono introdotte gradualmente. Questo significa che questa funzionalità potrebbe non essere ancora disponibile o essere diversa da quella descritta negli articoli della Guida. Se non è ancora disponibile, lo sarà a breve. 
  
Se si vuole conoscere la quantità di attività eseguita in ogni account OneDrive e l'utilizzo di spazio di archiviazione, è possibile visualizzare il [report di utilizzo di OneDrive](onedrive-for-business-usage.md).
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Come ottenere il report Attività di OneDrive?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **attività**di **OneDrive** \> .
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretare il report sull'attività di OneDrive for Business

Per avere una visuale dell'attività di OneDrive for Business, è possibile osservare le visualizzazioni **File** e **Utenti**. 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |Il report **Attività di OneDrive for Business** visualizza le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore. <br/>|
|3.  <br/> |La visualizzazione **File** consente di conoscere il numero univoco di utenti con licenza che hanno interagito con il file in qualsiasi account OneDrive.  <br/> |
|4.  <br/> |La visualizzazione **Utenti** consente di conoscere la tendenza nel numero di utenti attivi di OneDrive. Un utente viene considerato attivo se ha eseguito un'attività di file (salvataggio, sincronizzazione, modifica o condivisione) entro il periodo di tempo specificato.  <br/> Nota: un'attività dei file può verificarsi più volte per un singolo file, ma verrà conteggiato solo come un solo file attivo. Ad esempio, è possibile salvare e sincronizzare più volte lo stesso file in un periodo di tempo specificato, ma verrà conteggiato come un solo file attivo e un solo file sincronizzato nei dati.           |
|5.  <br/> | Nel grafico **File** l'asse Y è il numero di file univoci che ogni utente ha salvato, sincronizzato, modificato oppure condiviso.  <br/>  Nel grafico **Utenti** l'asse Y è il numero di utenti univoci che hanno interagito con il file (salvataggio, sincronizzazione, modifica o condivisione) in qualsiasi account OneDrive.  <br/>  L'asse X in tutti i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|6.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **file** selezionare **visualizzati o modificati** oppure **sincronizzati** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non cambia le informazioni nella tabella della griglia.  <br/> |
|7.  <br/> | La tabella visualizza un'analisi dei dati a livello di utente. È possibile aggiungere o rimuovere colonne in una tabella.   <br/>  **Username** è il nome utente del proprietario dell'account OneDrive.  <br/> **Data ultima attività (UTC)** è la data più recente in cui è stata eseguita un'attività sull'account OneDrive per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.  <br/> ![Selezionare una data specifica nel grafico](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  In questo modo la tabella verrà filtrata per visualizzare i dati relativi alle attività dei file solo per gli utenti che hanno eseguito l'attività in quel giorno specifico.  <br/> **File visualizzati o modificati** è il numero di file che l'utente ha caricato, scaricato, modificato o visualizzato.  <br/> **File sincronizzati** è il numero di file che sono stati sincronizzati dal dispositivo locale di un utente nell'account OneDrive.  <br/> **File condivisi internamente** è il numero di file che sono stati condivisi con gli utenti all'interno dell'organizzazione o con utenti all'interno di gruppi (che potrebbero includere utenti esterni).  <br/> **File condivisi esternamente** è il numero di file che sono stati condivisi con gli utenti all'esterno dell'organizzazione.  <br/> **Eliminato** indica che la licenza dell'utente è stata rimossa.  <br/> Nota: l'attività per un utente eliminato continuerà a essere visualizzata in un report a condizione che sia stata concessa una licenza in un determinato momento durante il periodo di tempo selezionato. La colonna **Eliminati** consente di notare che l'utente potrebbe non essere più attivo, ma ha contribuito ai dati nel report.<br/>**Data eliminazione** è la data in cui la licenza dell'utente è stata rimossa.  <br/> **Prodotto assegnato** sono i prodotti Microsoft 365 che sono concessi in licenza all'utente.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come nascondere i dettagli a livello di utente** nei [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Selezionare l'icona ![ **Gestisci colonne** gestione](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) colonne per aggiungere o rimuovere colonne dal report.  <br/> |
|9.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   

