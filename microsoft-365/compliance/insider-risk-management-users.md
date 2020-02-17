---
title: Utenti di gestione dei rischi Insider (anteprima)
description: Informazioni sugli utenti di gestione dei rischi insider in Microsoft 365
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
ms.openlocfilehash: a9ff7e38a99a5fe5bd8da5301bec5e19bc015cf3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072789"
---
# <a name="insider-risk-management-users-preview"></a>Utenti di gestione dei rischi Insider (anteprima)

Gli utenti di gestione dei rischi Insider sono impiegati nell'organizzazione che sono inclusi in uno o più criteri di gestione dei rischi Insider. Utilizzare il **Dashboard utenti** per esaminare rapidamente le informazioni sui rischi per i dipendenti e per aggiungere un dipendente a un criterio di gestione dei rischi Insider esistente. Ogni utente incluso in un criterio di gestione dei rischi Insider contiene le seguenti informazioni visualizzate nel **dashboard degli utenti**:

- **Users: il**nome utente di un utente.
- **Livello di rischio**: 
- **Avvisi attivi**: il numero di avvisi attivi per tutti i criteri.
- **Violazioni confermate**: il numero di casi risolti come *violazioni dei criteri confermate* per l'utente.
- **Caso**: il caso attivo corrente per l'utente.

![Dashboard degli utenti di gestione dei rischi Insider](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a>Visualizzare i dettagli dell'utente

Per visualizzare ulteriori dettagli sull'attività di rischio per un utente, aprire il riquadro dei dettagli dell'utente facendo doppio clic su un utente nel **Dashboard utenti**. Nel riquadro dei dettagli, è possibile visualizzare le informazioni seguenti:

- Scheda **profilo utente**
    - **Nome e titolo**: il nome e il titolo della posizione per l'utente.
    - **Messaggio**di posta elettronica dell'utente: l'indirizzo di posta elettronica per l'utente.
    - **Alias**: l'alias di rete per l'utente.
    - **Organizzazione o reparto**: organizzazione o reparto dell'utente.

- Scheda **attività utente**
    - **Cronologia delle attività degli utenti recenti**: elenca sia gli eventi di attivazione dei criteri sia gli indicatori di rischio per le attività degli utenti. Un evento di attivazione può essere l'accettazione di una data di dimissioni o l'ultima data di lavoro pianificata per il dipendente. Gli indicatori di rischio sono attività determinate per avere un elemento di rischio e che corrispondono a criteri in base ai quali l'utente è incluso. Gli eventi e le attività di rischio sono elencati con l'elemento più recente elencato per primo.

## <a name="add-a-user-to-a-policy"></a>Aggiungere un utente a un criterio

Per aggiungere un utente a un criterio di gestione dei rischi Insider, è possibile utilizzare la procedura guidata nuovo criterio o la scheda **utenti** nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365.

Completare la procedura seguente per aggiungere un utente a un criterio di rischio Insider esistente:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **utenti** .
2. Selezionare **Aggiungi un utente a un criterio** sulla barra degli strumenti.
3. Nella finestra di dialogo **Aggiungi nuovo utente** , iniziare a digitare un nome utente nel campo **utente** . Selezionare l'utente che si desidera aggiungere a un criterio.
4. Selezionare la freccia a discesa del campo **criterio** per visualizzare i criteri di gestione dei rischi Insider configurati. Selezionare il criterio a cui aggiungere l'utente.
5. Utilizzare il controllo del dispositivo di scorrimento della **finestra di monitoraggio** per definire il...... L'intervallo per la finestra di monitoraggio è compreso tra 5 e 30 giorni.
6. Selezionare **Aggiungi** e quindi **conferma** per aggiungere l'utente al criterio.
