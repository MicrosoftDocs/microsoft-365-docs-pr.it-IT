---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo delle cassette postali
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
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Informazioni su come ottenere il report sull'utilizzo delle cassette postali per conoscere le attività degli utenti con una cassetta postale utente.
ms.openlocfilehash: d7d36359801fe72ac1c3ffc210c7795030f0b2e2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241306"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo delle cassette postali

Il **report sull'utilizzo delle cassette postali** fornisce informazioni sugli utenti che dispongono di una cassetta postale utente e il livello di attività in base all'attività di invio, lettura, creazione appuntamento, invio riunione, accettazione riunione, declino riunione e annullamento riunione. Fornisce anche informazioni sullo spazio di archiviazione usato da ogni cassetta postale utente e sul numero di cassette postali che hanno quasi raggiunto le quote di archiviazione. 
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint o Skype for business per visualizzare i report. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Come accedere al report sull'utilizzo delle cassette postali

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **utilizzo delle cassette postali**di **Exchange** \> .
  
## <a name="interpret-the-mailbox-usage-report"></a>Interpretare il report sull'utilizzo delle cassette postali

È possibile ottenere una panoramica sull' **utilizzo delle cassette postali** dell'organizzazione esaminando i grafici **Cassetta postale**, **Spazio di archiviazione** e **Quota**. 
  
|||
|:-----|:-----|
|1.  <br/> |Il report **Utilizzo delle cassette postali** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |Il grafico Cassetta postali mostra il numero totale di cassette postali utente nell'organizzazione e il numero totale di cassette attive in un determinato giorno del periodo oggetto del report. Una cassetta postale utente è considerata attiva se dispone di un messaggio di posta elettronica di invio, lettura, creazione appuntamento, invio riunione, accettazione riunione, declino riunione e annullamento riunione.  <br/> |
|4.  <br/> |Il grafico **Spazio di archiviazione** mostra la quantità di spazio di archiviazione usata nell'organizzazione. Il grafico di archiviazione non include cassette postali di archiviazione. Per ulteriori informazioni sull'archiviazione automatica, vedere [Overview of Unlimited Archiving in Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/unlimited-archiving).<br/> |
|5.  <br/> | Il grafico **Quota** mostra il numero di cassette postali utente in ogni categoria di quota. Sono disponibili quattro categorie di quota:  <br/>  Buona: numero di utenti il cui spazio di archiviazione è inferiore alla Quota per inviare avviso.  <br/>  Avviso: numero di utenti il cui spazio di archiviazione usato è pari o superiore alla Quota per inviare avviso, ma inferiore alla Quota per impedire invio  <br/>  Non è possibile inviare: numero di utenti il cui spazio di archiviazione usato è pari o superiore alla Quota per impedire invio, ma inferiore alla Quota per impedire invio/ricezione  <br/>  Non è possibile inviare/ricevere: numero di utenti il cui spazio di archiviazione usato è pari o superiore alla Quota per impedire invio/ricezione  <br/> |
|6.  <br/> | Nel grafico **Cassetta postale** l'asse Y è il numero di cassette postali utente.  <br/>  Nel grafico **Spazio di archiviazione** l'asse Y è la quantità di spazio di archiviazione usata dalle cassette postali utente nell'organizzazione.  <br/>  Nel grafico **Quota** l'asse Y è il numero di cassette postali utente in ogni quota di archiviazione.  <br/>  L'asse X nei grafici Cassetta postale e Spazio di archiviazione rappresenta l'intervallo di date selezionato per il report specifico.  <br/>  L'asse X nei grafici Quota è la categoria di quota.  <br/> |
|7.  <br/> |È possibile filtrare i grafici visualizzati selezionando un elemento nella legenda.  <br/> |
|8.  <br/> | La tabella mostra un'analisi dell'utilizzo delle cassette postali a livello di utente. È possibile aggiungere altre colonne alla tabella.  <br/> **Nome utente** è l'indirizzo di posta elettronica dell'utente.  <br/> **Nome visualizzato** è il nome completo dell'utente.  <br/> **Eliminato** si riferisce alla cassetta postale il cui stato corrente è eliminato, ma che era attiva durante una parte del periodo oggetto del report.  <br/> **Data eliminazione** indica la data di eliminazione della cassetta postale.  <br/> **Data di creazione** indica la data di creazione della cassetta postale.  <br/> **Data ultima attività** indica la data in cui è stata eseguita un'attività di invio o lettura di un messaggio di posta elettronica nella cassetta postale.  <br/> **Numero di elementi** indica il numero totale di elementi nella cassetta postale.  <br/> **Spazio di archiviazione usato (MB)** indica lo spazio di archiviazione totale usato.  <br/> **Conteggio elementi eliminati** indica il numero totale di elementi eliminati nella cassetta postale. <br/> La **dimensione dell'elemento eliminato (MB)** si riferisce alla dimensione totale di tutti gli elementi eliminati nella cassetta postale. <br/> **Quota per inviare avviso (MB)** indica il limite dello spazio di archiviazione raggiunto il quale il proprietario della cassetta postale riceve un avviso che lo avverte che sta per raggiungere la quota di archiviazione.  <br/> **Quota per impedire invio (MB)** indica il limite dello spazio di archiviazione raggiunto il quale la cassetta postale non può più inviare messaggi di posta elettronica.  <br/> **Quota per impedire invio/ricezione (MB)** indica il limite dello spazio di archiviazione raggiunto il quale la cassetta postale non può più inviare o ricevere messaggi di posta elettronica.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Consultare i **Dettagli dell'utente Hide nella sezione Reports** nei [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** .  <br/> |
|||
   

