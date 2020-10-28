---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-report sull'utilizzo di dispositivi Yammer
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
description: Ottenere il report sull'utilizzo di dispositivi di Yammer per conoscere i dispositivi su cui gli utenti utilizzano Yammer.
ms.openlocfilehash: fae76e9ef769248217140c059004efc7ad330928
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779385"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-report sull'utilizzo di dispositivi Yammer

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
I report sull'utilizzo di dispositivi Yammer forniscono informazioni sui dispositivi su cui gli utenti usano Yammer. È possibile visualizzare il numero di utenti giornalieri per tipo di dispositivo e il numero di utenti per il tipo di dispositivo in un periodo di tempo selezionato. È anche possibile visualizzare i dettagli per ogni utente.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Come si ottiene il report sull'utilizzo di dispositivi Yammer?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella Home page del dashboard, fare clic sul pulsante **Visualizza altro** sulla scheda Yammer.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretare il report sull'utilizzo di dispositivi Yammer

È possibile visualizzare l'utilizzo nel report OneDrive scegliendo la scheda **utilizzo dispositivo** .<br/>![Microsoft 365 Reports-report sull'utilizzo di dispositivi di Microsoft Yammer.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report sull'utilizzo di dispositivi di Yammer-scegliere colonne](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Nome utente  <br/> |L'indirizzo di posta elettronica dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo. Questa griglia consente di visualizzare gli utenti che hanno effettuato l'accesso a Yammer utilizzando l'account Microsoft 365 o che hanno effettuato l'accesso alla rete tramite Single Sign-on. <br/> |
|Nome visualizzato  <br/> |Nome completo dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo.  <br/> |
|Stato dell'utente  <br/> |Uno dei tre valori seguenti: attivo, eliminato o sospeso. Questi report mostrano i dati relativi agli utenti attivi, sospesi ed eliminati. Gli utenti in sospeso sono esclusi, in quanto non possono pubblicare, leggere o aggiungere Mi piace a un messaggio.   <br/> |
|Data modifica stato (UTC)  <br/> |La data in cui lo stato dell'utente è stato modificato in Yammer.  <br/> |
|Data ultima attività (UTC)  <br/> |Data e ora UTC in cui l'utente ha partecipato a un'attività di Yammer.  <br/> |
|Web  <br/> |Indica se l'utente ha utilizzato Yammer sul Web.  <br/> |
|Windows Phone  <br/> | Indica se l'utente ha utilizzato Yammer in un Windows Phone.  <br/> |
|Telefono Android  <br/> |Indica se l'utente ha usato Yammer in un telefono Android. <br/>|
|iPhone <br/> | Indica se l'utente ha utilizzato Yammer su un iPhone.  <br/> |
|iPad  <br/> |Indica se l'utente ha utilizzato Yammer su un iPad. <br/>|
|altri  <br/> |Indica se l'utente ha utilizzato Yammer in un altro dispositivo, non elencato in precedenza. <br/>|
|||