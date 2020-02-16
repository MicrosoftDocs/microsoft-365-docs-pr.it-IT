---
title: Configurazione del Punteggio di conformità Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come effettuare l'accesso, configurare le autorizzazioni e comprendere il dashboard per il Punteggio di conformità di Microsoft, che semplifica e automatizza le valutazioni dei rischi.
ms.openlocfilehash: 8233fb3174d822e4f71115cab2a1a174c1749810
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078613"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Configurazione del Punteggio di conformità Microsoft (anteprima)

## <a name="before-you-begin"></a>Informazioni preliminari

L'amministratore globale di Microsoft 365 per l'organizzazione sarà probabilmente il primo utente ad accedere al Punteggio di conformità. Si consiglia di accedere all'amministratore globale e di impostare le autorizzazioni utente come indicato di seguito quando si visita il Punteggio di conformità per la prima volta.

## <a name="sign-in"></a>Accedi

1. Accedere al [centro conformità di microsoft 365](https://compliance.microsoft.com/) e **accedere** con l'account di amministratore globale di Microsoft 365.
2. Seleziona **Punteggio di conformità** nel riquadro di spostamento a sinistra. Sarà quindi possibile visualizzare il [Dashboard Punteggio di conformità con il Punteggio](#understand-the-compliance-score-dashboard).

## <a name="set-user-permissions-and-assign-roles"></a>Impostazione delle autorizzazioni utente e assegnazione dei ruoli

Il Punteggio di conformità utilizza un modello di autorizzazione di controllo di accesso basato sui ruoli (RBAC). Solo gli utenti a cui è assegnato un ruolo possono accedere al Punteggio di conformità e le azioni consentite da ogni utente sono limitate dal tipo di ruolo.

### <a name="where-to-set-permissions"></a>Dove impostare le autorizzazioni

L'amministratore globale dell'organizzazione può impostare le autorizzazioni utente nel centro conformità Microsoft 365 o in Azure Active Directory (Azure AD). Dopo aver impostato i ruoli in una di queste posizioni, gli utenti saranno in grado di accedere al Punteggio di conformità (così come Compliance Manager).

Si noti che i ruoli di gestione della conformità esistenti non **vengono** trasferiti al Punteggio di conformità.  Questo significa che, se in precedenza è stato assegnato un ruolo in Compliance Manager, tale ruolo non consentirà di accedere al Punteggio di conformità. L'amministratore globale dovrà impostare le autorizzazioni e un ruolo per l'utente nel centro conformità Microsoft 365 o Azure AD in modo che sia possibile accedere al Punteggio di conformità.

### <a name="role-types"></a>Tipi di ruolo

Nella tabella seguente viene illustrato il modo in cui ogni ruolo di centro conformità di Microsoft 365 viene mappato ai ruoli di gestione conformità esistenti e le funzioni consentite da ogni ruolo.


| L'utente può: | Ruolo centro conformità di Microsoft 365 | Ruolo di Compliance Manager | 
| :------------- | :-------------: | :------------: |
| **Leggere ma non modificare i dati**| Lettore globale di Azure AD  | Lettore globale di Azure AD | 
| **Leggere ma non modificare i dati**| Ruolo con autorizzazioni di lettura per la sicurezza | Reader di Compliance Manager  | 
| **Modificare i dati**| Amministratore di conformità | Collaboratore di Compliance Manager | 
| **Modificare i risultati dei test**| Amministratore di conformità | Responsabile del giudizio di Compliance Manager | 
| **Gestire le valutazioni e i dati del modello e del tenant**| Amministratore di conformità<br>Amministratore dati di conformità<br>Amministratore della sicurezza | Amministratore di Compliance Manager | 
| **Assegnare gli utenti**| Amministratore globale | Amministratore portale | 

> [!NOTE]
> Quando si passa da Punteggio di conformità a Compliance Manager per completare un'attività (ad esempio, per gestire le valutazioni), il browser aprirà una nuova scheda e verrà visualizzata una finestra di dialogo. Nella sezione superiore con l'intestazione, "già un cliente dei servizi cloud Microsoft? Accedi al tuo account, **"seleziona Accedi** per accedere a Compliance Manager; non sarà necessario immettere di nuovo le credenziali.

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>Come impostare le autorizzazioni e i ruoli nel centro conformità di Microsoft 365

Per impostare le autorizzazioni nel centro conformità di Microsoft 365:

1. Accedere al [centro conformità di Microsoft 365](https://compliance.microsoft.com) e accedere con l'account di amministratore globale.
2. Selezionare **autorizzazioni** nel riquadro di spostamento a sinistra. Da qui, è possibile visualizzare i ruoli e assegnare le autorizzazioni.

## <a name="configure-automatic-secure-score-updates"></a>Configurare gli aggiornamenti automatici del Punteggio sicuro

Per impostazione predefinita, tutti i nuovi tenant dispongono degli aggiornamenti automatici di [Secure Score](../security/mtp/microsoft-secure-score.md) attivati. Questo significa che tutte le azioni monitorate dal punteggio sicuro aggiorneranno automaticamente lo stato per la stessa azione nel punteggio di conformità.

L'amministratore globale può gestire questa impostazione per disattivare gli aggiornamenti automatici per tutte le azioni o impostare gli aggiornamenti per le azioni singolarmente.

Durante l'anteprima pubblica, è necessario accedere al Microsoft Service Trust Portal (in cui si trova la gestione della conformità) per gestire gli aggiornamenti dei punti di sicurezza.

Per gestire gli aggiornamenti automatici del Punteggio sicuro, attenersi alla seguente procedura:

1. Accedere al [Service Trust Portal](https://servicetrust.microsoft.com) con l'account di amministratore globale.

2. Nella barra dei menu del servizio di attendibilità del Service Top, in **altro**, selezionare **amministratore** e quindi scegliere **Impostazioni**.

3. Nella scheda **Punteggio sicuro** selezionare il pulsante corrispondente per **attivarla per tutte le azioni**, disattivarla **per tutte le azioni**o **impostare per azione.**

Se si sceglie **imposta per azione,** eseguire i passaggi aggiuntivi per abilitare gli aggiornamenti dei punti di sicurezza per le singole azioni:

4. Scegliere **Compliance Manager** dal menu in alto (Nota: non selezionare "Compliance Manager (Classic)").

5. Selezionare **gestione tenant** nell'angolo in alto a destra dello schermo.

6. Nel riquadro **azioni cliente** individuare l'azione desiderata con puntini di sospensione (**...**) nella colonna **azioni coinvolte** . Fare clic sui puntini di ellisse e selezionare **modifica.**

7. Cambiare l'opzione attiva/disattiva **aggiornamento continuo Punteggio** **su attivato.**

8. Selezionare **Salva.** Secure Score il monitoraggio continuo è ora attivato per tale azione.

**Nota:** Solo l'amministratore globale può abilitare o disattivare gli aggiornamenti automatici per tutte le azioni. L'amministratore di Compliance Manager può abilitare gli aggiornamenti automatici per singole azioni, ma non per tutte le azioni a livello globale.

Per ulteriori informazioni, vedere [Managing Secure Score Updates](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Comprendere il dashboard del Punteggio di conformità

Il dashboard del Punteggio di conformità è stato creato per fornire una visualizzazione a colpo d'occhio della posizione di conformità corrente.

![Punteggio di conformità-dashboard](../media/compliance-score-dashboard.png "Dashboard del Punteggio di conformità")

### <a name="overall-compliance-score"></a>Punteggio di conformità globale

Il Punteggio di conformità, evidenziato in primo piano nella parte superiore, presenta una percentuale basata sui punti ottenibili per il completamento delle azioni di miglioramento relative agli standard e alle normative sulla protezione dei dati.

Quando si giunge al Punteggio di conformità per la prima volta, il punteggio iniziale è basato sulla linea di base di protezione dei dati integrata di Microsoft 365, ovvero un insieme di controlli che include normative e standard di settore. Poiché il Punteggio di conformità analizza il sistema delle soluzioni Microsoft 365 esistenti, fornisce una valutazione iniziale della postura di conformità in base alle impostazioni di privacy e sicurezza attualmente abilitate dall'organizzazione.

Quando si aggiungono valutazioni rilevanti per la propria organizzazione, il punteggio diventa ancora più significativo. Per ulteriori informazioni [, vedere Calcolo del Punteggio](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Azioni di miglioramento principali

In questa sezione sono elencate le operazioni di miglioramento più importanti che è possibile eseguire in questo momento per ottenere un impatto positivo maggiore sul punteggio di conformità globale. Elenca le azioni che non sono state completate o non sono state eseguite con la valutazione con rischi elevati.

### <a name="solutions-that-affect-your-score"></a>Soluzioni che influiscono sul Punteggio

In questa sezione vengono illustrate le soluzioni che contengono azioni con la maggiore possibilità di influenzare positivamente il punteggio e il numero di azioni di miglioramento eccezionali disponibili in ogni soluzione.

### <a name="compliance-score-breakdown"></a>Ripartizione del Punteggio di conformità

In questa sezione viene fornita una visualizzazione più dettagliata del punteggio in due modi diversi:

- **Categorie**: indica la percentuale del Punteggio generale all'interno delle categorie di protezione dei dati, ad esempio "Protect Information" o "Manage Devices".
- **Valutazioni**: indica la percentuale di progressi nella gestione delle valutazioni per una particolare conformità e standard di protezione dei dati, normative o leggi, come GDPR o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrare la visualizzazione del dashboard

È possibile filtrare la visualizzazione del dashboard per visualizzare solo gli elementi relativi a specifiche normative e standard, soluzioni, tipo di azione, [gruppi di valutazioni configurati](working-with-compliance-manager.md#groups)o categorie di protezione dei dati. Il filtraggio della visualizzazione in questo modo consente di filtrare anche il punteggio nel dashboard, mostrando quanti punti sono stati raggiunti fuori dai possibili punti totali in base ai criteri di filtro.

Per applicare i filtri:

1. Selezionare **filtro** sul lato superiore destro del dashboard.
2. Selezionare i criteri di filtro dal riquadro **filtri** a comparsa, quindi fare clic su **applica**.

Dopo l'applicazione di un filtro, vedrai il tuo punteggio regolato in tempo reale. La percentuale del Punteggio di conformità e le informazioni di ripartizione e le azioni e le soluzioni di miglioramento, ora riguardano solo i dati trattati dai criteri di filtro. Se si disattiva il Punteggio di conformità, la visualizzazione filtrata rimane quando si effettua l'accesso.

Per rimuovere i filtri:

- Nella sezione **filtri applicati** sopra il Punteggio di conformità, selezionare la **X** accanto al singolo filtro che si desidera rimuovere. o
- Seleziona **filtro** nella parte superiore destra del dashboard, quindi seleziona **Pulisci filtri**.

## <a name="next-step"></a>Passaggio successivo

Visitare l' [utilizzo del Punteggio di conformità](working-with-compliance-score.md) per comprendere il flusso di lavoro di come eseguire azioni per migliorare il punteggio.
