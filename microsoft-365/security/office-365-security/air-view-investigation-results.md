---
title: Visualizzare i risultati di un'indagine automatizzata in Microsoft 365
keywords: AIR, autoIR, ATP, automatizzato, indagine, correzione, azioni
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Durante e dopo un'indagine automatizzata in Microsoft 365, è possibile visualizzare i risultati e i risultati chiave.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bf18a9fb80805581a1439b3965a664fd0868248
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205532"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Dettagli e risultati di un'indagine automatizzata in Microsoft 365

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Quando si [verifica un'indagine](office-365-air.md) automatizzata in [Microsoft Defender per Office 365,](defender-for-office-365.md)i dettagli su tale indagine sono disponibili durante e dopo il processo di indagine automatizzata. Se si dispone delle autorizzazioni necessarie, è possibile visualizzare tali dettagli nel Centro sicurezza Microsoft 365. I dettagli dell'indagine forniscono lo stato aggiornato e la possibilità di approvare eventuali azioni in sospeso.

> [!TIP]
> Vedere la nuova pagina di indagine unificata nel Centro sicurezza Microsoft 365. Per ulteriori informazioni, vedere [(NEW!) Pagina di indagine unificata](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Stato dell'indagine

Lo stato dell'indagine indica l'avanzamento dell'analisi e delle azioni. Durante l'esecuzione dell'indagine, lo stato cambia per indicare se sono state trovate minacce e se le azioni sono state approvate.

|Stato|Descrizione|
|:---|:---|
|**In avvio**|L'indagine è stata attivata e in attesa di avviare l'esecuzione.|
|**In esecuzione**|Il processo di indagine è iniziato ed è in corso. Questo stato si verifica anche quando [le azioni in sospeso](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) vengono approvate.|
|**Nessuna minaccia trovata**|L'indagine è terminata e non sono state identificate minacce (account utente, messaggio di posta elettronica, URL o file). <p> **SUGGERIMENTO:** se si sospetta che qualcosa sia stato perso (ad esempio un falso negativo), è possibile eseguire un'azione utilizzando [Esplora minacce.](threat-explorer.md)|
|**Minacce trovate**|L'indagine automatizzata ha rilevato problemi, ma non esistono azioni di correzione specifiche per risolverli. <p> Lo **stato Minacce trovate** può verificarsi quando è stato identificato un tipo di attività utente, ma non sono disponibili azioni di pulizia. Tra gli esempi sono incluse le attività utente seguenti: <br/>- Un [evento di prevenzione della](../../compliance/data-loss-prevention-policies.md) perdita dei dati (DLP)<br/>- Anomalia di invio di un messaggio di posta elettronica<br/>- Malware inviato<br/>- Phish inviato <p> L'indagine non ha rilevato URL, file o messaggi di posta elettronica dannosi da correggere e nessuna attività della cassetta postale da correggere, ad esempio la disattivazione delle regole di inoltro o della delega. <p> **SUGGERIMENTO:** se si sospetta che sia stato perso qualcosa (ad esempio un falso negativo), è possibile analizzare ed eseguire azioni tramite [Threat Explorer.](threat-explorer.md)|
|**Terminated By System**|L'indagine è stata interrotta. Un'indagine può interrompersi per diversi motivi: <br/>- Le azioni in sospeso dell'indagine sono scadute. Timeout delle azioni in sospeso dopo l'attesa dell'approvazione per una settimana.<br/>- Sono presenti troppe azioni. Ad esempio, se ci sono troppi utenti che fa clic su URL dannosi, può superare la capacità dell'indagine di eseguire tutti gli analizzatori, quindi l'indagine si interrompe.<p> **SUGGERIMENTO:** se un'indagine si interrompe prima dell'azione, prova a usare [Esplora](threat-explorer.md) minacce per trovare e affrontare le minacce.|
|**Azione in sospeso**|L'indagine ha rilevato una minaccia, ad esempio un messaggio di posta elettronica dannoso, un URL dannoso o un'impostazione della cassetta postale rischiosa e un'azione per correggere tale minaccia in attesa di [approvazione.](air-review-approve-pending-completed-actions.md) <p> Lo **stato Azione** in sospeso viene attivato quando viene trovata qualsiasi minaccia con un'azione corrispondente. Tuttavia, l'elenco delle azioni in sospeso può aumentare durante l'esecuzione di un'indagine. Visualizzare i dettagli dell'indagine per verificare se altri elementi sono ancora in attesa di completamento.|
|**Correzione**|L'indagine è stata completata e tutte le azioni di correzione sono state approvate (come completamente corretti). <p> **NOTA:** le azioni di correzione approvate possono contenere errori che impediscono l'azione. Indipendentemente dal fatto che le azioni di correzione siano state completate correttamente, lo stato dell'indagine non cambia. Visualizzare i dettagli dell'indagine.|
|**Parzialmente corretti**|L'indagine ha comportato azioni correttive e alcune sono state approvate e completate. Altre azioni sono ancora in [sospeso.](air-review-approve-pending-completed-actions.md)|
|**Operazione non riuscita**|Almeno un analizzatore delle indagini ha incontrato un problema per cui non è stato possibile completarlo correttamente. <p> **NOTA:** se un'indagine ha esito negativo dopo l'approvazione delle azioni di correzione, è possibile che le azioni di correzione abbia avuto esito positivo. Visualizzare i dettagli dell'indagine. |
|**Accodati dalla limitazione**|È in corso un'indagine in una coda. Al termine di altre indagini, iniziano le indagini in coda. La limitazione consente di evitare prestazioni del servizio scarse.  <p> **SUGGERIMENTO:** le azioni in sospeso possono limitare il numero di nuove indagini che possono essere eseguite. Assicurarsi di [approvare (o rifiutare) le azioni in sospeso.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Terminated By Throttling**|Se un'indagine viene mantenuta nella coda troppo a lungo, si interrompe. <p> **SUGGERIMENTO:** è possibile [avviare un'indagine da Threat Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Visualizzare i dettagli di un'indagine

1. Accedere al Centro sicurezza Microsoft 365 ( <https://security.microsoft.com> ) e accedere.
2. Nel riquadro di spostamento selezionare **Centro notifiche.**
3. Nella scheda **In sospeso** o **Cronologia** selezionare un'azione. Verrà visualizzato il riquadro a comparsa.
4. Nel riquadro a comparsa selezionare Apri **pagina analisi.** 
5. Utilizzare le varie schede per ulteriori informazioni sull'indagine.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visualizzare i dettagli di un avviso correlato a un'indagine

Alcuni tipi di avvisi attivano un'indagine automatizzata in Microsoft 365. Per ulteriori informazioni, vedere [Criteri di avviso che attivano indagini automatizzate.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Accedere al Centro sicurezza Microsoft 365 ( <https://security.microsoft.com> ) e accedere.
2. Nel riquadro di spostamento selezionare **Centro notifiche.**
3. Nella scheda **In sospeso** o **Cronologia** selezionare un'azione. Verrà visualizzato il riquadro a comparsa.
4. Nel riquadro a comparsa selezionare Apri **pagina analisi.** 
5. Selezionare la **scheda Avvisi** per visualizzare un elenco di tutti gli avvisi associati all'indagine.
6. Selezionare un elemento nell'elenco per aprire il riquadro a comparsa. Qui è possibile visualizzare ulteriori informazioni sull'avviso.

## <a name="keep-the-following-points-in-mind"></a>Tenere presenti i punti seguenti

- I conteggi dei messaggi di posta elettronica vengono calcolati al momento dell'indagine e alcuni conteggi vengono ricalcolati quando si aprono i riquadri a comparsa dell'indagine (in base a una query sottostante).

- I conteggi dei messaggi di posta  elettronica visualizzati per i cluster di posta elettronica nella scheda Posta elettronica e il valore della quantità di posta elettronica visualizzato nel riquadro a comparsa del cluster vengono calcolati al momento dell'analisi e non cambiano.

- Il conteggio della posta  elettronica visualizzato nella parte inferiore della scheda Posta elettronica del riquadro a comparsa del cluster di posta elettronica e il conteggio dei messaggi di posta elettronica visualizzati in Esplora risorse riflettono i messaggi di posta elettronica ricevuti dopo l'analisi iniziale dell'indagine.

  Di conseguenza, un cluster di posta elettronica che mostra una quantità originale di 10 messaggi di posta elettronica mostrerebbe un elenco di posta elettronica totale di 15 quando arrivano altri cinque messaggi di posta elettronica tra la fase di analisi dell'indagine e quando l'amministratore esamina l'indagine. Analogamente, le indagini precedenti potrebbero iniziare a mostrare conteggi più alti rispetto alle query di Explorer, perché i dati in Microsoft Defender per Office 365 Piano 2 scadono dopo sette giorni per le versioni di valutazione e dopo 30 giorni per le licenze a pagamento.

  La visualizzazione del conteggio cronologico e corrente in visualizzazioni diverse viene eseguita per indicare l'impatto della posta elettronica al momento dell'indagine e l'impatto corrente fino al momento in cui viene eseguita la correzione.

- Nel contesto della posta elettronica, è possibile che nell'ambito dell'indagine venga visualizzata una minaccia di anomalia del volume. Un'anomalia del volume indica un picco di messaggi di posta elettronica simili attorno al tempo dell'evento di indagine rispetto a tempi precedenti. Un picco del traffico di posta elettronica insieme a determinate caratteristiche (ad esempio, il dominio dell'oggetto e del mittente, la somiglianza del corpo e l'IP del mittente) è tipico dell'inizio di campagne di posta elettronica o attacchi. Tuttavia, le campagne di posta elettronica in blocco, posta indesiderata e legittime condividono in genere queste caratteristiche.

- Le anomalie del volume rappresentano una potenziale minaccia e di conseguenza potrebbero essere meno gravi rispetto alle minacce malware o phish identificate tramite motori antivirus, detonazione o reputazione dannosa.

- Non è necessario approvare tutte le azioni. Se non si accetta l'azione consigliata o l'organizzazione non sceglie determinati  tipi di azioni, è possibile scegliere di rifiutare le azioni o semplicemente ignorarle e non eseguire alcuna azione.

- L'approvazione e/o il rifiuto di tutte le azioni consente all'indagine di chiudersi completamente (lo stato viene modificato), lasciando alcune azioni incomplete, lo stato dell'indagine diventa parzialmente correttivo.

## <a name="next-steps"></a>Passaggi successivi

- [Rivedere e approvare le azioni in sospeso](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
