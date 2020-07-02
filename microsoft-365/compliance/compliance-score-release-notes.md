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
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022193"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Note sulla versione di Microsoft Compliance Score (Preview)

**In questo articolo:** In questa pagina vengono illustrate le **novità** nell'anteprima pubblica del [Punteggio di conformità di Microsoft](compliance-score.md), che consente di accedere in anticipo alle nuove funzionalità.

## <a name="assessment-creation-and-management-functionality"></a>Funzionalità di creazione e gestione della valutazione

La versione di giugno 2020 aggiunge la funzionalità per gli utenti di creare, eliminare e gestire le loro valutazioni direttamente nel punteggio di conformità. In precedenza, tutta la gestione della valutazione risiedeva in Compliance Manager. Quando si crea o si modifica una valutazione nel punteggio di conformità, gli aggiornamenti verranno ripartiti in Compliance Manager. Analogamente, tutti i lavori di valutazione eseguiti in Compliance Manager avranno un punteggio di conformità. Informazioni su come [gestire le valutazioni nel punteggio di conformità](compliance-score-assessments.md). Si noti che la creazione e la modifica del modello sono ancora gestite in Compliance Manager.

## <a name="new-templates-for-assessments"></a>Nuovi modelli per le valutazioni

I nuovi modelli pronti per l'uso per le valutazioni vengono rilasciati nel punteggio di conformità man mano che diventano disponibili. Controllare l' [elenco completo dei modelli qui](compliance-score-templates.md). Aggiunta di recente:

- Risoluzione sulla sicurezza delle informazioni di Dubai (DGISR)

## <a name="compliance-score-relationship-to-compliance-manager"></a>Relazione tra Punteggio di conformità e Compliance Manager

Molte delle funzioni gestite in Compliance Manager possono ora essere eseguite nel punteggio di conformità. Tuttavia, alcune funzioni sono ancora attive in Compliance Manager. Tenere presente questi punti quando si lavora con score compliance e Compliance Manager durante l'anteprima pubblica:

 - **Creazione di modelli per le valutazioni**: 
   - Gli utenti devono accedere a Compliance Manager per [creare nuovi modelli e modificare i modelli esistenti](working-with-compliance-manager.md#templates).
   - I nuovi modelli devono includere le dimensioni per il **prodotto** e la **certificazione**.
 - **Impostazione delle autorizzazioni**: Punteggio di conformità gli utenti che non dispongono già delle autorizzazioni in Compliance Manager devono disporre delle autorizzazioni impostate nel centro conformità di Microsoft 365 (ulteriori[informazioni](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Trasferimento di dati**: le organizzazioni che dispongono di dati in Compliance Manager vedranno che i dati vengono visualizzati come Punteggio di conformità e lo stesso vale anche per l'altro.
- **Accesso a Compliance Manager dal punteggio di conformità**: se un utente ha eseguito l'accesso a Score compliance e seleziona un collegamento per accedere a Compliance Manager, l'utente non dovrà accedere di nuovo. Dopo aver fatto clic sul collegamento, una nuova scheda viene visualizzata nel browser con una finestra di dialogo. Nella sezione superiore con l'intestazione, "già un cliente dei servizi cloud Microsoft? Accedere al proprio account, "selezionare il pulsante di **accesso** per accedere automaticamente a Compliance Manager.

## <a name="known-issues-in-compliance-score-preview"></a>Problemi noti nel punteggio di conformità (anteprima)

Nelle sezioni seguenti vengono illustrati i problemi noti da risolvere nelle prossime versioni del Punteggio di conformità.

### <a name="long-load-times-for-non-admin-users"></a>Tempi di caricamento lunghi per utenti non amministratori
Punteggio di conformità gli utenti che dispongono di ruoli diversi da un ruolo di amministratore possono riscontrare tempi di caricamento lunghi quando si tenta di accedere a un utente. Se si aggiorna il browser, questo problema verrà risolto. Per ulteriori informazioni, vedere [Role Score Compliance](compliance-score-setup.md#set-user-permissions-and-assign-roles).

### <a name="supported-browsers"></a>Browser supportati

- Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.
- I dati aggiornati a volte non vengono visualizzati fino a quando non viene aggiornato il browser.
- Internet Explorer non è supportato.
