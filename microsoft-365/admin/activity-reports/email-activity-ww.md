---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di posta elettronica
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
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Informazioni su come ottenere un report attività di posta elettronica tramite il dashboard report di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 65ef74ccd05aa4b55fc127985c03a490bb109b4b
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921995"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di posta elettronica

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
È ad esempio possibile ottenere una panoramica del traffico di posta elettronica nell'organizzazione nella pagina Report e quindi usare il widget analitico Attività posta elettronica per comprendere le tendenze e i dettagli a livello di singolo utente dell'attività di posta elettronica nell'organizzazione.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business. 

## <a name="how-to-get-to-the-email-activity-report"></a>Come accedere al report attività di posta elettronica

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Selezionare **Visualizza altro in** Attività di posta **elettronica.** 
3. **Nell'elenco a discesa Attività** di posta elettronica selezionare Attività di posta elettronica di **Exchange.** \> 
  
## <a name="interpret-the-email-activity-report"></a>Interpretare il report attività di posta elettronica

Per visualizzare l'attività di posta elettronica dell'utente, è possibile esaminare i grafici **Attività** e **Utenti**. 
  
![Report attività di posta elettronica](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report **Attività posta elettronica** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |I dati in ogni report in genere riguardano fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |Il **grafico Attività** consente di comprendere la tendenza della quantità di attività di posta elettronica in corso nell'organizzazione. È possibile comprendere la suddivisione delle attività di invio, lettura, ricezione, creazione di riunioni o interazione della riunione tramite posta elettronica.  <br/> |
|4.  <br/> |Il **grafico Utente** consente di comprendere la tendenza della quantità di utenti univoci che generano le attività di posta elettronica. È possibile osservare la tendenza degli utenti che eseguono l'invio di posta elettronica, la lettura della posta elettronica, la ricezione della posta elettronica, la creazione di riunioni o le attività di interazione delle riunioni.  <br/> |
|5.  <br/> | Nel grafico **Attività,** l'asse Y è il conteggio delle attività del tipo di messaggio di posta elettronica inviato, ricevuto, letto e inviato tramite posta elettronica, riunione creata e riunione interagita.  <br/>  Nel grafico **attività Utenti,** l'asse Y è l'attività dell'utente che esegue il tipo di messaggio di posta elettronica inviato, ricevuto, letto e-mail, riunione creata o riunione interagita.  <br/>  L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|6.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda.  <br/> |
|7.  <br/> | La tabella mostra un'analisi delle attività di posta elettronica a livello di utente. Sono indicati tutti gli utenti a cui è assegnato un prodotto Exchange unitamente alle relative attività di posta elettronica. <br/> <br/> **Nome utente** è l'indirizzo di posta elettronica dell'utente.  <br/> **Il nome visualizzato** è il nome completo se l'utente.  <br/> **Eliminato** si riferisce all'utente il cui stato corrente è eliminato, ma che era attivo durante una parte del periodo oggetto del report.  <br/> **Data eliminazione** indica la data di eliminazione dell'utente.  <br/> **Data ultima attività** si riferisce all'ultima volta in cui l'utente ha eseguito un'attività di lettura o invio di messaggi di posta elettronica.  <br/> **Azioni di invio** è il numero di volte in cui un'azione di invio di un messaggio di posta elettronica è stata registrata per l'utente.  <br/> **Azioni di ricezione** è il numero di volte in cui un'azione di ricezione di un messaggio di posta elettronica è stata registrata per l'utente.  <br/> **Azioni di lettura** è il numero di volte in cui un'azione di lettura di un messaggio di posta elettronica è stata registrata per l'utente.  <br/> **Azioni create riunione è** il numero di volte in cui è stata registrata un'azione di invio di una convocazione di riunione per l'utente.  <br/> **Azioni interagite riunione** è il numero di volte in cui una convocazione di riunione accetta, provvisoria, rifiuta o annulla l'azione è stata registrata per l'utente.  <br/> **I prodotti** assegnati sono i prodotti assegnati a questo utente.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **Come nascondere i dettagli** a livello di utente nei report attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|8.  <br/> |Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report attività di posta elettronica - scegliere le colonne](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)|
|9.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   
> [!NOTE]
> Il report Attività di posta elettronica è disponibile solo per le cassette postali associate agli utenti che dispongono di licenze.
