---
title: Dashboard degli utenti di gestione dei rischi Insider
description: Informazioni sul dashboard degli utenti di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0997ecc83ad7f97d1fb7273bcac8b026f6432091
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199509"
---
# <a name="insider-risk-management-users-dashboard"></a>Dashboard degli utenti di gestione dei rischi Insider

Il **dashboard degli utenti** è uno strumento importante nel flusso di lavoro di gestione dei rischi Insider e aiuta gli investigatori e gli analisti a comprendere meglio le attività relative ai rischi. Questo dashboard offre visualizzazioni e funzionalità di gestione che soddisfano le esigenze amministrative tra i criteri di gestione dei rischi e la gestione dei rischi di insider

Dopo aver aggiunto gli utenti ai criteri di gestione dei rischi Insider, i processi in background valutano automaticamente le attività utente per l' [attivazione degli indicatori](insider-risk-management-settings.md#indicators). Dopo che sono presenti indicatori di attivazione, le attività degli utenti vengono assegnate ai punteggi dei rischi. Alcune di queste attività possono causare un avviso di rischio Insider, ma alcune attività potrebbero non essere in grado di raggiungere un livello di rischio minimo e non verrà creato un avviso di rischio Insider. Il **Dashboard utenti** consente di visualizzare gli utenti con questi tipi di indicatori e punteggi di rischio, nonché gli utenti che hanno avvisi di rischio attivi Insider.

È inoltre possibile che vi siano scenari in cui è necessario aggiungere temporaneamente gli utenti ai criteri di rischio Insider dopo che un evento insolito è stato segnalato all'esterno del flusso di lavoro di gestione dei rischi Insider. Il **dashboard degli utenti** consente di aggiungere manualmente un utente a un criterio di rischio Insider per un determinato intervallo di tempo e di ignorare il requisito per un utente di avere un indicatore di attivazione. Questi utenti vengono sempre visualizzati nel dashboard degli utenti quando vengono assegnati attivamente a un criterio.

Per ulteriori informazioni su come il dashboard degli utenti Visualizza gli utenti negli scenari seguenti:

- Utenti del dashboard con avvisi sui criteri di rischio Insider Active
- Utenti del dashboard con indicatori di attivazione
- Gli utenti del dashboard sono stati aggiunti temporaneamente ai criteri

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Utenti del dashboard con avvisi sui criteri di rischio Insider Active

Il **Dashboard utenti** Visualizza automaticamente tutti gli utenti con avvisi sui criteri di rischio Insider attivi. Questi utenti con avvisi dispongono sia di un indicatore di attivazione che di un punteggio di rischio di attività che soddisfa i requisiti per la creazione di un avviso di rischio Insider. Le attività per questi utenti vengono visualizzate selezionando l'utente nel **Dashboard utenti** e passando alla scheda **attività utente** .

## <a name="dashboard-users-with-triggering-indicators"></a>Utenti del dashboard con indicatori di attivazione

Il **dashboard degli utenti** Visualizza automaticamente tutti gli utenti con indicatori di attivazione, ma che non hanno un punteggio di rischio di attività che potrebbe creare un avviso di rischio Insider. Ad esempio, un utente con una data di dimissioni segnalata viene visualizzato perché questo evento è un indicatore di attivazione ma non è un'attività che ha un punteggio di rischio. Le attività per questi utenti vengono visualizzate selezionando l'utente nel **Dashboard utenti** e passando alla scheda **attività utente** .

## <a name="dashboard-users-added-temporarily-to-policies"></a>Gli utenti del dashboard sono stati aggiunti temporaneamente ai criteri

Il **dashboard degli utenti** consente di aggiungere temporaneamente gli utenti a un criterio di gestione dei rischi Insider esistente dopo un evento insolito al di fuori del flusso di lavoro di gestione dei rischi Insider. L'aggiunta temporanea degli utenti è anche un modo per aggiungere gli utenti a un criterio di gestione dei rischi Insider per testare il criterio, anche se non è configurato un connettore obbligatorio.

