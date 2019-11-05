---
title: Gestire i messaggi e i file in quarantena come amministratore in Office 365
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 'In qualità di amministratore, è possibile visualizzare, rilasciare e segnalare messaggi in quarantena falsi positivi in Office 365. È possibile configurare i criteri in modo che Office 365 filtri i messaggi e li invii in quarantena per diversi motivi: perché sono stati identificati come posta indesiderata, in blocco, phishing, malware o perché hanno trovato una regola del flusso di posta. '
ms.openlocfilehash: 1450b88bdb3336923891bbbe041d9ca384a3c875
ms.sourcegitcommit: 9206e7f2d61b5ba7f788fe5e7f75a2218c12c716
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968474"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a>Gestire i messaggi e i file in quarantena come amministratore in Office 365

Come amministratore, è possibile visualizzare, rilasciare ed eliminare i messaggi in quarantena e segnalare i messaggi in quarantena falsi positivi in Office 365. È inoltre possibile visualizzare, scaricare ed eliminare i file in quarantena acquisiti da Advance Threat Protection (ATP) per SharePoint Online, OneDrive for business e Microsoft teams. È possibile configurare i criteri in modo che Office 365 filtri i messaggi e li invii in quarantena per diversi motivi: perché sono stati identificati come posta indesiderata, messaggi in blocco, messaggi di phishing, contenenti malware o perché corrispondono a una regola del flusso di posta.
  
Per impostazione predefinita, Office 365 invia i messaggi di phishing e i messaggi contenenti malware direttamente in quarantena. Gli altri messaggi filtrati vengono inviati alla cartella posta indesiderata degli utenti, a meno che non sia stato impostato un criterio per inviarli alla quarantena.
  
Per utilizzare i messaggi in quarantena o i file in quarantena, è necessario disporre delle autorizzazioni di amministratore globale (GA) in Office 365 o essere membri di uno o più gruppi di ruoli Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) .
  
