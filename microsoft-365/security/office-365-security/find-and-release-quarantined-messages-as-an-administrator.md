---
title: Individuazione e rilascio dei messaggi in quarantena come amministratore
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: In questo argomento viene descritto in che modo gli amministratori di Exchange Online e Exchange Online Protection (EOP) possono trovare, rilasciare e segnalare i messaggi che sono in quarantena nell'interfaccia di amministrazione di Exchange (EAC).
ms.openlocfilehash: 479766e573f5b7fefc334d70c7f44a664944dc16
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083483"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Trovare e rilasciare messaggi in quarantena come amministratore

In questo argomento viene descritto in che modo gli amministratori di Exchange Online e Exchange Online Protection (EOP) possono trovare, rilasciare e segnalare i messaggi che sono in quarantena nell'interfaccia di amministrazione di Exchange (EAC). Office 365 indirizza i messaggi alla quarantena perché sono stati identificati come posta indesiderata o hanno trovato una regola del flusso di posta (nota anche come regola di trasporto). 
  
Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
I messaggi in quarantena vengono elencati nella pagina **quarantena** di EAC. Per impostazione predefinita, i messaggi di posta indesiderata in quarantena vengono ordinati dal più recente al più vecchio nel campo **RICEVUTO**. Per ogni messaggio vengono visualizzati anche i valori di **MITTENTE**, **OGGETTO** e **SCADENZA**. È possibile ordinare in base a uno di tali valori facendo clic sull'intestazione corrispondente. Facendo clic su un'intestazione di colonna una seconda volta l'ordine viene invertito. Nella pagina **quarantena**, è possibile visualizzare al massimo 500 messaggi. 
  
È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure cercare messaggi specifici indicando i criteri di filtro (il filtro può essere utile per ridurre la serie di risultati se sono presenti più di 500 messaggi). Dopo aver cercato e individuato uno specifico messaggio in quarantena, è possibile visualizzarne i dettagli. È inoltre possibile:
  
- Rilasciare un messaggio in quarantena a uno o più destinatari e facoltativamente segnalarlo come falso positivo (non posta indesiderata) al team di analisi di posta indesiderata di Microsoft, il quale valuterà e analizzerà il messaggio. A seconda dei risultati dell'analisi, i criteri di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificati per consentire l'inoltro del messaggio.
    
- Rilasciare il messaggio e consentire tutti i messaggi futuri dello stesso mittente.
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Quarantine" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
    
- È possibile rilasciare o segnalare più messaggi contemporaneamente nella pagina **quarantena**. In alternativa, è possibile creare uno script di Windows PowerShell remoto per eseguire questa operazione. Utilizzare il cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) per cercare i messaggi e il cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) per rilasciarli. 
    
- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Utilizzo della ricerca avanzata per filtrare e individuare i messaggi in quarantena
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

Nell'interfaccia di amministrazione di Exchange, è possibile filtrare gli elementi in quarantena in base a diverse condizioni, utilizzando la ricerca avanzata. Le condizioni possono essere utilizzate separatamente o in combinazione. La ricerca fornirà un elenco di messaggi che soddisfano tutti i criteri di ricerca specificati.
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Quarantena**, quindi fare clic su **Ricerca avanzata**.
    
2. Nella finestra **Ricerca avanzata**, selezionare una combinazione delle seguenti condizioni. Per abilitare una condizione, selezionare la casella di controllo associata. I caratteri jolly non sono supportati. 
    
1. **ID messaggio** È possibile utilizzare questo parametro per eseguire una ricerca mirata a uno specifico messaggio. Ad esempio, se uno specifico messaggio è stato inviato da un utente dell'organizzazione o è destinato a un utente dell'organizzazione ma non raggiunge la destinazione prevista, è possibile cercarlo utilizzando la funzionalità di traccia dei messaggi. Per ulteriori informazioni, vedere [Esecuzione di Ritrova messaggio e Visualizza risultati](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). Se si scopre che il messaggio è stato inviato alla quarantena, ad esempio perché corrispondeva a una regola di trasporto o perché era stato identificato come posta indesiderata, è possibile trovarlo facilmente nella quarantena specificandone l'ID messaggio. Accertarsi di indicare la stringa completa dell'ID messaggio, che potrebbe includere parentesi angolari (\<\>). 
    
