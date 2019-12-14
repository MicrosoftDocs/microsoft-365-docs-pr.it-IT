---
title: Trovare e rilasciare i messaggi messi in quarantena come utente di Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: "Gli utenti di Office 365 possono gestire i propri messaggi di posta indesiderata messi in quarantena in due modi: rispondendo alle notifiche di posta indesiderata inviate direttamente a loro (se l'amministratore ha configurato questa funzionalità) oppure usando la funzionalità Quarantena posta indesiderata del &amp;Centro sicurezza e conformità."
ms.openlocfilehash: c912c19571cde31c39f4ca3f44c7628ba8b29526
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970462"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Trovare e rilasciare i messaggi messi in quarantena come utente di Office 365

Gli utenti di Office 365 possono gestire i messaggi inviati in quarantena anziché a loro in due modi: [rispondendo alle notifiche di posta indesiderata inviate direttamente a loro ](use-spam-notifications-to-release-and-report-quarantined-messages.md)(se l'amministratore ha configurato la funzionalità) oppure usando il &amp;Centro sicurezza e conformità.

> [!NOTE]
> Gli amministratori possono [gestire i messaggi in quarantena](manage-quarantined-messages-and-files.md) per gli altri utenti dell'organizzazione.

## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Visualizzare i messaggi non ricevuti perché messi in quarantena

1. Eseguire l’accesso a Office 365 e [passare al Centro sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md) usando l'account aziendale o dell'istituto di istruzione.

2. A sinistra, espandere **Gestione delle minacce**, scegliere **Revisione**, poi scegliere **Quarantena**.

    > [!TIP]
    > Per passare direttamente alla pagina **Quarantena** nel &amp;Centro sicurezza e conformità, usare questo URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)

Per impostazione predefinita, il &amp;Centro sicurezza e conformità visualizza tutti i messaggi di posta elettronica messi in quarantena come posta indesiderata. I messaggi sono ordinati dal più recente al più vecchio in base alla **Data** in cui sono stati ricevuti. **Mittente**, **Oggetto** e la data di scadenza (in **Scadenza**) vengono visualizzati anche per i singoli messaggi. È possibile ordinare in base a un campo facendo clic sull'intestazione di colonna corrispondente. Se si fa clic una seconda volta sull'intestazione di una colonna, si inverte il tipo di ordinamento.

È possibile visualizzare un elenco di tutti i messaggi messi in quarantena oppure cercarne alcuni specifici tramite filtro. Le operazioni in blocco possono essere eseguite su un massimo di 100 elementi, quindi i filtri aiutano anche a ridurre il numero di risultati se sono presenti più elementi. È possibile filtrare rapidamente i messaggi per un singolo motivo di quarantena scegliendo un'opzione nell'elenco a discesa. Le opzioni disponibili sono:

- Messaggio identificato come posta indesiderata. Questi messaggi in quarantena sono visualizzati per impostazione predefinita.

- Messaggio identificato come posta inviata in blocco.

Dopo aver trovato uno specifico messaggio in quarantena, fare clic sul messaggio per visualizzare i relativi dettagli e procedere. È possibile rilasciare il messaggio nella cassetta postale, visualizzare in anteprima il messaggio, scaricare il messaggio o eliminare direttamente il messaggio dalla quarantena.

> [!NOTE]
> Per gestire i messaggi in quarantena inviati ad altri utenti, è necessario avere le autorizzazioni di amministratore in Office 365.

## <a name="to-filter-and-find-quarantined-messages"></a>Per filtrare e trovare messaggi in quarantena

Se sono presenti molti elementi in quarantena, è possibile ridurne il numero usando i filtri.

1. Nella pagina **Quarantena** scegliere se visualizzare la **posta indesiderata** o i messaggi in quarantena **in blocco**.

