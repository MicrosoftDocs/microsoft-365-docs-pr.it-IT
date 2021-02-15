---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Report attività di Yammer
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
description: Ottenere il report Attività di Yammer e saperne di più sul numero di utenti che usano Yammer per pubblicare, aggiungere mi piace o leggere un messaggio.
ms.openlocfilehash: fc6bf252892cc9b3f30cdcf464cd44cfc83c4f75
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779375"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Report attività di Yammer

In qualità di amministratore di Microsoft 365, il **dashboard** Report mostra i dati sull'utilizzo dei prodotti all'interno dell'organizzazione. Consultare i [report attività nell'interfaccia di amministrazione.](activity-reports.md) Il **report Attività su Yammer** consente di capire il livello di utilizzo di Yammer nell'organizzazione calcolando il numero di utenti che usano Yammer per pubblicare, aggiungere Mi piace o leggere un messaggio e la quantità di attività generata nell'intera organizzazione. 
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Come si ottiene il report attività di Yammer?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Dalla home page del dashboard, fare clic sul pulsante **Visualizza** altro nella scheda Yammer.

  
## <a name="interpret-the-yammer-activity-report"></a>Interpretare il report Attività in Yammer

È possibile visualizzare le attività nel report di Yammer scegliendo la **scheda** Attività.<br/>![Report di Microsoft 365 - Report attività di Microsoft Yammer.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività di Yammer - scegliere le colonne](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |Indirizzo di posta elettronica dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo. Questa griglia mostra gli utenti che hanno effettuato l'accesso a Yammer con l'account Di Microsoft 365 o che hanno effettuato l'accesso alla rete con single sign-on. <br/> |
|Nome visualizzato  <br/> |Nome completo dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo.  <br/> |
|Stato dell'utente  <br/> |Uno dei tre valori seguenti: Attivato, Eliminato o Sospeso. Questi report mostrano i dati relativi agli utenti attivi, sospesi ed eliminati. Gli utenti in sospeso sono esclusi, in quanto non possono pubblicare, leggere o aggiungere Mi piace a un messaggio.  <br/> |
|Data modifica stato (UTC)  <br/> |Data in cui lo stato dell'utente è stato modificato in Yammer.  <br/> |
|Data ultima attività (UTC)  <br/> | Data dell'ultima pubblicazione, lettura o mi piace di un messaggio da parte dell'utente.  <br/> |
|Pubblicato  <br/> |Numero di messaggi inseriti dall'utente durante il periodo di tempo specificato. <br/>|
|Lettura  <br/> |Numero di conversazioni lette dall'utente durante il periodo di tempo specificato.  <br/> |
|Mi piace  <br/> |Numero di messaggi apprezzati dall'utente durante il periodo di tempo specificato.  <br/>|
|Prodotto assegnato  <br/> |I prodotti assegnati a questo utente.|
|||