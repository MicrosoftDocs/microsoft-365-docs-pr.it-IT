---
title: Report avanzati di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c3bd87f6a6b06cf6fc75705073df5a95a1025a31
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079955"
---
# <a name="advanced-ediscovery-reports-preview"></a>Report avanzati di eDiscovery (anteprima)

I report avanzati di eDiscovery consentono di aggregare i dati dei casi nell'organizzazione per semplificare l'analisi dei dati e la creazione di report organizzativi. La funzionalità Advanced eDiscovery Reports include numerosi report incorporati che consentono di rispondere a domande quali:

- Quanti depositari attivi sono presenti per tutti i casi nell'organizzazione?

- Quante origini dati sono in attesa per tutti i casi nell'organizzazione?

- Quante notifiche di blocco sono state rilasciate nell'ultimo mese per tutti i casi nell'organizzazione?

- Quanti casi attivi e chiusi sono presenti nell'organizzazione?

## <a name="before-you-begin"></a>Informazioni preliminari

- Per accedere ai report avanzati di eDiscovery, è necessario essere membri del gruppo di ruoli amministratore di eDiscovery. Essere membri di questo gruppo di ruolo fornisce le autorizzazioni necessarie per visualizzare, filtrare ed esportare i dati nei rapporti. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).

- I report avanzati di eDiscovery vengono aggiornati ogni giorno. Di conseguenza, è possibile che si verifichi un ritardo quando vengono creati nuovi casi, depositari, origini dati e comunicazioni e quando vengono visualizzati nel rapporto corrispondente.

Per accedere ai report avanzati di eDiscovery:

1. Passare a https://protection.office.com.
  
2. Accedere a Office 365 utilizzando l'account aziendale o dell'Istituto di istruzione.
  
3. Nel centro sicurezza & conformità, fare clic su **eDiscovery > Advanced eDiscovery**.
  
   Nella Home page di **Advanced eDiscovery** , le schede case, custode, origine dati e report comunicazioni vengono visualizzate nella parte superiore della pagina. 
  
   ![Rapporti avanzati di eDiscovery nella Home page](../media/report-home.png)

5. Per visualizzare un report, fare clic su una scheda report e quindi, se necessario, è possibile eseguire una delle operazioni seguenti:

   ![È possibile filtrare o scaricare i dati dei report](../media/AeDReportsFilterDownload.png)

   a. Fare clic su **filtro** per limitare i dati del report. È possibile filtrare in base a proprietà diverse per ogni report.
  
   b. Fare clic su **Download in CSV** per esportare i dati del report in un file CSV.

## <a name="case-report"></a>Rapporto di caso

Il rapporto case aggrega le informazioni sui casi di eDiscovery Advance attivi e chiusi nell'organizzazione.

|Colonna        |Descrizione|
|:-------------|:-------------|
|ID maiuscole/minuscole | Identificatore univoco per ogni caso.| 
|Nome del caso | Nome definito dall'utente del caso.|
|Stato | Indica se il caso è attivo o chiuso.|
|Data creazione |Data e ora in cui è stato creato il caso. Le date sono in formato UTC.|
|Data ultima modifica |La data in cui il caso è stato chiuso o ultimo aggiornamento. Le date sono in formato UTC.| 
|||

## <a name="custodian-report"></a>Report del custode

Nel flusso di lavoro di eDiscovery, gli utenti che sono oggetto di un caso legale o di un'indagine sono denominati *depositari dei dati* (o solo *depositari*) e sono definiti come "persone che hanno il controllo amministrativo di un documento o di un file elettronico". Il rapporto depositaria consente di identificare tutti i depositari le cui origini dati vengono conservate per tutti i casi nell'organizzazione.

|Colonna         |Descrizione|
|:-------------|:-------------|
|Nome del custode| Nome del custode in Active Directory.|
|UPN del custode | Nome dell'entità utente del custode.|
|ID custode | Identificatore univoco per il custode all'interno di un caso specifico. |
|Nome del caso | Nome definito dall'utente del caso.|
|Stato del blocco | Indica se il custode è attualmente in attesa o se sono stati rilasciati dal caso.|
|ID maiuscole/minuscole | Identificatore univoco del caso.|
|Stato comunicazione |Indica se il custode ha emesso una notifica di conservazione legale o meno. |
|Custode aggiunto | La data in cui il custode è stato aggiunto al caso. Le date sono in formato UTC.|
|||

## <a name="data-source-report"></a>Report origine dati

È possibile utilizzare un caso avanzato di eDiscovery per creare le esenzioni per conservare il contenuto che potrebbe essere pertinente al caso. Utilizzando le funzionalità avanzate di archiviazione di eDiscovery, è possibile applicare le esenzioni ai depositari e alle relative origini dati. Inoltre, è possibile applicare un blocco non detentivo alle cassette postali e agli account di OneDrive for business. È possibile utilizzare il rapporto origini dati per aggregare i dettagli sui percorsi di contenuto in attesa per tutti i casi nell'organizzazione.

|Colonna        |Descrizione|
| -------------|-------------|
|ID maiuscole/minuscole |Identificatore univoco per ogni caso. |
|Carico di lavoro |Indica il tipo di percorso del contenuto posizionato in attesa (ad esempio, Exchange o SharePoint).
|Nome percorso |Indica l'indirizzo SMTP (per le cassette postali di Exchange) o l'URL (per i siti di SharePoint) del percorso del contenuto. | 
|ID custode |Se l'origine dati appartiene a un custode, in questa colonna viene visualizzato l'identificatore univoco per il custode in un caso specifico. Questa colonna sarà null per i percorsi non detentivi.|
|Nome del custode |Nome del custode in Active Directory.| 
|Nome del caso |Nome definito dall'utente del caso.| 
|Stato |Indica se il percorso del contenuto è attualmente in attesa. | 
|ID criterio di blocco |Identificatore univoco per il blocco che contiene il percorso del contenuto. | 
|Data di creazione di esenzioni |Indica la data in cui è stato creato il criterio di conservazione. Le date sono in formato UTC. | 
|Nome del criterio di blocco |Nome dell'esenzione che contiene il percorso del contenuto. |
|Mantenere la data di modifica |Data dell'Ultima modifica dell'esenzione. Le date sono in formato UTC.| 
|Archiviazione Ultima modifica|Nome dell'utente che ha modificato l'ultimo blocco.| 
|||

## <a name="communication-report"></a>Report di comunicazione

L'organizzazione può emettere avvisi di conservazione per informare i depositari dell'obbligo di conservare informazioni rilevanti come parte di un caso legale o di un'indagine. È possibile utilizzare il report comunicazioni per visualizzare i dati di aggregazione sui riconoscimenti, i promemoria, le escalation e altri tipi di comunicazioni.

|Colonna         |Descrizione|
| -------------|-------------|
|ID maiuscole/minuscole | Identificatore univoco del caso.|
|Nome del caso | Nome definito dall'utente del caso.|
|ID custode |Identificatore univoco per il custode in un caso specifico.|
|Nome del custode |Nome del custode.|
|Tipo di avviso |Indica il tipo di avviso emesso per il custode.|
|Responsabile del rilascio |Nome dell'utente che ha emesso la notifica di blocco legale.|
|Evento di notifica|Indica il messaggio di notifica di archiviazione legale inviato all'utente. I valori possibili sono: promemoria, escalation, riconoscimento e rilascio di esenzioni.|
|Data di invio |La data in cui è stata emessa la comunicazione. Per i ringraziamenti, questa colonna indica l'ora in cui l'avviso è stato riconosciuto dal custode. Le date sono in formato UTC.|
|||