2. **Indirizzo di posta elettronica mittente** Specificare l'indirizzo di posta elettronica della persona che ha inviato il messaggio. 
    
3. **Indirizzo di posta elettronica destinatario** Specificare l'indirizzo di posta elettronica del destinatario previsto del messaggio. 
    
4. **Oggetto** Specificare il testo nella riga dell'oggetto del messaggio. 
    
5. **Ricevuto** È possibile indicare che il messaggio è stato ricevuto dalla quarantena entro le 24 ore precedenti ( **Oggi**), le 48 ore precedenti ( **Ultimi 2 giorni**), la settimana precedente ( **Ultimi 7 giorni**) oppure specificare un intervallo di tempo personalizzato. 
    
6. **Scadenza** È possibile indicare che il messaggio sarà eliminato dalla quarantena entro le 24 ore successive ( **Oggi**), le 48 ore successive ( **Prossimi 2 giorni**), la settimana successiva ( **Prossimi 7 giorni**) oppure specificare un intervallo di tempo personalizzato entro il quale il messaggio sarà eliminato dalla quarantena.
    
    > [!IMPORTANT]
    > Per impostazione predefinita, i messaggi in quarantena della posta indesiderata vengono mantenuti per 15 giorni, mentre i messaggi in quarantena che corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per 7 giorni. Al termine di questo periodo di tempo Office 365 elimina i messaggi e non sono recuperabili. Il periodo di conservazione per i messaggi in quarantena che corrispondono a una regola del flusso di posta elettronica non è configurabile. Tuttavia, il periodo di conservazione può essere ridotto con l'impostazione **Conserva posta indesiderata per (giorni)** nei criteri di filtro contenuto. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). 
  
7. **Tipo** di È possibile specificare se cercare i messaggi in quarantena identificati come **posta indesiderata**o se cercare i messaggi corrispondenti a una regola del flusso di posta (**regola di trasporto**).
    
3. Fare clic su **OK** per avviare l'esecuzione della ricerca avanzata. 
    
    > [!NOTE]
    > Per cancellare i criteri di ricerca e visualizzare tutti i messaggi in quarantena, deselezionare le caselle di controllo nella finestra **Ricerca avanzata** e fare clic su **OK**. 
  
Dopo aver cercato i messaggi, i risultati corrispondenti ai criteri specificati saranno visualizzati nell'interfaccia utente. In EAC è possibile visualizzare fino a 500 messaggi. 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>Visualizzare i dettagli su uno specifico messaggio in quarantena
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

Dopo aver individuato uno specifico messaggio in quarantena, è possibile visualizzarne i dettagli nella pagina **quarantena**. 
  
