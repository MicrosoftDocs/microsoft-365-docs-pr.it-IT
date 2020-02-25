---
title: Report di Office 365 nell'interfaccia di amministrazione-utilizzo del dispositivo Microsoft Teams
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Ottenere informazioni sulle app di Microsoft teams utilizzate nell'organizzazione ottenendo il report sull'utilizzo delle app di Microsoft teams dai report di Office 365.
ms.openlocfilehash: 1b337c7e6d7668c708bdd93185e8d0b034a29981
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241843"
---
# <a name="office-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Report di Office 365 nell'interfaccia di amministrazione-utilizzo del dispositivo Microsoft Teams

Il dashboard **report** di Office 365 Visualizza la panoramica delle attività nei prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Utilizzo app Microsoft Teams è possibile ottenere informazioni approfondite sulle app di Microsoft Teams usate nell'organizzazione.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint o Skype for business per visualizzare i report. 
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Come accedere al report Utilizzo app Microsoft Teams

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **utilizzo del dispositivo** **Microsoft teams** \> .
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretare il report Utilizzo app Microsoft Teams

Per avere un quadro d'insieme dell'utilizzo delle app di Microsoft Teams, è possibile esaminare i grafici **Utenti** e **Distribuzione**. 
  
![Office 365 reports - Microsoft Teams app usage](../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |Il report **Utilizzo di dispositivi Microsoft Teams** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |La visualizzazione **Utenti** mostra il numero di utenti univoci giornalieri per app.  <br/> |
|4.  <br/> |La visualizzazione **Distribuzione** mostra il numero di utenti univoci per app nel periodo di tempo selezionato.  <br/> |
|5.  <br/> | Nel grafico **Utenti** l'asse Y rappresenta il numero di utenti per app.  <br/>  Nel grafico **Distribuzione** l'asse Y rappresenta il numero di utenti che usano l'app specificata.  <br/>  L'asse X nei grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|6.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **degli utenti** , selezionare **Windows**, **Mac**, **chiamate**, **Web**, **telefono Android**o **Windows Phone** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> ![È possibile filtrare i grafici di utilizzo delle app di Microsoft teams selezionando il tipo di app.](../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | L'elenco dei gruppi visualizzati dipende dal set di tutti i gruppi che erano presenti (che non sono stati eliminati) nell'intervallo di tempo più ampio (180 giorni). Il numero di attività varia in base alla data selezionata.  <br/> Nota: è possibile che non vengano visualizzati tutti gli elementi nell'elenco in basso nelle colonne finché non vengono aggiunti.<br/> **Nome utente** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere questo campo anonimo.  <br/> **Data ultima attività (UTC)** è la data più recente in cui l'utente ha partecipato a un'attività di Microsoft Teams in un'app.  <br/> **Eliminato** indica se il team è stato eliminato. Se il team viene eliminato, ma c'è stata attività nel periodo di generazione dei report, viene visualizzato nella griglia con questa voce impostata su true.  <br/> **Data eliminazione** indica la data di eliminazione del team.  <br/> **Windows** è selezionato se l'utente era attivo in un'app Windows durante il periodo di tempo specificato.  <br/> **Mac** è selezionato se l'utente era attivo in un'app Mac durante il periodo di tempo specificato.  <br/> **Web** è selezionato se l'utente era attivo in un'app Web durante il periodo di tempo specificato.  <br/> **iOS** è selezionato se l'utente era attivo in un'app per iOS durante il periodo di tempo specificato.  <br/> **Telefono Android** è selezionato se l'utente era attivo in un'app per Android durante il periodo di tempo specificato.  <br/> **Windows Phone** è selezionato se l'utente era attivo in un'app per Windows Phone durante il periodo di tempo specificato.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come nascondere i dettagli a livello di utente** nei [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Selezionare **colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Teams uapp usage report - choose columns](../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   
  

