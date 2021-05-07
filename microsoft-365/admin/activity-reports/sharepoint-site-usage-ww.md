---
title: Microsoft 365 Report nell'interfaccia di amministrazione - utilizzo SharePoint sito
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: Ottenere il report SharePoint utilizzo del sito per sapere quanti file gli utenti archiviano nei siti di SharePoint, quanti sono utilizzati attivamente e lo spazio di archiviazione totale utilizzato.
ms.openlocfilehash: 62bf01c867b7e9217d25e655af6633a72773caa1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241869"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Report nell'interfaccia di amministrazione - utilizzo SharePoint sito

Come amministratore Microsoft 365, il dashboard **Report** mostra la panoramica delle attività tra i vari prodotti dell'organizzazione. Consente di eseguire il drill-down per ottenere informazioni più dettagliate sulle attività specifiche di ogni prodotto. È possibile, ad esempio, ottenere una visualizzazione generale del valore ricavato da SharePoint in termini di numero totale di file archiviati dagli utenti nei siti di SharePoint, numero di file attivamente in uso e spazio di archiviazione utilizzato in tutti questi siti. È quindi possibile eseguire il drill-down del report sull'utilizzo dei siti di SharePoint per conoscere le tendenze e i dettagli a livello di sito. 
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.
Microsoft 365 I report nell'interfaccia di amministrazione non sono supportati GCC tenant High e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Come ottenere il report sull'utilizzo del sito di SharePoint

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella home page del dashboard fai clic sul **pulsante** Visualizza altro nella SharePoint dashboard.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretare il report SharePoint utilizzo del sito

È possibile visualizzare l'utilizzo del sito nel report SharePoint sito scegliendo la **scheda Utilizzo** sito.<br/>![Microsoft 365 report - Report sull'utilizzo SharePoint sito di Microsoft SharePoint.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![SharePoint utilizzo del sito - Scegliere le colonne](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

È inoltre possibile esportare i dati del report in Excel .csv file selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|URL del sito  <br/> |URL completo del sito. <br/> |
|Eliminato  <br/> |Stato di eliminazione del sito. Occorrono almeno sette giorni affinché un account sia contrassegnato come eliminato.  <br/> |
|Proprietario del sito  <br/> |Nome utente del proprietario principale del sito.   <br/> |
|Nome dell'entità proprietario del sito  <br/> |Indirizzo di posta elettronica del proprietario del sito. <br/> |
|Data ultima attività (UTC)  <br/> | Data dell'ultima volta in cui è stata rilevata l'attività del file o è stata visualizzata una pagina nel sito.  <br/> |
|ID etichetta riservatezza sito  <br/> | Etichetta di riservatezza nel sito.  <br/> |
|Condivisione esterna  <br/> | Impostazioni di condivisione esterna nel sito.  <br/> |
|Criteri dei dispositivi non gestiti  <br/> | Criteri di accesso al sito per i dispositivi non gestiti.  <br/> |
|Posizione geografica  <br/> | Posizione geografica del sito.  <br/> |
|File  <br/> |Numero di file nel sito. <br/>|
|File attivi  <br/> | Numero di file attivi nel sito.<br/> NOTA: se i file sono stati rimossi durante il periodo di tempo specificato per il report, il numero di file attivi visualizzati nel report potrebbe essere superiore al numero corrente di file nel sito.  <br/> |
|Archiviazione utilizzato (MB)  <br/> |Quantità di spazio di archiviazione attualmente in uso nel sito.  <br/>|
|Archiviazione allocato (MB)  <br/> |Quantità massima di spazio di archiviazione allocata per il sito.  <br/>|
|Visualizzazioni pagina  <br/> |Numero di volte in cui le pagine sono state visualizzate nel sito.  <br/>|
|Pagine visitate  <br/> |Numero di pagine univoche visitate nel sito.  <br/>|
|Conteggio collegamenti anonimi  <br/> |Il numero di volte in cui i documenti o le cartelle vengono condivisi utilizzando "Chiunque abbia il collegamento" nel sito.  <br/>|
|Conteggio collegamenti società  <br/> |Il numero di volte in cui i documenti o le cartelle vengono condivisi utilizzando "Persone nell'organizzazione con il collegamento" nel sito.  <br/>|
|Collegamento sicuro per il numero di guest  <br/> |Numero di volte in cui i documenti o le cartelle vengono condivisi utilizzando "persone specifiche" nel sito.  <br/>|
|Collegamento sicuro per il numero di membri  <br/> |Numero di volte in cui i documenti o le cartelle vengono condivisi utilizzando "persone specifiche" nel sito.  <br/>|
|Modello Web radice  <br/> |Modello utilizzato per la creazione del sito.  <br/> NOTA: se si desidera filtrare i dati in base a diversi tipi di sito, esportare i dati e utilizzare la colonna Modello Web radice. |
|||