> [!IMPORTANT]
>Per impostazione predefinita, i messaggi di posta indesiderata, di massa e di phishing vengono mantenuti in quarantena per 30 giorni. I messaggi in quarantena perché corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per 7 giorni. I messaggi di malware vengono mantenuti in quarantena per 15 giorni. È possibile personalizzare il tempo di quarantena della posta indesiderata nelle impostazioni di &amp; protezione da posta indesiderata nel centro sicurezza e conformità. I messaggi eliminati dalla quarantena in Office 365 non possono essere recuperati. Se lo si desidera, è possibile modificare il periodo di conservazione per i messaggi in quarantena nei criteri di filtro della protezione da posta indesiderata. Per ulteriori informazioni, vedere [impostazione del periodo di conservazione della quarantena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in questo articolo. 
  
## <a name="view-your-organizations-quarantined-messages"></a>Visualizzare i messaggi in quarantena dell'organizzazione

1. L'utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale (o ruoli di sicurezza & conformità corretti) nell'organizzazione di Office 365, accedere a Office 365 e [passare al centro sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md).
    
2. Nell'elenco a sinistra espandere **gestione minacce**, fare clic su **Revisione**e quindi scegliere **quarantena**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **Quarantena** nel &amp;Centro sicurezza e conformità, usare questo URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
    Per impostazione predefinita, il &amp;Centro sicurezza e conformità visualizza tutti i messaggi di posta elettronica messi in quarantena come posta indesiderata. I messaggi sono ordinati dal più recente al più vecchio in base alla **Data** in cui sono stati ricevuti. **Mittente**, **Oggetto** e la data di scadenza (in **Scadenza**) vengono visualizzati anche per i singoli messaggi. È possibile ordinare in base a un campo facendo clic sull'intestazione di colonna corrispondente. Se si fa clic una seconda volta sull'intestazione di una colonna, si inverte il tipo di ordinamento. 
    
3. È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure ridurre il set di risultati in base al filtro. Le operazioni in blocco possono essere eseguite su un massimo di 100 elementi, quindi i filtri aiutano anche a ridurre il numero di risultati se sono presenti più elementi. È possibile filtrare rapidamente i messaggi per una singola causa di quarantena scegliendo un'opzione dal filtro nella parte superiore della pagina. Le opzioni disponibili sono:
    
  - Posta elettronica identificata come posta indesiderata
    
  - Posta in quarantena perché corrisponde a un criterio impostato da una regola del flusso di posta (nota anche come regola di trasporto)
    
  - Posta elettronica identificata come posta in blocco
    
  - Posta elettronica identificata come messaggio di phishing
    
  - Posta in quarantena perché contiene malware
    
Inoltre, come amministratore, è possibile scegliere di filtrare tutti i messaggi per l'organizzazione o solo i messaggi inviati all'utente. Gli utenti finali possono visualizzare e utilizzare solo i messaggi inviati.
  
È inoltre possibile filtrare i risultati per individuare messaggi specifici. Per suggerimenti, vedere [per filtrare i risultati e trovare i messaggi e i file in quarantena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in questo articolo. 
  
Dopo aver individuato uno specifico messaggio in quarantena, fare clic sul messaggio per visualizzarne i dettagli e intraprendere azioni, ad esempio il rilascio del messaggio alla cassetta postale di un utente.
  
## <a name="view-your-organizations-quarantined-files"></a>Visualizzare i file in quarantena dell'organizzazione

1. L'utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione di Office 365, accedere a Office 365 e [passare al centro sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md).
    
2. A sinistra, espandere **Gestione delle minacce**, scegliere **Revisione**, poi scegliere **Quarantena**. <br/>
    > [!TIP]
    > Per passare direttamente alla pagina **Quarantena** nel &amp;Centro sicurezza e conformità, usare questo URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
3. Per impostazione predefinita, la pagina Visualizza i messaggi di posta elettronica in quarantena. Per visualizzare i file in quarantena, impostare i filtri nella parte superiore della pagina per visualizzare **i file**, in quarantena a causa di **malware**. Per utilizzare i file in quarantena, è necessario disporre delle autorizzazioni di amministratore in Office 365. 
    
4. I file sono ordinati dal più recente al più vecchio in base alla data in cui il file è stato messo in quarantena. L' **utente** che ha modificato l'ultima volta il file, il **servizio** a cui è stato inviato il file, il **nome del file**, la **posizione**, la **dimensione del file**e la data di scadenza ( **scade**) sono elencati anche per ogni file. È possibile ordinare su un campo facendo clic su un'intestazione. fare clic su un'intestazione di colonna una seconda volta per invertire la sequenza di ordinamento.
    
È possibile visualizzare un elenco di tutti i file in quarantena oppure è possibile cercare file specifici filtrando. Analogamente ai messaggi, è possibile eseguire operazioni in blocco solo su un massimo di 100 elementi. Attualmente, il centro &amp; sicurezza e conformità consente di visualizzare e gestire i file in quarantena perché sono stati identificati come contenenti malware. Per suggerimenti, vedere [per filtrare i risultati e trovare i messaggi e i file in quarantena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in questo articolo. 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a>Per filtrare i risultati e trovare i messaggi e i file in quarantena
<a name="BKMK_AdvSearch"> </a>

A seconda delle impostazioni, è possibile che vi siano molti messaggi e file in quarantena. Per trovare un messaggio o un file o un insieme di messaggi specifici, è possibile filtrare gli elementi in quarantena in base a una serie di informazioni aggiuntive.
  
1. Nella pagina **quarantena** verificare che la riga superiore dei filtri sia impostata in modo da visualizzare i messaggi o i file in base alle esigenze: 
    
      - Per cercare i file, impostare i filtri per visualizzare **i file** in quarantena a causa di **malware**.<br/>
    Per i file in quarantena, nella pagina vengono visualizzati tutti i file in quarantena, non solo quelli personali, indipendentemente dal tipo di informazioni che si desidera visualizzare.
    
      - Per cercare i messaggi in quarantena, impostare filtri per visualizzare **tutto** o **solo il mio** **messaggio di posta elettronica**. Per l'ultimo filtro scegliere il tipo di messaggio in quarantena che si sta cercando. È possibile cercare i messaggi in quarantena identificati come **posta indesiderata**, per i messaggi che corrispondono a una regola del flusso di posta (**regola di trasporto**), alla posta in **blocco** , alla posta elettronica di **phishing** o alla posta che contiene **malware**.
    
2. In **Ordina risultati**fare clic sul filtro o sui filtri che si desidera utilizzare per la ricerca negli elenchi a discesa. Le opzioni variano in base al fatto che si cerchino file o messaggi. I caratteri jolly non sono supportati nei campi di ricerca in questo momento.<br/><br/>Sia per i file che per i messaggi, è possibile scegliere di filtrare in base alla data in cui il messaggio o il file è stato inviato alla quarantena. È possibile specificare la data o un intervallo di date, inclusa l'ora. È inoltre possibile filtrare i risultati della ricerca in base alla data di scadenza in cui il file o il messaggio verrà eliminato dalla quarantena oppure è possibile utilizzare una combinazione di filtri. Per eseguire la ricerca in base alla data di scadenza, scegliere **filtro avanzato**. In **scadenza**, è possibile selezionare i messaggi che verranno eliminati dalla quarantena entro le 24 ore successive ( **oggi**), entro le 48 ore successive ( **prossimi 2 giorni**), entro la settimana successiva ( **prossimi 7 giorni**) oppure è possibile selezionare un intervallo di tempo personalizzato.<br/><br/>Per i messaggi, sono disponibili le seguenti opzioni aggiuntive:
    
      - **ID messaggio**. Utilizzare questa pagina per identificare un messaggio specifico quando si conosce l'ID del messaggio.<br/><br/>
    Se ad esempio il mittente o il destinatario di un certo messaggio è un utente dell'organizzazione, ma il messaggio non è stato recapitato al destinatario, è possibile cercarlo usando una traccia messaggio. Vedere [Eseguire una traccia messaggio e visualizzare i risultati](https://go.microsoft.com/fwlink/?LinkId=799737). Se si rileva che il messaggio è stato inviato alla quarantena, probabilmente perché corrisponde a una regola del flusso di posta o è stato identificato come posta indesiderata, è possibile trovare facilmente questo messaggio in quarantena specificando l'ID del messaggio. Assicurarsi di includere la stringa dell'ID del messaggio completo. che potrebbe includere parentesi acute (\<\>), ad esempio:<br/>
    `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`
    
      - **Indirizzo di posta elettronica del mittente**. Scegliere di filtrare in base a un singolo indirizzo di posta elettronica del mittente. 
    
      - **Indirizzo di posta elettronica del destinatario**. Scegliere di filtrare in base a un singolo indirizzo di posta elettronica del destinatario. 
    
      - **Oggetto**. Immettere l'oggetto di un indirizzo di posta elettronica che si desidera trovare. Poiché la ricerca con caratteri jolly non è supportata, è necessario utilizzare l'intero oggetto del messaggio affinché la ricerca restituisca il messaggio nei risultati. La ricerca non è con distinzione tra maiuscole e minuscole. 
    
## <a name="view-details-about-quarantined-messages-and-files"></a>Visualizzare i dettagli relativi ai messaggi e ai file in quarantena

Quando si seleziona un elemento visualizzato nell'elenco quarantena, verrà visualizzato un riepilogo delle relative proprietà nel riquadro dei **Dettagli** a destra del Centro sicurezza &amp; e conformità. 
  
**Dettagli visualizzati per i messaggi in quarantena**
  
- **ID messaggio**. Identificatore univoco del messaggio. 
    
- **Indirizzo del mittente**. Chi ha inviato il messaggio. 
    
- **Ricevuti**. La data e l'ora in cui il messaggio è stato ricevuto. 
    
- **Oggetto**. Il testo della riga dell'oggetto del messaggio. 
    
- **Tipo**. Indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, in **phishing**, in base alla regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.
    
- **Scade**. La data e l'ora in cui il messaggio verrà eliminato automaticamente dalla quarantena. 
    
- **Rilasciato su**. Tutti gli indirizzi di posta elettronica (se presenti) a cui è stato rilasciato il messaggio. 
    
- **Non è stato ancora rilasciato**. Tutti gli indirizzi di posta elettronica (se presenti) a cui il messaggio non è stato ancora rilasciato. 
    
 **Dettagli visualizzati per i file in quarantena**
  
- **Nome file** Nome del file in quarantena. 
    
- **Percorso del sito** URL che definisce la posizione del file in Office 365. 
    
- **Data/ora rilevata** La data e l'ora in cui il file è stato messo in quarantena. 
    
- **Scade** La data in cui il messaggio verrà eliminato dalla quarantena. 
    
- **Rilevato da** Il metodo utilizzato per rilevare il malware nel file. Questo può essere ATP (Advanced Threat Protection) o il motore antimalware di Microsoft. 
    
- **Rilasciato** Descrive se il file è stato rilasciato o meno. 
    
- **Nome malware** Famiglia e nome del malware rilevato nel file. 
    
- **ID documento** Identificatore univoco per il documento. 
    
- **Dimensioni file** Le dimensioni del file in KB. 
    
- **Organizzazione** ID univoco dell'organizzazione in Office 365. 
    
- **Modificato da** L'account aziendale o dell'Istituto di istruzione dell'ultimo utente che ha modificato il file. 
    
- **Dimensioni file** Le dimensioni del file in KB. 
    
- **Hash SHA256** Hash del file. È possibile utilizzare questa pagina per cercare altri archivi di reputazione che potrebbero essere presenti o per individuare il percorso in cui si trova il file nell'ambiente in uso. 
    
## <a name="managing-messages-and-files-in-quarantine"></a>Gestione di messaggi e file in quarantena
<a name="BKMK_ManageQuarantinedItem"> </a>

Dopo aver selezionato un messaggio o un gruppo di messaggi, sono disponibili diverse opzioni per la gestione dei messaggi in quarantena.
  
- Nessuna operazione. Se si sceglie di non eseguire alcuna operazione, il messaggio verrà eliminato automaticamente alla scadenza da Office 365. Per impostazione predefinita, la posta indesiderata, la massa, il malware, il phishing e i messaggi in quarantena perché corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per 30 giorni. I messaggi eliminati dalla quarantena in Office 365 non possono essere recuperati. Se lo si desidera, è possibile modificare il periodo di conservazione per i messaggi in quarantena configurando l'impostazione **Mantieni posta indesiderata per (giorni)** nei criteri di protezione da posta indesiderata. Per ulteriori informazioni, vedere [impostazione del periodo di conservazione della quarantena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in questo articolo. 
    
- **Visualizzare l'intestazione del messaggio** Scegliere questo collegamento per visualizzare il testo dell'intestazione del messaggio. Per analizzare in modo approfondito l'intestazione, copiare il testo dell'intestazione del messaggio negli Appunti e quindi scegliere **analizzatore intestazione messaggio Microsoft** per accedere all'analizzatore connettività remota (fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si desidera lasciare Office 365 per completare questa attività. Incollare l'intestazione del messaggio nella pagina nella sezione Analizzatore intestazioni del messaggio e scegliere **Analyze Headers**.
    
- **Anteprima messaggio** Consente di vedere la versione non elaborata o HTML del testo del corpo del messaggio. Nella visualizzazione HTML i collegamenti sono disabilitati. 
    
- **Scaricare** il file del messaggio o **scaricare**. Scegliere questa opzione per scaricare una copia del messaggio o del file nel dispositivo locale. È necessario verificare che i rischi associati al download degli elementi dalla quarantena siano compresi prima che sia possibile farlo. I messaggi vengono salvati nel formato. eml in una cartella specificata. I file in quarantena vengono salvati nel formato originale.
    
- **Eliminare** Se lo si desidera, è possibile eliminare immediatamente un elemento in quarantena (o un insieme di elementi) anziché attendere la data di scadenza impostata da Office 365. Per eliminare un messaggio o un file, nell'elenco quarantena selezionare l'elemento e quindi scegliere **Elimina**. Per eliminare contemporaneamente più elementi, selezionare la casella di controllo a sinistra degli elementi nell'elenco quarantena e quindi nella pagina **azioni in blocco** visualizzata, scegliere **Elimina messaggi selezionati** o **Elimina file selezionati**.
    
- **Versione** Rilascia un elemento in quarantena (o un insieme di elementi) e segnala gli elementi in quarantena (falsi positivi) a Microsoft. 
    
    Per rilasciare e segnalare un singolo messaggio o file, nell'elenco quarantena selezionare l'elemento, scegliere **rilascia file** o **rilascia messaggio**. Nella pagina successiva, verificare che sia selezionata l'opzione **segnala i messaggi a Microsoft** per l'analisi o **i file di report a Microsoft per l'analisi** . 
    
    Per rilasciare contemporaneamente più elementi, selezionare la casella di controllo a sinistra degli elementi nell'elenco quarantena e quindi nella pagina **azioni in blocco** visualizzata, scegliere **rilascia file** o **rilascia messaggi**. Nella pagina successiva, verificare che sia selezionata l'opzione **segnala i messaggi a Microsoft** per l'analisi o **i file di report a Microsoft per l'analisi** . 
    
Quando si rilasciano i messaggi, tenere presente quanto segue:
  
- Quando si esegue una versione in blocco di più messaggi contemporaneamente, i messaggi vengono rilasciati a tutti i destinatari originariamente identificati. Se si desidera solo rilasciare i messaggi solo a destinatari specifici, è necessario rilasciarli uno alla volta e identificare i destinatari singolarmente.
    
- Un messaggio non può essere rilasciato più di una volta allo stesso destinatario.
    
- Quando si rilascia un messaggio a più destinatari, solo i destinatari che non sono stati precedentemente ricevuti il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.
    
- Quando si sceglie di segnalare falsi positivi, se il messaggio o i messaggi rilasciati sono stati messi in quarantena come posta indesiderata, in blocco, in caso di phishing o come contenente malware, il messaggio verrà segnalato anche al team di analisi di posta indesiderata di Microsoft. Il team valuterà e analizzerà il messaggio e, a seconda dei risultati dell'analisi, le regole di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificate per consentire il messaggio.
    
## <a name="setting-the-quarantine-retention-period"></a>Impostazione del periodo di conservazione della quarantena
<a name="BKMK_ModQuarantineTime"> </a>

È possibile configurare il tempo di permanenza di messaggi e file in quarantena prima della scadenza. Per impostazione predefinita, gli elementi in quarantena vengono conservati per 30 giorni. Questa impostazione viene configurata per ogni criterio creato. È inoltre possibile modificare il valore per il criterio predefinito, come descritto in questo articolo. 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a>Per modificare il periodo di conservazione della quarantena per i criteri di filtro della posta indesiderata predefiniti nel centro sicurezza e conformità

1. L'utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale (o ruoli di sicurezza & conformità corretti) nell'organizzazione di Office 365, accedere a Office 365 e [passare al centro sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md).
    
2. A sinistra espandere **gestione minacce**, scegliere **criteri**e quindi protezione da **posta indesiderata**. <br/>
    > [!TIP]
    > Per passare direttamente alla pagina protezione da **posta indesiderata** nel &amp; Centro sicurezza e conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)
  
 
3. Espandere la riga **criteri di filtro posta indesiderata predefinita (sempre attiva)** . 
    
4. Scegliere **modifica criterio**. Le impostazioni per il criterio di filtro di protezione da posta indesiderata predefinito vengono visualizzate in una nuova pagina.
    
5. Espandere la **posta indesiderata e le azioni in blocco**.
    
6. In **quarantena**, nella casella di testo **Mantieni posta indesiderata per (giorni)** , immettere il periodo di tempo in cui si desidera che Office 365 mantenga i messaggi e i file in quarantena. Il valore predefinito è 30 giorni. Questo è anche il massimo. 
    
7. Fare clic su **Salva**.
    

