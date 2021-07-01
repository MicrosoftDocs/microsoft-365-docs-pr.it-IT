---
title: Dashboard utenti per la gestione dei rischi Insider
description: Informazioni sulla gestione dei rischi insider Dashboard utenti in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 802f3fdacba62839b93b8441502334ae486cdacc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226324"
---
# <a name="insider-risk-management-users-dashboard"></a>Dashboard utenti per la gestione dei rischi Insider

Il **dashboard Utenti è** uno strumento importante nel flusso di lavoro per la gestione dei rischi insider e consente a investigatori e analisti di avere una comprensione più completa delle attività di rischio. Questo dashboard offre visualizzazioni e funzionalità di gestione per soddisfare le esigenze amministrative tra la creazione di criteri di gestione dei rischi insider e la gestione dei casi di gestione dei rischi insider.

Dopo l'aggiunta degli utenti ai criteri di gestione dei rischi insider, i processi in background valutano automaticamente le attività degli utenti per [l'attivazione degli indicatori.](insider-risk-management-settings.md#indicators) Dopo la presenza degli indicatori di attivazione, alle attività degli utenti vengono assegnati i punteggi di rischio. Alcune di queste attività possono comportare un avviso di rischio insider, ma alcune attività potrebbero non soddisfare un livello di punteggio di rischio minimo e non verrà creato un avviso di rischio insider. Il **dashboard Utenti** consente di visualizzare gli utenti con questi tipi di indicatori e punteggi di rischio, nonché gli utenti che dispongono di avvisi di rischio insider attivi.

Ulteriori informazioni su come il dashboard Utenti visualizza gli utenti negli scenari seguenti:

- Utenti con avvisi dei criteri di rischio insider attivi
- Utenti con eventi di attivazione
- Utenti aggiunti temporaneamente ai criteri

## <a name="users-with-active-insider-risk-policy-alerts"></a>Utenti con avvisi dei criteri di rischio insider attivi

Il **dashboard Utenti visualizza automaticamente** tutti gli utenti con avvisi dei criteri di rischio insider attivi. Questi utenti con avvisi dispongono sia di un indicatore di attivazione che di un punteggio di rischio di attività che soddisfa i requisiti per la creazione di un avviso di rischio insider. Le attività per questi utenti vengono visualizzate selezionando l'utente nel **dashboard** Utenti e passando alla **scheda Attività** utente.

## <a name="users-with-triggering-events"></a>Utenti con eventi di attivazione

Il **dashboard Utenti visualizza** automaticamente tutti gli utenti con eventi di attivazione, ma che non hanno un punteggio di rischio di attività che creerebbe un avviso di rischio insider. Ad esempio, un utente con una data di rassegnazione segnalata viene visualizzato perché questa attività è un evento di attivazione ma non è un'attività con un punteggio di rischio. Le attività per questi utenti vengono visualizzate selezionando l'utente nel **dashboard** Utenti e passando alla **scheda Attività** utente.

## <a name="users-added-temporarily-to-policies"></a>Utenti aggiunti temporaneamente ai criteri

Il **dashboard Utenti include** gli utenti aggiunti ai criteri di gestione dei rischi insider dopo un evento insolito al di fuori del flusso di lavoro per la gestione dei rischi insider. L'aggiunta temporanea di utenti (dal dashboard Criteri) è anche un modo per iniziare a segnare l'attività degli utenti per un criterio di gestione dei rischi insider per testare il criterio, anche se non è configurato un connettore obbligatorio.

Quando un utente viene aggiunto manualmente a un criterio, le attività utente per i 90 giorni precedenti vengono classificate e aggiunte alla sequenza temporale **attività** utente. Ad esempio, si dispone di un utente attualmente non assegnato punteggi di rischio per un criterio di rischio insider e l'utente ha attività di perdita di dati segnalate al reparto legale dell'organizzazione. L'ufficio legale consiglia di configurare nuovi requisiti di monitoraggio a breve termine per l'utente. È possibile assegnare temporaneamente l'utente al *criterio* perdite di dati per un periodo di tempo designato (finestra di attivazione). Tutti gli utenti aggiunti temporaneamente vengono visualizzati nel **dashboard** Utenti perché i requisiti di attivazione degli eventi non sono più necessari.

> [!NOTE]
> La visualizzazione dei nuovi utenti aggiunti manualmente nel dashboard Utenti può richiedere **diverse ore.** La visualizzazione delle attività dei 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **dashboard** Utenti e aprire la **scheda Attività** utente nel riquadro dei dettagli.

L'utente viene rimosso automaticamente dal **dashboard** Utenti e il  punteggio si interrompe alla scadenza del tempo definito nella finestra Di attivazione se:

- l'utente non ha altri eventi di attivazione o avvisi dei criteri di rischio insider e
- se la durata della finestra **di** attivazione definita manualmente è maggiore della durata della finestra di attivazione **del criterio** globale.

**L'impostazione della finestra** di attivazione con la durata più lunga sostituisce sempre l'impostazione **della** finestra di attivazione con una durata più breve. Ad esempio, hai configurato  la finestra  Attivazione nella scheda Temporale dei criteri globali nelle impostazioni globali di gestione dei rischi insider per 15 giorni, che viene applicata automaticamente a tutti i criteri di rischio insider.

Si aggiunge temporaneamente un  utente ai criteri di rischio insider perdite di dati e si definiscono 30 giorni come finestra **di attivazione** per l'utente. **L'impostazione della finestra** di attivazione globale di 15 giorni viene ignorata definendo l'impostazione della finestra di attivazione di 30 giorni per l'utente aggiunto temporaneamente.  L'utente aggiunto temporaneamente rimarrà nel **dashboard Utenti** e sarà nell'ambito del criterio per 30 giorni.

Nello scenario opposto in  cui l'impostazione  della finestra di attivazione globale è più lunga dell'impostazione  della finestra di attivazione definita per un utente aggiunto temporaneamente, l'impostazione della finestra di attivazione globale ha la precedenza sull'impostazione della finestra di attivazione per l'utente aggiunto temporaneamente.  L'utente aggiunto temporaneamente rimarrà nel **dashboard** Utenti e sarà nell'ambito del criterio per il numero di giorni definito nelle impostazioni globali della finestra **di** attivazione.

## <a name="view-user-information-on-the-users-dashboard"></a>Visualizzare le informazioni utente nel dashboard Utenti

Ogni utente visualizzato nel **dashboard Utenti** dispone delle informazioni seguenti:

- **Utenti**: nome utente per un utente. Questo campo viene anonimizzato se è abilitata l'impostazione di anonimizzazione globale per la gestione dei rischi insider.
- **Livello di rischio**: Livello di rischio calcolato corrente dell'utente. Questo punteggio viene calcolato ogni 24 ore e utilizza i punteggi del rischio di avviso di tutti gli avvisi attivi associati all'utente. Per gli utenti con solo indicatori di attivazione, il livello di rischio è zero.
- **Avvisi attivi**: numero di avvisi attivi per tutti i criteri.
- **Violazioni confermate:** numero di casi risolti come violazione del criterio *confermata* per l'utente.
- **Case**: il caso attivo corrente per l'utente.

![Dashboard degli utenti della gestione dei rischi Insider](../media/insider-risk-users-dashboard.png)

> [!NOTE]
> Il numero di utenti visualizzati nel **dashboard** Utenti può essere limitato in alcuni casi, a seconda del volume di avvisi attivi e criteri di corrispondenza. Gli utenti con avvisi attivi vengono visualizzati nel **dashboard** Utenti durante la generazione degli avvisi e possono verificarsi rari casi in cui viene raggiunto il numero massimo di utenti visualizzati. Se questo limite si verifica, gli utenti con avvisi attivi che non vengono visualizzati verranno aggiunti al **dashboard** Utenti quando gli avvisi utente esistenti vengono valutati.

## <a name="view-user-details"></a>Visualizzare i dettagli utente

Per visualizzare ulteriori dettagli sull'attività di rischio per un utente, aprire il riquadro dei dettagli utente facendo doppio clic su un utente nel **dashboard Utenti.** Nel riquadro dei dettagli è possibile visualizzare le informazioni seguenti:

- **Scheda Profilo** utente
  - **Nome e titolo**: il nome e il titolo della posizione per l'utente da Azure Active Directory. Questi campi utente saranno anonimi o vuoti se è abilitata l'impostazione di anonimizzazione globale per la gestione dei rischi insider.
  - **Posta elettronica utente**: Indirizzo di posta elettronica per l'utente.
  - **Alias**: alias di rete per l'utente.
  - **Organizzazione o reparto:** l'organizzazione o il reparto per l'utente.

- **Scheda Attività utente**
  - **Cronologia delle attività degli utenti recenti:** elenca sia gli indicatori di attivazione che gli indicatori di rischio insider per le attività degli utenti fino agli ultimi 180 giorni. Vengono inoltre classificate tutte le attività pertinenti agli indicatori di rischio insider, anche se le attività potrebbero aver generato o meno un avviso di rischio insider. Gli esempi di indicatori di attivazione possono essere una data di rinuncia o l'ultima data di lavoro programmata per l'utente. Gli indicatori di rischio Insider sono attività determinate per avere un elemento di rischio e sono definite nei criteri in cui l'utente è incluso. Le attività di evento e rischio sono elencate con l'elemento più recente elencato per primo.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Rimuovere gli utenti dall'assegnazione nell'ambito ai criteri

In alcuni scenari potrebbe essere necessario interrompere l'assegnazione dei punteggi di rischio all'attività di un utente nei criteri di gestione dei rischi insider. Utilizzare **Rimuovi utenti nella** pagina **Dashboard** utenti per interrompere l'assegnazione dei punteggi di rischio per uno o più utenti da tutti i criteri di gestione dei rischi insider per cui sono attualmente nell'ambito. Questa azione non rimuove gli utenti dall'assegnazione complessiva dei criteri (quando si aggiungono utenti o gruppi a una configurazione di criteri), ma semplicemente rimuove gli utenti dall'elaborazione attiva dai criteri dopo gli eventi di attivazione correnti. Se gli utenti avranno un altro evento di attivazione in futuro, i punteggi di rischio dei criteri inizieranno automaticamente ad essere assegnati di nuovo agli utenti. Eventuali avvisi o casi esistenti per questo utente non verranno rimossi.

> [!NOTE]
> Il completamento della rimozione di un utente da un criterio può richiedere alcuni minuti. Al termine, l'utente non sarà più elencato nella pagina Utenti. Se l'utente rimosso ha avvisi o casi attivi, l'utente rimarrà nella pagina Utenti e i dettagli dell'utente mostreranno che non sono più nell'ambito di un criterio.

Per rimuovere manualmente gli utenti dallo stato nell'ambito in tutti i criteri di gestione dei rischi insider, eseguire la procedura seguente:

1. Nella finestra [Centro conformità Microsoft 365](https://compliance.microsoft.com), passare a **Gestione dei rischi Insider** e selezionare la **scheda** Utenti.
2. Nel **dashboard Utenti selezionare** l'utente o gli utenti che si desidera rimuovere dall'ambito nei criteri di gestione dei rischi insider.
3. Selezionare **Rimuovi utenti**.
4. Nel riquadro **Rimuovi utente** selezionare **Rimuovi** o **Annulla** per ignorare le modifiche e chiudere la finestra di dialogo.
5. Selezionare **Rimuovi** nel riquadro di conferma per rimuovere l'utente.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Eseguire attività automatizzate con Power Automate per un utente

Utilizzando i flussi Power Automate di rischio consigliati, gli investigatori e gli analisti del rischio possono agire rapidamente per:

- Notificare agli utenti quando vengono aggiunti a un criterio di rischio insider

Per eseguire, gestire o creare flussi Power Automate per un utente insider di gestione dei rischi:

1. Seleziona **Automatizza sulla** barra degli strumenti delle azioni dell'utente.
2. Scegliere il Power Automate da eseguire, quindi selezionare **Esegui flusso.**
3. Al termine del flusso, selezionare **Fatto.**

Per ulteriori informazioni sui flussi Power Automate per la gestione dei rischi insider, vedere Introduzione alle impostazioni di gestione dei rischi [insider.](insider-risk-management-settings.md#power-automate-flows-preview)
