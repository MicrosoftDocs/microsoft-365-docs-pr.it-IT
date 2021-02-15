---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Report attività dei gruppi di Yammer
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Ottenere il report attività dei gruppi di Yammer per conoscere il numero di gruppi di Yammer creati e utilizzati nell'organizzazione e le relative attività.
ms.openlocfilehash: 4e579fdf6a62dafc3f9a6b58d098d9094e62226b
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779194"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Report attività dei gruppi di Yammer

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività dei gruppi di Yammer, è possibile ottenere informazioni approfondite sull'attività dei gruppi di Yammer nell'organizzazione e vedere quanti gruppi di Yammer vengono creati e usati.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Come accedere al report Attività dei gruppi di Yammer

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. **Nell'elenco a discesa Selezionare un report** selezionare Attività gruppi **di Yammer.** \> 
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Interpretare il report Attività dei gruppi di Yammer

Per avere una visuale delle attività dei gruppi di Yammer, è possibile osservare i grafici **Gruppi** e **Attività**.<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report **Attività dei gruppi di Yammer** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |I dati in ogni report in genere riguardano fino alle ultime 24-48 ore. <br/> |
|3.  <br/> |La visualizzazione **Gruppi** mostra il numero totale di gruppi esistenti e quanti di essi hanno eseguito attività di conversazione di gruppo.  <br/> |
|4.  <br/> |La visualizzazione **Attività** mostra il numero di messaggi di Yammer pubblicati, letti e con Mi piace nei gruppi.  <br/> |
|5.  <br/> | Nel grafico **Gruppi** l'asse Y rappresenta il numero dei gruppi totali o attivi.  <br/>  Nel grafico **Attività** l'asse Y rappresenta il numero delle attività specificate per i gruppi di Yammer.  <br/>  L'asse X in tutti e tre i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|6.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Nel grafico Gruppi, **ad**  esempio, selezionare Le icone Totale o Totale attivo e Attivo per visualizzare solo le informazioni correlate a  ![ ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) ognuna.   La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> |
|7.  <br/> | L'elenco dei gruppi da mostrare dipende dal set di tutti i gruppi che erano presenti (che non sono stati eliminati) nel periodo della relazione più ampio (180 giorni). Il numero di attività (i messaggi ricevuti) varia in base alla data selezionata.  <br/> NOTA: potresti non vedere tutti gli elementi nell'elenco seguente nelle colonne finché non li aggiungi.<br/>**Nome gruppo** è il nome del gruppo.  <br/> **Amministratore gruppo** è il nome dell'amministratore del gruppo o del proprietario.  <br/> **Eliminati** è il numero di gruppi di Yammer eliminati. Se il gruppo viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con questo flag impostato su true.  <br/> **Tipo** indica il tipo di gruppo, ad esempio pubblico o privato.  <br/> **Connesso a Office 365** indica se il gruppo di Yammer è anche un gruppo di Microsoft 365.  <br/> **La data dell'ultima** attività è l'ultima data in cui un messaggio è stato letto, pubblicato o mi piace dal gruppo.  <br/> **Membri** è il numero di membri del gruppo.  <br/> **Pubblicati** è il numero dei messaggi pubblicati nel gruppo di Yammer nel periodo di riferimento.  <br/> **Letti** è il numero delle conversazioni lette nel gruppo di Yammer nel periodo di riferimento.  <br/> **Apprezzati** è il numero dei messaggi con Mi piace nel gruppo di Yammer nel periodo di riferimento. <br/> **Il nome** di rete è il nome completo della rete a cui appartiene il gruppo. <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come nascondere i dettagli** a livello di utente in Report attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|8.  <br/> |Selezionare **Colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Yammer groups activity - choose columns](../../media/c56c807f-fbc0-4d37-8bd3-e779bd0606a7.png)|
|9.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   

