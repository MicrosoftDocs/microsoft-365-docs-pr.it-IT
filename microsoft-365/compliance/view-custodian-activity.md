---
title: Visualizzazione dell'attività di controllo del custode
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
ms.openlocfilehash: 91123838ec0ab649aca93bfd210b94d5a5cab3f8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084298"
---
# <a name="view-custodian-audit-activity"></a>Visualizzazione dell'attività di controllo del custode

È necessario individuare se un utente ha visualizzato un documento specifico o ha eliminato un elemento dalla propria cassetta postale? Advanced eDiscovery è ora integrato con lo strumento di ricerca del registro di controllo esistente nel centro sicurezza & Compliance. Usando questa esperienza incorporata, è possibile utilizzare lo strumento di gestione dei depositari di Advanced eDiscovery per facilitare le indagini, accedendo facilmente e ricercando l'attività dei depositari all'interno del caso.

## <a name="before-you-begin"></a>Informazioni preliminari

È necessario essere assegnati al ruolo di controllo di sola visualizzazione o ai registri di controllo in Exchange Online per eseguire una ricerca nel registro di controllo di Office 365. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina autorizzazioni nell'interfaccia di amministrazione di Exchange. Per concedere a un utente la possibilità di eseguire ricerche nel log di controllo avanzato di eDiscovery con il livello minimo di privilegi, è possibile creare un gruppo di ruoli personalizzato in Exchange Online, aggiungere i registri di controllo o i registri di controllo di sola visualizzazione e quindi aggiungere l'utente come membro del nuovo gruppo di ruoli. Per ulteriori informazioni, vedere gestire i gruppi di ruoli in Exchange Online.

> [!IMPORTANT]
> Se si assegna a un utente il ruolo di controllo solo visualizzazione o log di controllo nella pagina autorizzazioni nel centro sicurezza & Compliance, non sarà possibile eseguire la ricerca nel registro di controllo di Office 365. È necessario assegnare le autorizzazioni in Exchange Online. Ciò è dovuto al fatto che il cmdlet sottostante utilizzato per eseguire la ricerca nel registro di controllo è un cmdlet di Exchange Online.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Passaggio 1: ricerca del registro di controllo per le attività eseguite da un custode

1. Accedere a **eDiscovery > Advanced eDiscovery** e aprire il caso.
  
2. Fare clic sulla scheda **depositari** .
  
3. Selezionare un custode dall'elenco, quindi fare clic su **Visualizza attività custode** sulla pagina a comparsa.

    Viene visualizzata la pagina di ricerca attività del custode. Tenere presente che il custode selezionato nel passaggio precedente viene visualizzato nella casella di menu a discesa **custode** . È possibile selezionare diversi depositari nell'elenco a discesa, ma è possibile cercare solo le attività per un custode alla volta.

    ![Pagina di ricerca attività del custode](media/AeDCustodianActivities1.png)
   
4. Configurare i seguenti criteri di ricerca:
      
   un. **Attività** -fare clic sull'elenco a discesa per visualizzare le attività che è possibile cercare. Dopo aver eseguito la ricerca, vengono visualizzati solo i record di controllo per le attività selezionate. Se si seleziona **Mostra risultati per tutte le attività** , verranno visualizzati i risultati di tutte le attività eseguite dal custode che corrispondono agli altri criteri di ricerca.

      ![Elenco delle attività](media/CustodianActivityAudit.PNG)
      
      b. Data di **inizio e data di fine** : selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati entro quel periodo. Gli ultimi sette giorni sono selezionati per impostazione predefinita. La data e l'ora vengono visualizzate in formato UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare è di un anno.
      
      c. **Depositari** -fare clic in questa casella e quindi selezionare un custode specifico per visualizzare i risultati della ricerca. I record di controllo per l'attività selezionata eseguita dagli utenti selezionati in questa casella vengono visualizzati nell'elenco dei risultati.
      
   5. Fare clic su   ![Pulsante Cerca](media/SearchButton.PNG)  per eseguire la ricerca utilizzando i criteri di ricerca. I risultati della ricerca vengono caricati e, dopo alcuni istanti, vengono visualizzati in risultati nella pagina di ricerca attività del custode. 

## <a name="step-2-view-the-audit-log-search-results"></a>Passaggio 2: visualizzazione dei risultati di ricerca del registro di controllo

I risultati di una ricerca del registro di controllo vengono visualizzati nella pagina dei risultati nella pagina del registro di controllo del custode. Un massimo di 5.000 eventi (più recenti) viene visualizzato con incrementi di 150 eventi. Per visualizzare altri eventi, è possibile utilizzare la barra di scorrimento nel riquadro dei risultati oppure premere MAIUSC + fine per visualizzare i successivi 150 eventi.

I risultati contengono le seguenti informazioni su ogni evento restituito dalla ricerca.
- **Date**: la data e l'ora (in formato UTC) quando si è verificato l'evento.

