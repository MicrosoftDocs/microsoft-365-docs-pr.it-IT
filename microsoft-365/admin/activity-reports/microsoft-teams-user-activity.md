---
title: Microsoft 365 dell'interfaccia di amministrazione - Microsoft Teams'attività degli utenti
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
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Informazioni su come ottenere il report attività Microsoft Teams utente e ottenere informazioni dettagliate sull'attività Teams nell'organizzazione.
ms.openlocfilehash: c824a0ce285a085c9ae8b7326647ad4bcdf5f013
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924268"
---
# <a name="microsoft-365-admin-center-reports---microsoft-teams-user-activity"></a>Microsoft 365 dell'interfaccia di amministrazione - Microsoft Teams'attività degli utenti

Il dashboard Microsoft 365 **report mostra** la panoramica dell'attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività degli utenti di Microsoft Teams è possibile ottenere informazioni approfondite sull'attività di Microsoft Teams nell'organizzazione.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Come accedere al report Attività degli utenti di Microsoft Teams

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. **Nell'elenco a discesa Selezionare** un report selezionare Microsoft Teams Attività  \> **utente.**
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report Attività degli utenti di Microsoft Teams

Per avere un quadro d'insieme delle attività degli utenti di Microsoft Teams, è possibile osservare i grafici **Attività** e **Utenti**.<br/>![Microsoft 365 report- Microsoft Teams'attività utente.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report **Attività degli utenti di Microsoft Teams** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data di generazione del report).  <br/> |
|2.  <br/> |I dati in ogni report in genere coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |Per garantire la qualità dei dati, eserciteremo controlli di convalida dei dati giornalieri per gli ultimi cinque giorni e colmando eventuali lacune rilevate. Durante il processo potrebbero verificarsi differenze nei dati cronologici.  <br/> |
|4.  <br/> |La visualizzazione **Attività** mostra il numero di attività di Microsoft Teams per tipo di attività. I tipi di attività sono numero di messaggi in chat dei team, messaggi in chat privati, chiamate o riunioni.  <br/> |
|5.  <br/> |La visualizzazione **Utenti** mostra il numero di utenti per tipo di attività. I tipi di attività sono numero di messaggi in chat dei team, messaggi in chat privati, chiamate o riunioni.  <br/> |
|6.  <br/> | Nel grafico **Attività,** l'asse Y è il conteggio dell'attività specificata.  <br/>  Nel grafico **File,** l'asse Y è il numero di utenti che partecipano a chat di team, chat private, chiamate o riunioni.  <br/>  L'asse X dei grafici è l'intervallo di date selezionato per il report specifico.  <br/> |
|7.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **Attività** seleziona Messaggi di **canale,** **Messaggi chat,** **Chiamate** o **Riunioni** per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> ![Filtrare i grafici Microsoft Teams attività](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | L'elenco dei gruppi visualizzati dipende dal set di tutti i gruppi che erano presenti (che non sono stati eliminati) nell'intervallo di tempo più ampio (180 giorni). Il numero di attività varia in base alla data selezionata.  <br/> NOTA: potresti non visualizzare tutte le voci dell'elenco seguente nelle colonne finché non le aggiungi.<br/>**Nome utente** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere questo campo anonimo.  <br/> **Data ultima attività (UTC)** è la data più recente in cui l'utente ha partecipato a un'attività di Microsoft Teams.  <br/> **Messaggi del canale** è il numero di messaggi univoci che l'utente ha pubblicato in una chat del team nel periodo di tempo specificato.  <br/> **Messaggi in chat** è il numero di messaggi univoci che l'utente ha pubblicato in una chat privata nel periodo di tempo specificato.  <br/> **Chiamate** è il numero di chiamate a cui l'utente ha partecipato nel periodo di tempo specificato.  <br/> **Riunioni** è il numero di riunioni online a cui l'utente ha partecipato nel periodo di tempo specificato.  <br/> **Altra attività** è il numero di altre attività del team a cui l'utente ha partecipato.  <br/> **Eliminato** indica se il team è stato eliminato. Se il team viene eliminato, ma c'è stata attività nel periodo di generazione dei report, viene visualizzato nella griglia con questa voce impostata su true.  <br/> **Data eliminazione** indica la data di eliminazione del team.  <br/> **Prodotto assegnato** indica l'elenco dei prodotti assegnati all'utente.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come nascondere i dettagli a** livello di utente nei Report attività [nell'Microsoft 365 di amministrazione.](activity-reports.md)  <br/> |
|9.  <br/> |Selezionare **Colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |È inoltre possibile esportare i dati del report in Excel .csv file selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   

