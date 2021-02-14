---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo di OneDrive for Business
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: "Ottenere il Report sull'utilizzo di OneDrive for Business per conoscere il numero totale di file e spazio di archiviazione usato nell'organizzazione. "
ms.openlocfilehash: e08dff4e763479afa197377d37e474384492c012
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948917"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo di OneDrive for Business

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
Ad esempio, la scheda OneDrive sul dashboard offre una panoramica generale del valore ricevuto da OneDrive for Business per quanto riguarda il numero totale di file e di risorse di archiviazione usati in tutti gli account nell'organizzazione. È quindi possibile analizzare questo valore per comprendere le tendenze degli account di OneDrive attivi, il numero di file con cui interagiscono gli utenti e le risorse di archiviazione usate. Vengono visualizzati anche dettagli per i singoli account di OneDrive.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Come si ottiene il report sull'utilizzo di OneDrive?

1. Nell'interfaccia di amministrazione passare a **Utilizzo** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">report.</a>

    
2. **Nell'elenco a discesa Selezionare un report** selezionare Uso di **OneDrive.** \>  
  
## <a name="interpret-the-onedrive-usage-report"></a>Interpretare il report sull'utilizzo di OneDrive

Per avere una panoramica dell'utilizzo di OneDrive for Business, è possibile osservare le visualizzazioni **Account**, **File** e **Archiviazione**. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report **Uso di OneDrive** mostra le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |I dati in ogni report in genere riguardano fino alle ultime 24-48 ore. <br/>|
|3.  <br/> |La visualizzazione **Account** mostra la tendenza del numero totale di account OneDrive e di quelli attivi. Gli "Account attivi" sono gli account che gli utenti usano per visualizzare, modificare, caricare, condividere o sincronizzare i file.  <br/> |
|4.  <br/> |La **visualizzazione File** mostra il numero di file totali e attivi. Un file viene considerato attivo se è stato salvato, sincronizzato, modificato o condiviso in un periodo di tempo specifico.  <br/> NOTA: un'attività di file può verificarsi più volte per un singolo file, ma verrà conteggiato come un solo file attivo. Ad esempio, è possibile salvare e sincronizzare più volte lo stesso file in un periodo di tempo specificato, ma verrà conteggiato come un solo file attivo e un solo file sincronizzato nei dati.           |
|5.  <br/> |La visualizzazione **Archiviazione** mostra la tendenza relativa alla quantità di risorse di archiviazione OneDrive usate. Se si desidera controllare i limiti di archiviazione, vedere Verificare se un utente ha il limite di archiviazione predefinito [o un limite specifico.](https://docs.microsoft.com/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit)  <br/> NOTA: le dimensioni includono tutte le versioni e i metadati associati ai file.           |
|6.  <br/> | Nel grafico **Account**, l'asse Y rappresenta il numero di account OneDrive.  <br/>  Nel grafico **File**, l'asse Y rappresenta il numero di file archiviati in OneDrive.  <br/>  Nel grafico **Archiviazione**, l'asse Y rappresenta la quantità di risorse di archiviazione OneDrive usate.  <br/>  L'asse X in tutti i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|7.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Nel grafico File, ad **esempio,** selezionare **Totale file** o **File attivi.** Nel grafico **Account** selezionare **Account totali o** Account **attivi.** In or on the **Storage** chart, select **Storage used.** La modifica della selezione non cambia le informazioni nella tabella.  <br/> |
|8.  <br/> | La tabella mostra un'analisi dei dati per ciascun utente OneDrive. Per comparire nella tabella, è necessario che all'utente sia stata assegnata una licenza che include OneDrive, e che il suo SharePoint Online sia stato attivato. È inoltre necessario che l'utente abbia effettuato l'accesso al client di sincronizzazione OneDrive, o che abbia visitato il proprio OneDrive in un web browser.  <br/>  Se in OneDrive ci sono state attività sui file, sarà mostrata la data in cui si è verificata l'ultima attività sui file. Le righe nella tabella sono ordinate in base al valore **Data ultima attività** per cui il OneDrive con le attività più recenti verrà visualizzato all'inizio dell'elenco.  <br/>  È possibile aggiungere o rimuovere colonne nella tabella.  <br/> ![Opzioni colonna](../../media/onedriveusage-columns.png)  <br/> **L'URL** è l'indirizzo Web del OneDrive dell'utente.  <br/> **Eliminato** è lo stato di eliminazione di OneDrive. Un account viene contrassegnato come eliminato dopo almeno 7 giorni.  <br/> **Proprietario** è il nome utente dell'amministratore principale di OneDrive.  <br/> **Il nome dell'entità** proprietario è l'indirizzo di posta elettronica del proprietario di OneDrive.  <br/> **Data ultima attività (UTC)** è la data più recente in cui è stata eseguita un'attività sui file in OneDrive. Se in OneDrive non ci sono state attività sui file, il valore sarà vuoto.  <br/> **File** indica il numero di file in OneDrive.  <br/> **File attivi** è il numero di file attivi in un periodo di tempo determinato.<br/> NOTA: se i file sono stati rimossi durante il periodo di tempo specificato per il report, il numero di file attivi visualizzati nel report potrebbe essere superiore al numero corrente di file in OneDrive. Gli utenti eliminati continueranno a essere visualizzati nei report per 180 giorni.<br/>**Spazio di archiviazione usato (MB)** è la quantità di spazio di archiviazione usato in OneDrive, espressa in MB. <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come nascondere i dettagli** a livello di utente nei report attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|9.  <br/> |Selezionare **l'icona Gestisci** colonne ![ Gestisci colonne per aggiungere o rimuovere colonne dal ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) report.  <br/> |
|10.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati per ciascun OneDrive, che possono poi essere ordinati e filtrati per un'ulteriore analisi. Se gli account OneDrive sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli account OneDrive sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> NOTA: quando i dati vengono esportati in un file di Excel, la data in cui è stato generato il report del contenuto viene riflessa nel file nella colonna **Data as of.**  <br/> |
|||
   