- **Indirizzo IP**: l'indirizzo IP del dispositivo utilizzato quando è stata registrata l'attività. L'indirizzo IP viene visualizzato in un formato di indirizzo IPv4 o IPv6.

- **Utente**: l'utente (o l'account di servizio) che ha eseguito l'azione che ha attivato l'evento.

- **Attività**: attività eseguita dall'utente. Questo valore corrisponde alle attività selezionate nell'elenco a discesa attività. Per un evento proveniente dal registro di controllo di amministrazione di Exchange, il valore di questa colonna è un cmdlet di Exchange.

- **Elemento**: l'oggetto che è stato creato o modificato a seguito dell'attività corrispondente. Ad esempio, il file che è stato visualizzato o modificato o l'account utente che è stato aggiornato. Non tutte le attività hanno un valore in questa colonna.

- **Dettaglio**: informazioni aggiuntive su un'attività. Anche in questo caso, non tutte le attività avranno un valore.

## <a name="step-3-filter-the-search-results"></a>Passaggio 3: filtrare i risultati della ricerca

Oltre all'ordinamento, è anche possibile filtrare i risultati di una ricerca nel registro di controllo. In questo modo è possibile filtrare rapidamente i risultati per un utente o un'attività specifica. 

Per filtrare i risultati:

 1. Creare ed eseguire una ricerca nel registro di controllo.
  
2. Quando vengono visualizzati i risultati, fare clic su **Filtra risultati**.
 
3. Le caselle di parole chiave vengono visualizzate sotto ogni intestazione di colonna.
  
4. Fare clic su una delle caselle all'interno di un'intestazione di colonna e digitare una parola o una frase, a seconda della colonna in base alla quale si sta applicando il filtro. I risultati verranno riadattati dinamicamente per visualizzare gli eventi che corrispondono al filtro.
  
5. Per cancellare un filtro, fare clic sulla **X** nella casella filtro oppure fare clic su **Nascondi filtro**.

## <a name="export-the-search-results-to-a-file"></a>Esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca nel registro di controllo in un file con valori delimitati da virgole (CSV) nel computer locale. È possibile aprire il file in Microsoft Excel e utilizzare funzionalità quali la ricerca, l'ordinamento, il filtraggio e la suddivisione di una singola colonna (che contiene celle a più valori) in più colonne.

1. Eseguire una ricerca nel registro di controllo e quindi rivedere i criteri di ricerca fino a quando non si hanno i risultati desiderati.
  
2. Fare clic su Esporta risultati e selezionare una delle opzioni seguenti:

    - **Salvare i risultati caricati:** Scegliere questa opzione per esportare solo le voci visualizzate in **results** nella pagina di **ricerca del registro di controllo della banca depositaria** . Il file CSV scaricato contiene le stesse colonne (e i dati) visualizzati nella pagina (data, utente, attività, elemento e dettagli). Nel file CSV è inclusa una colonna aggiuntiva (intitolata **più**) che contiene ulteriori informazioni dalla voce del registro di controllo. Poiché si stanno esportando gli stessi risultati caricati (e visualizzabili) nella pagina di ricerca del registro di controllo, vengono esportate al massimo 5.000 voci.
        
    - **Scaricare tutti i risultati:** Scegliere questa opzione per esportare tutte le voci dal registro di controllo di Office 365 che soddisfano i criteri di ricerca. Per un set di risultati di ricerca di grandi dimensioni, scegliere questa opzione per scaricare tutte le voci dal registro di controllo oltre ai risultati di 5.000 che possono essere visualizzati nella pagina di ricerca del **Registro di controllo della banca depositaria** . Questa opzione consente di scaricare i dati non elaborati dal registro di controllo in un file CSV e contiene informazioni aggiuntive dalla voce del registro di controllo in una colonna denominata AuditData. Se si sceglie questa opzione di esportazione, potrebbe essere necessario più tempo per scaricare il file, in quanto il file potrebbe essere molto più grande di quello scaricato se si sceglie l'opzione altro.
    
      > [!IMPORTANT]
      > È possibile scaricare un massimo di 50.000 voci in un file CSV da una singola ricerca del registro di controllo. Se 50.000 voci vengono scaricate nel file CSV, è probabile che siano presenti più di 50.000 eventi che soddisfano i criteri di ricerca. Per esportare più di questo limite, provare a utilizzare un intervallo di date per ridurre il numero di voci del registro di controllo. Potrebbe essere necessario eseguire più ricerche con intervalli di date inferiori per esportare più di 50.000 voci.
        

3. Dopo aver selezionato un'opzione di esportazione, nella parte inferiore della finestra viene visualizzato un messaggio in cui viene richiesto di aprire il file CSV, salvarlo nella cartella Downloads o salvarlo in una cartella specifica.

Per ulteriori informazioni sulla visualizzazione, il filtro o l'esportazione dei risultati di ricerca del registro di controllo, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
