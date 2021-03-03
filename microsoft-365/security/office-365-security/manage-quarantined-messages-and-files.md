---
title: Gestire i messaggi e i file in quarantena come amministratore
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a visualizzare e gestire i messaggi in quarantena per tutti gli utenti in Exchange Online Protection (EOP). Gli amministratori delle organizzazioni con Microsoft Defender per Office 365 possono anche gestire i file in quarantena in SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0515d610b38986c2b5339c1cb967a7b150914a2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405819"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Gestire i messaggi e i file messi in quarantena come amministratore in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati. Per ulteriori informazioni, vedere [Messaggi di posta elettronica in quarantena in EOP.](quarantine-email-messages.md)

Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono gestire i messaggi messi in quarantena come malware, phishing ad alta probabilità o come risultato delle regole del flusso di posta (note anche come regole di trasporto). Gli amministratori possono anche segnalare falsi positivi a Microsoft.

Gli amministratori delle organizzazioni con Microsoft Defender per Office 365 possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for Business e Microsoft Teams.

I messaggi in quarantena vengono visualizzati e gestiti nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>. Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**
  - Per intervenire sui messaggi in quarantena per tutti gli utenti, è necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Amministratore sicurezza o **Amministratore** <sup>\*</sup> quarantena.
  - Per l'accesso in sola lettura ai messaggi in quarantena per  tutti  gli utenti, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365.  Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.
  - <sup>\*</sup> I membri del **gruppo di** ruoli Amministratore quarantena devono inoltre essere membri del gruppo di ruoli Gestione **di Hygiene** in Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) per eseguire le procedure di quarantena in PowerShell di Exchange Online.

- I messaggi in quarantena vengono conservati per un periodo di tempo predefinito prima di essere eliminati automaticamente:
  - 30 giorni per i messaggi messi in quarantena dai criteri di protezione dalla posta indesiderata (posta indesiderata, phishing e posta elettronica in blocco). Questo è il valore predefinito e il valore massimo. Per configurare (inferiore) questo valore, vedere [Configurare i criteri di protezione da posta indesiderata.](configure-your-spam-filter-policies.md)
  - 15 giorni per i messaggi contenenti malware.
  - 15 giorni per i file messi in quarantena dagli allegati sicuri per SharePoint, OneDrive e Microsoft Teams in Defender per Office 365.

  Quando un messaggio scade dalla quarantena, non è possibile recuperarlo.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Usare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena

### <a name="view-quarantined-email"></a>Visualizzare la posta elettronica in quarantena

1. Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.

2. Verificare che **la visualizzazione in quarantena** sia impostata sul valore predefinito e-mail. 

3. È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile. Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne. I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):

   - **Ricevuto**<sup>\*</sup>
   - **Mittente**<sup>\*</sup>
   - **Oggetto**<sup>\*</sup>
   - **Motivo della quarantena**<sup>\*</sup>
   - **Rilasciato?**<sup>\*</sup>
   - **Tipo di criterio**<sup>\*</sup>
   - **Scadenza**
   - **Destinatario**
   - **ID messaggio**
   - **Nome criterio**
   - **Dimensioni**
   - **Direzione**

   Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.

4. Per filtrare i risultati, selezionare **Filtro**. I filtri disponibili sono:

   - **Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:
     - **Oggi**
     - **Prossimi 2 giorni**
     - **Prossimi 7 giorni**
     - **Personalizzato**: immettere una **data di inizio** e una **data di fine**.

   - **Ora ricezione**: immettere una **data di inizio** e una **data di fine**.

   - **Motivo della quarantena**:
     - **Criterio:** il messaggio soddisfa le condizioni di una regola del flusso di posta (nota anche come regola di trasporto).
     - **Invio in blocco**
     - **Phishing:** il verdetto del filtro della posta indesiderata è stato posta elettronica di **phishing** o protezione anti-phishing messo in quarantena il messaggio ([impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) o [protezione della rappresentazione).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
     - **Malware**
     - **Posta indesiderata**
     - **Phish ad alta confidenza**

   - **Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:
     - **Criteri antimalware**
     - **Criteri allegati sicuri**
     - **Criteri anti-phishing**
     - **Criteri filtro contenuti ospitati** (criteri di protezione dalla posta indesiderata)
     - **Regola di trasporto**

   - **Destinatario di** posta elettronica: tutti gli utenti o solo i messaggi inviati all'utente. Gli utenti finali possono gestire solo i messaggi in quarantena inviati loro.

   Per cancellare il filtro, fare clic su **Cancella**. Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.

5. Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici. I caratteri jolly non sono supportati. È possibile cercare in base ai seguenti valori:

   - **ID messaggio**: identificatore univoco globale del messaggio.

     Ad esempio, [](message-trace-scc.md) è stata utilizzata la traccia dei messaggi per cercare un messaggio inviato a un utente dell'organizzazione e si determina che il messaggio è stato messo in quarantena anziché recapitato. Assicurarsi di includere il valore completo dell'ID messaggio, che potrebbe includere parentesi angolari ( \<\> ). Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.

   - **Nome dei criteri**: usare l'intero nome dei criteri del messaggio. Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.

   - **Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.

   - **Oggetto**: utilizzare l'intero oggetto del messaggio. Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.

   - **Nome criterio:** il nome del criterio responsabile della messa in sicurezza del messaggio.

   Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.

Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).

