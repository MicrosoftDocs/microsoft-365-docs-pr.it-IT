---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-attività utente di Microsoft Teams
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
description: Informazioni su come ottenere il report attività degli utenti di Microsoft teams e acquisire maggiori informazioni sull'attività dei team nell'organizzazione.
ms.openlocfilehash: 8ce29b43e6238883470d1159ad1d22fefca88792
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637068"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-attività utente di Microsoft Teams

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività degli utenti di Microsoft Teams è possibile ottenere informazioni approfondite sull'attività di Microsoft Teams nell'organizzazione.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Come accedere al report Attività degli utenti di Microsoft Teams

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altro** sulla scheda attività Microsoft teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretare il report Attività degli utenti di Microsoft Teams

È possibile visualizzare l'attività utente nel rapporto teams scegliendo la scheda **attività utente** . <br/>![Microsoft 365 Reports-attività utente di Microsoft teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. Il formato esportato per il tempo **audio**, **video** e tempo di **condivisione dello schermo** segue il formato di durata ISO8601.

|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |L'indirizzo di posta elettronica dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo.   <br/> |
|Messaggi di canale   <br/> |Il numero di messaggi univoci inviati dall'utente in una chat del team durante il periodo di tempo specificato.  <br/> |
|Messaggi chat   <br/> |Il numero di messaggi univoci che l'utente ha inviato in una chat privata durante il periodo di tempo specificato.  <br/> |
|Totale riunioni   <br/> |Il numero di riunioni online a cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|1:1 chiamate   <br/> | Il numero di chiamate 1:1 che l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Data ultima attività (UTC)  <br/> |Ultima data in cui l'utente ha partecipato a un'attività di Microsoft teams.<br/> |
|Gli incontri hanno partecipato ad Adhoc   <br/> | Il numero di riunioni non pianificate nel calendario in cui l'utente ha partecipato durante il periodo di tempo specificato.  <br/> |
|Riunioni organizzate ad hoc <br/> |Il numero di riunioni non pianificate nel calendario che l'utente ha organizzato durante il periodo di tempo specificato. <br/>|
|Riunioni organizzate pianificate  <br/> |Il numero di riunioni pianificate che un utente ha organizzato durante il periodo di tempo specificato.  <br/> |
|È concesso in licenza |Selezionato se l'utente è autorizzato a usare i team.|
|Altre attività|l'utente è considerato attivo ma ha un valore pari a zero per i messaggi di chat, 1:1 chiamate, i messaggi di canale, le riunioni totali e i valori metrici organizzati per le riunioni. Esempi di azioni si verificano quando un utente apre un messaggio di canale, ma non risponde o quando viene ricevuto un messaggio privato e viene letto ma non risposto. |
|||