Quando un utente viene aggiunto manualmente a un criterio, le attività degli utenti per i 90 giorni precedenti vengono segnate e aggiunte alla sequenza temporale delle **attività dell'utente** . Ad esempio, un utente non presente nell'ambito di un criterio di rischio Insider e l'utente dispone di attività di perdita di dati segnalate al reparto legale dell'organizzazione. Il reparto legale consiglia di configurare nuovi requisiti di monitoraggio a breve termine per l'utente. È possibile assegnare temporaneamente l'utente ai criteri di *perdita dei dati* per un periodo di tempo specificato (finestra di attivazione). Tutti gli utenti aggiunti temporaneamente vengono visualizzati nel **dashboard degli utenti** perché i requisiti degli indicatori di trigger sono stati rinunziati.

>[!NOTE]
>Potrebbe essere necessario diverse ore prima che i nuovi utenti aggiunti manualmente vengano visualizzati nel **dashboard degli utenti**. Le attività per i 90 giorni precedenti per questi utenti possono richiedere fino a 24 ore per la visualizzazione. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **Dashboard utenti** e aprire la scheda **attività utente** nel riquadro dei dettagli.

L'utente viene automaticamente rimosso dal criterio Insider e dal **dashboard degli utenti** quando il tempo definito nella **finestra di attivazione** scade se:

- l'utente non dispone di indicatori di attivazione o avvisi per i criteri di rischio Insider e
- Se la durata della **finestra di attivazione** definita manualmente è più lunga rispetto alla durata della **finestra di attivazione** dei criteri globali. 

L'impostazione della **finestra di attivazione** con la durata più lunga sostituisce sempre l'impostazione della **finestra di attivazione** con una durata più breve. Ad esempio, è stata configurata la **finestra di attivazione** sulla scheda **scadenze dei criteri** globali nelle impostazioni globali di gestione dei rischi Insider per 15 giorni, che viene applicata automaticamente a tutti i criteri di rischio Insider. 

È possibile aggiungere temporaneamente un utente alle *perdite di dati* Insider Risk Policy e definire 30 giorni come la **finestra di attivazione** per questo utente. L'impostazione della **finestra di attivazione** globale di 15 giorni viene ignorata definendo l'impostazione della finestra di **attivazione** di 30 giorni per l'utente temporaneamente aggiunto. L'utente temporaneamente aggiunto rimarrà nel **dashboard degli utenti** e sarà nell'ambito del criterio per 30 giorni.

Nello scenario opposto, in cui l'impostazione della **finestra di attivazione** globale è più lunga **rispetto all'impostazione** definita per un utente temporaneamente aggiunto, l'impostazione della finestra di **attivazione** globale potrebbe ignorare l'impostazione della **finestra di attivazione** per l'utente temporaneamente aggiunto. L'utente temporaneamente aggiunto rimarrà nel **dashboard degli utenti** e sarà nell'ambito del criterio per il numero di giorni definiti nelle impostazioni della finestra di **attivazione** globale.

## <a name="view-user-information-on-the-users-dashboard"></a>Visualizzare le informazioni sull'utente nel dashboard degli utenti

Ogni utente visualizzato nel **Dashboard utenti** dispone delle informazioni seguenti:

- **Utenti**: il nome utente di un utente. Questo campo è anonimi se l'impostazione di Anonymization globale per la gestione dei rischi Insider è abilitata.
- **Livello di rischio**: il livello di rischio calcolato corrente dell'utente. Questo punteggio viene calcolato ogni 24 ore e utilizza i punteggi dei rischi di avviso provenienti da tutti gli avvisi attivi associati all'utente. Per gli utenti con solo indicatori di attivazione, il livello di rischio è zero.
- **Avvisi attivi**: il numero di avvisi attivi per tutti i criteri.
- **Violazioni confermate**: il numero di casi risolti come *violazioni dei criteri confermate* per l'utente.
- **Caso**: il caso attivo corrente per l'utente.

