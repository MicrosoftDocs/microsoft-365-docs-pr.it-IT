---
title: Visualizzare l'attività di controllo di persone di interesse
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
ms.openlocfilehash: 7b7109f2a14e2d215573cfe461fc64676d4247c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626322"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a>Visualizzare l'attività di controllo di persone di interesse

Se è necessario verificare se un utente ha visualizzato un documento specifico o ha eliminato un elemento dalla cassetta postale, Indagini sui dati (Preview) è ora integrato con lo strumento di ricerca del registro di controllo esistente nel centro sicurezza & conformità. Usando questa esperienza incorporata, è possibile utilizzare lo strumento di gestione dei dati (Preview) People of interest Management Tool per facilitare le indagini, accedendo facilmente e ricercando le attività per gli utenti di interesse all'interno dell'indagine.

## <a name="before-you-begin"></a>Prima di iniziare

Per eseguire la ricerca nel registro di controllo, è necessario essere assegnati al ruolo di controllo di sola visualizzazione o ai registri di controllo in Exchange Online. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina Autorizzazioni nell'Interfaccia di amministrazione di Exchange. Per concedere a un utente la possibilità di eseguire ricerche nel log di controllo (anteprima) dei dati con il livello minimo di privilegi, è possibile creare un gruppo di ruoli personalizzato in Exchange Online, aggiungere i registri di controllo o i registri di controllo e quindi aggiungere l'utente come membro del nuovo gruppo di ruoli. Per altre informazioni, vedere Gestire i gruppi di ruoli in Exchange Online.

> [!IMPORTANT]
> Se si assegna a un utente il ruolo di controllo solo visualizzazione o log di controllo nella pagina autorizzazioni nel centro sicurezza & Compliance, non sarà possibile eseguire la ricerca nel registro di controllo. È necessario assegnare le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online.

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a>Passaggio 1: creare un'analisi dei dati (anteprima) ricerca del registro di controllo

   1. Selezionare un'analisi esistente dal **Centro sicurezza & conformità > indagini sui dati (Preview)**.
   
   2. Passare alla scheda **utenti** e selezionare una persona.
   
   3. Dopo aver selezionato una persona, fare clic su **Visualizza attività** dal riquadro dettagli.
   
   4. Configurare i criteri di ricerca seguenti: 
      
      a. **Attività** -fare clic sull'elenco a discesa per visualizzare le attività che è possibile cercare. Dopo aver eseguito la ricerca, vengono visualizzati solo i record di controllo per le attività selezionate. Se si seleziona **Mostra risultati per tutte le attività** , verranno visualizzati i risultati di tutte le attività che soddisfano gli altri criteri di ricerca.
      
      b. Data di **inizio e data di fine** : selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati entro quel periodo. Gli ultimi sette giorni sono selezionati per impostazione predefinita. La data e l'ora sono specificate in formato UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare è di un anno.
      
      c. **People of interest** -fare clic in questa casella e quindi selezionare un custode specifico per visualizzare i risultati della ricerca. I record di controllo per l'attività selezionata eseguita dagli utenti selezionati in questa casella vengono visualizzati nell'elenco dei risultati.
    
    1. Fare clic su **Cerca** per eseguire la ricerca usando i criteri di ricerca. I risultati della ricerca vengono caricati e, dopo alcuni istanti, vengono visualizzati in risultati nella pagina ricerca attività persone di interesse. 

## <a name="step-2-view-the-audit-log-search-results"></a>Passaggio 2: visualizzazione dei risultati di ricerca del registro di controllo

I risultati di una ricerca del registro di controllo vengono visualizzati nella pagina dei risultati nella pagina log di controllo persone interessate. Un massimo di 5.000 eventi (più recenti) viene visualizzato con incrementi di 150 eventi. Per visualizzare più eventi, è possibile usare la barra di scorrimento nel riquadro Risultati oppure è possibile premere MAIUSC+FINE per visualizzare i 150 eventi successivi.

I risultati contengono le seguenti informazioni su ogni evento restituito dalla ricerca.
- **Data**: data e ora (in formato UTC) in cui si è verificato l'evento.

- **Indirizzo IP**: indirizzo IP del dispositivo usato durante la registrazione dell'attività. L'indirizzo IP viene visualizzato in formato IPv4 o IPv6.

- **Utente**: utente (o account del servizio) che ha eseguito l'azione che ha attivato l'evento.