#### <a name="view-quarantined-message-details"></a>Visualizzare i dettagli dei messaggi in quarantena

Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:

- **ID messaggio**: identificatore univoco globale per il messaggio.

- **Indirizzo del mittente**

- **Ricezione**: data/ora di ricezione del messaggio.

- **Oggetto**

- **Motivo quarantena:** indica se un messaggio è stato identificato come Posta **indesiderata,** In **blocco,** **Phish,** corrisponde a una regola del flusso di posta **(** regola di trasporto ) o è stato identificato come contenente **malware.**

- **Numero di destinatari**

- **Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.

- **Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.

- **Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.

- **Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.

### <a name="take-action-on-quarantined-email"></a>Eseguire azioni sulla posta elettronica in quarantena

Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le azioni da eseguire sui messaggi nel **riquadro** a comparsa Dettagli:

- **Messaggio di** rilascio: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:

  - **Segnalare i messaggi** a Microsoft per l'analisi: questa opzione è selezionata per impostazione predefinita e segnala il messaggio erroneamente in quarantena a Microsoft come falso positivo. Se il messaggio è stato messo in quarantena come posta indesiderata, in blocco, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi della posta indesiderata di Microsoft. A seconda dell'analisi, le regole di filtro della posta indesiderata a livello di servizio potrebbero essere modificate per consentire l'invio del messaggio.

  - Scegliere una delle opzioni seguenti:
    - **Rilasciare messaggi a tutti i destinatari**
    - **Rilasciare messaggi a destinatari specifici**
    - **Rilasciare messaggi ad altre persone:** si noti che il rilascio di messaggi di malware a utenti diversi dai destinatari originali non è supportato.

  Al termine, fare clic su **Rilascia messaggio**.

  Note sul rilascio dei messaggi:

  - Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.
  - Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei potenziali destinatari.

- **Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio. Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività. Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:

- **Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:

  - **Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.
  - **Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.

- **Rimuovi dalla quarantena:** dopo aver fatto clic su **Sì** nell'avviso visualizzato, il messaggio viene immediatamente eliminato senza essere inviato ai destinatari originali.

- **Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.

- **Invia messaggio:** nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:

  - **Tipo di oggetto:** **Posta** elettronica (impostazione predefinita), **URL** o **Allegato.**

  - **Formato invio**: **ID** messaggio di rete (impostazione predefinita, con il valore corrispondente nella casella **ID** messaggio di rete) o **File** (passare a un file con estensione eml o msg locale). Si noti che se si seleziona **File** e quindi si seleziona **ID messaggio di** rete, il valore iniziale non è più disponibile.

  - **Destinatari:** digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona** tutto per identificare tutti i destinatari. È inoltre possibile fare clic **su Seleziona tutto** e quindi rimuovere in modo selettivo singoli destinatari.

  - **Motivo dell'invio:** **non deve essere stato bloccato** (impostazione predefinita) o deve essere stato **bloccato.**

  Al termine, fare clic su **Invia.**

Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Eseguire azioni su più messaggi di posta elettronica in quarantena

Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:

