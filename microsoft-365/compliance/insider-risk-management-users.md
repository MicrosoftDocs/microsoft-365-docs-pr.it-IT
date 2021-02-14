---
title: Dashboard degli utenti per la gestione dei rischi Insider
description: Informazioni sul dashboard degli utenti per la gestione dei rischi insider in Microsoft 365
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
ms.openlocfilehash: 224221950104b5dee6a6e8f179db34ee6fad014e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208772"
---
# <a name="insider-risk-management-users-dashboard"></a>Dashboard degli utenti per la gestione dei rischi Insider

Il **dashboard Utenti è** uno strumento importante nel flusso di lavoro di gestione dei rischi Insider e consente agli investigatori e agli analisti di avere una conoscenza più completa delle attività di rischio. Questo dashboard offre visualizzazioni e funzionalità di gestione per soddisfare le esigenze amministrative tra la creazione di criteri di gestione dei rischi Insider e la gestione dei casi di gestione dei rischi Insider.

Dopo l'aggiunta degli utenti ai criteri di gestione dei rischi Insider, i processi in background valutano automaticamente le attività degli utenti per [l'attivazione degli indicatori.](insider-risk-management-settings.md#indicators) Dopo la presenza degli indicatori di attivazione, alle attività degli utenti vengono assegnati i punteggi di rischio. Alcune di queste attività possono comportare un avviso di rischio Insider, ma alcune attività potrebbero non soddisfare un livello di punteggio di rischio minimo e non verrà creato un avviso di rischio Insider. Il **dashboard Utenti** consente di visualizzare gli utenti con questi tipi di indicatori e punteggi di rischio, nonché gli utenti che dispongono di avvisi di rischio Insider attivi.

Possono inoltre verificarsi scenari in cui è necessario aggiungere temporaneamente utenti ai criteri di rischio Insider dopo che un evento insolito viene segnalato all'esterno del flusso di lavoro di gestione dei rischi Insider. Il **dashboard Utenti** consente di aggiungere manualmente un utente a un criterio di rischio Insider per un periodo di tempo specifico e di ignorare il requisito per un utente di avere un indicatore di attivazione. Questi utenti vengono sempre visualizzati nel dashboard degli utenti quando sono assegnati attivamente a un criterio.

Ulteriori informazioni sul modo in cui il dashboard utenti visualizza gli utenti negli scenari seguenti:

- Utenti del dashboard con avvisi dei criteri di rischio Insider attivi
- Utenti del dashboard con indicatori di attivazione
- Utenti del dashboard aggiunti temporaneamente ai criteri

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Utenti del dashboard con avvisi dei criteri di rischio Insider attivi

Il **dashboard Utenti visualizza** automaticamente tutti gli utenti con avvisi dei criteri di rischio Insider attivi. Questi utenti con avvisi dispongono sia di un indicatore di attivazione che di un punteggio di rischio dell'attività che soddisfa i requisiti per la creazione di un avviso di rischio Insider. Le attività per questi utenti vengono visualizzate selezionandolo nel **dashboard** Utenti e passando alla **scheda Attività** utente.

## <a name="dashboard-users-with-triggering-indicators"></a>Utenti del dashboard con indicatori di attivazione

Il **dashboard Utenti** visualizza automaticamente tutti gli utenti con indicatori di attivazione, ma che non hanno un punteggio di rischio attività che creerebbe un avviso di rischio Insider. Ad esempio, un utente con una data di ritiro segnalata viene visualizzato perché questo evento è un indicatore di attivazione ma non è un'attività con un punteggio di rischio. Le attività per questi utenti vengono visualizzate selezionandolo nel **dashboard** Utenti e passando alla **scheda Attività** utente.

## <a name="dashboard-users-added-temporarily-to-policies"></a>Utenti del dashboard aggiunti temporaneamente ai criteri

Il **dashboard Utenti** consente di aggiungere temporaneamente utenti a un criterio di gestione dei rischi Insider esistente dopo un evento insolito al di fuori del flusso di lavoro di gestione dei rischi Insider. L'aggiunta temporanea di utenti è anche un modo per aggiungere utenti a un criterio di gestione dei rischi Insider per testare il criterio, anche se non è configurato un connettore necessario.

Quando un utente viene aggiunto manualmente a un criterio, le attività dell'utente per i 90 giorni precedenti vengono classificate e aggiunte alla sequenza temporale **delle attività** utente. Ad esempio, un utente non è attualmente nell'ambito di un criterio di rischio Insider e l'utente ha attività di perdita di dati segnalate al reparto legale dell'organizzazione. L'ufficio legale consiglia di configurare nuovi requisiti di monitoraggio a breve termine per l'utente. È possibile assegnare temporaneamente l'utente ai *criteri* di perdita dei dati per un periodo di tempo designato (finestra di attivazione). Tutti gli utenti aggiunti temporaneamente vengono visualizzati nel **dashboard** degli utenti perché i requisiti degli indicatori di attivazione non vengono più soddisfatti.

>[!NOTE]
>La visualizzazione di nuovi utenti aggiunti manualmente nel dashboard utenti può richiedere diverse **ore.** La visualizzazione delle attività per i 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **dashboard** Utenti e aprire la **scheda Attività** utente nel riquadro dei dettagli.

L'utente viene rimosso automaticamente dai criteri Insider e dal  **dashboard** Utenti quando scade il tempo definito nella finestra di attivazione se:

- l'utente non dispone di indicatori di attivazione o avvisi dei criteri di rischio Insider e
- se la durata della finestra **di** attivazione definita manualmente è maggiore della durata della finestra di attivazione **dei criteri** globali. 

**L'impostazione della finestra** di attivazione con la durata più lunga sostituisce sempre l'impostazione della **finestra** di attivazione con una durata più breve. Ad esempio, hai configurato  la finestra  di attivazione nella scheda temporale dei criteri globali nelle impostazioni globali di gestione dei rischi Insider per 15 giorni, che viene applicata automaticamente a tutti i criteri di rischio Insider. 

Si aggiunge temporaneamente un utente ai criteri *di* rischio insider per la perdita di dati e si definiscono 30 giorni come finestra **di attivazione** per l'utente. **L'impostazione globale della finestra** di attivazione di 15 giorni viene ignorata definendo l'impostazione della finestra di attivazione di 30 giorni per l'utente aggiunto temporaneamente.  L'utente aggiunto temporaneamente rimarrà nel **dashboard** degli utenti e sarà nell'ambito del criterio per 30 giorni.

Nello scenario opposto,  in cui l'impostazione  della finestra di attivazione globale è più lunga dell'impostazione della finestra di attivazione definita per un utente aggiunto temporaneamente, l'impostazione della finestra di attivazione globale sovrascrive l'impostazione della finestra di attivazione per l'utente aggiunto temporaneamente.   L'utente aggiunto temporaneamente rimarrà nel **dashboard** degli utenti e sarà nell'ambito del criterio per il numero di giorni definito nelle impostazioni globali della finestra **di** attivazione.

## <a name="view-user-information-on-the-users-dashboard"></a>Visualizzare le informazioni utente nel dashboard utenti

Ogni utente visualizzato nel **dashboard Utenti** contiene le informazioni seguenti:

- **Utenti**: nome utente di un utente. Questo campo è anonimizzato se è abilitata l'impostazione di anonimizzazione globale per la gestione dei rischi Insider.
- **Livello di rischio:** il livello di rischio calcolato corrente dell'utente. Questo punteggio viene calcolato ogni 24 ore e utilizza i punteggi di rischio degli avvisi di tutti gli avvisi attivi associati all'utente. Per gli utenti con solo indicatori di attivazione, il livello di rischio è zero.
- **Avvisi attivi**: numero di avvisi attivi per tutti i criteri.
- **Violazioni confermate:** numero di casi risolti come *violazione del* criterio confermata per l'utente.
- **Caso:** il caso attivo corrente per l'utente.

![Dashboard degli utenti della gestione dei rischi Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>Il numero di utenti visualizzati nel **dashboard** degli utenti può essere limitato in alcuni casi, a seconda del volume di avvisi attivi e dei criteri di corrispondenza. Gli utenti con avvisi attivi vengono visualizzati nel **dashboard** Degli utenti quando vengono generati e possono verificarsi rari casi in cui viene raggiunto il numero massimo di utenti visualizzati. In questo caso, gli utenti con avvisi attivi che non vengono visualizzati verranno aggiunti al **dashboard** utenti quando vengono valutati gli avvisi utente esistenti.

## <a name="view-user-details"></a>Visualizzare i dettagli utente

Per visualizzare ulteriori dettagli sull'attività di rischio per un utente, aprire il riquadro dei dettagli dell'utente facendo doppio clic su un utente nel **dashboard Utenti.** Nel riquadro dei dettagli è possibile visualizzare le informazioni seguenti:

- **Scheda Profilo** utente
    - **Nome e titolo**: il nome e il titolo della posizione per l'utente di Azure Active Directory. Questi campi utente saranno anonimi o vuoti se è abilitata l'impostazione di anonimizzazione globale per la gestione dei rischi Insider.
    - **Indirizzo di posta elettronica** dell'utente: l'indirizzo di posta elettronica dell'utente.
    - **Alias**: alias di rete per l'utente.
    - **Organizzazione o reparto:** l'organizzazione o il reparto per l'utente.

- **Scheda Attività utente**
    - **Cronologia delle attività degli utenti recenti:** elenca gli indicatori di attivazione e gli indicatori di rischio Insider per le attività degli utenti fino agli ultimi 180 giorni. Vengono inoltre classificate tutte le attività pertinenti agli indicatori di rischio Insider, anche se le attività possono aver generato o meno un avviso di rischio Insider. Gli esempi di indicatori di attivazione possono essere una data di dimissioni o l'ultima data di lavoro programmata per l'utente. Gli indicatori di rischio Insider sono attività determinate per avere un elemento di rischio e sono definite nei criteri in cui l'utente è incluso. Le attività di evento e rischio sono elencate con l'elemento più recente elencato per primo.

## <a name="temporarily-add-a-user-to-a-policy"></a>Aggiungere temporaneamente un utente a un criterio

Per aggiungere temporaneamente un utente a un criterio di  gestione dei rischi Insider, si userà la scheda Utenti nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365. Gli utenti aggiunti ignorano manualmente i requisiti degli indicatori di attivazione per il criterio a cui vengono aggiunti e vengono visualizzati nel **dashboard utenti.** Per aggiungere definitivamente un utente a un criterio di gestione dei rischi Insider, si userà la procedura guidata dei criteri.

Completare la procedura seguente per aggiungere un utente a un criterio di rischio Insider esistente:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Utenti.
2. Selezionare **Aggiungi un utente a un criterio sulla** barra degli strumenti.
3. Nella finestra **di dialogo Aggiungi nuovo utente** iniziare a digitare un nome utente nel **campo** Utente. Selezionare l'utente che si desidera aggiungere a un criterio.
4. Selezionare la freccia a discesa per il **campo Criteri** per visualizzare i criteri di gestione dei rischi Insider configurati. Selezionare il criterio a cui aggiungere l'utente.
5. Usa il **dispositivo di scorrimento** della finestra Attivazione per definire per quanto tempo l'utente viene incluso in un criterio e visualizzato nel dashboard utenti. L'ora specificata determina per quanto tempo il criterio è attivo per questo utente e viene avviato quando viene generato il primo avviso o viene rilevato un indicatore di attivazione (ad esempio una corrispondenza al criterio DLP). L'intervallo per la **finestra di attivazione** è compreso tra 5 e 30 giorni.
6. Selezionare **Aggiungi** e quindi **Conferma** per aggiungere l'utente al criterio.

>[!NOTE]
>La visualizzazione di nuovi utenti aggiunti manualmente nel dashboard utenti può richiedere diverse **ore.** La visualizzazione delle attività per i 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **dashboard** Utenti e aprire la **scheda Attività** utente nel riquadro dei dettagli.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Eseguire attività automatizzate con i flussi di Power Automate per un utente

Utilizzando i flussi di Power Automate consigliati, gli investigatori e gli analisti del rischio possono intervenire rapidamente per:

- Notificare agli utenti quando vengono aggiunti a un criterio di rischio Insider

Per eseguire, gestire o creare flussi di Power Automate per un utente insider di gestione dei rischi:

1. Selezionare **Automate sulla** barra degli strumenti delle azioni dell'utente.
2. Scegliere il flusso di Power Automate da eseguire, quindi selezionare **Esegui flusso.**
3. Al termine del flusso, selezionare **Fine.**

Per ulteriori informazioni sui flussi di Power Automate per la gestione dei rischi Insider, vedere [Introduzione alle impostazioni di gestione dei rischi Insider.](insider-risk-management-settings.md#power-automate-flows-preview)
