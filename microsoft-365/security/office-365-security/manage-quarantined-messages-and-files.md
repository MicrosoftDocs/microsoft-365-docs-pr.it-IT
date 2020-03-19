---
title: Gestire i messaggi e i file in quarantena come amministratore in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (regole di trasporto).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857074"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Gestire i messaggi e i file in quarantena come amministratore in Office 365

La quarantena contiene messaggi potenzialmente pericolosi o indesiderati in Office 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online. Per ulteriori informazioni, vedere [Quarantine in Office 365](quarantine-email-messages.md).

Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto). Gli amministratori possono anche segnalare falsi positivi a Microsoft.

Gli amministratori nelle organizzazioni con Office 365 Advance Threat Protection (ATP) possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.

È possibile visualizzare e gestire i messaggi in quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per i clienti di Office 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il centro conformità & sicurezza di Office 365, passare <https://protection.office.com>a. Per aprire direttamente la pagina di quarantena, andare <https://protection.office.com/quarantine>a.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter gestire la quarantena come amministratore. Le autorizzazioni sono controllate dal ruolo **Quarantine** nel centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli **Gestione organizzazione** (amministratori globali), **amministratori della quarantena**e **amministratore della sicurezza** nel centro sicurezza & conformità. Per ulteriori informazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- I messaggi in quarantena vengono mantenuti per un periodo di tempo predefinito prima di essere eliminati automaticamente:

  - Messaggi in quarantena da criteri di protezione da posta indesiderata (posta indesiderata, phishing e posta elettronica in blocco): 30 giorni. Questo è il valore predefinito e massimo. Per configurare questo valore, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

  - Messaggi messi in quarantena dalle regole del flusso di posta (l'azione della regola è **recapitare il messaggio alla quarantena ospitata**): 30 giorni. Non è possibile modificare questo valore.

  - Messaggi contenenti malware: 15 giorni.

  Quando un messaggio scade dalla quarantena, non è possibile ripristinarlo.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena

### <a name="view-quarantined-email"></a>Visualizzazione posta in quarantena

1. Nel centro sicurezza e conformità, passare alla **quarantena**di **Verifica** \> **della gestione** \> delle minacce.

2. Verificare che la **visualizzazione in quarantena** sia impostata sul valore predefinito **e-mail**.

3. È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile. Fare clic su **modifica colonne** per visualizzare un massimo di sette colonne. I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):

   - **Ricevuto**<sup>\*</sup>

   - **Mittente**<sup>\*</sup>

   - **Oggetto**<sup>\*</sup>

   - **Motivo della quarantena**<sup>\*</sup>

   - **Rilasciato?**<sup>\*</sup>

   - **Tipo di criterio**<sup>\*</sup>

   - **Scade**<sup>\*</sup>

   - **Destinatario**

   - **ID messaggio**

   - **Nome criterio**

   - **Dimensioni**

   - **Direzione**

   Al termine, fare clic su **Salva**o su **Imposta come predefinito**.

4. Per filtrare i risultati, fare clic su **filtro**. I filtri disponibili sono i seguenti:

   - **Scade il tempo**: filtrare i messaggi quando scadranno dalla quarantena:

     - **Oggi**

     - **Prossimi 2 giorni**

     - **Prossimi 7 giorni**

     - **Personalizzato**: immettere una data di **inizio** e una **Data di fine**.

   - **Tempo ricevuto**: immettere una data di **inizio** e una **Data di fine**.

   - **Motivo della quarantena**:

     - **Criterio**: il messaggio corrisponde alle condizioni di una regola del flusso di posta (nota anche come regola di trasporto).

     - **Bulk**

     - **Phishing**

     - **Malware**

     - **Posta indesiderata**

     - **Phishing ad alta sicurezza**

   - **Destinatario di posta elettronica**: tutti gli utenti o solo i messaggi inviati all'utente. Gli utenti finali possono gestire solo i messaggi in quarantena inviati.

   Per cancellare il filtro, fare clic su **Pulisci**. Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtra** .

