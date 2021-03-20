---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali
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
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Informazioni su come ottenere un rapporto sull'utilizzo delle cassette postali per conoscere le attività degli utenti con una cassetta postale utente.
ms.openlocfilehash: 13a2d2382799052423300f72e8af0df1ca596bb6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904565"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali

Il report Utilizzo **cassetta** postale fornisce informazioni sugli utenti con una cassetta postale utente e sul livello di attività di ognuno in base all'invio e-mail, alla lettura, alla creazione di un appuntamento, all'invio di riunioni, all'accettazione di riunioni, al rifiuto della riunione e all'annullamento dell'attività di riunione. Fornisce anche informazioni sullo spazio di archiviazione usato da ogni cassetta postale utente e sul numero di cassette postali che hanno quasi raggiunto le quote di archiviazione. 
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Come accedere al report sull'utilizzo delle cassette postali

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.
2. Selezionare **Visualizza altro in** Attività di posta **elettronica.** 
3. **Nell'elenco a discesa Attività** di posta elettronica selezionare Utilizzo cassetta postale di **Exchange** \> .

## <a name="interpret-the-mailbox-usage-report"></a>Interpretare il report sull'utilizzo delle cassette postali

È possibile ottenere una panoramica sull' **utilizzo delle cassette postali** dell'organizzazione esaminando i grafici **Cassetta postale**, **Spazio di archiviazione** e **Quota**. 
  
![Report utilizzo cassetta postale](../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png)

|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report **Utilizzo delle cassette postali** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, nella tabella verranno visualizzati i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |I dati in ogni report in genere coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |Il grafico Cassetta postali mostra il numero totale di cassette postali utente nell'organizzazione e il numero totale di cassette attive in un determinato giorno del periodo oggetto del report. Una cassetta postale utente è considerata attiva se aveva un messaggio di posta elettronica per inviare, leggere, creare un appuntamento, inviare una riunione, accettare una riunione, rifiutare la riunione e annullare l'attività riunione.  <br/> |
|4.  <br/> |Il grafico **Spazio di archiviazione** mostra la quantità di spazio di archiviazione usata nell'organizzazione. Il grafico di archiviazione non include le cassette postali di archiviazione. Per ulteriori informazioni sull'espansione automatica dell'archiviazione, vedere [Panoramica dell'archiviazione illimitata in Microsoft 365.](../../compliance/unlimited-archiving.md)<br/> |
|5.  <br/> | Il grafico **Quota** mostra il numero di cassette postali utente in ogni categoria di quota. Sono disponibili quattro categorie di quota:  <br/>  Buona: numero di utenti il cui spazio di archiviazione è inferiore alla Quota per inviare avviso.  <br/>  Avviso: numero di utenti il cui spazio di archiviazione usato è pari o superiore alla Quota per inviare avviso, ma inferiore alla Quota per impedire invio  <br/>  Non è possibile inviare: numero di utenti il cui spazio di archiviazione usato è pari o superiore alla Quota per impedire invio, ma inferiore alla Quota per impedire invio/ricezione  <br/>  Non è possibile inviare/ricevere: numero di utenti il cui spazio di archiviazione usato è pari o superiore alla Quota per impedire invio/ricezione  <br/> |
|6.  <br/> | Nel grafico **Cassetta postale** l'asse Y è il numero di cassette postali utente.  <br/>  Nel grafico **Spazio di archiviazione** l'asse Y è la quantità di spazio di archiviazione usata dalle cassette postali utente nell'organizzazione.  <br/>  Nel grafico **Quota** l'asse Y è il numero di cassette postali utente in ogni quota di archiviazione.  <br/>  L'asse X nei grafici Cassetta postale e Spazio di archiviazione rappresenta l'intervallo di date selezionato per il report specifico.  <br/>  L'asse X nei grafici Quota è la categoria di quota.  <br/> |
|7.  <br/> |È possibile filtrare i grafici visualizzati selezionando un elemento nella legenda.  <br/> |
|8.  <br/> | La tabella mostra un'analisi dell'utilizzo delle cassette postali a livello di utente. È possibile aggiungere altre colonne alla tabella.  <br/> **Nome utente** è l'indirizzo di posta elettronica dell'utente.  <br/> **Nome visualizzato** è il nome completo dell'utente.  <br/> **Eliminato** si riferisce alla cassetta postale il cui stato corrente è eliminato, ma che era attiva durante una parte del periodo oggetto del report.  <br/> **Data eliminazione** indica la data di eliminazione della cassetta postale.  <br/> **Data di creazione** indica la data di creazione della cassetta postale.  <br/> **Data ultima attività** indica la data in cui è stata eseguita un'attività di invio o lettura di un messaggio di posta elettronica nella cassetta postale.  <br/> **Numero di elementi** indica il numero totale di elementi nella cassetta postale.  <br/> **Spazio di archiviazione usato (MB)** indica lo spazio di archiviazione totale usato.  <br/> **Conteggio elementi eliminati** indica il numero totale di elementi eliminati nella cassetta postale. <br/> **Dimensione elementi eliminati (MB)** si riferisce alla dimensione totale di tutti gli elementi eliminati nella cassetta postale. <br/> **Quota per inviare avviso (MB)** indica il limite dello spazio di archiviazione raggiunto il quale il proprietario della cassetta postale riceve un avviso che lo avverte che sta per raggiungere la quota di archiviazione.  <br/> **Quota per impedire invio (MB)** indica il limite dello spazio di archiviazione raggiunto il quale la cassetta postale non può più inviare messaggi di posta elettronica.  <br/> **Quota per impedire invio/ricezione (MB)** indica il limite dello spazio di archiviazione raggiunto il quale la cassetta postale non può più inviare o ricevere messaggi di posta elettronica.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la **sezione Nascondere i dettagli dell'utente nei report** nei report attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|9.  <br/> |Selezionare **Scegli colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Report sull'utilizzo delle cassette postali - scegliere le colonne](../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png)|
|10.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.**  <br/> |
|||
