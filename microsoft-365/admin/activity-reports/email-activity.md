---
title: Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di posta elettronica
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Informazioni su come ottenere un rapporto attività di posta elettronica utilizzando il Dashboard Microsoft 365 Reports nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 2cdf20014b04010e1912fbc41ec6f4ce61eaaca1
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "43046832"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di posta elettronica

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
È ad esempio possibile ottenere una panoramica del traffico di posta elettronica nell'organizzazione nella pagina Report e quindi usare il widget analitico Attività posta elettronica per comprendere le tendenze e i dettagli a livello di singolo utente dell'attività di posta elettronica nell'organizzazione.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report. 

## <a name="how-to-get-to-the-email-activity-report"></a>Come accedere al report attività di posta elettronica

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare attività di **Exchange** \> **posta elettronica**di Exchange.
  
## <a name="interpret-the-email-activity-report"></a>Interpretare il report attività di posta elettronica

Per visualizzare l'attività di posta elettronica dell'utente, è possibile esaminare i grafici **Attività** e **Utenti**. 
  
![Report attività di posta elettronica](../../media/21c1e082-317e-4b5e-b736-661ca5744def.png)
  
|||
|:-----|:-----|
|1.  <br/> |Il report **Attività posta elettronica** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |Il grafico **Attività** consente di interpretare la tendenza delle attività di posta elettronica all'interno dell'organizzazione, suddividendo le attività correlate ai messaggi di posta elettronica inviati, letti o ricevuti.<br/> |
|4.  <br/> |Il grafico **Utenti** consente di interpretare la tendenza degli utenti che generano le attività di posta elettronica, esaminando gli utenti che eseguono attività di invio, lettura e ricezione di messaggi di posta elettronica.<br/> |
|5.  <br/> | Nel grafico **Attività** l'asse Y indica il numero delle attività di invio, ricezione e lettura di messaggi di posta elettronica.  <br/>  Nel grafico **Utenti** l'asse Y rappresenta l'utente che esegue l'attività di invio, ricezione e lettura di messaggi di posta elettronica.  <br/>  L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|6.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **attività** selezionare i grafici di filtro **inviati**, **ricevuti**o **letti** ![per dati](../../media/a3a9cb3d-b8b1-4c6a-9f6f-18aebf74c3a0.png) correlati specifici per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> |
|7.  <br/> | La tabella mostra un'analisi delle attività di posta elettronica a livello di utente. Sono indicati tutti gli utenti a cui è assegnato un prodotto Exchange unitamente alle relative attività di posta elettronica. <br/> <br/> **Nome utente** è l'indirizzo di posta elettronica dell'utente.  <br/> **Nome visualizzato** è il nome completo se l'utente.  <br/> **Eliminato** si riferisce all'utente il cui stato corrente è eliminato, ma che era attivo durante una parte del periodo oggetto del report.  <br/> **Data eliminazione** indica la data di eliminazione dell'utente.  <br/> **Data ultima attività** si riferisce all'ultima volta in cui l'utente ha eseguito un'attività di lettura o invio di messaggi di posta elettronica.  <br/> **Azioni di invio** è il numero di volte in cui un'azione di invio di un messaggio di posta elettronica è stata registrata per l'utente.  <br/> **Azioni di ricezione** è il numero di volte in cui un'azione di ricezione di un messaggio di posta elettronica è stata registrata per l'utente.  <br/> **Azioni di lettura** è il numero di volte in cui un'azione di lettura di un messaggio di posta elettronica è stata registrata per l'utente.  <br/> **Prodotto assegnato** sono i prodotti assegnati a questo utente.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come nascondere i dettagli a livello di utente** nei [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **Export** ![collegamento del pulsante](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) Esporta esportazione. Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   
Nota: il rapporto attività di posta elettronica è disponibile solo per le cassette postali associate a utenti che dispongono di licenze.