1. Nella pagina **quarantena**, selezionare un messaggio specifico e un riepilogo delle proprietà del messaggio che vengono visualizzate nel riquadro relativo ai dettagli, nella parte a destra dello schermo. 
    
    I valori disponibili per **Stato messaggio** sono i seguenti: 
    
  - **Tipo** di Indica se il messaggio è stato identificato come **posta indesiderata** o ha trovato una regola del flusso di posta (**regola di trasporto**).
    
  - **Scadenza** La data in cui il messaggio sarà eliminato dalla quarantena. 
    
    I valori per **Dettagli messaggio** sono i seguenti: 
    
  - **Mittente** L'indirizzo di posta elettronica della persona che ha inviato il messaggio. 
    
  - **Oggetto** Il testo della riga dell'oggetto del messaggio. 
    
  - **Ricevuto** La data in cui il messaggio è stato ricevuto dalla quarantina. 
    
  - **Dimensione** La dimensione del messaggio, in kilobyte (KB) oppure, se maggiore di 999 KB, in megabyte (MB). 
    
  - **Visualizzazione delle intestazioni del messaggio** Fare clic su questo collegamento per aprire la finestra di dialogo **intestazione del messaggio**, che consente di visualizzare il testo dell'intestazione del messaggio. È anche possibile copiare e incollare il testo dell'intestazione del messaggio negli Appunti e incollarlo in [Analizzatore intestazione messaggio](https://testconnectivity.microsoft.com/?tabid=mha). Una volta effettuato l'accesso allo strumento Analizzatore intestazione messaggio, fare clic su **Analizza intestazioni** per recuperare le informazioni sull'intestazione. 
    
    > [!TIP]
    > Per informazioni sui campi specifici delle intestazioni messaggi di protezione da posta indesiderata inseriti dal servizio, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md). 
  
  - **Anteprima del messaggio di posta elettronica** Fare clic su questo collegamento per rivedere il testo del messaggio. 
    
2. Se si fa doppio clic su un messaggio in quarantena, viene visualizzata la finestra **Messaggio in quarantena** con le seguenti informazioni: 
    
  - **Rilasciato a** Un elenco di tutti gli indirizzi di posta elettronica a cui è stato rilasciato il messaggio. 
    
  - **Non ancora rilasciato a** Un elenco di tutti gli indirizzi di posta elettronica a cui il messaggio non è stato rilasciato. È possibile fare clic sul collegamento **Rilascia a** per rilasciare il messaggio. Per ulteriori informazioni sul rilascio di un messaggio, vedere la sezione successiva. 
    
  - **ID messaggio** L'ID messaggio Internet (detto anche ID client) trovato nell'intestazione del messaggio. 
    
    Fare clic su **Chiudi** per tornare al riquadro principale della quarantena. 
    
## <a name="release-messages-from-quarantine"></a>Rilasciare messaggi dalla quarantena
<a name="sectionSection3"> </a>

Se si desidera rilasciare messaggi ai destinatari, le opzioni disponibili sono:
  
