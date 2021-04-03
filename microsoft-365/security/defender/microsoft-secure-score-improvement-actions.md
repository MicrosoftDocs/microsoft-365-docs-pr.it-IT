---
title: Valutare il proprio livello di sicurezza tramite Microsoft Secure Score
description: Descrive come intervenire per migliorare microsoft Secure Score nel Centro sicurezza Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 0b2b9f1f01a583a96e0ae663e3f78cb0a7d846fc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570601"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Valutare il proprio stato di sicurezza con Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score è una misurazione della postura di sicurezza di una organizzazione, in cui i numeri più alti indicano l'esecuzione di più azioni di miglioramento. È disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

Per trovare più rapidamente le informazioni necessarie, le azioni di miglioramento Microsoft sono organizzate in gruppi:

* Identity (account di Azure Active Directory & ruoli)
* Dispositivo (Microsoft Defender for Endpoint, noto come [Microsoft Secure Score per dispositivi](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
* App (app di posta elettronica e cloud, tra cui Office 365 e Microsoft Cloud App Security)

>[!NOTE]
>Nella recente versione di Microsoft Secure Score è stato rilasciato un modello di punteggio migliorato che ha reso Microsoft Secure Score temporaneamente incompatibile con Identity Secure Score e l'API Graph. [Visualizza dettagli](microsoft-secure-score-whats-new.md)

Nella pagina panoramica di Microsoft Secure Score, visualizzare la modalità di suddivisione dei punti tra questi gruppi e i punti disponibili. Puoi anche ottenere una visualizzazione generale del punteggio totale, della tendenza storica del punteggio sicuro con confronti di benchmark e delle azioni di miglioramento con priorità che possono essere intraprese per migliorare il punteggio.

![Home page punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Controllare il punteggio corrente

Per controllare il punteggio corrente, passare alla pagina Panoramica del punteggio sicuro Microsoft e cercare il riquadro **Il punteggio sicuro**. Il punteggio verrà visualizzato come percentuale, insieme al numero di punti ottenuti rispetto al totale dei punti possibili.

Inoltre, se si seleziona il **pulsante Includi** accanto al punteggio, è possibile scegliere diverse visualizzazioni del punteggio. Queste diverse visualizzazioni del punteggio verranno visualizzate nel grafico nel riquadro del punteggio e nel grafico di suddivisione dei punti.

Di seguito sono riportati i punteggi che è possibile aggiungere alla visualizzazione del punteggio complessivo per ottenere un quadro più completo del punteggio complessivo:

- **Punteggio pianificato**: mostra il punteggio proiettato al termine delle azioni pianificate
- **Punteggio di licenza corrente:** mostra il punteggio che può essere ottenuto con la licenza Microsoft corrente
- **Punteggio raggiungibile**: Mostra il punteggio che può essere ottenuto con le licenze Microsoft e l'accettazione del rischio corrente

Questa visualizzazione è l'aspetto che avrà se hai incluso tutte le possibili visualizzazioni del punteggio:

![Il punteggio sicuro, incluso il punteggio pianificato, il punteggio della licenza corrente e il punteggio raggiungibile](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Agire per migliorare il punteggio

Nella **scheda Azioni di miglioramento** sono elencati i suggerimenti per la sicurezza che affrontano le possibili superfici di attacco. Include anche il loro stato (per affrontare, pianificato, rischio accettato, risolto tramite terze parti, risolto tramite mitigazione alternativa e completato). È possibile cercare, filtrare e raggruppare tutte le azioni di miglioramento.  

### <a name="ranking"></a>Classificazione

La classificazione si basa sul numero di punti da raggiungere, sulla difficoltà di implementazione, sull'impatto dell'utente e sulla complessità. Le azioni di miglioramento di livello più alto hanno un gran numero di punti rimanenti con difficoltà, impatto utente e complessità bassi.

### <a name="view-improvement-action-details"></a>Visualizzare i dettagli delle azioni di miglioramento

Quando si seleziona un'azione di miglioramento specifica, viene visualizzato un riquadro a comparsa a pagina intera.  

![Esempio di riquadro a comparsa azione di miglioramento](../../media/secure-score/secure-score-improvement-action-details.png)

Per completare l'azione, sono disponibili alcune opzioni:

- Seleziona **Gestisci** per passare alla schermata di configurazione e apportare la modifica. Potrai quindi ottenere i punti che valgono l'azione, visibili nel fly out. L'aggiornamento dei punti in genere è di circa 24 ore.

- Selezionare **Condividi** per copiare il collegamento diretto all'azione di miglioramento. È inoltre possibile scegliere la piattaforma per condividere il collegamento, ad esempio posta elettronica, Microsoft Teams, Microsoft Planner o ServiceNow. Selezionando ServiceNow è possibile creare un ticket di modifica che sarà visibile in ServiceNow e nella home page del Centro sicurezza Microsoft 365. Per ulteriori informazioni, vedere Centro sicurezza [Microsoft 365 e Integrazione ServiceNow.](./tickets.md)

Aggiungere **note** per tenere traccia dello stato o di qualsiasi altro elemento su cui si desidera aggiungere commenti. Se aggiungi tag  personalizzati all'azione di miglioramento, puoi filtrare in base a tali tag.

### <a name="choose-an-improvement-action-status"></a>Scegliere lo stato di un'azione di miglioramento

Scegliere eventuali stati e registrare note specifiche per l'azione di miglioramento.

- **Da affrontare:** si riconosce che l'azione di miglioramento è necessaria e si prevede di affrontarla a un certo punto in futuro. Questo stato si applica anche alle azioni rilevate parzialmente, ma non completamente completate.
- **Pianificato:** sono in atto piani concreti per completare l'azione di miglioramento.
- **Rischio accettato:** la sicurezza deve essere sempre bilanciata con l'usabilità e non tutte le raccomandazioni funzioneranno per l'ambiente. In questo caso, è possibile scegliere di accettare il rischio o il rischio rimanente e non di eseguire l'azione di miglioramento. Non verranno dati punti, ma l'azione non sarà più visibile nell'elenco delle azioni di miglioramento. È possibile visualizzare questa azione nella cronologia o annullarla in qualsiasi momento.
- **Risolto tramite terze parti** e **risolto** tramite mitigazione alternativa: l'azione di miglioramento è già stata affrontata da un'applicazione o un software di terze parti o uno strumento interno. Potrai ottenere i punti che valgono l'azione, in modo che il punteggio rifletta meglio la tua posizione di sicurezza complessiva. Se uno strumento interno o di terze parti non copre più il controllo, puoi scegliere un altro stato. Tieni presente che Microsoft non avrà visibilità sulla completezza dell'implementazione se l'azione di miglioramento viene contrassegnata come uno di questi stati.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Azioni di miglioramento della gestione delle & delle minacce

Per le azioni di miglioramento nella categoria "Dispositivo", non puoi scegliere gli stati. Al contrario, sarai indirizzato alla raccomandazione di sicurezza per la gestione delle minacce e delle vulnerabilità [associata](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) per intraprendere un'azione. L'eccezione scelta e la giustificazione da scrivere saranno specifiche per tale portale. Non sarà presente nel portale Microsoft Secure Score.

#### <a name="completed-improvement-actions"></a>Azioni di miglioramento completate

Le azioni di miglioramento hanno uno stato "completato" dopo aver raggiunto tutti i punti possibili per l'azione di miglioramento. Le azioni di miglioramento completate vengono confermate anche se i dati Microsoft sono stati confermati e non è possibile modificare lo stato.

### <a name="assess-information-and-review-user-impact"></a>Valutare le informazioni ed esaminare l'impatto degli utenti

La sezione **"A colpo d'occhio"** ti dirà la categoria, gli attacchi da cui può proteggersi e il prodotto.

**L'impatto** dell'utente è ciò che gli utenti  sperimenteranno se viene eseguita l'azione di miglioramento e gli utenti interessati sono le persone che saranno interessate.

### <a name="implement-the-improvement-action"></a>Implementare l'azione di miglioramento

La **sezione Implementazione** mostra tutti i prerequisiti, i passaggi successivi dettagliati per completare l'azione di miglioramento, lo stato di implementazione corrente dell'azione di miglioramento e altri collegamenti.

I prerequisiti includono le licenze necessarie o le azioni da completare prima che venga affrontata l'azione di miglioramento. Assicurati di disporre di postazioni sufficienti nella licenza per completare l'azione di miglioramento e che tali licenze siano applicate agli utenti necessari.  

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando la community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Stiamo monitorando la community e forniremo assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Panoramica di Microsoft Secure Score](microsoft-secure-score.md)
- [Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)