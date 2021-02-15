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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Ottenere il report attività dei gruppi di Yammer per conoscere il numero di gruppi di Yammer creati e utilizzati nell'organizzazione e le relative attività.
ms.openlocfilehash: db2136e049e448b1727dc4612256288da2c64402
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779341"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Report attività dei gruppi di Yammer

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività dei gruppi di Yammer, è possibile ottenere informazioni approfondite sull'attività dei gruppi di Yammer nell'organizzazione e vedere quanti gruppi di Yammer vengono creati e usati.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>Come si ottiene il report attività dei gruppi di Yammer?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Dalla home page del dashboard, fare clic sul **pulsante Visualizza** altro nella scheda Yammer.

  
## <a name="interpret-the-yammer-groups-activity-report"></a>Interpretare il report Attività dei gruppi di Yammer

È possibile visualizzare le attività dei gruppi nel report di Yammer scegliendo la **scheda Attività** gruppi.<br/>![Report di Microsoft 365 - Report attività dei gruppi di Microsoft Yammer.](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività dei gruppi di Yammer - scegliere le colonne](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome del gruppo  <br/> |Nome del gruppo. <br/> |
|Amministratore del gruppo  <br/> |Nome dell'amministratore o del proprietario del gruppo.  <br/> |
|Eliminato  <br/> |Numero di gruppi di Yammer eliminati. Se il gruppo viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con questo flag impostato su true.  <br/> |
|Tipo  <br/> |Tipo di gruppo, pubblico o privato. <br/> |
|Connesso a Office 365  <br/> |Indica se il gruppo di Yammer è anche un gruppo di Microsoft 365. <br/> |
|Data ultima attività (UTC)  <br/> | La data più recente in cui un messaggio è stato letto, pubblicato o mi piace dal gruppo.  <br/> |
|Membri  <br/> | Numero di membri del gruppo.  <br/> |
|Pubblicato  <br/> |Numero di messaggi inseriti nel gruppo di Yammer nel periodo di segnalazione. <br/>|
|Lettura  <br/> |Numero di conversazioni lette nel gruppo di Yammer nel periodo di segnalazione.  <br/> |
|Mi piace  <br/> |Il numero di messaggi con mi piace nel gruppo yammer nel periodo di segnalazione. <br/>|
|Nome rete  <br/> |Nome completo della rete a cui appartiene il gruppo. |
|||