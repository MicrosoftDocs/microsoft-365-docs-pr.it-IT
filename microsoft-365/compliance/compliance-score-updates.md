---
title: Aggiornamenti per il Punteggio di conformità Microsoft
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
description: Informazioni dettagliate sugli aggiornamenti futuri per Microsoft Compliance Score (Preview), una funzionalità del centro conformità di M365 che consente di semplificare e automatizzare le valutazioni dei rischi.
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857783"
---
# <a name="microsoft-compliance-score-preview-updates"></a>Microsoft Compliance Score (anteprima) aggiornamenti

 In questo articolo vengono fornite informazioni dettagliate sugli aggiornamenti futuri di Microsoft Compliance [Score](compliance-score.md) e [Microsoft Compliance Manager](compliance-manager-overview.md). Ulteriori informazioni sulla [relazione](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="improved-template-creation-and-update-processes"></a>Processi di creazione e aggiornamento dei modelli migliorati

Il processo di importazione, esportazione e modifica dei modelli per le valutazioni è semplificato. La nuova esperienza renderà più facile portare le proprie valutazioni nel punteggio di conformità e mantenerle aggiornate.

### <a name="the-current-process"></a>Il processo corrente

Esistono due modi per creare un modello in Compliance Manager. È possibile copiare un modello esistente oppure importare i dati dei modelli da un foglio di calcolo di Excel in un nuovo modello. Dalla pagina **modelli** è possibile selezionare **+ Aggiungi modello** per creare un nuovo modello immettendo un nome, selezionando dimensioni e caricando un file di Excel con un formato e uno schema specifici. In alternativa, è possibile controllare la **copia da una casella modello esistente** , selezionare un modello da copiare e verificare le dimensioni, come illustrato nell'immagine riportata di seguito. La personalizzazione del modello richiede un [processo](working-with-compliance-manager.md#templates) in più passaggi che inizia con la selezione di **Aggiungi controllo personalizzato** dopo la creazione del modello.

![Punteggio di conformità-dashboard](../media/compliance-score-template-update-old.png "Processo di copia corrente del modello")

### <a name="whats-changing"></a>Cosa cambia

Per creare nuovi modelli è più facile. In un processo di **estensione** a un solo passaggio, è possibile aggiungere un foglio di calcolo con le azioni e i controlli a un modello Microsoft esistente per rendere la propria versione personalizzata. Nel riquadro a comparsa **modello** selezionare la casella di controllo **Crea estensione da modello globale** , come illustrato nell'immagine seguente. Verranno quindi aggiunte le personalizzazioni utilizzando un nuovo formato di Excel meno complesso rispetto a quello corrente. Questo nuovo processo sostituisce la **copia corrente da un modello esistente** e **aggiunge funzioni di controllo personalizzate** .

Ogni volta che la valutazione originale viene aggiornata tramite il processo di controllo delle versioni descritto di seguito, la valutazione personalizzata erediterà tali aggiornamenti e manterrà i controlli personalizzati.

È inoltre possibile semplificare la modifica dei modelli esistenti. È possibile esportare il modello, modificare la stessa cartella di lavoro e quindi importarlo con le modifiche salvate.

![Punteggio di conformità-dashboard](../media/compliance-score-template-update-new.png "Processo di creazione di un nuovo modello")

## <a name="versioning-notice-and-control"></a>Avviso per il controllo delle versioni

L'organizzazione riceverà valutazioni aggiornate nella prossima versione di Score compliance e Compliance Manager per aiutarti a allineare gli aggiornamenti relativi alla certificazione e alle normative.

In futuro, ogni volta che un aggiornamento è disponibile per il modello di una valutazione o per un'azione di miglioramento, un'icona di avviso informa che è pronto un aggiornamento. Quando si fa clic su quell'icona, viene visualizzata una finestra popup che spiega l'aggiornamento e chiede di accettare. Di seguito è riportato un esempio di avviso per il controllo delle versioni per una valutazione:

![Avviso di conformità del Punteggio-Versioning](../media/compliance-score-assessment-version.png "Avviso di aggiornamento della versione di valutazione")

Se si seleziona l'icona di avviso, viene illustrato un riquadro a comparsa che illustra l'aggiornamento e viene richiesto di accettare:

![Riquadro a comparsa del controllo delle versioni](../media/compliance-score-assessment-version-accept.png "Riquadro di conferma dell'aggiornamento di valutazione")

## <a name="common-actions-will-synch-status-across-groups"></a>Azioni comuni lo stato di sincronizzazione tra i gruppi

Se l'organizzazione dispone di più gruppi di valutazioni, il comportamento delle azioni **tecniche** (ovvero azioni che interessano l'intera organizzazione) cambierà. Tutte le azioni duplicate tra i gruppi verranno combinate in un'unica azione. Tale azione singola conterrà tutte le note e le evidenze caricate dalle versioni duplicate. Con questa modifica, le azioni tecniche si comporteranno come attualmente fanno quando appartengono allo stesso gruppo. Tutte le modifiche apportate all'azione in un gruppo o in una valutazione verranno riflesse in tutte le istanze. Lo **stato di implementazione**, l' **implementazione dat**, **lo stato del test**e la **Data** di test rispecchiano gli aggiornamenti più recenti.

## <a name="language-support"></a>Supporto lingue

Il Punteggio di conformità sarà ora disponibile nelle seguenti lingue oltre all'inglese: cinese (semplificato), cinese (tradizionale), francese, tedesco, italiano, giapponese, coreano, portoghese (Brasile), russo e spagnolo.
