---
title: Valutare il livello di sicurezza tramite Microsoft Secure Score
description: Descrive come intervenire per migliorare Microsoft Secure Score nel Centro sicurezza Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930643"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Valutare la sicurezza con Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero maggiore che indica più azioni di miglioramento intraprese. È disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

Per facilitare l'utilizzo delle informazioni necessarie più rapidamente, le azioni di miglioramento di Microsoft sono organizzate in gruppi:

* Identità (account Azure Active Directory & ruoli)
* Dispositivo (Microsoft Defender per Endpoint, noto come [Microsoft Secure Score per dispositivi)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* App (posta elettronica e app cloud, tra cui Office 365 e Microsoft Cloud App Security)

>[!NOTE]
>Nella recente versione di Microsoft Secure Score è stato rilasciato un modello di punteggio migliorato che ha reso Microsoft Secure Score temporaneamente incompatibile con Identity Secure Score e l'API Graph. [Visualizza dettagli](microsoft-secure-score-whats-new.md)

Nella pagina di panoramica di Microsoft Secure Score, visualizzare il modo in cui i punti vengono suddivisi tra questi gruppi e quali punti sono disponibili. È inoltre possibile ottenere una visualizzazione generale del punteggio totale, della tendenza cronologica del punteggio sicuro con confronti di benchmark e delle azioni di miglioramento prioritarie che è possibile eseguire per migliorare il punteggio.

![Home page di Secure Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Controllare il punteggio corrente

Per controllare il punteggio corrente, passare alla pagina di panoramica di Microsoft Secure Score e cercare il riquadro che indica **il punteggio sicuro.** Il punteggio verrà visualizzato come percentuale, insieme al numero di punti ottenuti rispetto al totale dei punti possibili.

Inoltre, se si seleziona il pulsante **Includi** accanto al punteggio, è possibile scegliere diverse visualizzazioni del punteggio. Queste diverse visualizzazioni del punteggio verranno visualizzate nel grafico nel riquadro del punteggio e nel grafico di suddivisione dei punti.

Di seguito sono riportati i punteggi che è possibile aggiungere alla visualizzazione del punteggio complessivo per ottenere un quadro più completo del punteggio complessivo:

- **Punteggio pianificato**: mostra il punteggio proiettato al termine delle azioni pianificate
- **Punteggio di licenza corrente:** mostra il punteggio che può essere ottenuto con la licenza Microsoft corrente
- **Punteggio raggiungibile: mostra** il punteggio che può essere raggiunto con le licenze Microsoft e l'accettazione dei rischi correnti

Questa visualizzazione è l'aspetto che avrà se hai incluso tutte le visualizzazioni dei punteggi possibili:

![Punteggio sicuro che include il punteggio pianificato, il punteggio della licenza corrente e il punteggio raggiungibile](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Intervenire per migliorare il punteggio

Nella **scheda Azioni di miglioramento** sono elencati i suggerimenti per la sicurezza che affrontano le possibili superfici di attacco. Include anche il loro stato (per risolvere, pianificato, rischio accettato, risolto tramite terze parti, risolto tramite mitigazione alternativa e completato). È possibile cercare, filtrare e raggruppare tutte le azioni di miglioramento.  

### <a name="ranking"></a>Classificazione

La classificazione si basa sul numero di punti da raggiungere, sulla difficoltà di implementazione, sull'impatto sugli utenti e sulla complessità. Le azioni di miglioramento di livello più alto hanno un numero elevato di punti rimanenti con bassa difficoltà, impatto utente e complessità.

### <a name="view-improvement-action-details"></a>Visualizzare i dettagli delle azioni di miglioramento

Quando si seleziona un'azione di miglioramento specifica, viene visualizzato un riquadro a comparsa a pagina intera.  

![Esempio di riquadro a comparsa delle azioni di miglioramento](../../media/secure-score/secure-score-improvement-action-details.png)

Per completare l'azione, sono disponibili alcune opzioni:

- Seleziona **Gestisci** per passare alla schermata di configurazione e apportare la modifica. Potrai quindi ottenere i punti che valgono l'azione, visibili nel riquadro a comparsa. L'aggiornamento dei punti in genere richiedere circa 24 ore.

- Selezionare **Condividi** per copiare il collegamento diretto all'azione di miglioramento. È inoltre possibile scegliere la piattaforma per condividere il collegamento, ad esempio posta elettronica, Microsoft Teams, Microsoft Planner o ServiceNow. La selezione di ServiceNow consente di creare un ticket di modifica che sarà visibile in ServiceNow e nella home page del Centro sicurezza Microsoft 365. Per altre informazioni, vedere Centro sicurezza [Microsoft 365 e l'integrazione di ServiceNow.](tickets-security-center.md)

Aggiungere **note** per tenere traccia dello stato di avanzamento o di qualsiasi altro elemento su cui si desidera aggiungere commenti. Se si aggiungono tag **personalizzati all'azione** di miglioramento, è possibile filtrare in base a tali tag.

### <a name="choose-an-improvement-action-status"></a>Scegliere lo stato di un'azione di miglioramento

Scegliere eventuali stati e registrare note specifiche per l'azione di miglioramento.

- **Da affrontare:** si riconosce che l'azione di miglioramento è necessaria e si prevede di affrontarla in un certo momento in futuro. Questo stato si applica anche alle azioni rilevate come parzialmente, ma non completamente completate.
- **Pianificato:** sono in atto piani concreti per completare l'azione di miglioramento.
- **Rischio accettato:** la sicurezza deve essere sempre bilanciata con l'usabilità e non tutte le raccomandazioni funzioneranno per il proprio ambiente. In questo caso, è possibile scegliere di accettare il rischio o il rischio rimanente e non di eseguire l'azione di miglioramento. Non ti verranno dati punti, ma l'azione non sarà più visibile nell'elenco delle azioni di miglioramento. È possibile visualizzare questa azione nella cronologia o annullarla in qualsiasi momento.
- **Risolto tramite terze parti** e risolto tramite mitigazione **alternativa:** l'azione di miglioramento è già stata affrontata da un'applicazione o un software di terze parti o da uno strumento interno. Potrai ottenere i punti che valgono l'azione, in modo che il punteggio rifletta meglio la tua posizione di sicurezza complessiva. Se una terza parte o uno strumento interno non copre più il controllo, puoi scegliere un altro stato. Tieni presente che Microsoft non avrà visibilità sulla completezza dell'implementazione se l'azione di miglioramento viene contrassegnata come uno di questi stati.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Azioni di & di gestione delle vulnerabilità

Per le azioni di miglioramento nella categoria "Dispositivo", non è possibile scegliere gli stati. Al contrario, si verrà indirizzati alla raccomandazione di sicurezza per la gestione delle minacce e delle vulnerabilità [associata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) per intervenire. L'eccezione scelta e la giustificazione che scrivi saranno specifiche per tale portale. Non sarà presente nel portale di Microsoft Secure Score.

#### <a name="completed-improvement-actions"></a>Azioni di miglioramento completate

Le azioni di miglioramento hanno uno stato "completato" dopo aver raggiunto tutti i punti possibili per l'azione di miglioramento. Le azioni di miglioramento completate vengono confermate anche se i dati Microsoft sono stati confermati e non è possibile modificare lo stato.

### <a name="assess-information-and-review-user-impact"></a>Valutare le informazioni ed esaminare l'impatto degli utenti

La sezione denominata **A colpo** d'occhio ti dirà la categoria, gli attacchi da cui può proteggersi e il prodotto.

**L'impatto** degli utenti è quello che gli utenti  sperimenteranno se viene eseguita l'azione di miglioramento e gli utenti interessati sono le persone interessate.

### <a name="implement-the-improvement-action"></a>Implementare l'azione di miglioramento

La **sezione Implementazione** mostra tutti i prerequisiti, i passaggi successivi dettagliati per completare l'azione di miglioramento, lo stato di implementazione corrente dell'azione di miglioramento e altri collegamenti.

I prerequisiti includono le licenze necessarie o le azioni da completare prima della gestione dell'azione di miglioramento. Assicurarsi di disporre di postazioni sufficienti nella licenza per completare l'azione di miglioramento e che tali licenze siano applicate agli utenti necessari.  

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando il post nella community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Stiamo monitorando la community e forniremo assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Panoramica di Microsoft Secure Score](microsoft-secure-score.md)
- [Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)
