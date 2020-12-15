---
title: Microsoft Secure Score
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, come migliorare la posizione di sicurezza e gli amministratori di sicurezza che possono aspettarsi.
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682572"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite. Può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).

Seguendo i suggerimenti per il Punteggio sicuro è possibile proteggere l'organizzazione dalle minacce. Da un Dashboard centralizzato nel centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, delle app e dei dispositivi di Microsoft 365.

Secure Score aiuta le organizzazioni:  

* Segnalare lo stato corrente della posizione di sicurezza dell'organizzazione.
* Migliorare la propria posizione di sicurezza fornendo individuabilità, visibilità, orientamento e controllo.  
* Confronta con benchmark e stabilisci indicatori di prestazioni chiave (KPI).

Le organizzazioni accedono alla visualizzazione robusta delle metriche e delle tendenze, all'integrazione con altri prodotti Microsoft, al confronto tra organizzazioni simili e molto altro ancora. Il Punteggio può anche riflettere quando le soluzioni di terze parti sono state indirizzate alle azioni consigliate.

![Homepage del Punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funzionamento

Sono stati assegnati punti per le azioni seguenti:

- Configurazione delle funzionalità di sicurezza consigliate
- Esecuzione di attività correlate alla sicurezza
- Risoluzione delle operazioni di miglioramento con un'applicazione o un software di terze parti o una attenuazione alternativa

Alcune azioni di miglioramento offrono solo punti quando sono state completate. Alcuni forniscono punti parziali se sono stati completati per alcuni dispositivi o utenti. Se non è possibile o non si desidera applicare una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.

Se si dispone di una licenza per uno dei prodotti Microsoft supportati, verranno visualizzati i suggerimenti per tali prodotti. Viene mostrato il set completo di possibili miglioramenti per un prodotto, indipendentemente dall'edizione della licenza, dall'abbonamento o dal piano. In questo modo, è possibile comprendere le procedure consigliate per la sicurezza e migliorare il punteggio. La posizione di sicurezza assoluta, rappresentata da un punteggio sicuro, rimane invariata indipendentemente dalle licenze possedute dall'organizzazione per un prodotto specifico. Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente in uso.

Il Punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine di azione per la visualizzazione e il miglioramento. Secure Score sincronizza anche tutti i giorni per ricevere i dati di sistema relativi ai punti ottenuti per ogni azione.

### <a name="key-scenarios"></a>Scenari principali

- [Controllare il punteggio corrente](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Confronta il tuo punteggio con organizzazioni come le tue](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visualizzare le azioni di miglioramento e decidere un piano d'azione](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Avviare i flussi di lavoro per l'analisi o l'implementazione](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Centro sicurezza e integrazione di Microsoft 365 ServiceNow](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Come vengono segnate le azioni di miglioramento

Ogni azione di miglioramento vale 10 punti o meno e la maggior parte è classificata in modo binario. Se si implementa l'azione di miglioramento, ad esempio crea un nuovo criterio o si attiva un'impostazione specifica, si ottiene il 100% dei punti. Per altre azioni di miglioramento, i punti vengono assegnati come percentuale della configurazione totale.

Ad esempio, un'azione di miglioramento dichiara di ottenere 10 punti proteggendo tutti gli utenti con l'autenticazione a più fattori. Si hanno solo 50 di 100 utenti totali protetti, quindi si otterrebbe un punteggio parziale di 5 punti (50 protected/100 Total * 10 Max PTS = 5 pts).

### <a name="products-included-in-secure-score"></a>Prodotti inclusi nel punteggio sicuro

Sono attualmente disponibili suggerimenti per Microsoft 365 (incluso Exchange Online), Azure Active Directory, Microsoft Defender per endpoint, Microsoft Defender per Identity e cloud app Security. Sono disponibili suggerimenti per gli altri prodotti di sicurezza. I suggerimenti non riguarderanno tutte le superfici di attacco associate a ciascun prodotto, ma sono una buona linea di base. È inoltre possibile contrassegnare le azioni di miglioramento riportate da terze parti o da una attenuazione alternativa.

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Microsoft Secure Score ha aggiornato le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.

Se si attivano le impostazioni predefinite per la sicurezza, verranno assegnati punti completi per le azioni di miglioramento seguenti:

- Verificare che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro (9 punti)
- Richiedere l'AMF per i ruoli amministrativi (10 punti)
- Abilitare il criterio per bloccare l'autenticazione legacy (7 punti)

>[!IMPORTANT]
>Le impostazioni predefinite per la sicurezza includono funzionalità di sicurezza che forniscono una sicurezza analoga alle azioni di miglioramento "criterio di accesso a rischio" e "criterio di rischio utente". Invece di impostare questi criteri in base alle impostazioni predefinite per la sicurezza, è consigliabile aggiornare i relativi stati in "risolti tramite attenuazione alternativa".

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per avere l'autorizzazione per accedere a Microsoft Secure score, è necessario essere assegnati a uno dei ruoli seguenti in Azure Active Directory.

### <a name="read-and-write-roles"></a>Ruoli di lettura e scrittura

Con l'accesso in lettura e in scrittura, è possibile apportare modifiche e interagire direttamente con il Punteggio sicuro. È inoltre possibile assegnare l'accesso in sola lettura ad altri utenti.

* Amministratore globale
* Amministratore della sicurezza
* Amministratore di Exchange
* Amministratore di SharePoint
* Amministratore account

### <a name="read-only-roles"></a>Ruoli di sola lettura

Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare le aree dei punteggi o modificare i confronti personalizzati.

* Amministratore del supporto tecnico
* Amministratore utenti
* Amministratore del servizio
* Ruolo con autorizzazioni di lettura per la sicurezza
* Operatore della sicurezza
* Ruolo con autorizzazioni di lettura globali

## <a name="risk-awareness"></a>Sensibilizzazione ai rischi

Microsoft Secure Score è un riepilogo numerico della postura di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misure relative alla sicurezza. Non si tratta di una misura assoluta del modo in cui il sistema o i dati verranno violati. Piuttosto, rappresenta la misura in cui sono stati adottati controlli di sicurezza nell'ambiente Microsoft che possono contribuire a compensare il rischio di essere violati. Nessun servizio online è completamente immune dalle violazioni della sicurezza e il Punteggio sicuro non deve essere interpretato come garanzia contro la violazione della sicurezza in alcun modo.

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, inviaci informazioni scrivendo nella community [sicurezza, Privacy & conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Si sta monitorando la community e viene fornita assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)
