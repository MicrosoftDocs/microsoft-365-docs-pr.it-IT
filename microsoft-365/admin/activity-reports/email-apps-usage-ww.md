---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di posta elettronica
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
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Informazioni su come ottenere il report di utilizzo delle app di posta elettronica per conoscere le app di posta elettronica che si connettono a Exchange Online e alla versione outlook in uso.
ms.openlocfilehash: f2a7b79a00b47896dac4427c532f85dccb931c60
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921986"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di posta elettronica

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report sull'utilizzo delle app di posta elettronica, è possibile vedere quante app di posta elettronica si connettono a Exchange Online. È anche possibile visualizzare le informazioni sulla versione delle app di Outlook usate dagli utenti, che consentirà di contattare gli utenti che usano versioni non supportate per consigliare l'installazione di versioni supportate di Outlook.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Come accedere al report delle app di posta elettronica

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Selezionare **Visualizza altro in** Attività di posta **elettronica.** 
3. **Nell'elenco a discesa Attività di** posta elettronica selezionare Utilizzo delle app di posta elettronica di **Exchange.** \> 
  
## <a name="interpret-the-email-apps-report"></a>Interpretare il report delle app di posta elettronica

È possibile visualizzare l'attività delle app di posta elettronica esaminando i grafici **Utenti** **e** Client. 
  
![Client di posta elettronica utilizzati](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il **report sull'utilizzo delle** app di posta elettronica può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |I dati in ogni report in genere riguardano fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |La visualizzazione **Utenti** mostra il numero di utenti univoci che si sono connessi a Exchange Online con qualsiasi app di posta elettronica.  <br/> |
|4.  <br/> |La visualizzazione **App** mostra il numero di utenti univoci per ogni app nel periodo di tempo selezionato.  <br/> |
|5.  <br/> |La **visualizzazione** Versioni mostra il numero di utenti univoci per ogni versione di Outlook in Windows.  <br/> |
|6.  <br/> | Nel grafico **Utenti** l'asse Y rappresenta il numero totale di utenti univoci che si sono connessi a un'app in qualsiasi giorno del periodo di riferimento.  <br/>  Nel grafico **Utenti** l'asse X rappresenta il numero totale di utenti univoci che hanno usato l'app in tale periodo di riferimento.  <br/>  Nel grafico **App** l'asse Y rappresenta il numero totale di utenti univoci che hanno usato un'app specifica durante il periodo di riferimento.  <br/>  Nel grafico **App** l'asse X è l'elenco di app nella propria organizzazione.  <br/>  Nel grafico **Versioni** l'asse Y è il numero totale di utenti univoci che usano una versione specifica di Outlook per il desktop. Se il report non è in grado di risolvere il numero di versione di Outlook, la quantità verrà visualizzata **come Non determinato.**  <br/>  Nel grafico **Versioni** l'asse X è l'elenco di app nella propria organizzazione.  <br/> |
|7.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda.  <br/> |
|8.  <br/> | Non tutti gli elementi saranno visibili nelle colonne dell'elenco finché non verranno aggiunti.<br/> **Il nome** utente è il nome del proprietario dell'app di posta elettronica.  <br/> **La data dell'ultima** attività è l'ultima data in cui l'utente ha letto o inviato un messaggio di posta elettronica.  <br/> **Mac mail**, **Outlook per Mac** e **Outlook**, **Outlook Mobile** e **Outlook sul Web** sono alcuni esempi di app di posta elettronica che potrebbero essere presenti nell'organizzazione.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come nascondere i dettagli** a livello di utente nei report attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|9.  <br/> |Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report sull'utilizzo delle app di posta elettronica - scegliere le colonne](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)|
|10.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   