2. In **Ordina i risultati** scegliere una combinazione di condizioni impostando il filtro o i filtri appropriati. Al momento non è possibile usare i caratteri jolly. È possibile scegliere condizioni diverse, ad esempio:

   - **ID messaggio**: usare questa condizione per selezionare un messaggio specifico di cui si conosce l'ID.

     Se ad esempio il mittente o il destinatario di un certo messaggio è un utente dell'organizzazione, ma il messaggio non è stato recapitato al destinatario, è possibile cercarlo usando una traccia messaggio (vedere [Traccia messaggio nel Centro sicurezza e conformità](message-trace-scc.md)). Se si scopre che il messaggio è stato messo in quarantena, ad esempio perché corrisponde a una regola del flusso di posta o è stato identificato come posta indesiderata, è possibile trovarlo facilmente specificando il relativo ID. Assicurarsi di includere la stringa completa dell'ID del messaggio, che potrebbe includere parentesi acute (\<\>), ad esempio:

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - **Indirizzo di posta elettronica del mittente**: scegliere di filtrare in base all'indirizzo di posta elettronica di un singolo mittente.

   - **Indirizzo di posta elettronica del destinatario**: scegliere di filtrare in base all'indirizzo di posta elettronica di un singolo destinatario.

   - **Oggetto**: immettere l'oggetto di un indirizzo di posta elettronica da cercare.

   - **Intervallo date**: è possibile scegliere di filtrare in base alla data il messaggio inviato in quarantena. È possibile specificare la data o un intervallo di date, inclusa l'ora.

   - **Data scadenza**: per filtrare in base alla data di scadenza, scegliere **Filtro avanzato**. È possibile selezionare i messaggi che verranno eliminati dalla quarantena nelle prossime 24 ore (**Oggi**), nelle prossime 48 ore (**Prossimi 2 giorni**), nella prossima settimana (**Prossimi 7 giorni**) oppure selezionare un intervallo di tempo personalizzato.

     > [!IMPORTANT]
     > Per impostazione predefinita, i messaggi di posta indesiderata e inviati in blocco vengono mantenuti in quarantena per 30 giorni. Tuttavia, questo periodo di tempo è configurabile e l'amministratore potrebbe aver impostato un periodo di conservazione in quarantena diverso. I messaggi eliminati dalla quarantena in Office 365 non possono essere recuperati.

## <a name="view-details-for-a-specific-message"></a>Visualizzare i dettagli di un messaggio specifico

Dopo aver selezionato un messaggio, viene visualizzato un riepilogo delle relative proprietà in un riquadro a destra della pagina.

- **ID messaggio**: identificatore univoco del messaggio.

- **Indirizzo mittente**: mittente del messaggio.

- **Ricezione**: data di ricezione del messaggio.

- **Oggetto**: testo della riga dell'oggetto del messaggio.

- **Motivo quarantena**: indica se un messaggio è stato identificato come **Posta indesiderata** o **In blocco**.

- **Scadenza**: data in cui il messaggio verrà eliminato dalla quarantena.

- **Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.

- **Non ancora rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio non è stato rilasciato. È possibile scegliere **Rilasciato** se si vuole rilasciare il messaggio alla cassetta postale. Per altre informazioni sul rilascio dei messaggi, vedere la sezione successiva.

È possibile recuperare altri dettagli sul messaggio scegliendo una delle opzioni seguenti:

- **Visualizza intestazione messaggio**: scegliere questa opzione per vedere il testo dell'intestazione del messaggio. Per analizzare l'intestazione in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer ** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere Apri in una nuova scheda se non si vuole uscire da Office 365 per completare questa attività. Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere Analizza intestazioni.

- **Anteprima messaggio**: consente di vedere la versione non elaborata o HTML del testo del corpo del messaggio. Nella visualizzazione HTML i collegamenti sono disabilitati.

## <a name="manage-your-quarantined-messages"></a>Gestione dei messaggi in quarantena

Dopo aver selezionato un messaggio o un gruppo di messaggi, sono disponibili diverse opzioni per la gestione dei messaggi in quarantena.

- Nessuna operazione. Se si sceglie di non eseguire alcuna operazione, il messaggio verrà eliminato automaticamente alla scadenza da Office 365. Tenere presente che i messaggi eliminati dalla quarantena in Office 365 non possono essere recuperati.

- **Rilascia messaggio**: rilasciare un messaggio (o un gruppo di messaggi) dalla quarantena in modo che il messaggio venga inviato alla cassetta postale. Dopo aver rilasciato un messaggio, è possibile segnalarlo a Microsoft per l'analisi.

    Se si sceglie di segnalare un messaggio come falso positivo, il messaggio viene segnalato al team di analisi della posta indesiderata Microsoft. Il team valuta e analizza il messaggio come falso positivo e, in base ai risultati dell'analisi, è possibile che le regole di filtro del contenuto della posta indesiderata a livello di intero servizio vengano modificate per consentirne la ricezione.

- **Rimuovi dalla quarantena**: elimina il messaggio immediatamente dalla quarantena senza rilasciare il messaggio alla cassetta postale.
