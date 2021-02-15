---
title: Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi
description: Ottieni informazioni approfondite sulle attività che hanno interessato Microsoft Secure Score. Individuare le tendenze e impostare gli obiettivi.
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
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925673"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure Score è](microsoft-secure-score.md) una misura della posizione di sicurezza di un'organizzazione, con un numero maggiore che indica più azioni di miglioramento intraprese. È disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Ottenere informazioni approfondite sull'attività che ha influenzato il punteggio

Visualizzare un grafico del punteggio dell'organizzazione nel tempo nella **scheda** Cronologia.

Sotto il grafico è riportato un elenco di tutte le azioni eseguite nell'intervallo di tempo selezionato e dei relativi attributi, ad esempio i punti risultanti e la categoria. È possibile personalizzare un intervallo di date e filtrare in base alla categoria.

![Cronologia attività](../../media/secure-score/secure-score-history-activity.png)

Se si seleziona l'azione di miglioramento associata a un'attività, verrà visualizzato il riquadro a comparsa dell'azione di miglioramento completo.

Per visualizzare tutta la cronologia per quella specifica azione di miglioramento, selezionare il collegamento della cronologia nel riquadro a comparsa.

![Cronologia delle azioni di miglioramento](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Individuare le tendenze e impostare gli obiettivi

Nella scheda **Metriche & tendenze** sono disponibili diversi grafici e grafici per offrire maggiore visibilità sulle tendenze e impostare gli obiettivi. È possibile impostare l'intervallo di date per l'intera pagina di visualizzazioni. Le visualizzazioni includono:

* **Area secure score:** personalizzata in base a obiettivi dell'organizzazione e definizioni di intervalli di punteggi validi, validi e non validi.
* **Tendenza di regressione:** sequenza temporale dei punti che hanno regredito a causa delle modifiche apportate alla configurazione, all'utente o al dispositivo.  
* **Tendenza di confronto:** confronto tra Secure Score dell'organizzazione e altri utenti nel tempo. Questa visualizzazione può includere linee che rappresentano la media del punteggio delle organizzazioni con un numero di postazioni simile e una visualizzazione di confronto personalizzata che è possibile impostare.
* **Tendenza di accettazione dei rischi** - Sequenza temporale delle azioni di miglioramento contrassegnate come "rischio accettato".
* **Modifiche al** punteggio - Numero di punti ottenuti, punti regressi e modifiche al punteggio nell'intervallo di date specificato.

### <a name="compare-your-score-to-organizations-like-yours"></a>Confrontare il punteggio con organizzazioni come la tua

Esistono due posizioni in cui vedere il confronto tra il punteggio e le organizzazioni simili a te. In entrambi i grafici è possibile selezionare **Gestisci confronti per** visualizzare e modificare le informazioni dell'organizzazione. È inoltre possibile creare un confronto personalizzato in base al settore, alle dimensioni dell'organizzazione, alle licenze e alle aree geografiche.

#### <a name="comparison-bar-chart"></a>Grafico a barre di confronto

Il grafico a barre di confronto è la **scheda** Panoramica. Posizionare il puntatore del mouse sul grafico per visualizzare il punteggio e segnare le opportunità. I dati di confronto sono anonimi, quindi non sappiamo esattamente quali altri tenant sono in combinazione.

![Grafico a barre dei punteggi di un'organizzazione simile](../../media/secure-score/secure-score-comparison-bar.png)

- **Organizzazioni come la** tua : un punteggio medio di altri tenant (purché abbiamo almeno cinque o più tenant da confrontare) che si qualificano con i criteri seguenti:
    1. Stesso settore
    2. Stesse dimensioni dell'organizzazione
    3. Tutte le aree geografiche
    4. I prodotti Microsoft usati sono simili all'80%
    5. Opportunità (punteggio massimo che può essere ottenuto dalla licenza corrente) entro un intervallo del 20% dal tenant

- **Confronto personalizzato**: deve essere configurato selezionando **Gestisci** confronto in base ai criteri seguenti:
    1. Settori selezionati
    2. Dimensioni dell'organizzazione selezionate
    3. Aree selezionate
    4. Licenze selezionate
    5. I prodotti Microsoft usati sono simili all'80%
    6. Opportunità (punteggio massimo che può essere ottenuto dalla licenza corrente) entro un intervallo del 20% dal tenant

Se è stata effettuata una selezione personalizzata, ma i risultati hanno meno di cinque altri tenant che è possibile confrontare, verrà visualizzato "Non disponibile a causa di dati limitati".

#### <a name="comparison-trend"></a>Tendenza di confronto

Nella scheda **Metriche & tendenze,** visualizzare il confronto tra Secure Score dell'organizzazione e quello di altri utenti nel tempo.

![Grafico a linee dei punteggi di un'organizzazione simile nel tempo](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando il post nella community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We're monitoring the community and will provide help.

## <a name="related-resources"></a>Risorse correlate

- [Panoramica di Microsoft Secure Score](microsoft-secure-score.md)
- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)