- **Attività**: attività eseguita dall'utente. Questo valore corrisponde alle attività selezionate nell'elenco a discesa Attività. Per un evento del log di controllo dell'amministratore di Exchange, il valore in questa colonna è un cmdlet di Exchange.

- **Elemento**: oggetto creato o modificato come risultato dell'attività corrispondente. Ad esempio, il file che è stato visualizzato o modificato oppure l'account utente che è stato aggiornato. Non tutte le attività presentano un valore in questa colonna.

- **Dettaglio**: informazioni aggiuntive su un'attività. Anche in questo caso, non tutte le attività avranno un valore.

## <a name="step-3-filter-the-search-results"></a>Passaggio 3: Filtrare i risultati della ricerca

Oltre a ordinare i risultati di una ricerca nel log di controllo, è anche possibile filtrarli. In questo modo è possibile filtrare rapidamente i risultati per un utente o un'attività specifica. 

Per filtrare i risultati:

 1. Creare ed eseguire una ricerca nel registro di controllo.
  
2. Quando vengono visualizzati i risultati, fare clic su **Filtra risultati**.
 
3. Sotto ogni intestazione di colonna vengono visualizzate le caselle delle parole chiave.
  
4. Fare clic su una delle caselle sotto un'intestazione di colonna e digitare una parola o una fase, a seconda della colonna in base a cui si sta filtrando. I risultati verranno riorganizzati dinamicamente per visualizzare gli eventi corrispondenti al filtro.
  
5. Per cancellare un filtro, fare clic sulla **X** nella casella filtro oppure fare clic su **Nascondi filtro**.

## <a name="export-the-search-results-to-a-file"></a>Esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca nel registro di controllo in un file con valori delimitati da virgole (CSV) nel computer locale. È possibile aprire il file in Microsoft Excel e utilizzare funzionalità quali la ricerca, l'ordinamento, il filtraggio e la suddivisione di una singola colonna (che contiene celle a più valori) in più colonne.

1. Eseguire una ricerca nel log di controllo e quindi modificare i criteri di ricerca fino a ottenere i risultati desiderati.
  
2. Fare clic su Esporta risultati e selezionare una delle opzioni seguenti:

    - **Salvare i risultati caricati:** Scegliere questa opzione per esportare solo le voci visualizzate sotto **risultati** nella pagina **Ricerca log di controllo utenti interessati** . Il file CSV che viene scaricato contiene le stesse colonne (e gli stessi dati) presenti nella pagina (Data, Utente, Attività, Elemento e Dettagli). Nel file CSV è inclusa una colonna aggiuntiva (intitolata **più**) che contiene ulteriori informazioni dalla voce del registro di controllo. Poiché si stanno esportando gli stessi risultati caricati (e visualizzabili) nella pagina Ricerca log di controllo, verranno esportate al massimo 5.000 voci.
        
    - **Scaricare tutti i risultati:** Scegliere questa opzione per esportare tutte le voci dal registro di controllo che soddisfano i criteri di ricerca. Per un set di risultati di ricerca di grandi dimensioni, scegliere questa opzione per scaricare tutte le voci dal registro di controllo oltre ai risultati di 5.000 che possono essere visualizzati nella pagina **di ricerca dei log di controllo di interesse personale** . Questa opzione consente di scaricare i dati non elaborati dal registro di controllo in un file CSV e contiene informazioni aggiuntive dalla voce del registro di controllo in una colonna denominata AuditData. Se si sceglie questa opzione di esportazione potrebbe essere necessario più tempo per scaricare il file, in quanto il file potrebbe essere molto più grande di quello scaricato scegliendo l'altra opzione.
    
      > [!IMPORTANT]
      > È possibile scaricare al massimo 50.000 voci in un file CSV da una singola ricerca nel log di controllo. Se vengono scaricate 50.000 voci nel file CSV, è probabile che ci siano più di 50.000 eventi che soddisfano i criteri di ricerca. Per eseguire l'esportazione oltre questo limite, provare a usare un intervallo di date per ridurre il numero di voci del log di controllo. Potrebbe essere necessario eseguire più ricerche con intervalli di date più piccoli per esportare più di 50.000 voci.
        

3. Dopo aver selezionato un'opzione di esportazione, nella parte inferiore della finestra viene visualizzato un messaggio in cui viene richiesto di aprire il file CSV, salvarlo nella cartella Downloads o salvarlo in una cartella specifica.

Per ulteriori informazioni sulla visualizzazione, il filtro o l'esportazione dei risultati di ricerca del registro di controllo, vedere [Search the audit log in the Office 365](search-the-audit-log-in-security-and-compliance.md).