![Dashboard degli utenti di gestione dei rischi Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>Il numero di utenti visualizzati nel **dashboard degli utenti** potrebbe essere limitato in alcuni casi, a seconda del volume degli avvisi attivi e dei criteri di corrispondenza. Gli utenti con avvisi attivi vengono visualizzati nel **dashboard degli utenti** quando vengono generati gli avvisi e possono verificarsi casi rari in cui viene raggiunto il numero massimo di utenti visualizzati. In questo caso, gli utenti con avvisi attivi che non vengono visualizzati verranno aggiunti al **dashboard degli utenti** , in quanto gli avvisi utente esistenti sono stati valutati.

## <a name="view-user-details"></a>Visualizzare i dettagli dell'utente

Per visualizzare ulteriori dettagli sull'attività di rischio per un utente, aprire il riquadro dei dettagli dell'utente facendo doppio clic su un utente nel **Dashboard utenti**. Nel riquadro dei dettagli, è possibile visualizzare le informazioni seguenti:

- Scheda **profilo utente**
    - **Nome e titolo**: il nome e il titolo della posizione per l'utente da Azure Active Directory. Questi campi utente saranno anonimi o vuoti se è abilitata l'impostazione Anonymization globale per la gestione dei rischi Insider.
    - **Messaggio**di posta elettronica dell'utente: l'indirizzo di posta elettronica per l'utente.
    - **Alias**: l'alias di rete per l'utente.
    - **Organizzazione o reparto**: organizzazione o reparto dell'utente.

- Scheda **attività utente**
    - **Cronologia delle attività degli utenti recenti**: elenca gli indicatori di attivazione e gli indicatori di rischio Insider per le attività degli utenti fino agli ultimi 180 giorni. Vengono inoltre segnate tutte le attività pertinenti agli indicatori di rischio Insider, anche se le attività possono o meno generare un avviso di rischio Insider. Gli esempi degli indicatori di attivazione possono essere una data di dimissioni o l'ultima data di lavoro pianificata per l'utente. Gli indicatori di rischio Insider sono attività determinate per avere un elemento di rischio e sono definite nei criteri in cui l'utente è incluso. Le attività relative a eventi e rischi sono elencate con l'elemento più recente elencato per primo.

## <a name="temporarily-add-a-user-to-a-policy"></a>Aggiungere temporaneamente un utente a un criterio

Per aggiungere temporaneamente un utente a un criterio di gestione dei rischi Insider, si utilizzerà la scheda **utenti** nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365. Gli utenti hanno aggiunto manualmente il bypass dei requisiti degli indicatori di trigger per il criterio in cui vengono aggiunti e visualizzati nel **dashboard degli utenti**. Per aggiungere definitivamente un utente a un criterio di gestione dei rischi Insider, è possibile utilizzare la procedura guidata per i criteri.

Completare la procedura seguente per aggiungere un utente a un criterio di rischio Insider esistente:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **utenti** .
2. Selezionare **Aggiungi un utente a un criterio** sulla barra degli strumenti.
3. Nella finestra di dialogo **Aggiungi nuovo utente** , iniziare a digitare un nome utente nel campo **utente** . Selezionare l'utente che si desidera aggiungere a un criterio.
4. Selezionare la freccia a discesa del campo **criterio** per visualizzare i criteri di gestione dei rischi Insider configurati. Selezionare il criterio a cui aggiungere l'utente.
5. Utilizzare il controllo del dispositivo di scorrimento della **finestra di attivazione** per definire il periodo di tempo in cui l'utente è incluso in un criterio e visualizzato nel dashboard degli utenti. L'ora specificata determina la durata del criterio attivo per l'utente e viene avviata quando viene generato il primo avviso o viene rilevato un indicatore di attivazione (come la corrispondenza di un criterio DLP). L'intervallo per la **finestra di attivazione** è compreso tra 5 e 30 giorni.
6. Selezionare **Aggiungi** e quindi **conferma** per aggiungere l'utente al criterio.

>[!NOTE]
>Potrebbe essere necessario diverse ore prima che i nuovi utenti aggiunti manualmente vengano visualizzati nel **dashboard degli utenti**. Le attività per i 90 giorni precedenti per questi utenti possono richiedere fino a 24 ore per la visualizzazione. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **Dashboard utenti** e aprire la scheda **attività utente** nel riquadro dei dettagli.
