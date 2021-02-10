---
title: Trovare e rilasciare messaggi in quarantena come utente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come gli utenti possono visualizzare e gestire i messaggi in quarantena in Exchange Online Protection (EOP) che avrebbero dovuto essere recapitati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 126bf1f8c8ea8c16242b7b3749066131e8942304
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166136"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>Trovare e rilasciare i messaggi messi in quarantena come utente di EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati. Per altre informazioni, vedere [Quarantena in EOP](quarantine-email-messages.md).

L'utente può visualizzare, rilasciare ed eliminare i messaggi in quarantena di cui si è destinatari e che sono stati messi in quarantena come posta indesiderata o posta inviata in blocco. A partire da aprile 2020 è possibile visualizzare o eliminare i messaggi di phishing in quarantena, ad esclusione del phishing con alta confidenza, di cui si è destinatari. È possibile visualizzare e gestire i messaggi in quarantena nel Centro sicurezza e conformità oppure, nel caso in cui un amministratore l'abbia configurato, nelle [notifiche di posta indesiderata per l'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>. Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.

- Gli amministratori possono configurare per quanto tempo i messaggi vengono tenuti in quarantena prima di essere eliminati definitivamente (criteri di protezione dalla posta indesiderata). I messaggi scaduti dalla quarantena non sono recuperabili. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

- Gli amministratori possono anche [abilitare le notifiche di posta indesiderata per l'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) nei criteri di protezione dalla posta indesiderata. Gli utenti possono rilasciare messaggi di posta indesiderata in quarantena direttamente da queste notifiche. Gli utenti possono rivedere i messaggi di phishing in quarantena, non messaggi di phishing con probabilità elevata, direttamente da queste notifiche. Per altre informazioni, vedere [Notifiche di posta indesiderata per l'utente finale in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- I messaggi messi in quarantena per alta probabilà di phishing, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori e non sono visibili agli utenti. Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

- È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.

## <a name="view-your-quarantined-messages"></a>Visualizzazione dei messaggi in quarantena

1. Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.

2. È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile. Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne. I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):

   - **Ricevuto**<sup>\*</sup>
   - **Mittente**<sup>\*</sup>
   - **Oggetto**<sup>\*</sup>
   - **Motivo della quarantena**<sup>\*</sup>
   - **Rilasciato?**<sup>\*</sup>
   - **Tipo di criterio**<sup>\*</sup>
   - **Scadenza**<sup>\*</sup>
   - **Destinatario**
   - **ID messaggio**
   - **Nome criterio**
   - **Dimensioni**
   - **Direzione**

   Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.

3. Per filtrare i risultati, selezionare **Filtro**. I filtri disponibili sono:

   - **Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:
     - **Oggi**
     - **Prossimi 2 giorni**
     - **Prossimi 7 giorni**
     - **Personalizzato**: immettere una **data di inizio** e una **data di fine**.

   - **Ora ricezione**: immettere una **data di inizio** e una **data di fine**.

   - **Motivo della quarantena**:
     - **Invio in blocco**
     - **Posta indesiderata**
     - **Phishing**

   - **Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:
     - **Criteri anti-phishing**
     - **Criteri filtro contenuti ospitati** (criteri di protezione dalla posta indesiderata)

   Per cancellare il filtro, fare clic su **Cancella**. Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.

4. Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici. I caratteri jolly non sono supportati. È possibile cercare in base ai seguenti valori:

   - **ID messaggio**: identificatore univoco globale del messaggio. Se si seleziona un messaggio nell'elenco, il valore **ID messaggio** viene visualizzato nel riquadro a comparsa **Dettagli**. Gli amministratori possono usare [Traccia messaggio](message-trace-scc.md) per trovare i messaggi e i valori ID messaggio corrispondenti.

   - **Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.

   - **Nome dei criteri**: usare l'intero nome dei criteri del messaggio. Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.

   - **Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.

   - **Oggetto**: utilizzare l'intero oggetto del messaggio. Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.

   Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.

Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).

### <a name="export-message-results"></a>Esportare i risultati di un messaggio

1. Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.

2. Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.

3. Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.

### <a name="view-quarantined-message-details"></a>Visualizzare i dettagli dei messaggi in quarantena

Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:

- **ID messaggio**: identificatore univoco globale per il messaggio.

- **Indirizzo del mittente**

- **Ricezione**: data/ora di ricezione del messaggio.

- **Oggetto**

- **Motivo quarantena**: indica se un messaggio è stato identificato come **Posta indesiderata**, **Invio in blocco** o **Phishing**.

- **Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.

- **Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.

- **Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.

- **Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.

### <a name="take-action-on-quarantined-email"></a>Eseguire azioni sulla posta elettronica in quarantena

Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa **Dettagli**:

- **Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere se **segnalare i messaggi a Microsoft per l'analisi**. Questa opzione è selezionata per impostazione predefinita e riporta il messaggio messo in quarantena per errore a Microsoft come falso positivo.

  Al termine, fare clic su **Rilascia messaggio**.

- **Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio. Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività. Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:

- **Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:
  - **Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.
  - **Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.

- **Rimuovi da quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente.

Al termine, fare clic su **Chiudi**.

Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Eseguire azioni su più messaggi di posta elettronica in quarantena

Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:

- **Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.

- **Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.

Al termine, fare clic su **Chiudi**.
