---
title: Note sulla versione di Microsoft Compliance Manager
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
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: de69d4c7e5938d8bfd3fed74b9ae44288e48019c
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141541"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a>Note sulla versione di Microsoft Compliance Manager (anteprima)

L'anteprima pubblica di Compliance Manager fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti. Questa pagina contiene gli aggiornamenti sulle nuove funzionalità, le funzionalità migliorate e i problemi noti relativi alla versione corrente.

È possibile utilizzare lo strumento [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) sul [Service Trust Portal](https://servicetrust.microsoft.com) per tenere conto, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.

## <a name="improved-template-creation-and-update-process"></a>Processo di aggiornamento e creazione modelli migliorato

È stato aggiornato il processo di importazione, esportazione e modifica dei modelli per le valutazioni. La nuova esperienza semplificata renderà più facile portare le proprie valutazioni nel flusso di lavoro e tenerle aggiornate.

### <a name="the-old-process"></a>Il processo precedente

Sono disponibili due modi per creare un modello in Compliance Manager. È possibile copiare un modello esistente o importare i dati dei modelli da un foglio di calcolo di Excel in un nuovo modello. Dalla pagina **modelli** è necessario selezionare **+ Aggiungi modello** per creare un nuovo modello immettendo un nome, selezionando dimensioni e caricando un file di Excel con un formato e uno schema specifici. In alternativa, è possibile controllare la **copia da una casella modello esistente** , selezionare un modello da copiare e verificare le dimensioni. Personalizzazione del modello è stato richiesto un processo in più passaggi che è stato avviato selezionando **Aggiungi controllo personalizzato** dopo la creazione del modello.

### <a name="the-new-process"></a>Il nuovo processo

Per creare nuovi modelli è più facile. In un processo di **estensione** a un solo passaggio, è possibile aggiungere un foglio di calcolo con le azioni e i controlli a un modello Microsoft esistente per rendere la propria versione personalizzata. Nella pagina **modelli** in Compliance Manager selezionare **+ Aggiungi modello**. Nel riquadro a comparsa **modello** selezionare la casella **di controllo Crea estensione da modello globale** . È possibile aggiungere personalizzazioni con un nuovo formato di Excel meno complesso rispetto a quello precedente. Questo nuovo processo sostituisce la **copia precedente da un modello esistente** e **aggiunge funzioni di controllo personalizzate** .

Ogni volta che la valutazione originale viene aggiornata tramite il processo di controllo delle versioni descritto di seguito, la valutazione personalizzata erediterà tali aggiornamenti e manterrà i controlli personalizzati.

Inoltre, è più facile modificare i modelli esistenti. È possibile esportare il modello, modificare la stessa cartella di lavoro e quindi importarlo con le modifiche salvate.

Visualizzare istruzioni dettagliate sulla [creazione di modelli](working-with-compliance-manager.md#templates) con questo nuovo processo.

## <a name="versioning-notice-and-control"></a>Avviso per il controllo delle versioni

L'organizzazione ha ricevuto valutazioni aggiornate nella versione di aprile 2020 di Compliance Manager per aiutarti a allineare gli aggiornamenti relativi alla certificazione e alle normative. Avanzando, verrà fornito un modo chiaro per comprendere e accettare tutti gli aggiornamenti futuri tramite gli avvisi per il **controllo delle versioni**.

Ogni volta che un aggiornamento è disponibile per il modello di una valutazione o per un'azione di miglioramento, un'icona di avviso informa che è pronto un aggiornamento. Quando si fa clic su quell'icona, viene visualizzata una finestra popup che spiega l'aggiornamento e chiede di accettare. Selezionando l'icona di avviso, viene illustrato un riquadro a comparsa che illustra l'aggiornamento e richiede l'accettazione. Per ulteriori informazioni, vedere [accettazione degli aggiornamenti alle valutazioni](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).

## <a name="common-actions-will-synch-status-across-groups"></a>Azioni comuni lo stato di sincronizzazione tra i gruppi

Se l'organizzazione dispone di più gruppi di valutazioni, il comportamento delle azioni **tecniche** (ovvero azioni che interessano l'intera organizzazione) è stato modificato. Tutte le azioni duplicate tra i gruppi sono state combinate in un'unica azione. Questa singola azione contiene tutte le note e le evidenze caricate dalle versioni duplicate. Con questa modifica, le azioni tecniche si comportano in questo modo quando appartengono allo stesso gruppo. Tutte le modifiche apportate all'azione in un gruppo o in una valutazione verranno riflesse in tutte le istanze. Lo **stato**di implementazione, la **Data di implementazione**, **lo stato del test**e la data di **test** rispecchiano gli aggiornamenti più recenti.

## <a name="language-support"></a>Supporto lingue

Compliance Manager è ora disponibile nelle seguenti lingue oltre che in inglese: cinese (semplificato), cinese (tradizionale), francese, tedesco, italiano, giapponese, coreano, portoghese (Brasile), russo e spagnolo.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemi noti in Compliance Manager (anteprima)

Nella sezione seguente vengono illustrati i problemi noti della versione corrente di Compliance Manager.

### <a name="compliance-score"></a>Punteggio di conformità

- Per gli elementi azione contrassegnati come **non nell'ambito**, il punteggio assegnato all'elemento azione non è escluso dal calcolo del Punteggio di conformità. Gli elementi azione contrassegnati **non nell'ambito** non aumentano il Punteggio di conformità.

### <a name="secure-score"></a>Secure Score

- I risultati del Punteggio sicuro non sono disponibili per alcuni elementi di azioni in determinate sottoscrizioni di Microsoft 365 e Office 365. **Non è stato possibile rilevare** il risultato del Punteggio sicuro in questi casi.
- A volte vengono restituiti risultati di Punteggio sicuro per i criteri corrispondenti e gli elementi di azione non completati.
- Per i nuovi tenant, gli aggiornamenti del Punteggio sicuro per tutte le azioni vengono attivati automaticamente. L'amministratore globale può impostare l'opzione di aggiornamento continuo per il Punteggio sicuro su disattivato, che disattiva gli aggiornamenti per tutte le azioni.
  - **Nota**: quando le organizzazioni distribuiscono per la prima volta Microsoft 365 o Office 365, sono necessari circa sette giorni per ottenere un punteggio sicuro per raccogliere completamente i dati e fattorizzarli nello score. Durante questo periodo, l'impostazione dell'opzione aggiornamento continuo Punteggio sicuro su **disattivato** e l'impostazione manuale di un'azione su **implementata** consentiranno di contare tale azione verso il punteggio. Dopo sette giorni iniziali, la riattivazione dell'aggiornamento continuo dei punteggi sicuri consentirà il monitoraggio continuo da quel momento in poi.
- Quando gli aggiornamenti del Punteggio sicuro sono attivati, le azioni vengono monitorate attivamente dal punteggio sicuro, anche se la data di test dell'azione non verrà aggiornata per riflettere il monitoraggio.
- Quando vengono create nuove valutazioni, i punteggi includono automaticamente i punteggi dei controlli gestiti da Microsoft e l'integrazione del Punteggio sicuro.
- Tutte le azioni che non sono supportate dall'integrazione del Punteggio sicuro possono essere implementate manualmente. Un'implementazione manuale consentirà di fattorizzare lo score del gruppo dell'azione.

### <a name="export"></a>Esportazione

- L'esportazione dei modelli in JSON ha esito negativo quando lo stato del modello è impostato su **importazione** o **in attesa di approvazione**.

### <a name="supported-browsers"></a>Browser supportati

- Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.
- Possono verificarsi casi in cui i dati aggiornati non vengono visualizzati fino a quando non viene aggiornato il browser.
- La versione di anteprima di Microsoft Edge non è supportata ma non ha problemi noti.
- Internet Explorer non è supportato.

### <a name="session-timeout"></a>Timeout sessione

- Quando si verifica un timeout di una sessione, potrebbe essere visualizzato un errore "qualcosa è andato storto". Per risolvere il caso, passare a [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) e accedere di nuovo.