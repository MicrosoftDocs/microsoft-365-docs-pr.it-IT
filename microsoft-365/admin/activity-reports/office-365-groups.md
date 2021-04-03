---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Gruppi di Microsoft 365
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
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Ottenere un report sui gruppi di Microsoft 365 per conoscere i gruppi e le relative attività.
ms.openlocfilehash: 9ab034531099b5572c42eb3a48ec28d99487ac99
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579555"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Gruppi di Microsoft 365

Il **dashboard** dei report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Gruppi di Microsoft 365 è possibile ottenere informazioni dettagliate sull'attività dei gruppi nell'organizzazione e vedere quanti gruppi vengono creati e usati.
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business.  
  
## <a name="how-to-get-to-the-groups-report"></a>Come accedere al report gruppi

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

2. Nelle opzioni selezionare **Visualizza altro** in Utenti attivi - Servizi di Microsoft **365.**
3. **Nell'elenco a discesa Selezionare un report** selezionare Attività gruppi di Office **365.** \> 
  
## <a name="interpret-the-groups-report"></a>Interpretare il report dei gruppi

È possibile visualizzare l'attività dei gruppi esaminando i grafici **Gruppi,** **Attività,** **File** **e Archiviazione.** 
  
![Report di Microsoft 365 - attività dei gruppi](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report gruppi di **Microsoft 365** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data di generazione del report).  <br/> |
|2.  <br/> |I dati in ogni report in genere coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |La **visualizzazione** Gruppi mostra un numero totale di gruppi esistenti in un determinato giorno e gruppi attivi in tale giorno in base alle conversazioni di posta elettronica, ai post di Yammer e alle attività dei file di SharePoint e alle pagine di SharePoint visualizzate.  <br/> |
|4.  <br/> |La visualizzazione **Attività** mostra il numero di attività dei gruppi con tutti i carichi di lavoro di gruppo. È possibile visualizzare i messaggi di posta elettronica di Exchange ricevuti dalle cassette di posta elettronica di tutti i gruppi, in qualsiasi giorno durante il periodo di riferimento. È inoltre possibile visualizzare i messaggi inseriti, letti e apprezzati tra i gruppi di Yammer associati a un gruppo. <br/> |
|5.  <br/> |La **visualizzazione File** mostra il numero totale di file attivi e totali in tutti i siti di gruppo associati a un gruppo.  <br/> |
|6.  <br/> |La visualizzazione **Archiviazione** mostra lo spazio di archiviazione totale usato in tutte le cassette postali e in tutti i siti del gruppo.  <br/> |
|7.  <br/> | Nel grafico **Gruppi** l'asse Y rappresenta il numero di gruppi (che può essere visualizzato come confronto tra totali e attivi).  <br/>  Nel grafico **Attività,** l'asse Y è il numero di volte in cui un'attività è stata eseguita in gruppi.  <br/>  Nel grafico **File** l'asse Y rappresenta il numero di file totali o attivi.  <br/>  Nel grafico **Archiviazione** l'asse Y rappresenta lo spazio di archiviazione totale usato dalla cassetta postale o dal sito del gruppo.  <br/>  L'asse X in tutti e tre i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|8.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico  **Gruppi**  seleziona Totale o Totale attivo e Numero attivo di gruppi per visualizzare solo le informazioni correlate a ![ ognuno di ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> |
|9.  <br/> | L'elenco dei gruppi da mostrare dipende dal set di tutti i gruppi che erano presenti (che non sono stati eliminati) nel periodo di tempo di riferimento più ampio (180 giorni). Il numero di attività (le conversazioni di posta elettronica, i post di Yammer e le attività sui siti di SharePoint) varia in base alla selezione di date.  <br/> NOTA: potresti non visualizzare tutte le voci dell'elenco seguente nelle colonne finché non le aggiungi.<br/>**Nome gruppo** è il nome del gruppo.  <br/> **Eliminati** è il numero di gruppi eliminati. Se il gruppo viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con questo flag impostato su true.  <br/> **Proprietario del gruppo** è il nome del proprietario del gruppo.  <br/> **Data ultima attività** è l'ultima data in cui un messaggio è stato ricevuto dal gruppo. Si tratta dell'ultima data in cui si è verificata un'attività in una conversazione di posta elettronica, in Yammer o nel sito.  <br/> **Tipo** è il tipo di gruppo. Può essere privato o pubblico.  <br/> **Membri** è il numero di membri del gruppo.  <br/> **Membri esterni** è il numero di utenti esterni del gruppo.  <br/> **Exchange** <br/> **Messaggi ricevuti** è il numero di messaggi ricevuti dal gruppo.  <br/> **Totale elementi cassetta postale** è il numero di elementi presenti nella cassetta postale del gruppo.  <br/> **Spazio di archiviazione della cassetta postale usato** è lo spazio di archiviazione usato dalla cassetta postale del gruppo.  <br/> **File di SharePoint** <br/> **Totale file** è il numero di file archiviati nei siti del gruppo di SharePoint.  <br/> **File attivi** è il numero di file nel sito di gruppo di SharePoint che sono stati visualizzati, modificati, sincronizzati, condivisi internamente o esternamente durante il periodo di riferimento.  <br/> **Spazio di archiviazione del sito usato (MB)** è la quantità di spazio di archiviazione, in MB, usata durante il periodo di riferimento.  <br/> **Messaggi di Yammer** <br/> **Pubblicati** è il numero dei messaggi pubblicati nel gruppo di Yammer nel periodo di riferimento.  <br/> **Letti** è il numero delle conversazioni lette nel gruppo di Yammer nel periodo di riferimento.  <br/> **Apprezzati** è il numero dei messaggi con Mi piace nel gruppo di Yammer nel periodo di riferimento.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la **sezione Come nascondere i dettagli a livello di utente nelle** relazioni attività nell'interfaccia di amministrazione di Microsoft [365.](activity-reports.md)  <br/> |
|10,  <br/> |Selezionare o toccare **Il pulsante** Altre azioni OWA altre azioni accanto a un'intestazione di colonna per aggiungere o rimuovere colonne ![ dal ](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) report.  <br/> ![Report Gruppi - Scegliere le colonne](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|11,  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   
