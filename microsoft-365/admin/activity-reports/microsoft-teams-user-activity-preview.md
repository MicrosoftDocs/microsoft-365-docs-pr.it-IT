---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività degli utenti di Microsoft Teams
ms.author: kwekua
author: kwekua
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
description: Informazioni su come ottenere il report attività utente di Microsoft Teams e ottenere informazioni dettagliate sull'attività di Teams nell'organizzazione.
ms.openlocfilehash: a4f8cd995d1559da3846fbb38cc5a9441358da72
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579615"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività degli utenti di Microsoft Teams

Il **dashboard** dei report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività degli utenti di Microsoft Teams è possibile ottenere informazioni approfondite sull'attività di Microsoft Teams nell'organizzazione.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Come accedere al report Attività degli utenti di Microsoft Teams

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Nella home page del dashboard fai clic sul **pulsante Visualizza** altro nella scheda attività di Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report Attività degli utenti di Microsoft Teams

È possibile visualizzare l'attività utente nel report Teams scegliendo la **scheda Attività** utente. <br/>![Report di Microsoft 365 - Attività degli utenti di Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Teams user activity report - choose columns](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. Il formato esportato per **l'ora audio,** **l'ora video** e il tempo di condivisione dello schermo **segue** il formato di durata ISO8601.

Il report **Attività degli utenti di Microsoft Teams** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data di generazione del report).

Per garantire la qualità dei dati, eserciteremo controlli giornalieri di convalida dei dati negli ultimi tre giorni e colmando eventuali lacune rilevate. Durante il processo potrebbero verificarsi differenze nei dati cronologici.

|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Indirizzo di posta elettronica dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo.   <br/> |
|Messaggi di canale   <br/> |Numero di messaggi univoci che l'utente ha pubblicato in una chat del team durante il periodo di tempo specificato.  <br/> |
|Messaggi di chat   <br/> |Numero di messaggi univoci che l'utente ha pubblicato in una chat privata durante il periodo di tempo specificato.  <br/> |
|Totale riunioni   <br/> |Numero di riunioni online a cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Chiamate 1:1   <br/> | Numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Data ultima attività (UTC)  <br/> |Data dell'ultima partecipazione dell'utente a un'attività di Microsoft Teams.<br/> |
|Riunioni partecipate ad hoc   <br/> | Numero di riunioni ad hoc a cui un utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Riunioni organizzate ad hoc <br/> |Numero di riunioni ad hoc organizzate da un utente durante il periodo di tempo specificato. <br/>|
|Totale riunioni organizzate  <br/> |Somma delle riunioni programmate, ricorrenti, ad hoc e non classificate una sola volta organizzate da un utente durante il periodo di tempo specificato.  <br/> |
|Totale riunioni partecipate  <br/> |Somma delle riunioni programmate, ricorrenti, ad hoc e non classificate a cui un utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Riunioni organizzate una sola volta  <br/> |Numero di riunioni pianificate una sola volta organizzate da un utente durante il periodo di tempo specificato.  <br/> |
|Riunioni organizzate ricorrenti pianificate  <br/> |Numero di riunioni ricorrenti organizzate da un utente durante il periodo di tempo specificato.  <br/> |
|Riunioni partecipate una sola volta pianificate  <br/> |Numero di riunioni programmate una sola volta a cui un utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Riunioni partecipate ricorrenti pianificate  <br/> |Numero di riunioni ricorrenti a cui un utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|È concesso in licenza  <br/> |Selezionato se l'utente ha la licenza per l'utilizzo di Teams. <br/>|
|Altre attività  <br/>|L'utente è attivo, ma ha eseguito altre attività rispetto ai tipi di azione esposti offerti nel report (invio o risposta a messaggi di canale e messaggi di chat, pianificazione o partecipazione a chiamate e riunioni 1:1). Esempi di azioni sono quando un utente modifica lo stato di Teams o il messaggio di stato di Teams o apre un post di messaggio del canale ma non risponde.  <br/>|
|riunioni non classificate <br/>|Quella che non può essere classificata come pianificazione o ricorrente o ad hoc. Si tratta di numeri brevi e per lo più non possono essere identificati a causa di informazioni di telemetria manomissionate. |
|||