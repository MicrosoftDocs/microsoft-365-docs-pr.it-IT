---
title: Microsoft 365 Report nell'interfaccia di amministrazione - report sull Yammer di utilizzo dei dispositivi
f1.keywords:
- NOCSH
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
description: Ottieni il Yammer di utilizzo dei dispositivi per sapere su quali dispositivi gli utenti usano Yammer dispositivi.
ms.openlocfilehash: 817627cac791d35f49cd240ceb48de15ef328ef8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241845"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365 Report nell'interfaccia di amministrazione - report sull Yammer di utilizzo dei dispositivi

Il dashboard Microsoft 365 **report mostra** la panoramica dell'attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
I report sull'utilizzo di dispositivi Yammer forniscono informazioni sui dispositivi su cui gli utenti usano Yammer. È possibile visualizzare il numero di utenti giornalieri per tipo di dispositivo e il numero di utenti per il tipo di dispositivo in un periodo di tempo selezionato. È anche possibile visualizzare i dettagli per ogni utente.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Come si ottiene il report sull'utilizzo di dispositivi Yammer?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
2. Nella home page del dashboard fai clic sul **pulsante** Visualizza altro nella scheda Yammer dashboard.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretare il report Yammer utilizzo dei dispositivi

Puoi visualizzare l'utilizzo nel report OneDrive selezionando la **scheda Uso del** dispositivo.<br/>![Microsoft 365 report - Report sull'utilizzo Yammer dispositivo Microsoft.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Yammer utilizzo del dispositivo - scegliere le colonne](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

È inoltre possibile esportare i dati del report in Excel .csv file selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
  
|Elemento|Descrizione|
|:-----|:-----|
|**Metrica**|**Definizione**|
|Username  <br/> |Indirizzo di posta elettronica dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo. Questa griglia mostra gli utenti che hanno effettuato l'Yammer utilizzando l'account Microsoft 365 o che hanno effettuato l'accesso alla rete con single sign-on. <br/> |
|Nome visualizzato  <br/> |Nome completo dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo.  <br/> |
|Stato dell'utente  <br/> |Uno dei tre valori seguenti: Active, Deleted o Suspended. Questi report mostrano i dati relativi agli utenti attivi, sospesi ed eliminati. Gli utenti in sospeso sono esclusi, in quanto non possono pubblicare, leggere o aggiungere Mi piace a un messaggio.   <br/> |
|Data modifica stato (UTC)  <br/> |Data in cui lo stato dell'utente è stato modificato in Yammer.  <br/> |
|Data ultima attività (UTC)  <br/> |Data dell'ultima data (UTC) a cui l'utente ha partecipato a un'Yammer attività.  <br/> |
|Web  <br/> |Indica se l'utente ha utilizzato Yammer sul Web.  <br/> |
|Windows telefono  <br/> | Indica se l'utente ha usato Yammer telefono Windows telefono.  <br/> |
|Telefono Android  <br/> |Indica se l'utente ha usato Yammer su un telefono Android. <br/>|
|iphone <br/> | Indica se l'utente ha usato Yammer su un iPhone.  <br/> |
|ipad  <br/> |Indica se l'utente ha utilizzato Yammer su un iPad. <br/>|
|other  <br/> |Indica se l'utente ha usato Yammer su un altro dispositivo, non elencato in precedenza. <br/>|
|||