5. Utilizzare i **risultati di ordinamento** per (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per individuare messaggi specifici. I caratteri jolly non sono supportati. È possibile eseguire una ricerca in base ai valori seguenti:

   - **ID messaggio**: identificatore univoco globale del messaggio.

        Ad esempio, è stata utilizzata la [traccia dei messaggi](message-trace-scc.md) per cercare un messaggio che è stato inviato a un utente nell'organizzazione e si determina che il messaggio è stato messo in quarantena invece di essere recapitato. Assicurarsi di includere il valore dell'ID messaggio completo, che può includere parentesi angolari\<\>(). Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Indirizzo di posta elettronica del mittente**: l'indirizzo di posta elettronica di un singolo mittente.

   - **Indirizzo di posta elettronica del destinatario**: l'indirizzo di posta elettronica di un singolo destinatario.

   - **Oggetto**: utilizzare l'intero oggetto del messaggio. La ricerca non è con distinzione tra maiuscole e minuscole.

   Dopo aver immesso i criteri di ricerca, ![fare clic](../media/scc-quarantine-refresh.png) su **Aggiorna pulsante di aggiornamento per** filtrare i risultati.

Dopo aver individuato uno specifico messaggio in quarantena, selezionare il messaggio per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).

#### <a name="export-message-results"></a>Esportare i risultati dei messaggi

1. Selezionare i messaggi a cui si è interessati e fare clic su **Esporta risultati**.

2. Fare clic su **Sì** nel messaggio di conferma che avvisa di mantenere aperta la finestra del browser.

3. Quando l'esportazione è pronta, è possibile assegnare un nome e scegliere il percorso di download del file. csv.

#### <a name="view-quarantined-message-details"></a>Visualizzare i dettagli dei messaggi in quarantena

Quando si seleziona un messaggio di posta elettronica nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli del messaggio seguenti:

- **ID messaggio**: identificatore univoco globale del messaggio.

- **Indirizzo mittente**

- **Received**: la data e l'ora in cui il messaggio è stato ricevuto.

- **Oggetto**

- **Motivo della quarantena**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrisponde a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.

- **Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **visualizzare l'intestazione del messaggio** per visualizzare l'elenco completo dei destinatari.

- **Scade**: la data e l'ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.

- **Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.

- **Non ancora rilasciato**: tutti gli indirizzi di posta elettronica (se presenti) a cui il messaggio non è stato ancora rilasciato.

### <a name="take-action-on-quarantined-email"></a>Eseguire un'azione sulla posta in quarantena

Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa dei **Dettagli** :

- **Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:

  - **Segnalare i messaggi a Microsoft per l'analisi**: è selezionata per impostazione predefinita e segnala il messaggio in quarantena erroneamente a Microsoft come falso positivo. Se il messaggio è stato messo in quarantena come posta indesiderata, rinfusa, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi di posta indesiderata di Microsoft. A seconda dell'analisi, è possibile modificare le regole di filtro per la posta indesiderata a livello di servizio per consentire il passaggio del messaggio.

  - Scegliere una delle opzioni seguenti:

    - **Rilasciare messaggi a tutti i destinatari**

    - **Rilasciare messaggi a destinatari specifici**

    - **Rilasciare messaggi ad altri utenti**

  Al termine, fare clic su **rilascia messaggi**.

  Note sul rilascio dei messaggi:

  - Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.

  - Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.

- **Visualizza intestazione messaggio**: scegliere questo collegamento per visualizzare il testo dell'intestazione del messaggio. Per analizzare i campi e i valori di intestazione in profondità, copiare il testo dell'intestazione del messaggio negli Appunti e quindi scegliere **analizzatore intestazione messaggio Microsoft** per accedere all'analizzatore connettività remota (fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si desidera lasciare Office 365 per completare questa attività). Incollare l'intestazione del messaggio nella pagina nella sezione Analizzatore intestazioni del messaggio e scegliere **Analyze Headers**:

- **Messaggio di anteprima**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:

  - **Visualizzazione origine**: Mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.
  
  - **Visualizzazione testo**: Mostra il corpo del messaggio in formato testo normale.

- **Rimuovi dalla quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.

- **Scarica messaggio**: nel riquadro a comparsa visualizzato, selezionare i **rischi per il download di questo messaggio** per salvare una copia locale del messaggio in formato. eml.

- **Invia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:

  - **Tipo di oggetto**: **posta elettronica** (impostazione predefinita), **URL**o **allegato**.

  - **Formato di invio**: **ID messaggio di rete** (impostazione predefinita, con il valore corrispondente nella casella **ID messaggio di rete** ) oppure **file** (passare a un file local. eml o. msg). Si noti che se si seleziona **file** e quindi si seleziona **ID messaggio di rete**, il valore iniziale è Gone.

  - **Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona tutto** per identificare tutti i destinatari. È inoltre possibile fare clic su **Seleziona tutto** e quindi rimuovere selettivamente i singoli destinatari.

  - **Motivo dell'invio**: **non deve essere stato bloccato** (impostazione predefinita) o **deve essere stato bloccato**.

  Al termine, fare clic su **Invia**.

Se non si rilascia o si rimuove il messaggio, verrà eliminato dopo la scadenza del periodo di conservazione della quarantena predefinito.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Eseguire un'azione su più messaggi di posta elettronica in quarantena

Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:

