---
title: Microsoft Secure Score
description: Descrive Microsoft Secure Score nel Centro sicurezza Microsoft 365, come migliorare la sicurezza e cosa possono aspettarsi gli amministratori della sicurezza.
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
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930583"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score è una misura della posizione di sicurezza di un'organizzazione, con un numero maggiore che indica più azioni di miglioramento intraprese. È disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

Seguendo i consigli di Secure Score è possibile proteggere l'organizzazione dalle minacce. Da un dashboard centralizzato nel Centro sicurezza Microsoft 365, le organizzazioni possono monitorare e lavorare sulla sicurezza delle identità, delle app e dei dispositivi di Microsoft 365.

Secure Score consente alle organizzazioni di:  

* Report sullo stato corrente della sicurezza dell'organizzazione.
* Migliora la loro sicurezza fornendo individuabilità, visibilità, indicazioni e controllo.  
* Confrontare con i benchmark e stabilire indicatori di prestazioni chiave (KPI).

Le organizzazioni ottengono l'accesso a visualizzazioni affidabili di metriche e tendenze, integrazione con altri prodotti Microsoft, confronto dei punteggi con organizzazioni simili e molto altro ancora. Il punteggio può riflettere anche quando soluzioni di terze parti hanno indirizzato le azioni consigliate.

![Home page di Secure Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funzionamento

Sono stati dati punti per le azioni seguenti:

- Configurazione delle funzionalità di sicurezza consigliate
- Esecuzione di attività correlate alla sicurezza
- Gestione dell'azione di miglioramento con un'applicazione o un software di terze parti o una mitigazione alternativa

Alcune azioni di miglioramento forniscono punti solo quando sono completate. Alcuni forniscono punti parziali se vengono completati per alcuni dispositivi o utenti. Se non è possibile o non si desidera eseguire una delle azioni di miglioramento, è possibile scegliere di accettare il rischio o il rischio rimanente.

Se si dispone di una licenza per uno dei prodotti Microsoft supportati, verranno visualizzati suggerimenti per tali prodotti. Viene illustrato il set completo di possibili miglioramenti per un prodotto, indipendentemente dall'edizione della licenza, dall'abbonamento o dal piano. In questo modo, è possibile comprendere le procedure consigliate per la sicurezza e migliorare il punteggio. La tua posizione di sicurezza assoluta, rappresentata da Secure Score, rimane la stessa indipendentemente dalle licenze di cui l'organizzazione è proprietaria per un prodotto specifico. Tenere presente che la sicurezza deve essere bilanciata con l'usabilità e non tutte le raccomandazioni possono funzionare per il proprio ambiente.

Il punteggio viene aggiornato in tempo reale per riflettere le informazioni presentate nelle pagine delle azioni di miglioramento e visualizzazione. Secure Score si sincronizza anche ogni giorno per ricevere i dati di sistema sui punti raggiunti per ogni azione.

### <a name="key-scenarios"></a>Scenari chiave

- [Controllare il punteggio corrente](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Confrontare il punteggio con organizzazioni come la tua](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visualizzare le azioni di miglioramento e decidere un piano d'azione](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Avviare flussi di lavoro per analizzare o implementare](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Come vengono classificate le azioni di miglioramento

Ogni azione di miglioramento vale 10 punti o meno e la maggior parte viene classificata in modo binario. Se si implementa l'azione di miglioramento, ad esempio si crea un nuovo criterio o si attiva un'impostazione specifica, si ottiene il 100% dei punti. Per altre azioni di miglioramento, i punti vengono dati come percentuale della configurazione totale.

Ad esempio, un'azione di miglioramento indica di ottenere 10 punti proteggendo tutti gli utenti con l'autenticazione a più fattori. Hai solo 50 utenti su 100 in totale protetti, quindi ottieni un punteggio parziale di 5 punti (50 protetto / 100 totale * 10 max pts = 5 pts).

### <a name="products-included-in-secure-score"></a>Prodotti inclusi in Secure Score

Attualmente sono disponibili suggerimenti per i prodotti seguenti:

- Microsoft 365 (incluso Exchange Online)
- Azure Active Directory
- Microsoft Defender per endpoint
- Che cosa è Microsoft Defender per identità?
- Cloud App Security

Le raccomandazioni per altri prodotti per la sicurezza saranno presto disponibili. I consigli non coprono tutte le superfici di attacco associate a ogni prodotto, ma sono una buona linea di base. È inoltre possibile contrassegnare le azioni di miglioramento come coperte da una mitigazione alternativa o di terze parti.

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Microsoft Secure Score ha aggiornato le azioni di miglioramento per supportare le impostazioni predefinite di sicurezza [in Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)che facilitano la protezione dell'organizzazione con le impostazioni di sicurezza preconfigurato per gli attacchi comuni.

Se si attivano le impostazioni predefinite di sicurezza, verranno assegnati punti completi per le azioni di miglioramento seguenti:

- Assicurarsi che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso protetto (9 punti)
- Richiedere l'autenticazione a più fattori per i ruoli amministrativi (10 punti)
- Abilitare i criteri per bloccare l'autenticazione legacy (7 punti)

>[!IMPORTANT]
>Le impostazioni predefinite per la sicurezza includono funzionalità di sicurezza che forniscono una sicurezza simile alle azioni di miglioramento "criteri di rischio di accesso" e "criteri di rischio utente". Invece di configurare questi criteri sopra le impostazioni predefinite di sicurezza, ti consigliamo di aggiornarne lo stato in "Risolto tramite mitigazione alternativa".

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per disporre dell'autorizzazione per accedere a Microsoft Secure Score, è necessario disporre di uno dei ruoli seguenti in Azure Active Directory.

### <a name="read-and-write-roles"></a>Ruoli di lettura e scrittura

Con l'accesso in lettura e scrittura, è possibile apportare modifiche e interagire direttamente con Secure Score. È inoltre possibile assegnare l'accesso in sola lettura ad altri utenti.

* Amministratore globale
* Amministratore della sicurezza
* Amministratore di Exchange
* Amministratore di SharePoint
* Amministratore account

### <a name="read-only-roles"></a>Ruoli di sola lettura

Con l'accesso in sola lettura, non è possibile modificare lo stato o le note per un'azione di miglioramento, modificare le aree dei punteggi o modificare confronti personalizzati.

* Amministratore del supporto tecnico
* Amministratore utenti
* Amministratore del servizio
* Ruolo con autorizzazioni di lettura per la sicurezza
* Operatore della sicurezza
* Ruolo con autorizzazioni di lettura globali

## <a name="risk-awareness"></a>Consapevolezza dei rischi

Microsoft Secure Score è un riepilogo numerico dell'andamento della sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misurazioni correlate alla sicurezza. Non si tratta di una misura assoluta della probabilità che il sistema o i dati verranno violati. Rappresenta invece la misura in cui sono stati adottati i controlli di sicurezza nell'ambiente Microsoft che possono aiutare a compensare il rischio di violazione. Nessun servizio online è immune dalle violazioni della sicurezza e il punteggio sicuro non deve essere interpretato come una garanzia contro le violazioni della sicurezza in alcun modo.

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando il post nella community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Stiamo monitorando la community e forniremo assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
- [Novità](microsoft-secure-score-whats-new.md)