- **Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.

  > [!NOTE]
  > Considerare lo scenario seguente: john@gmail.com invia un messaggio a faith@contoso.com e john@subsidiary.contoso.com. Gmail biforca questo messaggio in due copie che vengono entrambe instradati in quarantena come phishing in Microsoft. Un amministratore rilascia entrambi questi messaggi a admin@contoso.com. Il primo messaggio rilasciato che raggiunge la cassetta postale dell'amministratore viene recapitato. Il secondo messaggio rilasciato viene identificato come recapito duplicato e viene ignorato. I messaggi vengono identificati come duplicati se hanno lo stesso ID messaggio e l'ora di ricezione.

- **Elimina messaggi:** dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi vengono immediatamente eliminati senza essere inviati ai destinatari originali.

Al termine, fare clic su **Chiudi**.

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Solo Microsoft Defender per Office 365: Usare il Centro sicurezza & conformità per gestire i file in quarantena

> [!NOTE]
> Le procedure per i file in quarantena in questa sezione sono disponibili solo per gli abbonati a Microsoft Defender per Office 365 Piano 1 e Piano 2.

Nelle organizzazioni con Defender per Office 365, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for Business e Microsoft Teams. Per abilitare la protezione per questi file, vedere [Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>Visualizzare i file in quarantena

1. Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.

2. Modificare **la visualizzazione in quarantena** per i file di **valore.** È possibile ordinare un campo facendo clic su un'intestazione di colonna disponibile.

3. È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile. Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne. Le colonne predefinite sono contrassegnate con un asterisco ( <sup>\*</sup> ):

   - **Utente:**<sup>\*</sup>
   - **Posizione**<sup>\*</sup>
   - **Nome file**<sup>\*</sup>
   - **File URL**<sup>\*</sup>
   - **Dimensioni file**<sup>\*</sup>
   - **Scadenza**<sup>\*</sup>
   - **Rilasciato?**<sup>\*</sup>
   - **Rilevato da**
   - **Modificato in base all'ora**

4. Per filtrare i risultati, selezionare **Filtro**. I filtri disponibili sono:

   - **Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:
     - **Oggi**
     - **Prossimi 2 giorni**
     - **Prossimi 7 giorni**
     - Un intervallo di data/ora personalizzato.
   - **Ora ricezione**
   - **Motivo quarantena:** l'unico valore disponibile è **Malware.**
   - **Tipo di criterio**

Dopo aver trovato un file in quarantena specifico, selezionare il file per visualizzarvi i dettagli e intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).

#### <a name="view-quarantined-file-details"></a>Visualizzare i dettagli dei file in quarantena

Quando si seleziona un file nell'elenco, nel  riquadro a comparsa Dettagli vengono visualizzati i dettagli seguenti:

- **FileName**
- **URL file**: URL che definisce il percorso del file , ad esempio in SharePoint Online.
- **Contenuto dannoso rilevato** Data/ora in cui il file è stato messo in quarantena.
- **Scadenza: data** in cui il file verrà eliminato dalla quarantena.
- **Rilevato da**: Defender per Office 365 o il motore antimalware di Microsoft.
- **Rilasciato?**
- **Nome malware**
- **ID documento:** identificatore univoco per il documento.
- **Dimensioni file**: in kilobyte (KB).
- **Organizzazione** ID univoco dell'organizzazione.
- **Data ultima modifica**
- **Modificato da:** l'ultimo utente che ha modificato il file.
- **Valore SHA-256 (Secure Hash Algorithm) a 256 bit:** è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni dell'ambiente.

### <a name="take-action-on-quarantined-files"></a>Eseguire un'azione sui file in quarantena

Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti sul file nel **riquadro a** comparsa Dettagli:

- **Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click Release **files**.
- **Scarica file**
- **Rimuovere un file dalla quarantena**

Se non si rilasciano o si rimuovono i file, questi verranno eliminati alla scadenza del periodo di conservazione della quarantena predefinito.

#### <a name="actions-on-multiple-quarantined-files"></a>Azioni su più file in quarantena

Quando si selezionano più file in quarantena nell'elenco  (fino a 100), viene visualizzato il riquadro a comparsa Azioni in blocco in cui è possibile eseguire le azioni seguenti:

- **Versione dei file**
- **Elimina file:** dopo aver fatto clic su **Sì** nell'avviso visualizzato, i file vengono eliminati immediatamente.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Utilizzare PowerShell di Exchange Online o PowerShell di EOP autonomo per visualizzare e gestire i messaggi e i file in quarantena

I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)si noti che questo cmdlet è solo per i messaggi e non per i file di malware provenienti da Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