- **Rilascia messaggi**: le opzioni sono uguali a quelle rilasciate da un singolo messaggio, tranne per il fatto che non è possibile selezionare **rilascia messaggi a destinatari specifici**. è possibile selezionare rilascia solo il **messaggio a tutti i destinatari** o **rilascia messaggi ad altri utenti**.

- **Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.

Al termine, fare clic su **Chiudi**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Solo ATP: utilizzare il Centro sicurezza & Compliance per gestire i file in quarantena

> [!NOTE]
> Le procedure per i file in quarantena in questa sezione sono disponibili solo per i sottoscrittori ATP Plan 1 e Plan 2.

Nelle organizzazioni con ATP, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.

### <a name="view-quarantined-files"></a>Visualizzare i file in quarantena

1. Nel centro sicurezza e conformità, passare alla **quarantena**di **Verifica** \> **della gestione** \> delle minacce.

2. Modificare la **visualizzazione in quarantena** nei **file**di valore predefiniti. È possibile ordinare su un campo facendo clic su un'intestazione di colonna disponibile.

3. È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile. Fare clic su **modifica colonne** per visualizzare un massimo di sette colonne. Le colonne predefinite sono contrassegnate con un asterisco<sup>\*</sup>():

   - **Utente:**<sup>\*</sup>

   - **Percorso**<sup>\*</sup>

   - **Nome file**<sup>\*</sup>

   - **URL file**<sup>\*</sup>

   - **Dimensioni file**<sup>\*</sup>

   - **Scade**<sup>\*</sup>

   - **Rilasciato?**<sup>\*</sup>

   - **Rilevato da**

   - **Modificato dal tempo**

4. Per filtrare i risultati, fare clic su **filtro**. I filtri disponibili sono i seguenti:

   - **Scade il tempo**: filtrare i messaggi quando scadranno dalla quarantena:

     - **Oggi**

     - **Prossimi 2 giorni**

     - **Prossimi 7 giorni**

     - Un intervallo di data/ora personalizzato.

   - **Tempo ricevuto**

   - **Motivo della quarantena**: l'unico valore disponibile è **malware**.

Dopo aver individuato uno specifico file in quarantena, selezionare il file per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).

#### <a name="export-file-results"></a>Esportare i risultati dei file

1. Selezionare i file a cui si è interessati e fare clic su **Esporta risultati**.

2. Fare clic su **Sì** nel messaggio di conferma che avvisa di mantenere aperta la finestra del browser.

3. Quando l'esportazione è pronta, è possibile assegnare un nome e scegliere il percorso di download del file. csv.

#### <a name="view-quarantined-file-details"></a>Visualizzare i dettagli dei file in quarantena

Quando si seleziona un file nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli dei file seguenti:

- **FileName**

- **URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.

- **Contenuto dannoso rilevato** La data e l'ora in cui il file è stato messo in quarantena.

- **Scade**: la data in cui il file verrà eliminato dalla quarantena.

- **Rilevato da**: ATP (Advanced Threat Protection) o dal motore antimalware di Microsoft.

- **Rilasciato?**

- **Nome malware**

- **ID documento**: identificatore univoco per il documento.

- **Dimensioni file**: in KILOBYTE (KB).

- **Organizzazione** ID univoco dell'organizzazione.

- **Data ultima modifica**

- **Modified by**: l'ultimo utente che ha modificato il file.

- **Secure Hash Algorithm 256-bit (SHA-256) valore**: è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni nell'ambiente.

### <a name="take-action-on-quarantined-files"></a>Eseguire un'azione sui file in quarantena

Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti nel file nel riquadro a comparsa dei **Dettagli** :

- **Rilasciare file**: selezionare (impostazione predefinita) o deselezionare **i file di report in Microsoft per l'analisi**e quindi fare clic su **rilascia file**.

- **Scaricare il file**

- **Rimuovi file dalla quarantena**

Se i file non vengono rilasciati o rimossi, verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.

#### <a name="actions-on-multiple-quarantined-files"></a>Azioni su più file in quarantena

Quando si selezionano più file in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:

- **Rilasciare i file**

- **Elimina file**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i file vengono eliminati immediatamente.

Al termine, fare clic su **Chiudi**.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Utilizzare Exchange Online PowerShell o standalone Exchange Online Protection PowerShell per visualizzare e gestire i messaggi e i file in quarantena

I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono i seguenti:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): si noti che questo cmdlet è solo per i messaggi, non per i file malware da ATP per SharePoint Online, OneDrive for business o teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