- [Rilasciare un messaggio in quarantena e consentire tutti i messaggi futuri dello stesso mittente](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [Rilasciare un messaggio in quarantena a destinatari specifici senza segnalarlo come falso positivo](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [Rilasciare uno o più messaggi in quarantena a tutti i destinatari](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [Rilasciare uno o più messaggi in quarantena a tutti i destinatari e segnalarli come falsi positivi](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Rilasciare un messaggio in quarantena e consentire tutti i messaggi futuri dello stesso mittente
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. In EAC, andare a **Protezione** \> **Quarantena**.
    
2. Selezionare un messaggio, fare clic sull'icona **Rilascia messaggio** come visualizzato nella seguente schermata. 
  
![Viene visualizzata la pagina della quarantena con l'icona del rilascio del messaggio evidenziata e con le opzioni di rilascio](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
Fare clic su **Rilascia il messaggio selezionato e consenti il mittente** dall'elenco a discesa. 
    
3. Viene visualizzata la finestra di dialogo **Rilascia il messaggio e consenti il mittente**. Facoltativamente, è possibile scegliere di segnalare il messaggio a Microsoft e quindi fare clic su **Rilascia e consenti**. Il messaggio verrà rilasciato a tutti i destinatari a cui è indirizzato e tutti i futuri messaggio di questo stesso mittente saranno consentiti. Tuttavia, se il messaggio è stato messo in quarantena a causa di una regola del flusso di posta o di un mittente bloccato, il mittente continuerà a essere bloccato per i messaggi futuri. 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Rilasciare un messaggio in quarantena a destinatari specifici senza segnalarlo come falso positivo
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. In EAC, andare a **Protezione** \> **Quarantena**.
    
2. Selezionare un messaggio, fare clic sull'icona **Rilascia messaggio**, quindi scegliere **Rilascia messaggio e segnalalo come falso positivo** dall'elenco a discesa. 
    
3. Nella finestra di dialogo **Rilascia messaggio** selezionare una delle seguenti opzioni: 
    
  - **Rilascia messaggio a tutti i destinatari** Selezionando questa opzione, tenere presente che il messaggio non può essere rilasciato più di una volta allo stesso destinatario. Se un destinatario ha già ricevuto il messaggio, non verrà nuovamente rilasciato. 
    
  - **Rilascia messaggio a destinatari specifici** Selezionare i destinatari ai quali rilasciare i messaggio. Poiché un messaggio può essere rilasciato una sola volta ad ogni destinatario, nell'elenco verranno visualizzati solo i destinatari ai quali è possibile rilasciarlo. È disponibile la selezione multipla. Dopo aver effettuato la selezione, fare clic su **Aggiungi**.
    
4. Fare clic su **rilascia**. 
    
Se si seleziona l'icona **Aggiorna**![Icona Aggiorna](../media/ITPro-EAC-RefreshIcon.gif) per aggiornare i dati e in seguito si fa doppio clic sul messaggio, è possibile verificare che sia stato rilasciato ai destinatari desiderati. 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Rilasciare uno o più messaggi in quarantena a tutti i destinatari
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. In EAC, andare a **Protezione** \> **Quarantena**.
    
2. Fare clic su un messaggio per selezionarlo oppure utilizzare il tasto MAIUSC per selezionare più messaggi. Fare quindi clic sull'icona **Rilascia messaggio**. 
    
3. Fare clic su **Rilascia i messaggi selezionati a TUTTI i destinatari** dall'elenco a discesa. 
    
4. Verrà visualizzata la finestra di dialogo di avviso. Leggere l'avviso e selezionare **Sì** se si desidera procedere. Selezionando questa opzione, tenere presente che il messaggio non può essere rilasciato più di una volta allo stesso destinatario. Se un destinatario ha già ricevuto il messaggio, non verrà nuovamente rilasciato. 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Rilasciare uno o più messaggi in quarantena a tutti i destinatari e segnalarli come falsi positivi
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. In EAC, andare a **Protezione** \> **Quarantena**.
    
2. Fare clic su un messaggio per selezionarlo oppure utilizzare il tasto MAIUSC per selezionare più messaggi. Fare quindi clic sull'icona **Rilascia messaggio**. 
    
3. Fare clic su **Rilascia i messaggi selezionati e segnalali come falsi positivi** dall'elenco a discesa. 
    
4. Verrà visualizzata la finestra di dialogo di avviso. Leggere l'avviso e selezionare **Sì** se si desidera procedere. Selezionando questa opzione, tenere presente che il messaggio non può essere rilasciato più di una volta allo stesso destinatario. Se un destinatario ha già ricevuto il messaggio, non verrà nuovamente rilasciato. 
    
     Scegliendo questa opzione, il messaggio verrà rilasciato a tutti i destinatari che non lo hanno ancora ricevuto. Se si tratta di un messaggio messo in quarantena perché identificato come posta indesiderata, sarà segnalato anche al team di analisi di posta indesiderata di Microsoft, che lo valuterà e lo analizzerà. A seconda dei risultati dell'analisi, i criteri di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificati per consentire l'inoltro del messaggio. 
    
> [!TIP]
> Come assicurarsi che un messaggio non venga contrassegnato come indesiderato in [Come per contribuire a garantire che un messaggio non è contrassegnato come posta indesiderata](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md). 
  
Se si seleziona l'icona **Aggiorna**![Icona Aggiorna](../media/ITPro-EAC-RefreshIcon.gif) per aggiornare i dati e in seguito si fa doppio clic sul messaggio, è possibile verificare che sia stato rilasciato ai destinatari desiderati. 
  
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection4"> </a>

[Domande frequenti sulla quarantena](quarantine-faq.md)
  

