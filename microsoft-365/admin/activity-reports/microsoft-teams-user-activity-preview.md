---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività degli utenti di Microsoft Teams
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Informazioni su come ottenere il report attività degli utenti di Microsoft Teams e ottenere informazioni approfondite sull'attività di Teams nell'organizzazione.
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233411"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività degli utenti di Microsoft Teams

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività degli utenti di Microsoft Teams è possibile ottenere informazioni approfondite sull'attività di Microsoft Teams nell'organizzazione.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Come accedere al report Attività degli utenti di Microsoft Teams

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Dalla home page del dashboard, fare clic sul pulsante Visualizza **altro** nella scheda attività di Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report Attività degli utenti di Microsoft Teams

È possibile visualizzare l'attività degli utenti nel report di Teams scegliendo la **scheda Attività** utente. <br/>![Report di Microsoft 365 - Attività degli utenti di Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. Il formato esportato per **l'ora audio,** **l'ora video** e il tempo di condivisione **dello** schermo segue il formato di durata ISO8601.

Il report **Attività degli utenti di Microsoft Teams** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).

Per garantire la qualità dei dati, eserciteremo controlli di convalida dei dati giornalieri per gli ultimi tre giorni e colmando eventuali lacune rilevate. Durante il processo potrebbero verificarsi differenze nei dati cronologici.

|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Indirizzo di posta elettronica dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo.   <br/> |
|Messaggi di canale   <br/> |Numero di messaggi univoci che l'utente ha pubblicato in una chat del team durante il periodo di tempo specificato.  <br/> |
|Messaggi di chat   <br/> |Numero di messaggi univoci che l'utente ha pubblicato in una chat privata durante il periodo di tempo specificato.  <br/> |
|Totale riunioni   <br/> |Numero di riunioni online a cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Chiamate 1:1   <br/> | Numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Data ultima attività (UTC)  <br/> |L'ultima data in cui l'utente ha partecipato a un'attività di Microsoft Teams.<br/> |
|Riunioni adhoc   <br/> | Numero di riunioni non pianificate nel calendario a cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Riunioni organizzate adhoc <br/> |Numero di riunioni non pianificate nel calendario organizzato dall'utente durante il periodo di tempo specificato. <br/>|
|Riunioni pianificate  <br/> |Numero di riunioni pianificate organizzate da un utente durante il periodo di tempo specificato.  <br/> |
|È concesso in licenza |Selezionato se l'utente ha la licenza per l'uso di Teams.|
|Altre attività|L'utente è attivo, ma ha eseguito altre attività rispetto ai tipi di azione esposti offerti nel rapporto (invio o risposta a messaggi di canale e messaggi di chat, pianificazione o partecipazione a chiamate e riunioni 1:1). Esempi di azioni sono quando un utente modifica lo stato di Teams o il messaggio di stato di Teams o apre un post di messaggio del canale, ma non risponde. |
|||