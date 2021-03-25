---
title: Microsoft Secure Score
description: Descrive Microsoft Secure Score nel Centro sicurezza Microsoft 365, come migliorare la sicurezza e cosa possono aspettarsi gli amministratori della sicurezza.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: 98f335a38b2e4f581d4b08def39353e53e1bafd4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064610"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score è una misurazione della postura di sicurezza di una organizzazione, in cui i numeri più alti indicano l'esecuzione di più azioni di miglioramento. È disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

Seguendo i consigli relativi al punteggio sicuro è possibile proteggere l'organizzazione dalle minacce. Da un dashboard centralizzato nel Centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, delle app e dei dispositivi di Microsoft 365.

Microsoft Secure Score aiuta le organizzazioni a:  

* Produrre report sullo stato corrente della postura di sicurezza dell’organizzazione.
* Migliorare la postura di sicurezza dell’organizzazione offrendo funzionalità di individuabilità, visibilità, linee guida e controllo.  
* Confrontarsi con i benchmark e definire gli indicatori di prestazioni chiave (KPI).

Le organizzazioni ottengono l'accesso a visualizzazioni affidabili di metriche e tendenze, integrazione con altri prodotti Microsoft, confronto dei punteggi con organizzazioni simili e molto altro ancora. Il punteggio può anche riflettere quando soluzioni di terze parti hanno indirizzato le azioni consigliate.

![Home page punteggio sicuro](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funzionamento

Ti vengono dati punti per le azioni seguenti:

- Configurazione delle funzionalità di sicurezza consigliate
- Esecuzione di attività correlate alla sicurezza
- Affrontare l'azione di miglioramento con un'applicazione o un software di terze parti o una mitigazione alternativa

Alcune azioni di miglioramento forniscono punti solo quando sono completate. Alcuni forniscono punti parziali se sono completati per alcuni dispositivi o utenti. Se non è possibile o non si desidera eseguire una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.

Se si dispone di una licenza per uno dei prodotti Microsoft supportati, verranno visualizzati suggerimenti per tali prodotti. Viene illustrato il set completo di possibili miglioramenti per un prodotto, indipendentemente dall'edizione, dall'abbonamento o dal piano di licenza. In questo modo, è possibile comprendere le procedure consigliate per la sicurezza e migliorare il punteggio. La posizione di sicurezza assoluta, rappresentata da Secure Score, rimane la stessa indipendentemente dalle licenze di proprietà dell'organizzazione per un prodotto specifico. Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per l'ambiente.

Il punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine delle visualizzazioni e delle azioni di miglioramento. Secure Score si sincronizza anche ogni giorno per ricevere i dati di sistema sui punti ottenuti per ogni azione.

### <a name="key-scenarios"></a>Scenari chiave

- [Controllare il punteggio corrente](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Confrontare il punteggio con organizzazioni come la tua](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visualizzare le azioni di miglioramento e decidere un piano d'azione](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Avviare flussi di lavoro per analizzare o implementare](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Come vengono segnate le azioni di miglioramento

Ogni azione di miglioramento vale 10 punti o meno e la maggior parte viene segnata in modo binario. Se implementi l'azione di miglioramento, ad esempio la creazione di un nuovo criterio o l'attivazione di un'impostazione specifica, ottieni il 100% dei punti. Per altre azioni di miglioramento, i punti vengono dati come percentuale della configurazione totale.

Ad esempio, un'azione di miglioramento indica di ottenere 10 punti proteggendo tutti gli utenti con l'autenticazione a più fattori. Hai solo 50 utenti su 100 protetti, quindi ottieni un punteggio parziale di 5 punti (50 protetti / 100 totali * 10 pts max = 5 pts).

### <a name="products-included-in-secure-score"></a>Prodotti inclusi in Secure Score

Attualmente sono disponibili suggerimenti per i prodotti seguenti:

- Microsoft 365 (incluso Exchange Online)
- Azure Active Directory
- Microsoft Defender ATP
- Microsoft Defender per identità
- Cloud App Security
- Microsoft Teams

Le raccomandazioni per altri prodotti di sicurezza saranno presto disponibili. I consigli non riguardano tutte le superfici di attacco associate a ogni prodotto, ma sono una buona linea di base. Puoi anche contrassegnare le azioni di miglioramento come coperte da una mitigazione alternativa o di terze parti.

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Microsoft Secure Score ha aggiornato le azioni di miglioramento per supportare le impostazioni predefinite di sicurezza [in Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)che semplificano la protezione dell'organizzazione con impostazioni di sicurezza preconfigurato per gli attacchi comuni.

Se si attivano le impostazioni predefinite di sicurezza, verranno assegnati punti completi per le azioni di miglioramento seguenti:

- Assicurarsi che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso protetto (9 punti)
- Richiedi MFA per i ruoli amministrativi (10 punti)
- Abilitare i criteri per bloccare l'autenticazione legacy (7 punti)

>[!IMPORTANT]
>Le impostazioni predefinite di sicurezza includono funzionalità di sicurezza che forniscono una sicurezza simile alle azioni di miglioramento "criteri di rischio di accesso" e "criteri di rischio utente". Invece di configurare questi criteri in base alle impostazioni predefinite di sicurezza, è consigliabile aggiornarne gli stati su "Risolto tramite mitigazione alternativa".

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per disporre dell'autorizzazione per accedere a Microsoft Secure Score, è necessario disporre di uno dei ruoli seguenti in Azure Active Directory.

### <a name="read-and-write-roles"></a>Ruoli di lettura e scrittura

Con l'accesso in lettura e scrittura, puoi apportare modifiche e interagire direttamente con Secure Score. È inoltre possibile assegnare l'accesso di sola lettura ad altri utenti.

* Amministratore globale
* Amministratore della sicurezza
* Amministratore di Exchange
* Amministratore di SharePoint
* Amministratore account

### <a name="read-only-roles"></a>Ruoli di sola lettura

Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare aree punteggio o modificare confronti personalizzati.

* Amministratore del supporto tecnico
* Amministratore utenti
* Amministratore del servizio
* Amministratore che legge i dati di sicurezza
* Operatore della sicurezza
* Ruolo con autorizzazioni di lettura globali

## <a name="risk-awareness"></a>Consapevolezza dei rischi

Microsoft Secure Score è un riepilogo numerico del comportamento di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misurazioni correlate alla sicurezza. Non è una misura assoluta della probabilità che il sistema o i dati siano violati. Rappresenta invece la misura in cui sono stati adottati i controlli di sicurezza nell'ambiente Microsoft che possono contribuire a compensare il rischio di violazione. Nessun servizio online è immune da violazioni della sicurezza e il punteggio sicuro non deve essere interpretato come una garanzia contro le violazioni della sicurezza in alcun modo.

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando la community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Stiamo monitorando la community e forniremo assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)