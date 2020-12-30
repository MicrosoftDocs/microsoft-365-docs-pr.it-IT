---
title: Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi
description: Ottenere informazioni sulle attività che hanno influenzato il Punteggio di Microsoft Secure. Individuare le tendenze e impostare gli obiettivi.
keywords: Microsoft Secure score, Secure score, Office 365 Secure score, Microsoft Security score, Microsoft 365 Security Center, azioni di miglioramento
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738044"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure Score](microsoft-secure-score.md) è una misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite. Può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Ottenere informazioni dettagliate sull'attività che ha influenzato il Punteggio

Visualizzare un grafico del punteggio dell'organizzazione nel tempo nella scheda **cronologia** .

Di seguito è riportato un elenco di tutte le azioni eseguite nell'intervallo di tempo selezionato e i relativi attributi, ad esempio i punti e la categoria risultanti. È possibile personalizzare un intervallo di date e filtrare in base alla categoria.

![Cronologia attività](../../media/secure-score/secure-score-history-activity.png)

Se si seleziona l'azione di miglioramento associata a un'attività, verrà visualizzato il riquadro a comparsa Azione miglioramento completo.

Per visualizzare tutta la cronologia per l'azione di miglioramento specifica, selezionare il collegamento cronologia nel riquadro a comparsa.

![Cronologia delle azioni di miglioramento](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Individuare le tendenze e impostare gli obiettivi

Nella scheda **tendenze & metriche** sono disponibili diversi grafici e grafici che consentono di ottenere maggiori visibilità nelle tendenze e impostare gli obiettivi. È possibile impostare l'intervallo di date per l'intera pagina di visualizzazioni. Le visualizzazioni includono:

* **Area di Punteggio sicuro** -personalizzata in base agli obiettivi dell'organizzazione e alle definizioni degli intervalli di buoni, OK e Bad score.
* **Tendenza di regressione** : una sequenza temporale di punti che sono stati regressi a causa di modifiche alla configurazione, all'utente o al dispositivo.  
* **Trend di confronto** : in che modo il Punteggio sicuro dell'organizzazione viene confrontato con gli altri nel corso del tempo. Questa visualizzazione può includere linee che rappresentano la media del Punteggio di organizzazioni con conteggio dei sedili analogo e una visualizzazione di confronto personalizzata che è possibile impostare.
* **Trend di accettazione dei rischi** -cronologia delle azioni di miglioramento contrassegnate come "rischio accettato".
* **Modifiche al Punteggio** : il numero di punti ottenuti, i punti di regressione e le modifiche apportate al punteggio nell'intervallo di date specificato.

### <a name="compare-your-score-to-organizations-like-yours"></a>Confronta il tuo punteggio con organizzazioni come le tue

Sono disponibili due posizioni per vedere come il punteggio viene confrontato con le organizzazioni che sono simili all'utente. In entrambi i grafici, è possibile selezionare **Gestisci confronti** per visualizzare e modificare le informazioni dell'organizzazione. È inoltre possibile creare un confronto personalizzato basato sull'industria, la dimensione dell'organizzazione, le licenze e le aree geografiche.

#### <a name="comparison-bar-chart"></a>Grafico a barre di confronto

Il grafico a barre di confronto è la scheda **Panoramica** . Posizionare il puntatore del mouse sul grafico per visualizzare la possibilità di punteggio e punteggio. I dati di confronto sono anonimi in modo che non si conoscano esattamente quali altri tenant sono presenti nella combinazione.

![Grafico a barre dei punteggi dell'organizzazione simili](../../media/secure-score/secure-score-comparison-bar.png)

- **Organizzazioni come la tua**: un punteggio medio di altri tenant (purché siano presenti almeno cinque o più tenant da confrontare) che si qualificano con i seguenti criteri:
    1. Stesso settore
    2. Stesse dimensioni dell'organizzazione
    3. Tutte le aree
    4. I prodotti Microsoft utilizzati sono 80% simili
    5. Opportunità (Punteggio massimo che può essere ottenuto dalla licenza corrente) all'interno di un intervallo del 20% dal tenant

- **Confronto personalizzato**: deve essere configurato selezionando **Gestisci confronto** in base ai criteri seguenti:
    1. Settore o settori selezionati
    2. Dimensioni dell'organizzazione selezionate
    3. Aree selezionate
    4. Licenze selezionate
    5. I prodotti Microsoft utilizzati sono 80% simili
    6. Opportunità (Punteggio massimo che può essere ottenuto dalla licenza corrente) all'interno di un intervallo del 20% dal tenant

Se è stata effettuata una selezione personalizzata, ma i risultati hanno meno di cinque altri tenant che è possibile confrontare, si vedrà "non disponibile a causa di dati limitati".

#### <a name="comparison-trend"></a>Trend di confronto

Nella scheda **tendenze & metriche** , visualizzare la modalità di confronto tra il Punteggio sicuro dell'organizzazione e gli altri nel corso del tempo.

![Grafico a linee dei punteggi dell'organizzazione simili nel corso del tempo](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, inviaci informazioni scrivendo nella community [sicurezza, Privacy & conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Si sta monitorando la community e viene fornita assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Panoramica del Punteggio Microsoft Secure](microsoft-secure-score.md)
- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)
