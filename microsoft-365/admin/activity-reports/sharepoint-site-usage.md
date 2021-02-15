---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo del sito di SharePoint
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
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: "Ottenere il report sull'utilizzo dei siti di SharePoint per conoscere il numero di file archiviati dagli utenti nei siti di SharePoint, il numero di file utilizzati attivamente e l'archiviazione totale utilizzata. "
ms.openlocfilehash: 7da72dccb4a90ed204ffa785040b1968ac70feb3
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688206"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo del sito di SharePoint

In qualità di amministratore di Microsoft 365, il **dashboard** Report mostra la panoramica delle attività in vari prodotti dell'organizzazione. Consente di eseguire il drill-down per ottenere informazioni più dettagliate sulle attività specifiche di ogni prodotto. È possibile, ad esempio, ottenere una visualizzazione generale del valore ricavato da SharePoint in termini di numero totale di file archiviati dagli utenti nei siti di SharePoint, numero di file attivamente in uso e spazio di archiviazione utilizzato in tutti questi siti. È quindi possibile eseguire il drill-down del report sull'utilizzo dei siti di SharePoint per conoscere le tendenze e i dettagli a livello di sito. 
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.
I report di Microsoft 365 nell'interfaccia di amministrazione non sono supportati per i tenant GCC High e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Come ottenere il report sull'utilizzo del sito di SharePoint

1. Nell'interfaccia di amministrazione passare a **Utilizzo** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">report.</a>
    
2. In **File di SharePoint fare** clic su Visualizza **altro.** 

3. Accanto ad **Attività di SharePoint** fare clic sulla freccia in giù per aprire il menu.

4. Selezionare Utilizzo **sito di SharePoint.** \> 
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Interpretazione del report sull'utilizzo del sito di SharePoint

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report **Uso del sito di SharePoint** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |I dati in ogni report in genere riguardano fino alle ultime 24-48 ore. <br/> |
|3.  <br/> |Il grafico **Siti** mostra il numero totale di siti attivi e totali, inclusi i siti in cui gli utenti hanno visualizzato, modificato, caricato, scaricato, condiviso o sincronizzato un file o visualizzato una pagina entro il periodo di reporting.  <br/> |
|4.  <br/> |Il grafico **File** mostra il numero totale di file in tutti i siti e il numero di file attivi. Il numero totale di file include sia i file dell'utente che quelli di sistema. Un file viene considerato attivo se è stato salvato, sincronizzato, modificato o condiviso entro il periodo di tempo specifico.  |
|5.  <br/> |Il grafico **Spazio di archiviazione** mostra la tendenza dello spazio di archiviazione allocato e utilizzato durante il periodo di riferimento del report.  <br/> |
|6.  <br/> |Il grafico **Pagine** mostra il numero di pagine visualizzate in tutti i siti.  <br/> |
|7.  <br/> |È possibile filtrare i grafici visualizzati selezionando un elemento nella legenda. Nel grafico File, **ad** esempio, selezionare **File** o **File attivi.** Nel grafico **Siti** è possibile selezionare Totale **siti** o **Siti attivi.** Nel grafico **Archiviazione,** è possibile selezionare Spazio di archiviazione **allocato** **o Spazio di archiviazione utilizzato.** La modifica di questa selezione non cambia le informazioni nella tabella della griglia.  <br/> |
|8.  <br/> | La tabella mostra un'analisi delle attività a livello di sito.  <br/> ![Opzioni delle colonne per il report sull'utilizzo](../../media/sharepointsite-usage.png)           <br/> **URL sito** è l'URL completo del sito.  <br/> **Eliminato** indica lo stato di eliminazione del sito. Occorrono almeno sette giorni affinché un account sia contrassegnato come eliminato.  <br/> **Proprietario del sito** è il nome utente del proprietario principale del sito.  <br/>**Il nome dell'entità proprietario del** sito è l'indirizzo di posta elettronica del proprietario del sito.  <br/> **Data ultima attività (UTC)** si riferisce alla data in cui è stata rilevata per l'ultima volta attività sui file nel sito.  <br/> **File** indica il numero di file nel sito.  <br/> **File attivi** è il numero di file attivi nel sito.<br/> NOTA: se i file sono stati rimossi durante il periodo di tempo specificato per il report, il numero di file attivi visualizzati nel report potrebbe essere superiore al numero corrente di file nel sito.<br/>**Spazio di archiviazione utilizzato (MB)** è la quantità di spazio di archiviazione attualmente usato nel sito.  <br/> **Spazio di archiviazione allocato (MB)** è la quantità massima di spazio di archiviazione allocato per il sito.  <br/> **Visualizzazioni pagine** indica il numero di volte in cui sono state visualizzate le pagine del sito.  <br/> **Pagine visitate** indica il numero di volte in cui sono state visitate le pagine del sito.  <br/> **Modello sito Web radice** è il modello usato per creare il sito.  <br/> NOTA: se si desidera filtrare i dati in base a tipi di sito diversi, esportare i dati e utilizzare la colonna Modello Web radice. <br/>Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come nascondere i dettagli** a livello di utente nei report attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|9.  <br/> |Selezionare **Gestisci colonne** Gestisci colonne per aggiungere o rimuovere colonne dal ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) report.    <br/> |
|10.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta** ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) esporta. Vengono esportati i dati per tutti i siti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se i siti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece i siti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> NOTA: quando i dati vengono esportati in un file di Excel, si noti che la data in cui è stato generato il report del contenuto viene riflessa nel file nella colonna Dati **come di.**      <br/>   |
|||
