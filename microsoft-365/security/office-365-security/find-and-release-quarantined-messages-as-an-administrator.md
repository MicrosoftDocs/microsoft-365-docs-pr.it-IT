---
title: Individuazione e rilascio dei messaggi in quarantena come amministratore
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: 8f127dd1e7c14bbf2ae1d3bf23e611ef5c3ac1dc
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37576034"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Trovare e rilasciare messaggi in quarantena come amministratore

In questo argomento viene descritto in che modo gli amministratori di Exchange Online e Exchange Online Protection (EOP) possono trovare, rilasciare e segnalare i messaggi che sono in quarantena nell'interfaccia di amministrazione di Exchange (EAC). Office 365 indirizza i messaggi alla quarantena perché sono stati identificati come posta indesiderata o hanno trovato una regola del flusso di posta (nota anche come regola di trasporto).

È possibile utilizzare il Centro sicurezza & Compliance anziché l'interfaccia di amministrazione di Exchange per completare anche una di queste attività. il portale di quarantena all'interno dell'interfaccia di amministrazione di Exchange (EAC) è impostato su decommisioned.  For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).

I messaggi in quarantena vengono elencati nella pagina **quarantena** di EAC. Per impostazione predefinita, i messaggi di posta indesiderata in quarantena vengono ordinati dal più recente al più vecchio nel campo **RICEVUTO**. Per ogni messaggio vengono visualizzati anche i valori di **MITTENTE**, **OGGETTO** e **SCADENZA**. È possibile ordinare in base a uno di tali valori facendo clic sull'intestazione corrispondente. Facendo clic su un'intestazione di colonna una seconda volta l'ordine viene invertito. Nella pagina **quarantena**, è possibile visualizzare al massimo 500 messaggi.

È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure cercare messaggi specifici indicando i criteri di filtro (il filtro può essere utile per ridurre la serie di risultati se sono presenti più di 500 messaggi). Dopo aver cercato e individuato uno specifico messaggio in quarantena, è possibile visualizzarne i dettagli. È inoltre possibile:

- Rilasciare un messaggio in quarantena a uno o più destinatari e facoltativamente segnalarlo come falso positivo (non posta indesiderata) al team di analisi di posta indesiderata di Microsoft, il quale valuterà e analizzerà il messaggio. A seconda dei risultati dell'analisi, i criteri di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificati per consentire l'inoltro del messaggio.

- Rilasciare il messaggio e consentire tutti i messaggi futuri dello stesso mittente.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Devi disporre delle autorizzazioni per poter eseguire queste procedure.  Per sapere quali autorizzazioni sono necessarie, vedere "Quarantine" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

- È possibile rilasciare o segnalare più messaggi contemporaneamente nella pagina **quarantena**. In alternativa, è possibile creare uno script di Windows PowerShell remoto per eseguire questa operazione. Utilizzare il cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) per cercare i messaggi e il cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) per rilasciarli.

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Utilizzo della ricerca avanzata per filtrare e individuare i messaggi in quarantena

Nell'interfaccia di amministrazione di Exchange, è possibile filtrare gli elementi in quarantena in base a diverse condizioni, utilizzando la ricerca avanzata. Le condizioni possono essere utilizzate separatamente o in combinazione. La ricerca fornirà un elenco di messaggi che soddisfano tutti i criteri di ricerca specificati.

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Quarantena**, quindi fare clic su **Ricerca avanzata**.

