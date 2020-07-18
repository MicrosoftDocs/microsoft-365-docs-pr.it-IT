---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-attività utente di Microsoft teams-anteprima
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
ms.openlocfilehash: 734a4dfd62160c2f4d29b8faffb3268a1962fe4f
ms.sourcegitcommit: a50260b7c5be7374e8e2bea19cc08406ef51ac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "45167342"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity--preview"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-attività utente di Microsoft teams-anteprima

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività degli utenti di Microsoft Teams è possibile ottenere informazioni approfondite sull'attività di Microsoft Teams nell'organizzazione.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-to-get-to-the-preview-microsoft-teams-user-activity-report"></a>Come accedere al report sull'attività degli utenti di Microsoft teams Preview

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Nell'elenco **a discesa selezionare un report** selezionare **Microsoft teams**.
  
## <a name="interpret-the-preview-microsoft-teams-user-activity-report"></a>Interpretare l'anteprima del rapporto attività utente di Microsoft Teams

È possibile visualizzare l'attività utente nel rapporto anteprima teams scegliendo la scheda **attività utente** .
  
|||
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
|Altre attività|L'utente è considerato attivo ma ha un valore pari a zero per i messaggi di chat, 1:1 chiamate, messaggi di canale, riunioni totali e riunioni organizzate. Esempi di azioni si verificano quando il client Microsoft teams viene attivato in primo piano, le azioni sono state eseguite nell'area di composizione dei messaggi, i toast sono stati visualizzati nel client Microsoft teams, i banner sono stati mostrati nel client Microsoft teams e così via. |
|||