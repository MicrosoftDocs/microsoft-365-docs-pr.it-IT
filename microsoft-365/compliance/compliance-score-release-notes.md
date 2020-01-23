---
title: Note sulla versione del Punteggio di conformità di Microsoft
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
description: Note sulla versione e i problemi noti di Microsoft Compliance Score (Preview), una funzionalità del centro conformità di M365 che consente di semplificare e automatizzare le valutazioni dei rischi.
ms.openlocfilehash: 370c714c927d09a16272f8ab265c7b0c4e36381a
ms.sourcegitcommit: 5fc0f2cd1f2596fd10299333c826c501936dcd98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2020
ms.locfileid: "41261870"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Note sulla versione di Microsoft Compliance Score (Preview)

L'anteprima pubblica del Punteggio di conformità di Microsoft fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti. Per informazioni sulle novità, vedere spesso questa pagina.

La conformità Score è una nuova funzionalità del [centro conformità di Microsoft 365](microsoft-365-compliance-center.md) che calcola un punteggio basato sui rischi, misurando i progressi compiuti verso il completamento delle azioni consigliate che consentono di ridurre i rischi di conformità.

## <a name="whats-new"></a>Novità

### <a name="new-templates-for-assessments"></a>Nuovi modelli per le valutazioni

I nuovi modelli preconfigurati per le valutazioni vengono rilasciati in produzione per il Punteggio di conformità (anteprima) Man mano che diventano disponibili. Controllare l' [elenco completo dei modelli qui](compliance-score.md#templates). I modelli aggiunti di recente includono:

- Legge generale sulla protezione dei dati (LGPD) in Brasile
- IRAP/governo australiano ISM (anteprima)
- ISO 27701:2019
- SOC 1
- SOC 2

### <a name="compliance-score-relationship-to-compliance-manager"></a>Relazione tra Punteggio di conformità e Compliance Manager

Molte delle funzioni di conformità gestite in Compliance Manager possono ora essere eseguite nel punteggio di conformità. Tuttavia, alcune funzionalità risiedono ancora solo in Compliance Manager e alcune funzionalità precedenti in Compliance Manager vengono modificate durante il periodo di anteprima pubblica. 

Tenere presente questi punti quando si lavora con score compliance e Compliance Manager durante l'anteprima pubblica:

- **Gestione delle valutazioni**: gli utenti possono visualizzare le valutazioni e i relativi dettagli sullo stato nel punteggio di conformità. Tuttavia, gli utenti possono eseguire solo attività di gestione della valutazione in Compliance Manager ([vedere le istruzioni](working-with-compliance-manager.md#assessments)) e le attività sono limitate alle seguenti:
    - Caricare nuove valutazioni, ma non modificare le valutazioni esistenti. Se è necessario modificare una valutazione esistente, sarà necessario caricare un nuovo modello.
    - Valutazioni dell'esportazione
    - Valutazioni dell'archivio
    - Visualizzazione delle valutazioni archiviate
 - **Creazione di modelli per le valutazioni**: 
   - Gli utenti devono accedere a Compliance Manager per creare nuovi modelli ed esportare modelli esistenti. 
   - I modelli esistenti non possono essere personalizzati. Leggere le istruzioni per la [gestione dei modelli in Compliance Manager](working-with-compliance-manager.md#templates).
   - Quando si crea un modello, è necessario includere le dimensioni per il **prodotto** e la **certificazione** per garantire che il modello venga visualizzato nel punteggio di conformità.
 - **Impostazione delle autorizzazioni**: Punteggio di conformità gli utenti che non sono stati precedentemente concessi autorizzazioni in Compliance Manager devono disporre delle autorizzazioni impostate nel centro conformità di Microsoft 365 (ulteriori[informazioni](compliance-score-setup.md#set-user-permissions-and-assign-roles)). Gli utenti i cui ruoli sono stati precedentemente impostati in Compliance Manager possono utilizzare lo stesso livello di accesso quando si lavora nel punteggio di conformità.
- **Trasferimento di dati**: le organizzazioni con dati che risiedono in Gestione conformità vedranno tali dati nel punteggio di conformità e viceversa.
- **Accesso a Compliance Manager dal punteggio di conformità**: se un utente ha eseguito l'accesso a Score compliance e seleziona un collegamento per accedere a Compliance Manager, l'utente non dovrà accedere di nuovo. Dopo aver fatto clic sul collegamento, una nuova scheda viene visualizzata nel browser con una finestra di dialogo. Nella sezione superiore con l'intestazione, "già un cliente dei servizi cloud Microsoft? Accedere al proprio account, "selezionare il pulsante di **accesso** per accedere automaticamente a Compliance Manager.

## <a name="known-issues-in-compliance-score-preview"></a>Problemi noti nel punteggio di conformità (anteprima)

Nelle sezioni seguenti vengono illustrati i problemi noti da risolvere nelle prossime versioni del Punteggio di conformità.

### <a name="launch-now-links-in-certain-improvement-actions"></a>Avviare i collegamenti ora in determinate azioni di miglioramento

In determinate azioni di miglioramento, selezionando il collegamento **Avvia ora** visualizzato al di sotto delle istruzioni di implementazione viene restituito un errore. Per accedere alla destinazione appropriata, che è l'interfaccia di amministrazione di SharePoint, eseguire la procedura seguente:

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).
2. Scegliere **Mostra tutto**dal menu di spostamento a sinistra.
3. In interfaccia **di amministrazione** selezionare **SharePoint**.

Di seguito sono riportate le azioni di miglioramento riportate, che risiedono tutti nella categoria **protezione delle informazioni** :
  - Applicare la crittografia alla raccolta di SharePoint
  - Classificazione dei dati in SharePoint Online
  - Configurare i collegamenti di condivisione esterna per la scadenza
  - Abilitare il controllo delle versioni per le raccolte documenti

### <a name="long-load-times-for-non-admin-users"></a>Tempi di caricamento lunghi per utenti non amministratori
Punteggio di conformità gli utenti che dispongono di ruoli diversi da un ruolo di amministratore possono riscontrare tempi di caricamento lunghi quando si tenta di accedere a un utente. Se si aggiorna il browser, questo problema verrà risolto. (Ulteriori informazioni sui [ruoli del Punteggio di conformità](compliance-score-setup.md#set-user-permissions-and-assign-roles))

### <a name="supported-browsers"></a>Browser supportati

- Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.
- Possono verificarsi casi in cui i dati aggiornati non vengono visualizzati fino a quando il browser non viene aggiornato.
- La versione di anteprima di Microsoft Edge non è supportata ma non ha problemi noti.
- Internet Explorer non è supportato.
 
### <a name="language-support"></a>Supporto lingue

- Il Punteggio di conformità è disponibile solo in inglese (Stati Uniti).