2. Nella finestra **Ricerca avanzata**, selezionare una combinazione delle seguenti condizioni. Per abilitare una condizione, selezionare la casella di controllo associata. I caratteri jolly non sono supportati.

   1. **ID messaggio**: è possibile utilizzare questo parametro per eseguire una ricerca mirata per un messaggio specifico. Ad esempio, se un messaggio specifico viene inviato o destinato a un utente dell'organizzazione, ma non raggiunge mai la destinazione, è possibile cercare il messaggio utilizzando la funzionalità di traccia dei messaggi. Per ulteriori informazioni, vedere [eseguire una traccia dei messaggi e visualizzare i risultati](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). Se si rileva che il messaggio è stato inviato alla quarantena, probabilmente perché corrisponde a una regola o è stato identificato come posta indesiderata, è possibile trovare facilmente questo messaggio in quarantena specificando il relativo ID messaggio. Includere la stringa completa dell'ID del messaggio. Questo potrebbe includere parentesi angolari\<\>().

   2. **Indirizzo di posta elettronica del mittente**: specificare l'indirizzo di posta elettronica della persona che ha inviato il messaggio.

   3. **Indirizzo di posta elettronica del destinatario**: specificare l'indirizzo di posta elettronica del destinatario previsto del messaggio.

   4. **Oggetto**: specificare il testo della riga dell'oggetto del messaggio.

   5. **Received**: è possibile selezionare che il messaggio è stato ricevuto dalla quarantena entro le 24 ore precedenti ( **oggi**), nelle ultime 48 ore ( **ultimi 2 giorni**), nella settimana precedente ( **ultimi 7 giorni**) oppure è possibile selezionare un intervallo di tempo personalizzato durante che il messaggio è stato ricevuto dalla quarantena.

   6. **Scade**: è possibile selezionare che il messaggio sarà eliminato dalla quarantena entro le 24 ore successive ( **oggi**), entro le 48 ore successive ( **prossimi 2 giorni**), entro la settimana successiva ( **prossimi 7 giorni**) oppure è possibile selezionare un intervallo di tempo personalizzato durante che il messaggio verrà eliminato dalla quarantena.

      > [!IMPORTANT]
      > Per impostazione predefinita, i messaggi in quarantena della posta indesiderata vengono mantenuti per 30 giorni, mentre i messaggi in quarantena che corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per un massimo di 30 giorni, in base al periodo di conservazione impostato nel criterio di filtro del contenuto predefinito. Al termine di questo periodo di tempo Office 365 elimina i messaggi e non sono recuperabili. Il periodo di conservazione per i messaggi in quarantena che corrispondono a una regola del flusso di posta elettronica non è configurabile. Tuttavia, il periodo di conservazione può essere ridotto con l'impostazione **Conserva posta indesiderata per (giorni)** nei criteri di filtro contenuto. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).

   7. **Tipo** di È possibile specificare se cercare i messaggi in quarantena identificati come **posta indesiderata**o se cercare i messaggi corrispondenti a una regola del flusso di posta (**regola di trasporto**).

3. Fare clic su **OK** per avviare l'esecuzione della ricerca avanzata.

   > [!NOTE]
   > Per cancellare i criteri di ricerca e visualizzare tutti i messaggi in quarantena, deselezionare le caselle di controllo nella finestra **Ricerca avanzata** e fare clic su **OK**.

Dopo aver cercato i messaggi, i risultati corrispondenti ai criteri specificati saranno visualizzati nell'interfaccia utente. In EAC è possibile visualizzare fino a 500 messaggi.

## <a name="view-details-about-a-specific-quarantined-message"></a>Visualizzare i dettagli su uno specifico messaggio in quarantena

Dopo aver individuato uno specifico messaggio in quarantena, è possibile visualizzarne i dettagli nella pagina **quarantena**.

