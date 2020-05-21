---
title: Note sulla versione del Punteggio di conformità di Microsoft
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
description: Note sulla versione e i problemi noti di Microsoft Compliance Score (Preview), una funzionalità del centro conformità di M365 che consente di semplificare e automatizzare le valutazioni dei rischi.
ms.openlocfilehash: 1567921b8bd07b0fe4deda0bab6601898eed75a9
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330780"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Note sulla versione di Microsoft Compliance Score (Preview)

L'anteprima pubblica del Punteggio di conformità di Microsoft fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti. Per informazioni sulle novità, vedere spesso questa pagina.

La conformità Score è una nuova funzionalità del [centro conformità di Microsoft 365](microsoft-365-compliance-center.md) che calcola un punteggio basato sui rischi, misurando i progressi compiuti verso il completamento delle azioni consigliate che consentono di ridurre i rischi di conformità.

## <a name="new-templates-for-assessments"></a>Nuovi modelli per le valutazioni

I nuovi modelli preconfigurati per le valutazioni vengono rilasciati in produzione per il Punteggio di conformità (anteprima) Man mano che diventano disponibili. Controllare l' [elenco completo dei modelli qui](compliance-score.md#templates). I modelli aggiunti di recente includono:

- Legge generale sulla protezione dei dati (LGPD) in Brasile
- Risoluzione sulla sicurezza delle informazioni di Dubai (DGISR)
- IRAP/governo australiano ISM (anteprima)
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>Miglioramenti nella gestione delle valutazioni

La versione più recente di Compliance Manager nell'aprile 2020 include gli aggiornamenti che semplificano la creazione e la personalizzazione delle valutazioni e l'aggiornamento. Per informazioni dettagliate, vedere le [Note sulla versione di Compliance Manager](compliance-manager-release-notes.md) .

## <a name="language-support"></a>Supporto lingue

Il Punteggio di conformità è ora disponibile nelle seguenti lingue oltre all'inglese: cinese (semplificato), cinese (tradizionale), francese, tedesco, italiano, giapponese, coreano, portoghese (Brasile), russo e spagnolo.

## <a name="common-actions-will-synch-status-across-groups"></a>Azioni comuni lo stato di sincronizzazione tra i gruppi

Se l'organizzazione dispone di più gruppi di valutazioni, il comportamento delle azioni **tecniche** (ovvero azioni che interessano l'intera organizzazione) è stato modificato. Tutte le azioni duplicate tra i gruppi sono state combinate in un'unica azione. Questa singola azione contiene tutte le note e le evidenze caricate dalle versioni duplicate. Con questa modifica, le azioni tecniche si comportano in questo modo quando appartengono allo stesso gruppo. Tutte le modifiche apportate all'azione in un gruppo o in una valutazione verranno riflesse in tutte le istanze. Lo **stato**di implementazione, la **Data di implementazione**, **lo stato del test**e la data di **test**   rispecchiano gli aggiornamenti più recenti.

## <a name="compliance-score-relationship-to-compliance-manager"></a>Relazione tra Punteggio di conformità e Compliance Manager

Molte delle funzioni gestite in Compliance Manager possono ora essere eseguite nel punteggio di conformità. Tuttavia, alcune funzioni sono ancora attive in Compliance Manager. Tenere presente questi punti quando si lavora con score compliance e Compliance Manager durante l'anteprima pubblica:

- **Gestione delle valutazioni**: gli utenti possono visualizzare le valutazioni e i relativi dettagli sullo stato nel punteggio di conformità. Tuttavia, gli utenti possono eseguire solo attività di gestione della valutazione in Compliance Manager ([vedere le istruzioni](working-with-compliance-manager.md#assessments)). Di seguito sono riportati alcuni esempi di attività:
    - Creazione e copia di valutazioni
    - Valutazioni dell'esportazione
    - Valutazioni dell'archivio
    - Visualizzazione delle valutazioni archiviate
 - **Creazione di modelli per le valutazioni**: 
   - Gli utenti devono accedere a Compliance Manager per creare nuovi modelli e modificare i [modelli](working-with-compliance-manager.md#templates)esistenti. 
   - Quando si crea un modello, è necessario includere le dimensioni per il **prodotto** e la **certificazione** per garantire che il modello venga visualizzato nel punteggio di conformità.
 - **Impostazione delle autorizzazioni**: Punteggio di conformità gli utenti che non dispongono già delle autorizzazioni in Compliance Manager devono disporre delle autorizzazioni impostate nel centro conformità di Microsoft 365 (ulteriori[informazioni](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Trasferimento di dati**: le organizzazioni che dispongono di dati in Compliance Manager vedranno che i dati vengono visualizzati come Punteggio di conformità e lo stesso vale anche per l'altro.
- **Accesso a Compliance Manager dal punteggio di conformità**: se un utente ha eseguito l'accesso a Score compliance e seleziona un collegamento per accedere a Compliance Manager, l'utente non dovrà accedere di nuovo. Dopo aver fatto clic sul collegamento, una nuova scheda viene visualizzata nel browser con una finestra di dialogo. Nella sezione superiore con l'intestazione, "già un cliente dei servizi cloud Microsoft? Accedere al proprio account, "selezionare il pulsante di **accesso** per accedere automaticamente a Compliance Manager.

## <a name="known-issues-in-compliance-score-preview"></a>Problemi noti nel punteggio di conformità (anteprima)

Nelle sezioni seguenti vengono illustrati i problemi noti da risolvere nelle prossime versioni del Punteggio di conformità.

### <a name="long-load-times-for-non-admin-users"></a>Tempi di caricamento lunghi per utenti non amministratori
Punteggio di conformità gli utenti che dispongono di ruoli diversi da un ruolo di amministratore possono riscontrare tempi di caricamento lunghi quando si tenta di accedere a un utente. Se si aggiorna il browser, questo problema verrà risolto. (Ulteriori informazioni sui [ruoli del Punteggio di conformità](compliance-score-setup.md#set-user-permissions-and-assign-roles))

### <a name="supported-browsers"></a>Browser supportati

- Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.
- I dati aggiornati a volte non vengono visualizzati fino a quando non viene aggiornato il browser.
- Internet Explorer non è supportato.