1. Nella pagina **quarantena**, selezionare un messaggio specifico e un riepilogo delle proprietà del messaggio che vengono visualizzate nel riquadro relativo ai dettagli, nella parte a destra dello schermo.

   I valori disponibili per **Stato messaggio** sono i seguenti:

   - **Tipo**: indica se il messaggio è stato identificato come **posta indesiderata** o ha trovato una regola del flusso di posta (**regola di trasporto**).

   - **Scade**: la data in cui il messaggio verrà eliminato dalla quarantena.

   I valori per **Dettagli messaggio** sono i seguenti:

   - **Sender**: l'indirizzo di posta elettronica della persona che ha inviato il messaggio.

   - **Oggetto**: testo della riga dell'oggetto del messaggio.

   - **Received**: la data in cui il messaggio è stato ricevuto dalla quarantena.

   - **Dimensione**: la dimensione del messaggio, in KILOBYTE (KB) oppure, se la dimensione del messaggio è maggiore di 999 KB, in megabyte (MB).

   - **Visualizza intestazione messaggio**: fare clic su questo collegamento per aprire la finestra di dialogo **intestazione del messaggio** , che consente di visualizzare il testo dell'intestazione del messaggio. È anche possibile copiare e incollare il testo dell'intestazione del messaggio negli Appunti e incollarlo in [Analizzatore intestazione messaggio](https://testconnectivity.microsoft.com/?tabid=mha). Una volta effettuato l'accesso allo strumento Analizzatore intestazione messaggio, fare clic su **Analizza intestazioni** per recuperare le informazioni sull'intestazione.

    > [!TIP]
    > Per informazioni sui campi specifici delle intestazioni messaggi di protezione da posta indesiderata inseriti dal servizio, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

   - **Anteprima del messaggio di posta elettronica** Fare clic su questo collegamento per rivedere il testo del messaggio.

2. Se si fa doppio clic su un messaggio in quarantena, viene visualizzata la finestra **Messaggio in quarantena** con le seguenti informazioni:

   - **Rilasciato a**: un elenco di tutti gli indirizzi di posta elettronica a cui è stato rilasciato il messaggio, se disponibile.

   - **Non ancora rilasciato**: un elenco di tutti gli indirizzi di posta elettronica a cui il messaggio non è stato rilasciato, se disponibile. È possibile fare clic sul collegamento **rilascia per** rilasciare il messaggio; Per ulteriori informazioni sul rilascio di un messaggio, vedere la sezione successiva.

   - **ID messaggio**: l'ID messaggio Internet (detto anche ID client) trovato nell'intestazione del messaggio.

   Fare clic su **Chiudi** per tornare al riquadro principale della quarantena.

## <a name="release-messages-from-quarantine"></a>Rilasciare messaggi dalla quarantena

Se si desidera rilasciare messaggi ai destinatari, le opzioni disponibili sono:

- [Rilasciare un messaggio in quarantena e consentire tutti i messaggi futuri dello stesso mittente](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [Rilasciare un messaggio in quarantena a destinatari specifici senza segnalarlo come falso positivo](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [Rilasciare uno o più messaggi in quarantena a tutti i destinatari](#release-one-or-more-quarantined-messages-to-all-recipients)

- [Rilasciare uno o più messaggi in quarantena a tutti i destinatari e segnalarli come falsi positivi](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Rilasciare un messaggio in quarantena e consentire tutti i messaggi futuri dello stesso mittente

1. In EAC, andare a **Protezione** \> **Quarantena**.

2. Selezionare un messaggio, fare clic sull'icona **Rilascia messaggio** come visualizzato nella seguente schermata.

   ![Viene visualizzata la pagina della quarantena con l'icona del rilascio del messaggio evidenziata e con le opzioni di rilascio](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   Fare clic su **Rilascia il messaggio selezionato e consenti il mittente** dall'elenco a discesa.

3. Viene visualizzata la finestra di dialogo **Rilascia il messaggio e consenti il mittente**. Facoltativamente, è possibile scegliere di segnalare il messaggio a Microsoft e quindi fare clic su **Rilascia e consenti**. Il messaggio verrà rilasciato a tutti i destinatari a cui è indirizzato e tutti i futuri messaggio di questo stesso mittente saranno consentiti. Tuttavia, se il messaggio è stato messo in quarantena a causa di una regola del flusso di posta o di un mittente bloccato, il mittente continuerà a essere bloccato per i messaggi futuri.

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Rilasciare un messaggio in quarantena a destinatari specifici senza segnalarlo come falso positivo

1. In EAC, andare a **Protezione** \> **Quarantena**.

2. Selezionare un messaggio, fare clic sull'icona **Rilascia messaggio**, quindi scegliere **Rilascia messaggio e segnalalo come falso positivo** dall'elenco a discesa.

3. Nella finestra di dialogo **Rilascia messaggio** selezionare una delle seguenti opzioni:

   - **Rilascia messaggio a tutti i destinatari** Selezionando questa opzione, tenere presente che il messaggio non può essere rilasciato più di una volta allo stesso destinatario. Se un destinatario ha già ricevuto il messaggio, non verrà nuovamente rilasciato.

   - **Rilascia messaggio a destinatari specifici** Selezionare i destinatari ai quali rilasciare i messaggio. Poiché un messaggio può essere rilasciato una sola volta ad ogni destinatario, nell'elenco verranno visualizzati solo i destinatari ai quali è possibile rilasciarlo. È disponibile la selezione multipla. Dopo aver effettuato la selezione, fare clic su **Aggiungi**.

4. Fare clic su **rilascia**.

Se si fa **** ![clic su Aggiorna](../media/ITPro-EAC-RefreshIcon.gif) l'icona Aggiorna per aggiornare i dati e quindi fare doppio clic sul messaggio, è necessario vedere che è stato rilasciato ai destinatari desiderati.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Rilasciare uno o più messaggi in quarantena a tutti i destinatari

1. In EAC, andare a **Protezione** \> **Quarantena**.

2. Fare clic su un messaggio per selezionarlo oppure utilizzare il tasto MAIUSC per selezionare più messaggi. Fare quindi clic sull'icona **Rilascia messaggio**.

3. Fare clic su **Rilascia i messaggi selezionati a TUTTI i destinatari** dall'elenco a discesa.

4. Verrà visualizzata la finestra di dialogo di avviso. Leggere l'avviso e selezionare **Sì** se si desidera procedere. Selezionando questa opzione, tenere presente che il messaggio non può essere rilasciato più di una volta allo stesso destinatario. Se un destinatario ha già ricevuto il messaggio, non verrà nuovamente rilasciato.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Rilasciare uno o più messaggi in quarantena a tutti i destinatari e segnalarli come falsi positivi

1. In EAC, andare a **Protezione** \> **Quarantena**.

2. Fare clic su un messaggio per selezionarlo oppure utilizzare il tasto MAIUSC per selezionare più messaggi. Fare quindi clic sull'icona **Rilascia messaggio**.

3. Fare clic su **Rilascia i messaggi selezionati e segnalali come falsi positivi** dall'elenco a discesa.

4. Verrà visualizzata la finestra di dialogo di avviso. Leggere l'avviso e selezionare **Sì** se si desidera procedere. Selezionando questa opzione, tenere presente che il messaggio non può essere rilasciato più di una volta allo stesso destinatario. Se un destinatario ha già ricevuto il messaggio, non verrà nuovamente rilasciato.

   Scegliendo questa opzione, il messaggio verrà rilasciato a tutti i destinatari che non lo hanno ancora ricevuto. Se si tratta di un messaggio messo in quarantena perché identificato come posta indesiderata, sarà segnalato anche al team di analisi di posta indesiderata di Microsoft, che lo valuterà e lo analizzerà. A seconda dei risultati dell'analisi, i criteri di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificati per consentire l'inoltro del messaggio.

> [!TIP]
> Come assicurarsi che un messaggio non venga contrassegnato come indesiderato in [Come per contribuire a garantire che un messaggio non è contrassegnato come posta indesiderata](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).

Se si seleziona l'icona **Aggiorna**![Icona Aggiorna](../media/ITPro-EAC-RefreshIcon.gif) per aggiornare i dati e in seguito si fa doppio clic sul messaggio, è possibile verificare che sia stato rilasciato ai destinatari desiderati.

## <a name="for-more-information"></a>Ulteriori informazioni

[Domande frequenti sulla quarantena](quarantine-faq.md)
